---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/get-wmsdiskprotection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmsDiskProtection
---

# Get-WmsDiskProtection

## SYNOPSIS
Gets the current state and configuration of the disk protection feature.

## SYNTAX

```
Get-WmsDiskProtection [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WmsDiskProtection** cmdlet gets the current configuration of the disk protection feature.
The configuration can be NotInstalled, Discard, or Passive.

## EXAMPLES

### Example 1: Get the disk protection configuration for the local computer
```
PS C:\> Get-WmsDiskProtection
Discard
```

This command returns the state of the disk protection feature on the local computer.

### Example 2: Get the disk protection configuration for a specified computer
```
PS C:\> Get-WmsDiskProtection -Server "Sample.microsoft.com"
Passive
```

This command returns the state of the disk protection feature on the specified computer.

## PARAMETERS

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command.
The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.WindowsServerSolutions.MultipointServer.PowerShell.Commands.Library.DiskProtectionMode

The **DiskProtectionMode** object is an enumeration with one of three values that reflect the current mode of the disk protection feature.
The possible values are NotInstalled, Discard, or Passive.

## NOTES

## RELATED LINKS

[Disable-WmsDiskProtection](./Disable-WmsDiskProtection.md)

[Enable-WmsDiskProtection](./Enable-WmsDiskProtection.md)

[Resume-WmsDiskProtection](./Resume-WmsDiskProtection.md)

[Suspend-WmsDiskProtection](./Suspend-WmsDiskProtection.md)

