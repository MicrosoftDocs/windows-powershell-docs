---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 0F0075C0-2945-448A-84E3-F0475A91AF25
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Set-ADDefaultDomainPasswordPolicy

## SYNOPSIS
Modifies the default password policy for an Active Directory domain.

## SYNTAX

```
Set-ADDefaultDomainPasswordPolicy [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-ComplexityEnabled <Boolean>]
 [-Credential <PSCredential>] [-Identity] <ADDefaultDomainPasswordPolicy> [-LockoutDuration <TimeSpan>]
 [-LockoutObservationWindow <TimeSpan>] [-LockoutThreshold <Int32>] [-MaxPasswordAge <TimeSpan>]
 [-MinPasswordAge <TimeSpan>] [-MinPasswordLength <Int32>] [-PassThru] [-PasswordHistoryCount <Int32>]
 [-ReversibleEncryptionEnabled <Boolean>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADDefaultDomainPasswordPolicy cmdlet modifies the properties of the default password policy for a domain.
You can modify property values by using the cmdlet parameters.

The Identity parameter specifies the domain whose default password policy you want modify.
You can identify a domain by its Distinguished Name (DN), GUID, Security Identifier (SID), DNS domain name, or NETBIOS name.
You can also set the parameter to an ADDomain  object variable,  or pass an ADDomain object through the pipeline to the Identity parameter.
For example, you can use the Get-ADDomain cmdlet to retrieve a domain object and then pass the object through the pipeline to the Set-ADDomainDefaultPasswordPolicy cmdlet.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADDefaultDomainPasswordPolicy -Identity fabrikam.com -LockoutDuration 00:40:00 -LockoutObservationWindow 00:20:00 -ComplexityEnabled $true -ReversibleEncryptionEnabled $false -MaxPasswordAge 10.00:00:00
```

Description

-----------

Set the default domain password policy for a given domain.
Note: setting MaxPwdAge to 0 will convert it to 'never' (Int64.MinValue or -9223372036854775808 in the directory).

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADDefaultDomainPasswordPolicy -Current LoggedOnUser | Set-ADDefaultDomainPasswordPolicy -LockoutDuration 00:40:00 -LockoutObservationWindow 00:20:00 -ComplexityEnabled $true -ReversibleEncryptionEnabled $false -MinPasswordLength 12
```

Description

-----------

Set the default domain password policy for the current logged on user domain.

## PARAMETERS

### -AuthType
Specifies the authentication method to use.
Possible values for this parameter include:

Negotiate or 0

Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

The following example shows how to set this parameter to Basic.

-AuthType Basic

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases: 
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: Microsoft.ActiveDirectory.Management.AuthType.Negotiate
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComplexityEnabled
Specifies whether password complexity is enabled for the password policy.
If enabled, the password must contain two of the following three character types:

Uppercase characters (A, B, C, D, E, ...)

Lowercase characters (a, b, c, d, e, ...)

Numerals (0, 1, 2, 3, ...)

This parameter sets the ComplexityEnabled property of a password policy.

Possible values for this parameter include:

$false or 0 - Disables password complexity

$true or 1 - Enables password complexity

The following example shows how to set this parameter to true.

-ComplexityEnabled $true

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: $true
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as "User1" or "Domain01\User01" or you can specify a PSCredential object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a PSCredential object by using a script or by using the Get-Credential cmdlet.
You can then set the Credential parameter to the PSCredential object The following example shows how to create credentials.

$AdminCredentials = Get-Credential "Domain01\User01"

The following shows how to set the Credential parameter to these credentials.

-Credential $AdminCredentials

If the acting credentials do not have directory-level permission to perform the task, Active Directory PowerShell returns a terminating error.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies an Active Directory domain object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
All values are for the domainDNS object that represents the domain.

Distinguished Name

Example: DC=redmond,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-

DNS domain name

Example: redmond.corp.contoso.com

NetBIOS domain name

Example: redmond

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a domain object instance.

This example shows how to set the parameter to a distinguished name.

-Identity  "DC=redmond,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to a domain object instance named "domainInstance".

-Identity   $domainInstance

```yaml
Type: ADDefaultDomainPasswordPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LockoutDuration
Specifies the length of time that an account is locked after the number of failed login attempts exceeds the lockout threshold.
You cannot login to an account that is locked until the lockout duration time period has expired.
This parameter sets the lockoutDuration property of a password policy object.
The LDAP display name (ldapDisplayName) of this property is "msDS-LockoutDuration".

The lockout duration must be greater than or equal to the lockout observation time for a password policy.
Use the LockOutObservationWindow parameter to set the lockout observation time.

Specify the lockout duration time interval in the following format.

\[-\]D.H:M:S.F

where:

D = Days (0 to 10675199)

H = Hours (0 to 23)

M = Minutes (0 to 59)

S = Seconds (0 to 59)

F= Fractions of a second (0 to 9999999)

The following examples show how to set this parameter.

Set the time to 2 days

-LockoutDuration "2"

Set the time to 4 hours

-LockoutDuration "4:00"

Set the time to 5 minutes

-LockoutDuration "0:5"

Set the time to 45 seconds

