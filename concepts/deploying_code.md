# How You Get Code To 100% Of Release


_Warning: this is written by NOT a Release Manager, and has not (yet) been vetted.  Reflects state of the world on 2018/07/19._

You have code.  You (eventually) want it to get to 100% of release, if it is good.

There are two paths.

1. Trains (Current Release Process):

  Manages risk by

    - allowing time for problems to emerge
    - small populuations at first (nightly => beta => release)
    - code linting
    - qa
    - evidence to 'go forward' is no bugs, crashes
    - developing in tree
    - module ownership system
    - policy: preventing 'uplift' beyond Beta

  Allows risk
    - pre-release populations might not yield evidence
    - hard to rollback
    - typically "all or nothing" in a release

2. Delivery Console (preffed off features and/or WebExtensionsExperiments)

  Manages risk

  - qa plans.
  - start small (0.1%) or in an early channel
  - allows reversion

  Allows Risk

  - development (sometimes) out of tree
  - (currently) hard to test

3. Hybrid Explorations

  - Path: Modules / code lives in tree (Pref))
  - The rollout is controlled by rolling out the Pref


All methods have
- QA plans
- RelMan oversight
- Peer review
