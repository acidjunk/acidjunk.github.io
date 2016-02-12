---
id: 261
title: Create a new remote GIT branch
date: 2011-07-27T16:19:39+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=261
permalink: /2011/07/create-a-new-remote-git-branch/
categories:
  - Computerz
---
My workflow is generally something like this:

  1. Create a remote branch
  2. Create a local branch that tracks it
  3. Work, Test, Commit (repeat) – this is all local
  4. Push (pushes commits to the remote repository)

<div>
  Because I always forget howto make a new remote branch I wrote this small article about it:
</div>

<div>
  <p>
    1. Create the remote branch
  </p>
  
  <div>
    <div>
      <pre>git push origin origin:refs/heads/new_feature_name</pre>
    </div>
  </div>
  
  <p>
    2. Make sure everything is up-to-date
  </p>
  
  <div>
    <div>
      <pre>git fetch origin</pre>
    </div>
  </div>
  
  <p>
    3. Then you can see that the branch is created.
  </p>
  
  <div>
    <div>
      <pre>git branch -r</pre>
    </div>
  </div>
  
  <p>
    This should show ‘origin/new_feature_name’
  </p>
  
  <p>
    4. Start tracking the new branch
  </p>
  
  <div>
    <pre>
git checkout  new_feature_name
</pre>
  </div>
</div>