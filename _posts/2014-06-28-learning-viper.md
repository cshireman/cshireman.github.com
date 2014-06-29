---
layout: post
title: "Learning VIPER"
description: "Any problem with a nick-name is pretty bad.  This particular problem is one of the most common problems in iOS development is what is often termed 'MVC', or Massive-View-Controller.  This nick-name for the tried and true Model-View-Controller architecture for application development refers to the problem of where to put application logic.  The most convenient place is the view controllerclass for whatever you are working on at the moment.  The problem is that these files tend to become huge, and it is something that has become painfully obvious in my day-to-day development efforts lately.  When something isn't working the way I want it to, I need to fix it.  In this case, I need a new way of thinking about application architecture that doesn't result in 10,000 line view controller files. Enter VIPER."
category: iOS
tags: [iOS,architecture]
---
{% include JB/setup %}

# The Problem

Any problem with a nick-name is pretty bad.  This particular problem is one of the most common problems in iOS development is what is often termed 'MVC', or Massive-View-Controller.  This nick-name for the tried and true Model-View-Controller architecture for application development refers to the problem of where to put application logic.  The most convenient place is the view controllerclass for whatever you are working on at the moment.  The problem is that these files tend to become huge, and it is something that has become painfully obvious in my day-to-day development efforts lately.  When something isn't working the way I want it to, I need to fix it.  In this case, I need a new way of thinking about application architecture that doesn't result in 10,000 line view controller files. Enter VIPER

# What is VIPER

VIPER is a new way of thinking about iOS and Mac architecture.  It's an acronym that means View-Interactor-Presenter-Entity-Routing.  It's catchy, which means I had to take a look.  I'm still messing around with it, but the basic idea is to separate the different responsibities of the view controller into specific classes.  The Interactor handles the business logic, presenter formats content for the view, the view handles display, entities handle data, and routing handles navigation.

# What I Like

So far, it's a nice change from the standard MVC model of doing things.  Being able to build out my business logic in the interactor using TDD is very nice.  I'm about to start working with the presenter, which should be equally simple to use.  The view is a mostly passive structure, although I need to work with it some more.  My first test app is a temperature converter, so no real need for entities or routing at this point.  My next test app will need ot have multiple screens so I can try out the whole architecture.

# What I Dislike

I have written a lot of code so far and I still don't have anything on the screen.  I know it works because the tests pass, but it is taking longer to implement that just placing everything in the view controller.  This is not unexpected since the whole point is to circumvent the laziness that leads to MVC.  Segues are fairly off limits too, so the story boards are turning into a multi-view XIB container.  

# Conclusions

I have not been able to reach any conclusions yet, I'll post again when I have made up my mind about this architecture, but so far it seems like a better way to do thing.

