---
id: 339
title: Rsync examples
date: 2011-11-02T19:52:28+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=339
permalink: /2011/11/rsync-examples/
categories:
  - Computerz
---
Rsync is arguably one of the most powerful tools you can have in your arsenal as a systems administrator or user. It does not matter if you take care of one system or thousands, rsync can make your life easier. You can backup files, transfer data from one system to another or make sure the data in two locations are identical. Rsync can do this for you without you worrying about what data has changed; it will take care of the details.

BUT: I always forgot how it works, weird slashes in the commands, spaces in paths, have to read to the complete manpage, do some googling for rsync examples and rsync howto to get stuff working. Hence as a reminder my most used examples with some explanations.

### Using rsync to copy locally

The simplest use of rsync is to copy data from on place to another on the same machine. You can copy entire disks, directories or just files with rsync. Lets says we have a external usb disk mount at /usbdisk/ that we are going to copy data from. We want to make sure the copy can resume even if someone unplugs the usb disk or we loose power to the unit. The following command will copy the files on the usb disk from the directory /usbdisk/ to the local disk in /localdisk/.

<pre>rsync -av /usbdisk/ /localdisk/</pre>

Now, what if you lost connectivity to the usb device and the sync stopped for some reason? You would then run the same rsync command a second time. Rsync would look at the files in both locations and copy the difference. In effect it would continue the copy from the point the sync was interrupted.

### Doing remote rsync stuff

Lets say we wanted to copy all of the files under our local directory, &#8220;/usbdisk/&#8221; and place a copy on the machine &#8220;somemachine&#8221; under the remote directory &#8220;/backups/&#8221;. The name of the user on the remote machine is &#8220;foo&#8221;. Notice we added the &#8220;-z&#8221; argument so all data will be compressed over the network. We could use the following line:

<pre>rsync -avz /usbdisk/ foo@somemachine:/backups/</pre>

What if you wanted to delete any files on the \_remote\_ machine that are no longer on the source machine? We can use the same command above and simply add the &#8220;&#8211;del&#8221; argument. This will tell rsync to delete any files from &#8220;/backups/&#8221; that are no longer on the source directory, &#8220;/usbdisk/&#8221;.

<pre>rsync -avz --del /usbdisk/ foo@somemachine:/backups/</pre>

What if you wanted to not just copy all of the files under /usbdisk/, but also the /usbdisk/ directory name. Just leave off the last &#8220;/&#8221; after the &#8220;/usbdisk&#8221; directory name. This will tell rsync to copy the directory name and all files under that directory. On the remote server you will then see the directory structure /backups/usbdisk/.

<pre>rsync -avz /usbdisk foo@somemachine:/backups/</pre>

You can also rsync multiple files or directories using a single rsync line. This is useful when coping over the network as you only need to enter your ssh password once. Here we will copy the source directories /data1 and /data2 to the remote machine &#8220;somemachine&#8221; in the /backups/ directory.

<pre>rsync -avz /data1 /data2 foo@somemachine:/backups/</pre>

You can also pull the data from a remote machine to your local box. To rsync all of the files from the same &#8220;somemachine&#8221; to our local box just reverse the target and destination of the previous example:

<pre>rsync -avz foo@somemachine:/backups/ /usbdisk/</pre>

### Dealing with spaces in paths

Spaces cause all sorts of problems. To rsync when you have spaces in the files and/or directories you need to use a single tick to encompass the entire string and then escape the spaces. The following line shows the remote directory name &#8220;/I Hate Spaces&#8221; and the file name &#8220;some File.avi&#8221;, both contain spaces. We will be rsync&#8217;ing the file to our local directory &#8220;/current_dir/&#8221;.

<pre>rsync -av foo@somemachine:'/I\ Hate\ Spaces/some\ File.avi' /current_dir/</pre>

### Execute remote shell command to rsync files


  
It is important to note rsync can also execute commands on the remote machine to help you generate a list of files copy. The shell command is expanded by your remote shell before rsync is called.

The following line will run the find command on the remote machine in the video directory and rsync all &#8220;avi&#8221; files it finds to our machine in the /download directory.

<pre>rsync -avR foo@somemachine:'`find /data/video -name "*.[avi]"`' /download/</pre>

### Pull data from a remote machine to local server using ssh

The following command will pull the data from &#8220;remote\_machine&#8221; in /stuff/data/ and place it on the local system in /BACKUP/remote\_machine/. The arguments &#8220;-avx&#8221; will set archive mode (-a) equivalent to -rlptgoD, be verbose (-v) and will not cross file system boundaries (-x) like NFS or samba. The timeout command makes sure rsync will not hang if the remote system is unreachable after 30 seconds. We will be deleting any files on the target directory (/BACKUP/remote\_machine/) that are \_not_ found in the source directory (data/). If you do not want to allow rsync to delete any files then take out &#8220;&#8211;delete-excluded&#8221;.

The directory structure of the target machine will look like /BACKUP/remote_machine/data/ and this is considered a non-relative path option. Notice /stuff/ is not in the path.

<pre>rsync -avx --timeout=30 --delete-excluded backupuser@remote_machine:/stuff/data/ 
/BACKUP/remote_machine/</pre>

If you wanted the target directory structure to be relative you can add the argument &#8220;-R&#8221;. The directory structure would then look like /BACKUP/remote_machine/stuff/data/ as the sync path name starts / on the source machine. The command with &#8220;-R&#8221; added looks like:

<pre>rsync -Ravx --timeout=30 --delete-excluded backupuser@remote_machine:/stuff/data/ 
/BACKUP/remote_machine/</pre>

### Incremental backups using rsync

The following example will make an incremental backup of the directory /data/working/ and put a copy of any file that changes into a dated directory in /BACKUP/ . This can be used to keep a daily backup tree of any changed files and not have to overwrite the previous days files. Note that this method does need to copy the entire file if it changes as the new files are made in the directory named under current day.

<pre>rsync --backup --backup-dir=`date +%Y.%m.%d` -a /data/working/ /BACKUP/</pre>

If you have a file under /BACKUP/ called file1 and that file has changed on the source machine in /data/working/ then a new directory will be made. The incremental dir would be named \`date +%Y.%m.%d\` or the numerical values for YEAR.MONTH.DAY and put under /BACKUP/. The changed data &#8220;file1&#8221; would be put under that directory.

### What should I be careful with when using Rsync?

>   1. Be careful with the &#8211;delete command. If your using a source dir that is not mounted (nfs,cifs,etc) but the mount for the dir is still there then you will sync your blank dir. All remote files will be deleted.
>   2. Be careful with slashes after the dir names on the source. A slash after the dir name compared to no slash after the dir name will do 2 totally different things.
>   3. Running out of memory with the older version of Rsync when doing a huge amount of files. Use the newer version due to its ability to do incremental file lists.