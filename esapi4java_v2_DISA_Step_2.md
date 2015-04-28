## Step 2. Build a common security control library using ESAPI ##

  1. Build a common security control library wrapper tailored for your application (such as adding an Adapter control that calls the other existing controls according to the [Extended factory pattern](http://code.google.com/p/owasp-esapi-java/wiki/esapi4java_v2_Extended_factory_pattern))
  1. Extend your common security control library with input validation functions for all inputs
  1. Extend your common security control library with output encoding functions for all output contexts
  1. Test your common security control library input validation function from your framework
  1. Test your common security control library output encoding function from your framework
  1. Check off AppSec STIG requirements
    * APP2060 No coding standards exist
    * APP2120 Security training not provided
    * APP3130 Secure design principle not followed