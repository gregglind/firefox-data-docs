# I want to deploy yesterday.

Also known as:  "Deploy using Shield"

- [Delivery Console](https://delivery-console.readthedocs.io/en/latest/) powers all the magic for off-train deployment.


## When to deploy ON the train (which is most of the time)

- The idea is obviously correct.
  - true bug fixes
  - new css selectors

- Primary iteration risk is **technical risk**.
- Going through the trains will catch crashes, bugs, etc.

## Why Deploy Off-Train

- **Control Opportunity Risk**

  + A business need to 'go now', for something that doesn't require a full point release or version.
  + The Feature can be packaged in a way that allows off-train deployment. (Addon, preference, message with link).

- **Control User Acceptance Risk** You need evidence from actual Release users to make a product /feature decision
  
  Examples:

  + Attitudinal Data, User impressions. 
    + Launch idea as part of a Max-Diff 
    + Idea-specific messaging Study or Survey (So, so cheap!)
  
  + Optimize a preference value or configuration
    +  Multi-arm preference experiment.
    +  Choose the winning value and move to **rollout**.
  
  + Complex probes, endings, surveys. Instrumented Shield Study Addon (Super expensive, boutique, high-touch)

- **Control Rollout Risk** The feature is complete / ready, AND you have fears that release will be "weird in unpredictable ways".  You want to be able to 'turn it off'.
  - Do a "Feature Gate". targeting release in a version.  

- **Targeting**. You want complex targeting.

  - Hotfix addons 
    + Example: target certain locale / geo combinations
  - Pref changes under complex conditions, away from 'general default'
    + Example: Users with some addon need a pref set a certain way.

## The Off-Train Deployment wizard

_Is Delivery Console right for you?_

You have "a thing".

- is the thing a Survey or other "message with link" task. => Off-train.

- is 'the thing' code?
  - does code target Nightly? 
    - use usual Peer / RelMan process.
  - does the code target beta / release?
  
    Choose one or more:
    - make an addon, release the addon with Delivery Console
    - Hide the feature behind a pref
      - ride the trains, or uplift to Beta
      - control the "rollout" using Delivery Console to change the pref

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


### What I can deploy Off-Train

Partial list of "things" you can rdeploy this way.

- "message and a link"
  + Surveys, max-diff
  + tasks like "look at this prototype", user testing
  + invision prototypes
  + Trail Balloons:  "click here to help Firefox / try a new feature"

- webExtensions 
  + Targeted HotFixes 
  + A/B Multivariation Studies

- Preference changes
  + Multivariation with 'revert'
  + Rollouts from small samples create the new normal
  + Turn on preference-controlled features existing in the tree

