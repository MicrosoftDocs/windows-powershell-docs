---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/test-adserviceaccount?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ADServiceAccount
---

# Test-ADServiceAccount

## SYNOPSIS
Tests a managed service account from a computer.

## SYNTAX

```
Test-ADServiceAccount [-AuthType <ADAuthType>] [-Identity] <ADServiceAccount> [<CommonParameters>]
```

## DESCRIPTION
The **Test-ADServiceAccount** cmdlet tests a managed service account (MSA) from a local computer.

the *Identity* parameter specifies the Active Directory MSA account to test.
You can identify a MSA by its distinguished name (DN), GUID, security identifier (SID), or Security Account Manager (SAM) account name.
You can also set the parameter to a MSA object variable, such as `$<localMSA>` or pass a MSA object through the pipeline to the *Identity* parameter.
For example, you can use the Get-ADServiceAccount to get a MSA object and then pass that object through the pipeline to the **Test-ADServiceAccount** cmdlet.

## EXAMPLES

### Example 1: Test an MSA
```
PS C:\> Test-ADServiceAccount -Identity MSA1
True
```

This command tests the specified service account, MSA1, from the local computer.
The test indicates whether the account is ready for use, which means it can be authenticated and that it can access the domain using its current credentials.

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

### -Identity
Specifies an Active Directory managed service account object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADServiceAccount
A managed service account object is received by the *Identity* parameter.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[Install-ADServiceAccount](./Install-ADServiceAccount.md)

[New-ADServiceAccount](./New-ADServiceAccount.md)

[Remove-ADServiceAccount](./Remove-ADServiceAccount.md)

[Set-ADServiceAccount](./Set-ADServiceAccount.md)

[Uninstall-ADServiceAccount](./Uninstall-ADServiceAccount.md)

