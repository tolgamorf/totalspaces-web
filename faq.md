---
layout: ts-doc
title: TotalSpaces Questions
subtitle: Questions I think you might ask
---

## What systems will TotalSpaces run on?

TotalSpaces is tested on **OSX Lion 10.7.4+**, and **OSX Mountain Lion 10.8+**, and should work on any mac that can run these operating systems.

## Where is TotalSpaces?

TotalSpaces runs without an icon in the Dock, but instead an icon like this should appear in your menu bar.

<img src="/images/menubar-icon.png">

## Help, I can't see the menu bar icon!

There is an option to hide the menu bar icon, and perhaps this is turned on for some reason. In order to re-show the menu bar icon, double click on TotalSpaces in your Applications folder (as if to launch the app). This should tell the app to show the menu bar icon again.

## How can I make a particular app stay on a particular desktop in the grid?

You can now do this from the new [Apps preferences](/apps)

## How do I assign an app to all spaces?

This is possible using Apple's own app assignment menus. You access them by ctrl-clicking the icons in your Dock. Then choose Options to see the Assign to menu.

<img src="/images/assign-to-menu.png">

Assign to all spaces will be added to TotalSpaces preferences later.

## Why is there black blocking on the screen when you change desktop?

This is because OSX is not quick enough at redrawing the screen windows and desktop.

When you change space, in order to do the animation correctly, we freeze the screen, ask OSX to change space instantly, then proceed with our animation. If OSX is not done by the time we start the animation then black areas will appear briefly.

We can solve this by making the delay longer, but this will make changing the desktop slower You can also of course turn animations off altogether in the preferences.

Ultimately we hope to solve the problem by getting an internal notification from the system as to when the new desktop is ready so we can avoid black blocking altogether.

## How can I make a particular appear on all desktops in the grid?

Control-click on the app in the dock, then choose Options and Assign to All Desktops.

## How can I uninstall TotalSpaces?

Use [the uninstaller](http://downloads.binaryage.com/UninstallTotalSpaces.app.zip).

TotalSpaces is a normal app that can be dragged to the Trash, except for one additional file that must be removed from /Library/ScriptingAdditions.

The uninstaller will remove this file along with the app itself, as well as restarting Dock so that no trace of TotalSpaces remains in the system.

## Why are there no diagonal transitions?

In Lion, the core graphics routines we are using do not support diagonal transitions for both diagonal axes. However, we may experiment with making our own transitions in future.

## How can I completely turn off growl notifications?

Use this command at the command line:

defaults write com.binaryage.TotalSpaces sendGrowlNotifications NO

then restart TotalSpaces.

## How can I make the transitions even faster than the slider allows?

Use this command at the command line:

defaults write com.binaryage.TotalSpaces transitionSpeed 115

then restart TotalSpaces. 

The normal preferences slider goes to 110, but 130 is the hard limit; do not set it higher - anyway you won't even see the transitions at that speed. 

Note that there is a small built in delay after you press the hotkey that is unavoidable with transitions - they take a little time to set up.