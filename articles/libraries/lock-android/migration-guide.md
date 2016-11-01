---
toc_title: Migration Notes v1 to v2
description: A reference for changed option names and behaviors in Lock for Android v2
---

# Lock for Android v1 to v2 Migration Guide

In v1 of Lock for Android, you were asked to create a custom `Application` class and initialize the `Lock.Context` there. **Now this is no longer needed**. In v2, to create a new `Lock` instance and configure it, you will just use the `Lock.Builder` class. The configurable options in v2 have been expanded, allowing more configuration while making the implementation and customization process easier than in v1.

## Changed Configuration Options

As in the previous version, Lock for Android v2 can be configured with extra options. Check below if the behavior for the option has changed, or if they only got renamed.



* `shouldUseWebView`: `DEPRECATED`. This option was renamed to `useBrowser`, but is now deprecated. Selects whether to use the WebView or the Browser to request calls to the `/authorize` endpoint. The default value is to use the Browser. Using the Browser has some restrictions.
* `shouldUseEmail`: Renamed to `withUsernameStyle`. Defines if it should ask for email only, username only, or both of them. By default it'll respect the Dashboard configuration of the parameter `requires_username`.
* `isClosable`: Renamed to `closable`. Defines if the `LockActivity` can be closed. By default it's not closable.
* `shouldLoginAfterSignUp`: Renamed to `loginAfterSignUp`. Determines whether after a signup the user should be logged in automatically. Defaults to `true`.
* `disableSignupAction`: Renamed to `allowSignUp`. Shows the Sign Up form if a Database connection is configured. Defaults to `true`.
* `disableResetAction`: Renamed to `allowForgotPassword`. Shows a link to the Forgot Password form if a Database connection is configured and it's allowed from the Dashboard. Defaults to `true`.
* `defaultUserPasswordConnection`: Renamed to `setDefaultDatabaseConnection`. Defines which will be the default Database connection. This is useful if your application has many Database connections configured.
* `setConnections`: Renamed to `allowedConnections`. Filters the allowed connections from the list configured in the Dashboard. If this value is empty, all the connections defined in the dashboard will be available. This is also the default behavior.
* `setAuthenticationParameters`: Renamed to `withAuthenticationParameters`. Defines extra authentication parameters to be sent on sign up and log in/sign in. The default `scope` used on authentication calls is `openid`. This is changed from v1, which also included the `offline_access` scope. 

Lock for Android v2 also features a bunch of new options. Check the [options documentation](/libraries/lock-android#lock-configuration-options) for a complete list of them.