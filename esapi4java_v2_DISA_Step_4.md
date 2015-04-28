## Step 4. Extend your common security control library each development cycle ##

  1. Add new baseline requirements for authentication
  1. Extend your common security control library with **authentication** functions
  1. Use your common security control library wrapper to make fixes to existing code
  1. Use your common security control library wrapper for new development going forward
  1. Check off AppSec STIG requirements
    * APP6210 No account management process in place
    * APP3390 User accounts not locked after invalid logons
    * APP3400 User accounts unlocked by person other than admin
    * APP3430 Authentication credentials not removed
    * APP3660 Last Login information not displayed
    * APP6220 Generated passwords do not comply with policy
    * APP6240 Inactive userids are not disabled
    * APP6250 Unnecessary built-in userids are not disabled
    * APP6260 Userids have default passwords
  1. Add new baseline requirements for session management
  1. Extend your common security control library with **session management** functions
  1. Use your common security control library wrapper to make fixes to existing code
  1. Use your common security control library wrapper for new development going forward
  1. Check off AppSec STIG requirements
    * APP3090 Session hijacking prevention not supported
    * APP3410 Session limits do not exist for the application
    * APP3415 Sessions do not automatically terminate
    * APP3420 Explicit logout not available
  1. Add new baseline requirements for access control
  1. Extend your common security control library with **access control** functions
  1. Use your common security control library wrapper to make fixes to existing code
  1. Use your common security control library wrapper for new development going forward
  1. Check off AppSec STIG requirements
    * APP3110 Unneeded functionality enabled
    * APP3240 Actions not authorized before execution
    * APP3360 Authentication data permissions not adequate
    * APP3450 Application resources has inappropriate permission
    * APP3460 Resource name used to control access
    * APP3480 Access control mechanism not in place
    * APP3500 Application runs with excessive privileges
    * APP3610 Hidden fields used to control access privileges
    * APP3470 Application functionality not role based
    * APP6230 Access granted by group authenticator
  1. Add new baseline requirements for cryptography
  1. Extend your common security control library with **cryptography** functions
  1. Use your common security control library wrapper to make fixes to existing code
  1. Use your common security control library wrapper for new development going forward
  1. Check off AppSec STIG requirements
    * APP3150 Application uses unapproved cryptographic modules
    * APP3170 Encryption for Key Exchange not used
    * APP3180 Encryption key permissions are not adequate
  1. Add new baseline requirements for error handling and logging
  1. Extend your common security control library with **error handling and logging** functions
  1. Use your common security control library wrapper to make fixes to existing code
  1. Use your common security control library wrapper for new development going forward
  1. Check off AppSec STIG requirements
    * APP3140 Application failure results in an insecure state
    * APP3120 Application has error handling vulnerabilities
    * APP3640 No logs for data access and changes
    * APP5060 System in insecure state during startup & shutdown
    * APP3620 Application discloses unnecessary information
    * APP3680 The application does not adequately log events
    * APP6090 No system alerts in a low resource condition
  1. Add new baseline requirements for data protection
  1. Extend your common security control library with **data protection** functions
  1. Use your common security control library wrapper to make fixes to existing code
  1. Use your common security control library wrapper for new development going forward
  1. Check off AppSec STIG requirements
    * APP3210 Sensitive data not protected at rest
    * APP3220 Sensitive data is not encrypted in memory
  1. Add new baseline requirements for **HTTP security**
  1. Start grepping through code, this is not something you'd use your library for
  1. Use your common security control library wrapper for new development going forward
  1. Check off AppSec STIG requirements
    * APP3530 Application does not set character set
  1. Add new baseline requirements for **communication security**
  1. Turn HTTPS and TLS on, this is not something you'd use your library for
  1. Use your common security control library wrapper for new development going forward
  1. Check off AppSec STIG requirements
    * APP3250 Sensitive data not protected in transit
    * APP3330 Passwords not transmitted encrypted
  1. Add new baseline requirements for **security configuration**
  1. Extend your common security control library with security configuration functions
  1. Use your common security control library wrapper to make fixes to existing code
  1. Use your common security control library wrapper for new development going forward
  1. Check off AppSec STIG requirements
    * APP3340 Passwords stored in an unapproved encrypted format
  1. Add new baseline requirements for **internal security**
  1. Extend your common security control library with internal security functions
  1. Use your common security control library wrapper to make fixes to existing code
  1. Use your common security control library wrapper for new development going forward
  1. Check off AppSec STIG requirements
    * APP3260 Integrity mechanisms on data files not supported