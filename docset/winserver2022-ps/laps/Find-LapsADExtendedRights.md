---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: lapspsh.dll-Help.xml
Module Name: LAPS
online version: https://learn.microsoft.com/powershell/module/laps/find-lapsadextendedrights?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
Locale: en-US
ms.date: 04/10/2023
title: Find-LapsADExtendedRights
---

# Find-LapsADExtendedRights

## SYNOPSIS

Queries Active Directory to find principals that have been granted permission to read Windows Local
Administrator Password Solution (LAPS) password attributes.

## SYNTAX

```
Find-LapsADExtendedRights [-Credential <PSCredential>] -Identity <String[]> [-Domain <String>]
 [-DomainController <String>] [-IncludeComputers] [<CommonParameters>]
```

## DESCRIPTION

The **Find-LapsADExtendedRights** cmdlet is used by administrators to query which principals have
been granted permissions to read the LAPS password attributes.

## EXAMPLES

### Example 1

```powershell
PS C:\> Find-LapsADExtendedRights -Identity LapsTestOU

ObjectDN                     ExtendedRightHolders
--------                     --------------------
OU=LapsTestOU,DC=laps,DC=com {NT AUTHORITY\SYSTEM, LAPS\Domain Admins, LAPS\LapsAdmins}
```

This example shows how to run the cmdlet.

## PARAMETERS

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

Specifies which Active Directory Organizational Unit to query.

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
