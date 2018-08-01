# Shield Study Engineering

**NOTE**:  this is a work in progress.  Feedback and questions welcome.

## Code is Expensive.

You want to write code.   Fight that urge.

**Shield Study Addons are very expensive, in both time and engineering cost**.  

Are you sure you [need a Shield Study](./need_shield_study.md)?  

If not, [What Design Do I Need?](experiments/shield_design_process.md)

You are an expert on coding.  We are experts on experiment design.
In particular, can you get your answers with a Survey?  If so, do that.  Have you gone through the design wizard?

**Important**

0. Are you coding first, before you have a decision to make / evidence collection plan?  If so, please stop and [contact us](./shield_help.md).

1. If we don't know about your project, [contact us](./shield_help.md). We cannot launch or offer engineering support to projects we don't know about.  

2. If your project doesn't have prior research from Surveys or other methods, we will not ship it.  [contact us](./shield_help.md).  


## What Is A Shield Study?

A Shield Study is an instrumented addon.  

A Shield Study is built and designed to expose users to probes to answer questions.  

All engineering and process decisions in the Shield Program serve this goal:  **get correct probes to users**.    


## Differences from General Feature Coding

You are used to making robust, high-quality Features. 

If you attempt to build a production level feature **and instrument it**, it will be more expensive than landing.

1.  In Study Engineering, the main goal is code to make probes survive the wild.  The Feature is secondary.  
2. QA and Engineering acceptance needs to check that probability.
3. Make the feature as thing as you can.  Some techniques:


## Topics of Shield Engineering


### Do I need the Study Utils?

[shield-studies-addon-utils](https://github.com/mozilla/shield-study-addon-utils)

Study Utils makes these things easier.

- persistent variation selection
- 'setActiveExperiment' in telemetry (which powers dashboards)
- some handling install, expiration
- formatting survey urls.
- sending properly formatted Telemetry to the `shield-study-addon` bucket.

You probably do NOT need the Study Utils, **if**

- you have exactly one branch
- you do not need Addon lifecycle telemetry
- no Surveys.


### General Tips

+ land more in the tree.  does this need to be an addon?
+ use the logging pref: 

  >  web-ext run --verbose --pref shieldStudy.logLevel=all
     
+ make a debugging pane that is pref controlled

### General Shield Study Issues

- Code requires Firefox Peer review.

- beginings
    + **First Install** is the first install different?
        * introduction screen
        * opt-in screen
    + **Eligilibity criteria** for entering the study? 
        * is it in the targeting at Delivery Console?
        * is it only calculated at run time, using `allowEnroll`

- every run

    + Choosing a variation.  Shield-utils chooses based on a hash of the study name and the activeExperimentName
    + What does the feature actually *do* in all off its variations.

- **interruptions**
    + what if they turn telemetry off.
    + what if they turn off shield
    + what if they uninstall the study

- **endings**
    + list all endings
    + User disable 
    + Addon uninstall

- surveys
    + urls gets special query args to make all the reporting work

- probes
    + must be analyzable
    + must reflect the question we are asking
    + event telemetry land in tree

- qa
    + Turns out that QA cares about this stuff


## Special Topics

### Understanding WebExtension Shutdown

- in your webExtensionExperiment code, handle things with an `onShutdown` method.


If uninstall is initiated (eg from `about:addons`) 
- we first disable the extension if it is active
- after that, we remove it from disk, from our records of what is installed.

https://firefox-source-docs.mozilla.org/toolkit/modules/toolkit_modules/AsyncShutdown.html

https://firefox-source-docs.mozilla.org/toolkit/components/extensions/webextensions/reference.html#Extension.callOnClose




