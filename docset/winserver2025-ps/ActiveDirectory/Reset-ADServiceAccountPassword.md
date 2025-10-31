---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/reset-adserviceaccountpassword?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-ADServiceAccountPassword
---

# Reset-ADServiceAccountPassword

## SYNOPSIS
Resets the password for a standalone managed service account.

## SYNTAX

```
Reset-ADServiceAccountPassword [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Identity] <ADServiceAccount>
 [-Partition <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Reset-ADServiceAccountPassword** cmdlet resets the password for the standalone managed service account (MSA) on the local computer.
You must run this cmdlet on the computer where the standalone MSA is installed.
Reset is not supported for group managed service accounts.

The *Identity* parameter specifies the Active Directory standalone MSA that receives the password reset.
You can identify an MSA by its distinguished name (DN), GUID, security identifier (SID) or Security Accounts Manager (SAM) account name.
You can also set the *Identity* parameter to a MSA object variable, such as `$<localServiceAccountObject>`, or pass a MSA object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADServiceAccount** cmdlet to retrieve a standalone MSA object and then pass the object through the pipeline to the **Reset-ADServiceAccountPassword** cmdlet.

Note: When you reset the password for a computer, you also reset all of the standalone MSA passwords for that computer.

## EXAMPLES

### Example 1: Reset the password for a standalone MSA
```
PS C:\> Reset-ADServiceAccountPassword -Identity ServiceAccount1
```

This command resets the password on the standalone managed service account ServiceAccount1.

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

### -Identity
Specifies an Active Directory account object by providing one of the following property values.
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A SAM account name (sAMAccountName)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADServiceAccount
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
The cmdlet searches this partition to find the object defined by the *Identity* parameter.

In many cases, a default value is used for the *Partition* parameter if no value is specified.
The rules for determining the default value are given below.
Note that rules listed first are evaluated first and once a default value can be determined, no further rules are evaluated.

In Active Directory Domain Services (AD DS) environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of *Partition* is set to the default partition or naming context of the target domain.

In Active Directory Lightweight Directory Services (AD LDS) environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of *Partition* is set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the *Partition* parameter does not take any default value.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADServiceAccount
A managed service account object is received by the *Identity* parameter.

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with Active Directory Lightweight Directory Services (AD LDS).
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

