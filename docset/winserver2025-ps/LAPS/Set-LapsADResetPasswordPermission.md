---
description: Configures security on an Active Directory (AD) Organizational Unit (OU) to grant specific users or groups permission to set the Windows Local Administrator Password Solution (LAPS) password expiration time.
external help file: lapspsh.dll-Help.xml
Module Name: LAPS
online version: https://learn.microsoft.com/powershell/module/laps/set-lapsadresetpasswordpermission?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
Locale: en-US
ms.date: 04/10/2023
title: Set-LapsADResetPasswordPermission
---

# Set-LapsADResetPasswordPermission

## SYNOPSIS
Configures security on an Active Directory (AD) Organizational Unit (OU) to grant specific users or
groups permission to set the Windows Local Administrator Password Solution (LAPS) password
expiration time.

## SYNTAX

```
Set-LapsADResetPasswordPermission [-Credential <PSCredential>] -Identity <String[]>
 -AllowedPrincipals <String[]> [-Domain <String>] [-DomainController <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Set-LapsADResetPasswordPermission` cmdlet is used by administrators to configure security
permissions on an OU to allow specific users or groups to reset the LAPS password expiration time on
computers in that OU. Users and groups must be fully qualified with both domain and user name
components. The only exception to this is when the specified name resolves to a built-in principal,
such as `Domain Admins`.

## EXAMPLES

### Example 1

```powershell
Set-LapsADResetPasswordPermission -Identity LapsTestOU -AllowedPrincipals "Domain Admins"
```

```Output
Name       DistinguishedName
----       -----------------
LapsTestOU OU=LapsTestOU,DC=laps,DC=com
```

This example shows how to run the cmdlet with an isolated name that successfully maps to a
well-known user or group.

### Example 2

```powershell
Set-LapsADResetPasswordPermission -Identity LapsTestOU -AllowedPrincipals @("S-1-5-21-2889755270-1324585639-743026605-1215")
```

```Output
Name       DistinguishedName
----       -----------------
LapsTestOU OU=LapsTestOU,DC=laps,DC=com
```

This example shows how to run the cmdlet specifying a user SID as input.

### Example 3

```powershell
Set-LapsADResetPasswordPermission -Identity 'OU=LapsTestOU,DC=laps,DC=com' -AllowedPrincipals @("laps.com\LapsAdmin1", "LapsAdmin2@laps.com")
```

```Output
Name       DistinguishedName
----       -----------------
LapsTestOU OU=LapsTestOU,DC=laps,DC=com
```

This example shows how to run the cmdlet specifying two fully qualified user names in different
formats.

### Example 4

```powershell
Set-LapsADResetPasswordPermission -Identity LapsTestOU -AllowedPrincipals @("LapsAdministratorsGroup")
```

```Output
Set-LapsADReadPasswordPermission : The 'LapsAdministratorsGroup' account appears to be an isolated
name but is not a well-known name. Please use a fully qualified name instead, such as
"LapsAdministratorsGroup@contoso.com" or "contoso\LapsAdministratorsGroup"
At line:1 char:1
+ Set-LapsADReadPasswordPermission -Identity LapsTestOU -AllowedPrincip ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Set-LapsADReadPasswordPermission], LapsPowershellException
    + FullyQualifiedErrorId : Invalid principal specified,Microsoft.Windows.LAPS.SetLapsADReadPasswordPermission
```

This example shows a failure caused by specifying an isolated name that didn't resolve to a
well-known or built-in account. The fix for this error would be to add a domain name qualifier to
the input name, for example "LapsAdministratorsGroup@laps.com".

## PARAMETERS

### -AllowedPrincipals

Specifies the name of the users or groups should be granted the permissions. Users or groups may be
specified in either name or SID format. If specified in name format, the name must always include
the identifying domain name portion unless the name maps to a well-known or built-in account.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the credentials to use when updating AD. If not specified, the current user's credentials
are used.

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

### -Domain

Specifies the name of the domain to connect to.

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

### -DomainController

Specifies the name of the domain controller to connect to.

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

### -Identity

Specifies the name of the OU to update.

This parameter accepts several different name formats that influence the criteria used in the
resultant AD search. The supported name formats are as follows:

- distinguishedName (begins with a `CN=`)
- name (for all other inputs)

Setting permissions on the domain root is only supported using the distinguishedName input format, for example 'DC=laps,DC=com'.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Default value: None
Accept pipeline input: False
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Windows LAPS Overview](https://go.microsoft.com/fwlink/?linkid=2233901)
