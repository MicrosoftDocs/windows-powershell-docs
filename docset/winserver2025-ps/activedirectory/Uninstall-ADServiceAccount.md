---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/uninstall-adserviceaccount?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-ADServiceAccount
---

# Uninstall-ADServiceAccount

## SYNOPSIS
Uninstalls an Active Directory managed service account from a computer or removes a cached group managed service account from a computer.

## SYNTAX

```
Uninstall-ADServiceAccount [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-ForceRemoveLocal]
 [-Identity] <ADServiceAccount> [<CommonParameters>]
```

## DESCRIPTION
The **Uninstall-ADServiceAccount** cmdlet removes an Active Directory standalone managed service account (MSA) on the computer on which the cmdlet is run.
For group MSAs, the cmdlet removes the group MSA from the cache.
However, if a service is still using the group MSA and the host has permission to retrieve the password, then a new cache entry is created.
The specified MSA must be installed on the computer.

the *Identity* parameter specifies the Active Directory MSA to uninstall.
You can identify an MSA by its distinguished name (DN), GUID, security identifier (SID), or Security Account Manager (SAM) account name.
You can also set the parameter to an MSA object variable, such as `$<localServiceAccountObject>` or pass an MSA object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADServiceAccount** cmdlet to get an MSA object and then pass that object through the pipeline to the **Uninstall-ADServiceAccount** cmdlet.

## EXAMPLES

### Example 1: Uninstall a specified MSA
```
PS C:\> Uninstall-ADServiceAccount -Identity SQL-SRV1
```

This command uninstalls the MSA identified as SQL-SRV1 from the local machine.

### Example 2: Uninstall an MSA from a server in a read-only domain controller site
```
PS C:\> Uninstall-ADServiceAccount -Identity sql-hr-01 -ForceRemoveLocal
```

This command uninstalls the specified standalone MSA from a server located in a read-only domain controller site such as a perimeter network.

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

### -ForceRemoveLocal
Indicates that you can remove the account from the local security authority (LSA) if there is no access to a writable domain controller.
This is required if you are uninstalling the MSA from a server that is placed in a segmented network such as a perimeter network with access only to a read-only domain controller.
If you specify this parameter and the server has access to a writable domain controller, the account is also un-linked from the computer account in the directory.

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

### -Identity
Specifies an Active Directory account object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A Distinguished Name
- A GUID (objectGUID)
- A Security Identifier (objectSid)
- A SAM Account Name (sAMAccountName)

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

### None or Microsoft.ActiveDirectory.Management.ADServiceAccount
A managed service account object is received by the *Identity* parameter.
A parameter with name **ForceRemoveLocal** is provided to un-install standalone MSAs on a read-only domain controller site.

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with AD LDS.
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[Install-ADServiceAccount](./Install-ADServiceAccount.md)

[New-ADServiceAccount](./New-ADServiceAccount.md)

[Remove-ADServiceAccount](./Remove-ADServiceAccount.md)

[Set-ADServiceAccount](./Set-ADServiceAccount.md)

