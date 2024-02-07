---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/add-adfinegrainedpasswordpolicysubject?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ADFineGrainedPasswordPolicySubject
---

# Add-ADFineGrainedPasswordPolicySubject

## SYNOPSIS
Applies a fine-grained password policy to one more users and groups.

## SYNTAX

```
Add-ADFineGrainedPasswordPolicySubject [-WhatIf] [-Confirm] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Identity] <ADFineGrainedPasswordPolicy>
 [-Partition <String>] [-PassThru] [-Server <String>] [-Subjects] <ADPrincipal[]>
 [<CommonParameters>]
```

## DESCRIPTION

The `Add-ADFineGrainedPasswordPolicySubject` cmdlet applies a fine-grained password policy to one or
more global security groups and users.

The **Identity** parameter specifies the fine-grained password policy to apply. You can identify a
fine-grained password policy by its distinguished name, GUID or name. You can also set the
**Identity** parameter to a fine-grained password policy object variable, such as
`$<localPasswordPolicyObject>`, or pass a fine-grained password policy object through the pipeline
operator to the **Identity** parameter. For example, you can use the
`Get-ADFineGrainedPasswordPolicy` cmdlet to get a fine-grained password policy object and then pass
the object through the pipeline operator to the `Add-ADFineGrainedPasswordPolicySubject` cmdlet.

The **Subjects** parameter specifies the users and global security groups. You can identify a user
or global security group by its distinguished name (DN), GUID, security identifier (SID), or
Security Account Manager (SAM) account name. You can also specify user and global security group
object variables, such as `$<localUserObject>`. If you are specifying more than one user or group,
use a comma-separated list. To pass user and global security group objects through the pipeline to
the **Subjects** parameter, use the `Get-ADUser` or the `Get-ADGroup` cmdlets to retrieve the user
or group objects, and then pass these objects through the pipeline operator to the
`Add-ADFineGrainedPasswordPolicySubject` cmdlet.

## EXAMPLES

### EXAMPLE 1

```powershell
Add-ADFineGrainedPasswordPolicySubject -Identity DomainUsersPSO -Subjects 'Domain Users'
```

This command applies the fine-grained password policy named `DomainUsersPSO` to the `Domain Users`
global security group.

### EXAMPLE 2

```powershell
Add-ADFineGrainedPasswordPolicySubject -Identity DlgtdAdminsPSO -Subjects BobKe, KimAb
```

This command applies the fine-grained password policy named `DlgtdAdminsPSO` to users with the SAM
account names `BobKe` and `KimAb`.

### EXAMPLE 3

```powershell
Add-ADFineGrainedPasswordPolicySubject -Identity DlgtdAdminsPSO -Subjects DlgtdAdminGroup
```

This command applies the fine-grained password policy named `DlgtdAdminsPSO` to the group
`DlgtdAdminGroup`.

### EXAMPLE 4

```powershell
Get-ADUser -Filter "lastname -eq 'Fuller'" |
    Add-ADFineGrainedPasswordPolicySubject -Identity DlgtdAdminsPSO
```

This command applies the fine-grained password policy named `DlgtdAdminsPSO` to any users whose last
name is `Fuller`.

## PARAMETERS

### -AuthType

Specifies the authentication method to use. The acceptable values for this parameter are:

- `Negotiate` or `0`
- `Basic` or `1`

The default authentication method is `Negotiate`.

A Secure Sockets Layer (SSL) connection is required for the `Basic` authentication method.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADAuthType
Parameter Sets: (All)
Aliases: 
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the user account credentials to use to perform this task. The default credentials are the
credentials of the currently logged on user unless the cmdlet is run from an Active Directory module
for Windows PowerShell provider drive. If the cmdlet is run from such a provider drive, the account
associated with the drive is the default.

To specify this parameter, you can type a user name, such as `User1` or `Domain01\User01` or you can
specify a **PSCredential** object. If you specify a user name for this parameter, the cmdlet prompts
for a password.

You can also create a **PSCredential** object by using a script or by using the `Get-Credential`
cmdlet. You can then set the **Credential** parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active
Directory module for Windows PowerShell returns a terminating error.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

Specifies an Active Directory fine-grained password policy object by providing one of the following
property values. The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP)
display name for the attribute. The acceptable values for this parameter are:

- A distinguished name
- A GUID (**objectGUID**)
- A name (name)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a
fine-grained password policy object instance.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Partition

Specifies the distinguished name of an Active Directory partition. The distinguished name must be
one of the naming contexts on the current directory server. The cmdlet searches this partition to
find the object defined by the **Identity** parameter.

In many cases, a default value is used for the **Partition** parameter if no value is specified. The
rules for determining the default value are given below. Note that rules listed first are evaluated
first and once a default value can be determined, no further rules are evaluated.

In Active Directory Domain Services environments, a default value for **Partition** is set in the
following cases:

- If the **Identity** parameter is set to a distinguished name, the default value of **Partition**
  is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of **Partition** is
  automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of **Partition** is set to the default
  partition or naming context of the target domain.

In Active Directory Lightweight Directory Services (AD LDS) environments, a default value for
**Partition** is set in the following cases:

- If the **Identity** parameter is set to a distinguished name, the default value of **Partition**
  is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of **Partition** is
  automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of **Partition** is
  set to the default naming context. To specify a default naming context for an AD LDS environment,
  set the **msDS-defaultNamingContext** property of the Active Directory directory service agent
  (DSA) object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the **Partition** parameter will not take any default value.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Returns an object representing the item with which you are working. By default, this cmdlet does
not generate any output.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

Specifies the Active Directory Domain Services instance to connect to, by providing one of the
following values for a corresponding domain name or directory server. The service may be any of the
following: Active Directory Lightweight Domain Services, Active Directory Domain Services or Active
Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that
they are listed:

- By using the **Server** value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows
  PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subjects

Specifies one or more users or groups. To specify more than one user or group, use a
comma-separated list. You can identify a user or group by one of the following property values:

- Distinguished name (DN)
- GUID (**objectGUID**)
- Security Identifier (**objectSid**)
- SAM account name (**sAMAccountName**)

Note: The identifier in parentheses is the LDAP display name for the attribute.

You can also provide objects to this parameter directly.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADPrincipal[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy, Microsoft.ActiveDirectory.Management.ADPrincipal

A fine-grained password policy object is received by the **Identity** parameter. One or more
principal objects that represent users and security group objects are received by the **Subjects**
parameter. Derived principal types, such as the following, are also accepted by the **Subjects**
parameter:

- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy

Returns the modified fine-grained password policy object when the **PassThru** parameter is
specified. By default, this cmdlet does not generate any output.

## NOTES

- This cmdlet does not work with AD LDS.
- This cmdlet does not work with a read-only domain controller.
- This cmdlet does not work with an Active Directory snapshot.

## RELATED LINKS

[Get-ADFineGrainedPasswordPolicySubject](./Get-ADFineGrainedPasswordPolicySubject.md)

[Remove-ADFineGrainedPasswordPolicySubject](./Remove-ADFineGrainedPasswordPolicySubject.md)
