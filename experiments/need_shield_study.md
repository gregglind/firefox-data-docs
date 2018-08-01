# I Need a Shield Study

"Shield Study" conflates two related, but distinct concepts:

- gathering evidence to make decisions
- off-train deployment.

Look through the scenarios below to see which fits what you are trying to do.

### I want to talk to someone.

### I need some evidence to make a decision.

Contact the S+I team, and let's talk about the decision, the method, and the mechanism.


### I want deploy **now** into Release (or other targeted popuation).

See [Delivery Console](./off_train_deployment.md).

Some things you can deploy off-trains.

- preference 
- hotfix addon
- survey or User Task


### I have a preference I want to slowly roll-out.

See [Delivery Console](./off_train_deployment.md).


### I have an instrumented user feature, with multiple variations, that I need to compare to a simulatenous control popululation.  This is the only way I can gather evidence to make my decision.

Condolences, you may actually need a Shield Study Addon.

Please contact us during the Hypothesis Design phase, before you start building, and *especially* before you start instrumenting.  

Contacting us early helps prevent known problems.

You are an expert on your feature.  We are experts on experiments coding.  

[Shield Study Engineering](./shield_study_engineering.md)







# Do you need a Shield Study?

Maybe.

Ask in #shield-support.  #experiments-support

(Long answer below)-->
# I need a shield study

## Quick View
<!-- toc -->









## Surveys are probably your answer.

If you can make decisions based on:
- competitive analysis
- a survey
- max-diff
- hallway test
- instrumented pseudo-experience
- messaging test

then do those instead.  

You can do 10 of them in the time it would take to deploy code.


## Shield Study Process Wizard:

Which is closest to your general goal? 

I need evidence to know the next stage for my idea:

1.  I have some ideas for features, or I have a list of aspects of a feature space.  I want to guage reactions to several messages.

    - Survey, Messaging Study, Max Diff

2.  Code / feature is finished, rode the train to release hidden behind a pref.  Can it go to 100%?  That's a **rollout**.

3.  Proposed new default value for a pref.  Can it go up to 100%. That's a **rollout**.

3.  Code lives in tree.  Not sure what the value for configuration should be.   That's a **pref experiment**

4. My feature needs some in-context UI with interaction.  It includes some surveys.  That's (sadly) a **Shield Study**.


## Shield Studies WebExtensionExperiments 

Shield Studies WebExtensionExperiments are the most expensive, high-touch path to gather data.

Still here?

That means, you have decided that you need to deploy
 
- a realistic feature 
- with complex interaction instrumentation
- with complex ending criteria
- to release users
- using an addon.

If not, consider another evidence gathering mechanism.


## So, you need a Shield Study

More questions:

- I can gather evidence to answer my question that is good enough without writing code.
    + Seriously, stop and do that.  Go back to Surveys.

- I have a 'finished' pref-hidden feature.  It rode the train to release or got uplifted. The pref has a known, proposed value.  I want slowly roll it out, up to 100%. I want to be able to 'rollback' if crash rates increase, we get back feedback.
    - This is called a 'rollout'.  New. The process for this is still TBD.  TODO.

- I have to deploy an instrumented addon.
    + Okay, this will be expensive, and risky.
- I have successfully launched a Shield Study Addon after January 2018.
    + Cool.  Carry on, then.
- I have never done this before.
    + Read on, so we can save you from wasted work.
- Are you engineering the instrumented feature?
    +  Please contact S+I to if all this is actually needful.
    +  Pause to develop your hypotehesis and instrumentation plan.
    +  Who is your Firefox Peer?  Your PM / Sponsor?
        *  If you don't know, find them.
    +  Stop and make a
        *  PHD
        *  QA / Engineering Accpetance Plan.  (TODO: write and link)
-  You are now building.  Your PHD should be approved. 
    +  Suggestion: [mozilla/shield-studies-addon-utils](https://github.com/mozilla/shield-studies-addon-utils) has specific engineering docs.
    


