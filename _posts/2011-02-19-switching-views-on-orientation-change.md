---
id: 100
title: Switching UIViews on Orientation change with an animation
date: 2011-02-19T17:48:20+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=100
permalink: /2011/02/switching-views-on-orientation-change/
categories:
  - Computerz
---
For our [Iscore Card App](http://itunes.apple.com/us/app/iscore-cards/id398621803?mt=8) we are working on an update which has card counting functionality for some complex card games including &#8220;Klaverjassen&#8221;.

We use the orientation in some UIViewControllers to show certain other features for a specific game. In Klaverjas mode landscape orientation will be used for totals after a couple of rounds. The nice thing is that you get fancy animation from iOS while doing the orientation change.

This is the code I came up with after googling the web. And combining some snippets I had elsewhere.

<!--more-->This what I did:

I originally had one viewController for the Klaverjas view, I added the other one in Xcode, with .h and .xib files. In both .h files I added the other viewController.h with an import.

One view is for portrait mode, the other for landscape; i created the design for both views with Interface Builder.

First add code to both UIViewControllers indicating which one is used for portrait and landscape orientation:

<pre>- (BOOL)shouldAutorotateToInterfaceOrientation:(UIInterfaceOrientation)interfaceOrientation {
    // Overriden to allow any orientation.
	//return YES;
	// portrait view controller
	return (interfaceOrientation == UIInterfaceOrientationPortrait);
}
- (BOOL)shouldAutorotateToInterfaceOrientation:(UIInterfaceOrientation)interfaceOrientation {
    // Overriden to allow any orientation.
    //return YES;
	return (interfaceOrientation == UIInterfaceOrientationLandscapeRight) || (interfaceOrientation == UIDeviceOrientationLandscapeLeft);
}</pre>

After that, make sure you get the rotation events, and attach a callback to it to do the view switching;
  
It does some animation morphing the 2 screens. If you enable the _animated:TRUE_ it will animate the change nicely <img src="http://www.renedohmen.nl/blog/wp-includes/images/smilies/simple-smile.png" alt=":-)" class="wp-smiley" style="height: 1em; max-height: 1em;" />

<pre>- (void)viewDidLoad {
    [super viewDidLoad];
	//get notification is orientation changes
	[[UIDevice currentDevice] beginGeneratingDeviceOrientationNotifications];
	NSNotificationCenter *notificationCenter = [NSNotificationCenter defaultCenter];
	[notificationCenter addObserver:self
				selector:@selector(didRotate:)
				name:UIDeviceOrientationDidChangeNotification
				object:nil];
	}
- (void)didRotate:(id)notification {
	NSLog(@"Switching to jassTotalsViewController");
	JassTotalsViewController *jassTotalsViewController = [[JassTotalsViewController alloc]init];
	jassTotalsViewController.modalTransitionStyle = UIModalTransitionStyleCrossDissolve;
	//[self dismissModalViewControllerAnimated:YES];
	[self presentModalViewController:jassTotalsViewController animated:TRUE];
	[jassTotalsViewController release];
}</pre>

Hier een screenshot van een early development versie:

[<img class="alignnone size-full wp-image-101" title="Screen shot 2011-02-19 at 18.29.33" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/02/Screen-shot-2011-02-19-at-18.29.33-e1298137658348.png" alt="" width="599" height="797" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/02/Screen-shot-2011-02-19-at-18.29.33.png)

[<img class="alignnone size-full wp-image-106" title="Screen shot 2011-02-19 at 18.47.17" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/02/Screen-shot-2011-02-19-at-18.47.17-e1298138525230.png" alt="" width="600" height="449" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/02/Screen-shot-2011-02-19-at-18.47.17.png)