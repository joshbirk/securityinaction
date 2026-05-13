---
title: Standard Baseline XML
layout: default
parent: Appendix
nav_order: 1
---

## **Appendix: Standard Baseline XML**

For Exercise 4

\<\!--    
     Please read Custom Baseline File Requirements for information about making changes in this file:  
     https://help.salesforce.com/articleView?id=security\_custom\_baseline\_file\_requirements.htm  
 \--\>  
\<baseline xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" name="SFDC recommended" developerName="SFDCRecommended" xsi:noNamespaceSchemaLocation="security-risk-baseline.xsd"\>  
\<highRiskSecuritySettings\>  
\<booleanSetting name="SessionSettings.lockSessionsToDomain" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.enableSmsIdentity" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.clickjackSetup" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.clickjackNonSetup" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.clickjackVisualForceHeaders" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.clickjackVisualForceNoHeaders" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.csrfGet" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.csrfPost" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.requireHttpOnly" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="Identity.mfaEnabled" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="ExternalClientApps.metadataApiAccess" compliant="false" nonCompliant="critical"/\>  
\<numericRangeSetting name="FileUploadAndDownloadSecurity.hybridSecurityRiskFileTypes" compliant="0.0" warning="0.5"/\>  
\<enumSetting name="PasswordPolicies.maxLoginAttempts" compliant="ThreeAttempts" warning="FiveAttempts,TenAttempts" critical="NoLimit"/\>  
\<numericRangeSetting name="CertificateAndKeyManagement.expiredCert" compliant="0.0" warning="1.0"/\>  
\<numericRangeSetting name="SharingSettings.orgWideDefaults" compliant="0.0" warning="1.0"/\>  
\<numericRangeSetting name="NetworkSecurity.trustedIpRangesConfigured" compliant="1.0" warning="0.5"/\>  
\</highRiskSecuritySettings\>  
\<mediumRiskSecuritySettings\>  
\<booleanSetting name="PasswordPolicies.minOneDayPasswordLifetime" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.forceRelogin" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.enforceLoginIp" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.terminateSessionsOnPasswordReset" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.cspOnEmail" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.contentSniffingProtection" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="LoginAccessPolicies.adminLoginAsAnyUser" compliant="false" nonCompliant="critical"/\>  
\<numericRangeSetting name="PasswordPolicies.history" compliant="3.0" warning="1.0"/\>  
\<numericRangeSetting name="PasswordPolicies.minPasswordLength" compliant="8.0" warning="6.0"/\>  
\<enumSetting name="PasswordPolicies.expiration" compliant="ThirtyDays,SixtyDays,NinetyDays" warning="SixMonths" critical="OneYear,Never"/\>  
\<enumSetting name="PasswordPolicies.complexity" compliant="SpecialCharacters,UpperLowerCaseNumeric,UpperLowerCaseNumericSpecialCharacters,Any3UpperLowerCaseNumericSpecialCharacters" warning="AlphaNumeric" critical="NoRestriction"/\>  
\</mediumRiskSecuritySettings\>  
\<lowRiskSecuritySettings\>  
\<booleanSetting name="PasswordPolicies.obscureSecretAnswer" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.forceLogoutOnTimeout" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.icOn2faRegistration" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.icOnEmailChange" compliant="true" nonCompliant="critical"/\>  
\<numericRangeSetting name="RemoteSiteSettings.remoteSiteSettings" compliant="0.0" warning="1.0"/\>  
\<enumSetting name="PasswordPolicies.questionRestriction" compliant="DoesNotContainPassword" warning="None"/\>  
\<enumSetting name="PasswordPolicies.lockoutInterval" compliant="ThirtyMinutes,SixtyMinutes,Forever" warning="FifteenMinutes"/\>  
\<enumSetting name="SessionSettings.timeout" compliant="FifteenMinutes,ThirtyMinutes,SixtyMinutes,NinetyMinutes,TwoHours" warning="FourHours,EightHours,TwelveHours" critical="TwentyFourHours"/\>  
\</lowRiskSecuritySettings\>  
\<informationalSecuritySettings\>  
\<numericRangeSetting name="CertificateAndKeyManagement.keySize" compliant="4096.0" warning="2048.0"/\>  
\<numericRangeSetting name="CertificateAndKeyManagement.certExpiration" compliant="180.0" warning="1.0"/\>  
\<booleanSetting name="UserPIISettings.enforceNameVisibility" compliant="true" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.redirectionAllowUntrusted" compliant="false" nonCompliant="critical"/\>  
\<booleanSetting name="SessionSettings.lockSessionsToIp" compliant="true" nonCompliant="warning"/\>  
\<booleanSetting name="Identity.samlEnabled" compliant="true" nonCompliant="critical"/\>  
\<numericRangeSetting name="GuestUserAccess.guestEditAccess" compliant="4.0" warning="9.0"/\>  
\<numericRangeSetting name="GuestUserAccess.guestReadAccess" compliant="4.0" warning="9.0"/\>  
\<numericRangeSetting name="GuestUserAccess.guestAccessSharingRules" compliant="0.0" warning="4.0"/\>  
\<numericRangeSetting name="AdminUsers.activeSystemAdministratorCount" compliant="5.0" warning="10.0"/\>  
\</informationalSecuritySettings\>  
\</baseline\>
