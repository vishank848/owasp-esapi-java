## Step 5. Scramble on the rest ##

  1. Perform a code review
  1. Write documentation
  1. Investigate the infrastructure
  1. Start chasing after people for program-level items
  1. Check off AppSec STIG requirements
    * Delivery and operation
      * APP2040 Classification guide does not exist
      * APP2130 Maintenance does not exist or not sufficient
      * APP6010 Critical application hosted on a multi-use serve
      * APP6020 COTS products not configured to best practices
      * APP6030 Unnecessary services or software not removed
      * APP6040 Administrator has not registered to updates
      * APP6050 Current patches and configurations not installed
      * APP6060 App not decommissioned when maintenance is expired
      * APP6070 No procedures exist to decommission application
      * APP6160 Disaster recovery plan does not exist
      * APP6140 Log files are not retained for at least one year
      * APP6170 Application backups not in a fire rated container
      * APP6180 Backup and restoration device not protected
      * APP6190 Backups or backup procedures are incomplete
      * APP6200 Disaster plan does not exist or is incomplete
    * Development
      * APP2010 System Security Plan non existent or not adequate
      * APP2050 No MAC and CONF levels documented
      * APP2070 Products are not NIAP/Common Criteria approved
      * APP2080 Products with no or unsuitable robustness profiles
      * APP2090 Public domain software in use
      * APP3010 Design document is not complete or does not exist
      * APP3020 Threat model not established or updated
    * Tests
      * APP5050 Tests plans not executed prior to release or patch
      * APP5070 Application has no code coverage statistics
      * APP5080 Code reviews not performed prior to release
      * APP5100 Fuzz testing is not performed
    * Guidance documents
      * APP2020 Application Configuration Guide does not exist
      * APP2140 An incident response process is not established
      * APP2150 Inadequate Workplace Security Procedures
    * Verification
      * APP2100 Application violates Ports and Protocols Guidance
      * APP2110 Not registered with the DoD Ports and Protocols
      * APP2160 Approved Security Configuration Guidance not used
      * APP3050 Inactive code and libraries not removed
      * APP3060 Application code and data are co-located
      * APP3070 Application components not separated from data storage
      * APP3080 Invalid URL or path references found
      * APP3100 Temporary objects not removed from system
      * APP3190 Database connections use administrative accounts
      * APP3200 No support for roll-back and journaling
      * APP3230 Application does not clear all memory blocks
      * APP3270 Classification labels not appropriately displayed
      * APP3280 The application is not PK-enabled
      * APP3290 The application utilizes a PKI other than DOD PKI
      * APP3300 Server authentication is not PK-enabled
      * APP3305 Expired revoked untrusted certificates honored
      * APP3310 Clear text passwords displayed
      * APP3320 Userids have weak passwords
      * APP3350 Embedded authentication data stored in code
      * APP3370 Unneeded accounts active
      * APP3380 Application userids are not unique
      * APP3440 Logon warning not displayed
      * APP3630 Application vulnerable to race conditions
      * APP3650 No warning when logs are near full
      * APP3670 No notification of time of last change of data
      * APP3690 Application audit logs have incorrect permissions
      * APP3700 Unsigned Cat 1A or 2 mobile code in use
      * APP5030 Data files modified outside the application
      * APP5040 Changes to the application are not assessed for IA
      * APP6080 Protections against DoS attacks not implemented
      * APP6100 Sensitive data not purged from production export
      * APP6110 Audit trail not periodically reviewed
      * APP6120 IAO has no process to report IA violations
      * APP6130 No automated audit trail monitoring
      * APP6270 DMZ not present between DoD and public networks
    * Other
      * APP2030 No established IA budget
      * APP3710 Mobile code executed without verifying signature
      * APP3720 Unsigned unconstrained mobile code used
      * APP3730 Uncategorized mobile code used
      * APP3740 Code sent in email
      * APP3750 New mobile development not compliant DoDI 520040
      * APP5110 Security flaws not addressed in project plan