---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://docs.microsoft.com/powershell/module/activedirectory/get-aduserresultantpasswordpolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADUserResultantPasswordPolicy

## SYNOPSIS
Gets the resultant password policy for a user.

## SYNTAX

```
Get-ADUserResultantPasswordPolicy [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADUser>
 [-Partition <String>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Get-ADUserResultantPasswordPolicy gets the resultant password policy object (RSoP) for a user.
The RSoP is defined by the Active Directory attribute named msDS-ResultantPSO.

A user can have multiple password policy objects (PSOs) associated with it, but only one PSO is the RSoP.
A PSO is associated with a user when the PSO applies directly to the user or when the PSO applies to an Active Directory group that contains the user.
When more than one PSO policy is associated with a user or group, the RSoP value defines the PSO to apply.

The resultant password policy or RSoP for a user is determined by using the following procedure.

- If only one PSO is associated with a user, this PSO is the RSoP.
- If more than one PSO is associated with a user, the PSO that applies directly to the user is the RSoP.
- If more than one PSO applies directly to the user, the PSO with the lowest msDS-PasswordSettingsPrecedence attribute value is the RSoP and this event is logged as a warning in the Active Directory event log. The lowest attribute value represents the highest PSO precedence. For example, if the msDS-PasswordSettingsPrecedence values of two PSOs are 100 and 200, the PSO with the attribute value of 100 is the RSoP.
- If there are no PSOs that apply directly to the user, the PSOs of the global security groups that have the user as a member are compared. The PSO with the lowest msDS-PasswordSettingsPrecedence value is the RSoP.

The Identity parameter specifies the Active Directory user.
You can identify a user by its distinguished name (DN), GUID, security identifier (SID) or Security Accounts Manager (SAM) account name.
You can also set the parameter to a user object variable, such as $\<localUserObject\> or pass a user object through the pipeline to the Identity parameter.
For example, you can use the Get-ADUser cmdlet to retrieve a user object and then pass the object through the pipeline to the Get-ADUserResultantPasswordPolicy cmdlet.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADUserResultantPasswordPolicy BobKe


Name                        : DomainUsersPSO
ComplexityEnabled           : True
LockoutThreshold            : 10
ReversibleEncryptionEnabled : False
LockoutDuration             : 12:00:00
LockoutObservationWindow    : 00:15:00
MinPasswordLength           : 8
Precedence                  : 500
ObjectGUID                  : f8d2653c-9b3b-499e-b272-4c7f4268df4c
ObjectClass                 : msDS-PasswordSettings
PasswordHistoryCount        : 24
MinPasswordAge              : 1.00:00:00
MaxPasswordAge              : 60.00:00:00
AppliesTo                   : {CN=Domain Users,CN=Users,DC=FABRIKAM,DC=COM}
DistinguishedName           : CN=DomainUsersPSO,CN=Password Settings Container,CN=System,DC=FABRIKAM,DC=COM
```

Description

-----------

Get the resultant password policy for the user with samAccountName 'BobKe'.

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
Specifies an Active Directory user object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example:  CN=SaraDavis,CN=Europe,CN=Users,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

SAM account name  (sAMAccountName)

Example: saradavis

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

This example shows how to set the parameter to a distinguished name.

-Identity  "CN=SaraDavis,CN=Europe,CN=Users,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to a user object instance named "userInstance".

-Identity   $userInstance

```yaml
Type: ADUser
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Partition
Specifies the distinguished name of an Active Directory partition.
The distinguished name must be one of the naming contexts on the current directory server.
The cmdlet searches this partition to find the object defined by the Identity parameter.

The following two examples show how to specify a value for this parameter.

-Partition "CN=Configuration,DC=EUROPE,DC=TEST,DC=CONTOSO,DC=COM"

-Partition "CN=Schema,CN=Configuration,DC=EUROPE,DC=TEST,DC=CONTOSO,DC=COM"

In many cases, a default value will be used for the Partition parameter if no value is specified. 
The rules for determining the default value are given below. 
Note that rules listed first are evaluated first and once a default value can be determined, no further rules will be evaluated.

In AD DS environments, a default value for Partition will be set in the following cases:  - If the Identity parameter is set to a distinguished name, the default value of Partition is automatically generated from this distinguished name.

- If running cmdlets from an Active Directory provider drive, the default value of Partition is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of Partition will be set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for Partition will be set in the following cases:

- If the Identity parameter is set to a distinguished name, the default value of Partition is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of Partition is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of Partition will be set to the default naming context.  To specify a default naming context for an AD LDS environment, set the msDS-defaultNamingContext property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance.
- If none of the previous cases apply, the Partition parameter will not take any default value.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADUser
A user object is received by the Identity parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy
Returns a fine grained password policy object that represents the resultant password policy for the user.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with an Active Directory Snapshot.

## RELATED LINKS

[Get-ADUser](./Get-ADUser.md)

