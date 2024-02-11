---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adfinegrainedpasswordpolicysubject?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADFineGrainedPasswordPolicySubject
---

# Get-ADFineGrainedPasswordPolicySubject

## SYNOPSIS
Gets the users and groups to which a fine-grained password policy is applied.

## SYNTAX

```
Get-ADFineGrainedPasswordPolicySubject [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADFineGrainedPasswordPolicy> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADFineGrainedPasswordPolicySubject** cmdlet gets users and groups that are subject to a fine-grained password policy.

The *Identity* parameter specifies the fine-grained password policy.
You can identify a fine-grained password policy by its distinguished name, GUID, or name.
You can also set the *Identity* parameter to a fine-grained password policy object variable, such as `$<localPasswordPolicyObject>`, or pass a fine-grained password policy object through the pipeline operator to the *Identity* parameter.
For example, you can use the **Get-ADFineGrainedPasswordPolicy** cmdlet to retrieve a fine-grained password policy object and then pass the object through the pipeline operator to the **Get-ADFineGrainedPasswordPolicySubject** cmdlet.

## EXAMPLES

### Example 1: Get the subject of a fine-grained password policy
```
PS C:\> Get-ADFineGrainedPasswordPolicySubject -Identity DomainUsersPSO | FT Name,ObjectClass,DistinguishedName -AutoSize
Name                     ObjectClass DistinguishedName
----                     ----------- -----------------
Domain Users group       CN=Domain   Users,CN=Users,DC=FABRIKAM,DC=COM
```

This command gets the fine-grained password policy subject of the password policy named DomainUsersPSO.

## PARAMETERS

### -AuthType
Specifies the authentication method to use.
The acceptable values for this parameter are:

- Negotiate or 0
- Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory module for Windows PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active Directory module for Windows PowerShell returns a terminating error.

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
Specifies an Active Directory fine-grained password policy object by providing one of the following property values.
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A name (name)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a fine-grained password policy object instance.

```yaml
Type: ADFineGrainedPasswordPolicy
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Server
Specifies the AD DS instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: AD LDS, AD DS, or Active Directory snapshot instance.

Specify the AD DS instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the AD DS Windows PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy
A fine-grained password policy object is received by the *Identity* parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADPrincipal
Returns principal objects that represent the users and groups to which the fine-grained password policy is applied.

## NOTES
* This cmdlet does not work with AD LDS.
* This cmdlet does not work when targeting a snapshot using the *Server* parameter.

## RELATED LINKS

[Add-ADFineGrainedPasswordPolicySubject](./Add-ADFineGrainedPasswordPolicySubject.md)

[Remove-ADFineGrainedPasswordPolicySubject](./Remove-ADFineGrainedPasswordPolicySubject.md)

