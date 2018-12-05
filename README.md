# Wrapper example cookbook for testing

This is to test an issue being seen with Automate, it appears that in some cases when the profile gets uploaded to Automate it's replacing another profile that already exists on the system.  If it happens to be one of the ones this wrapper depends on then it causes it to have a circular dependency error when trying to vendor.

```
inspec vendor wrapper-example
inspec compliance upload wrapper-example
inspec vendor wrapper-example --overwrite # BOOM blows up because of circular dependency
```