LockoutDuration "0:0:45"

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 0.00:30:00 (30 Minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### -LockoutObservationWindow
Specifies the maximum time interval between two unsuccessful login attempts before the number of unsuccessful login attempts is reset to 0.
An account is locked when the number of unsuccessful login attempts exceeds the password policy lockout threshold.
This parameter sets the lockoutObservationWindow property of a password policy object.
The LDAP Display Name (ldapDisplayName) of this property is "msDS-lockoutObservationWindow".

The lockout observation window must be smaller than or equal to the lockout duration for a password policy.
Use the LockoutDuration parameter to set the lockout duration time.

Specify the time interval in the following format.

\[-\]D:H:M:S.F

where:

D = Days (0 to 10675199)

H = Hours (0 to 23)

M = Minutes (0 to 59)

S = Seconds (0 to 59)

F= Fractions of a second (0 to 9999999)

Note: Time values must be between the following values: 0:0:0:0.0 and 10675199:02:48:05.4775807.

The following examples show how to set this parameter.

Set the time to 2 days

-LockoutObservationWindow "2"

Set the time to 4 hours

-LockoutObservationWindow "4:00"

Set the time to 5 minutes

-LockoutObservationWindow "0:5"

Set the time to 45 seconds

-LockoutObservationWindow "0:0:45"

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 0.00.30.00 (30 Minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### -LockoutThreshold
Specifies the number of unsuccessful login attempts that are permitted before an account is locked out.
This number increases when the time between unsuccessful login attempts is less than the time specified for the lockout observation time window.
This parameter sets the LockoutThreshold property of a password policy.

The following example shows how to set the lockout threshold to 3 login attempts.

-LockoutThreshold 3

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPasswordAge
Specifies the maximum length of time that you can have the same password.
After this time period, the password expires and you must create a new one.

This parameter sets the maxPasswordAge property of a password policy.
The LDAP Display Name (ldapDisplayName) for this property is "maxPwdAge".

Specify the time interval in the following format.

\[-\]D.H:M:S.F

where:

\[-\] = Specifies a negative time interval

D = Days (0 to 10675199)

H = Hours (0 to 23)

M = Minutes (0 to 59)

S = Seconds (0 to 59)

F= Fractions of a second (0 to 9999999)

Note: Time values must be between the following values: -10675199:02:48:05.4775808 and 10675199:02:48:05.4775807.

The following examples show how to set this parameter.

Set the time span to 2 days

MaxPasswordAge "2"

Set the time span to the previous 2 days

MaxPasswordAge "-2"

Set the time span to 4 hours

MaxPasswordAge "4:00"

Set the time span to 5 minutes

MaxPasswordAge "0:5"

Set the time span to 45 seconds

MaxPasswordAge "0:0:45"

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 42.00:00:00 (42 days)
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinPasswordAge
Specifies the minimum length of time before you can change a password.

This parameter sets the minPasswordAge property of a password policy.
The LDAP Display Name (ldapDisplayName) for this property is "minPwdAge".

Specify the time interval in the following format.

\[-\]D.H:M:S.F

where:

\[-\] = Specifies a negative time interval

D = Days (0 to 10675199)

H = Hours (0 to 23)

M = Minutes (0 to 59)

S = Seconds (0 to 59)

F= Fractions of a second (0 to 9999999)

Note: Time values must be between the following values: -10675199:02:48:05.4775808 and 10675199:02:48:05.4775807.

The following examples show how to set this parameter.

Set the time span to 2 days

-MinPasswordAge "2"

Set the time span to 4 hours

-MinPasswordAge "4:00"

Set the time span to 5 minutes

-MinPasswordAge "0:5"

Set the time span to 45 seconds

-MinPasswordAge "0:0:45"

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 1.00:00:00 (1day)
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinPasswordLength
Specifies the minimum number of characters that a password must contain. 
This parameter sets the MinPasswordLength property of the password policy.

The following example shows how to set this parameter.

-MinPasswordLength 15

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 7
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns the new or modified object.
By default (i.e.
if -PassThru is not specified), this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PasswordHistoryCount
Specifies the number of previous passwords to save. 
A user cannot reuse a password in the list of saved passwords.
This parameter sets the PasswordHistoryCount property for a password policy.

The following example shows how to set this parameter to save 10 previous passwords.

-PasswordHistoryCount 10

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 24
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReversibleEncryptionEnabled
Specifies whether the directory must  store passwords using reversible encryption.
This parameter sets the ReversibleEncryption property for a password policy.
Possible values for this parameter include the following:

$false or 0

$true or 1

The following example shows how to set this parameter to true.

-ReversibleEncryptionEnabled $true

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: $true
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory Snapshot instance.

Domain name values:

Fully qualified domain name

Examples: corp.contoso.com

NetBIOS name

Example: CORP

Directory server values:

Fully qualified directory server name

Example: corp-DC12.corp.contoso.com

NetBIOS name

Example: corp-DC12

Fully qualified directory server name and port

Example: corp-DC12.corp.contoso.com:3268

The default value for the Server parameter is determined by one of the following methods in the order that they are listed:

-By using Server value from objects passed through the pipeline.

-By using the server information associated with the Active Directory PowerShell provider drive, when running under that drive.

-By using the domain of the computer running Powershell.

The following example shows how to specify a full qualified domain name as the parameter value.

-Server "corp.contoso.com"

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADDomain
A domain object is received by the Identity parameter.

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADDefaultDomainPasswordPolicy](./Get-ADDefaultDomainPasswordPolicy.md)
