# Expo Android Build Failure: AndroidManifest.xml Activity Name Conflict

This repository demonstrates a common yet subtle bug encountered when building Android apps with Expo CLI. The problem stems from conflicts within the `AndroidManifest.xml` file, specifically concerning the `android:name` attribute in `<activity>` tags. The error messages provided by Expo during the build process are often unhelpful.

**The Bug:**

The primary cause is an inconsistency or duplicate definition of the `android:name` for Activities, often stemming from integrating libraries or navigation solutions like React Navigation. This leads to build failures without clear indication of the problematic activity.

**Solution:**

Carefully examine your `AndroidManifest.xml` file (located within the `android` directory of your Expo project). Verify that all `android:name` values for the `<activity>` tags are unique and correctly defined.

**Steps to Reproduce (Simplified):**

1. Create a new Expo project.
2. Implement a navigation structure that might generate multiple activities.
3. Try to build an Android release (eas build --platform android).
4. Observe the vague error message.

**Recommended Practice:**

Use a consistent naming convention for your activities. Avoid manually editing `AndroidManifest.xml` unless absolutely necessary.  Let Expo handle the manifest generation whenever possible.