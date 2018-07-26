# Shield Engineering

Topics of Shield Engineering

Note:  this is the same as the qa spec, engineering acceptance plan

- general tips
    + land more in the tree.  does this need to be an addon?
    + use the logger
    + make a debugging pane that is pref controlled

- beginings
    + is the first install different?
        * introduction screen
        * opt-in screen
    + is there eligilibity criteria for entering the study? 
        * is it in the targeting at Delivery Console? )
        * is it only calculated at run time?
- running
    + Choosing a variation.  Shield-utils chooses based on a hash of the study name and 

- interruptions
    + what if they turn telemetry off.
    + what if they turn off shield
    + what if they uninstall the study

- endings
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
- Code review by Firefox Peers









if uninstall is initiated (eg from about:addons) we first disable the extension if it is active
after that, we remove it from disk, from our records of what is installed, etc


Shield-linter


Are you working out of tree?
- you need linting

  https://firefox-source-docs.mozilla.org/tools/lint/linters/eslint.html

- please us CI



# Understanding WebExtension Shutdown

https://firefox-source-docs.mozilla.org/toolkit/modules/toolkit_modules/AsyncShutdown.html

https://firefox-source-docs.mozilla.org/toolkit/components/extensions/webextensions/reference.html#Extension.callOnClose




