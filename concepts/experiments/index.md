# Collecting Evidence to Make Decisions:  The Mozilla Shield Program

The Mozilla Shield Program exists to help make decisions using Evidence.

All engineering and process decisions in the Shield Program serve that goal.  

Shield exists to:

- Define The Decision
- Target Appropriate Users
- Deploy Directive Probes
- In a 'good enough' context
- So that Mozilla can make evidence-based decisions about existing and potential product features.

## 1. Defining  Decision

**The Decision to be made determines the evidence to collect, the deployment mechanism, and all engineering decisions.**

Decisions fall into two main classes:

1. **Okay to launch in Firefox?**  

    Implies this flow:
    
    -   lauch
    -   watch for problems 
    -   measure / ensure expected success
    -   rollback if not there.

    Examples:
    
    - make a pref into default
    - turn on a feature
    - change a security setting

    Methods:
    
    - on-train deployment: all or nothing.  Advance by channels
    - off-train deployment: targeting, preference rollout

2. **Choose a "best option"**.

    - Create Variations
    - Instrument
    - Launch and record
    - Recall / tear down
    - Make decision

    Examples:
    
    - which icon to use for thing
    - which langauge (messaging) to use

    Methods:
    
    - market research
    - hallway testing
    - surveys
    - prototypes
    - study extensions
    - pref-controlled features




## 2. Targeting Appropriate Users

Correct probes from innappropriate users leads to incorrect decisions.

Be as cheap as possible.

- Market Research
- User Testing
- Survey Panels
- Firefox Users

Related:

- Delivery Console
- On-train / Off Train / AMO / Panel deployment


## 3. Instrument with Directive Probes

Good probes yield directive evidence.

- directive: different data implies different decisions
- efficient: doesn't require many events
- engineerable:  relates directly to user action and attitudes 
- analyzable:  transmitted in a form such that simple counts, means, maxes and other 'stats 101' techniques will give a useful answer.  Plays well with existing tooling and automation.
    * Heuristic:  can I make decisions with the result of `count`, `group by` in a SQL query on the table?


## 4.  The "Good Enough" Context

To minimize engineering time and risk, use the lowest fidelity context you can to deploy the probes.

Be cheap:

- text 
- drawings 
- designs 
- engineering in js 
- engineering in C++ / Rust

Deployment is expensive.

QA is expensive.

Analysis is expensive.

Release is expensive.


### How to do 'just enough' to support the probes

- If showing people a screenshot is enough, do that.
- If a survey is enough, do that.
- If making 'just a button' in the ui is enough, do that.
- If a 'feature flag' that is pref-controlled is enough, do that
- If landing in nightly is enough, do that.
- If the 'real' system would have a server, bundle data instead.
- Don't translate
- Consider 'windows-only' or 'osx-only'
- Ignore edge cases
- Do 'just enough' to support the probes.


## 5. Make the Decision

You have data from your deployment.

It will not be perfect.

Make decision, and move to the next iteraction.

If you are not happy:
- generate new choices
- collect more (expensive, or better targeted) evidence
- return to step 1:  Define the Decision.


## Giant topic map:



"Shield" conflates several overlapping concepts.

  * [Off-Train Deployment Using **Delivery Console**](concepts/experiments/off_train_deployment.md)
  * [Feature Experimentation using Shield](concepts/experiments/experimentation_using_shield.md)
  * Preference Rollout
  * Targeting users
  * [Shield Study Addons (`webExtensionExperiments`)](concepts/experiments/shield-engineering.md)
  * [`shield-studies` and `shield-studies-addons` Telemetry Pings / Data Set](datasets/shield.md)

  New Telemetry (other)

  * [Creating and Deploying New Telemetry Probes](concepts/experiments/new_telemetry.md)




1. Making decisions using evidence

    - Minimalism:  Collect the cheapest, dirtiest evidence possible that will answer the question.
    - You probably don't need a Shield Study.  (How to know)

1. Four paths to Deployment, and how to choose which is right. 

1. Shield Study (Addon, webExtensionExperiment) Engineering Concerns

    - Do you need Shield Study Addon Utils (`browser.study`)
    Core concept: Engineering supports data collection
    
        A study:
        - the probes work correctly
        - get to the right people
        - with close enough fidelity







