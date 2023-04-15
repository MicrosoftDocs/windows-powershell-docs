---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: lapspsh.dll-Help.xml
Module Name: LAPS
online version: https://learn.microsoft.com/powershell/module/laps/set-lapsadresetpasswordpermission?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
Locale: en-US
ms.date: 04/10/2023
title: Set-LapsADResetPasswordPermission
---

# Set-LapsADResetPasswordPermission

## SYNOPSIS

Configures security on an Active Directory Organizational Unit to grant specific users or groups
permission to set the Windows Local Administrator Password Solution (LAPS) password expiration time.

## SYNTAX

```powershell
Set-LapsADResetPasswordPermission [-Credential <PSCredential>] -Identity <String[]>
 -AllowedPrincipals <String[]> [-Domain <String>] [-DomainController <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The **Set-LapsADResetPasswordPermission** cmdlet is used by administrators to configure security
permissions on an Active Directory Organizational Unit (OU) to allow specific users or groups to
reset the LAPS password expiration time on computers in that OU. Users and groups must be fully
qualified with both domain and user name components; the only exception to this is when the
specified name resolves to a built-in principal (for example "Domain Admins").

## EXAMPLES

### Example 1

```powershell
PS C:\> Set-LapsADResetPasswordPermission -Identity LapsTestOU -AllowedPrincipals "Domain Admins"

Name       DistinguishedName
----       -----------------
LapsTestOU OU=LapsTestOU,DC=laps,DC=com
```

This example shows how to run the cmdlet with an isolated name that successfully maps to a
well-known user or group.

### Example 2

```powershell
PS C:\> Set-LapsADResetPasswordPermission -Identity LapsTestOU -AllowedPrincipals @("S-1-5-21-2889755270-1324585639-743026605-1215")

Name       DistinguishedName
----       -----------------
LapsTestOU OU=LapsTestOU,DC=laps,DC=com
```

This example shows how to run the cmdlet specifying a user SID as input.

### Example 3

```powershell
PS C:\> Set-LapsADResetPasswordPermission -Identity 'OU=LapsTestOU,DC=laps,DC=com' -AllowedPrincipals @("laps.com\LapsAdmin1", "LapsAdmin2@laps.com")

Name       DistinguishedName
----       -----------------
LapsTestOU OU=LapsTestOU,DC=laps,DC=com
```

This example shows how to run the cmdlet specifying two fully qualified user names (in different
formats) as input.

### Example 4

```powershell
PS C:\> Set-LapsADResetPasswordPermission -Identity LapsTestOU -AllowedPrincipals @("LapsAdministratorsGroup")
Set-LapsADReadPasswordPermission : The 'LapsAdministratorsGroup' account appears to be an isolated name but is not a well-known name. Please use a
fully qualified name instead, such as "LapsAdministratorsGroup@contoso.com" or "contoso\LapsAdministratorsGroup"
At line:1 char:1
+ Set-LapsADReadPasswordPermission -Identity LapsTestOU -AllowedPrincip ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Set-LapsADReadPasswordPermission], LapsPowershellException
    + FullyQualifiedErrorId : Invalid principal specified,Microsoft.Windows.LAPS.SetLapsADReadPasswordPermission
```

This example shows a failure caused by specifying an isolated name that did not resolve to a
well-known or built-in account. The fix for this error would be to add a domain name qualifier to
the input name, for example "LapsAdministratorsGroup@laps.com".

## PARAMETERS

### -AllowedPrincipals

Specifies which users or groups should be granted the permissions. Users or groups may be specified
in either name or SID format. If specified in name format, the name must always include the
identifying domain name portion unless the name maps to a well-known or built-in account.

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

Specifies the credentials to use when updating Active Directory. If not specified the current user's
credentials will be used.

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

Specifies which Active Directory domain to connect to.

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

Specifies which Active Directory domain controller to connect to.

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

Specifies which Active Directory Organizational Unit to update.

This parameter accepts several different name formats which influence the criteria used in the
resultant Active Directory search. The supported name formats are as follows:

distinguishedName (begins with a "CN=")
name (for all other inputs)

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

Shows what would happen if the cmdlet runs. The cmdlet is not run.

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
