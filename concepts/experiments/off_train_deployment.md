# I want to deploy yesterday

_A Primer on Off-Train Deployment using Delivery Console_

Also known as:  "Deploy using Shield"

**Deployment Console** powers all the magic for off-train deployment.

## When to deploy ON the train (which is most of the time)

- The idea is obviously correct 
  - true bug fixes
  - new css selectors
- Going through the trains will catch crashes, bugs, etc.

## Why Deploy Off-Train

- You need evidence from actual Release users to make a product /feature decision
  
  Examples:

  + Attitudinal Data, User impressions. 
    + Launch idea as part of a Max-Diff 
    + Idea-specific messaging Study or Survey (So, so cheap!)
  
  + Optimize a preference value or configuration
    +  Multi-arm preference experiment.  (**Expensive**)
    +  Choose the winning value and move to **Rollout**.
  
  + Complex probes, endings, surveys => Instrumented Shield Study Addon (Super expensive, boutique, high-touch)

- The feature is complete / ready, AND you have fears that release will be "weird in unpredictable ways".  You want to be able to 'turn it off'.
  - Do a pref-rollout, targeting release in a version.  

- You want complex targeting.

  - Hotfix addons 
    + Example: target certain locale / geo combinations
  - Pref changes under complex conditions, away from 'general default'
    + Example: Users with some addon need a pref set a certain way.

## The Off-Train Deployment wizard

_Is Delivery Console right for you?_

You have "a thing".

- is the thing a Survey or other "message with link" task.
  
  + Yes.

- is 'the thing' code?
  - the code targets nightly? 
    - probably, land, Ride Trains, usual Peer / RelMan process.
  - if beta / release?
  
    Choose one or more:
    - make an addon, release the addon with Deployment Console
    - Hide the feature behind a pref
      - ride the trains, or uplift to beta
      - control the "rollout" using Deployment Console to change the pref

## What Actually Happens

When you say "deploy this USING Shield", you are actually saying:

- in the Delivery Console, create a new **recipe** with **target** and **action**

- (for code and prefs) Notify Release Management it is coming for approval / approval.  
- **target** (user match criteria)
  - channels
  - locales (langages)
  - countries (*geos*)
  - versions
  - [many other things from prefs, telemetry, addons](http://normandy.readthedocs.io/en/stable/user/filters.html)
  - limit to sample percentage

- **action** Choose the thing to release
  - signed addon
  - preference(s) and values
  - choose semantics (experiment vs. rollout)

Partial list of "things" you can deploy this way.

- "message and a link"
  + Surveys, max-diff
  + tasks like "look at this prototype", user testing
  + invision prototypes
  + Trail Balloons:  "click here to help Firefox / try a new feature"
- webExtensions 
  - Targeted HotFixes 
  - A/B Multivariation Studies
- Preference changes
  + Multivariation with 'revert'
  + Rollouts from small samples create the new normal
  + Turn on preference-controlled features existing in the tree

