---
description: Queries Active Directory (AD) to find principals that have been granted permission to read Windows Local Administrator Password Solution (LAPS) password attributes.
external help file: lapspsh.dll-Help.xml
Module Name: LAPS
online version: https://learn.microsoft.com/powershell/module/laps/find-lapsadextendedrights?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
Locale: en-US
ms.date: 04/10/2023
title: Find-LapsADExtendedRights
---

# Find-LapsADExtendedRights

## SYNOPSIS
Queries Active Directory (AD) to find principals that have been granted permission to read Windows
Local Administrator Password Solution (LAPS) password attributes.

## SYNTAX

```
Find-LapsADExtendedRights [-Credential <PSCredential>] -Identity <String[]> [-Domain <String>]
 [-DomainController <String>] [-IncludeComputers] [<CommonParameters>]
```

## DESCRIPTION

The `Find-LapsADExtendedRights` cmdlet is used by administrators to query which principals have
been granted permissions to read the LAPS password attributes.

## EXAMPLES

### Example 1

```powershell
Find-LapsADExtendedRights -Identity LapsTestOU
```

```Output
ObjectDN                     ExtendedRightHolders
--------                     --------------------
OU=LapsTestOU,DC=laps,DC=com {NT AUTHORITY\SYSTEM, LAPS\Domain Admins, LAPS\LapsAdmins}
```

This example shows how to run the cmdlet.

## PARAMETERS

### -Credential

Specifies the credentials to use when updating AD. If not specified, the current
user's credentials are used.

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

Specifies the name of the OU to query.

This parameter accepts several different name formats that influence the criteria used in the
resultant AD search. The supported name formats are as follows:

- distinguishedName (begins with a `CN=`)
- name (for all other inputs)

Querying permissions on the domain root is only supported using the distinguishedName input format, for example 'DC=laps,DC=com'.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -IncludeComputers

Specify this parameter to also check computer objects for the permissions.

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
