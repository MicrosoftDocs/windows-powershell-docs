---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/add-wmssystem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WmsSystem
---

# Add-WmsSystem

## SYNOPSIS
Adds a computer that can be remotely managed.

## SYNTAX

```
Add-WmsSystem [-ComputerName] <String[]> [-ManagedSystemsType] <ManagedSystemTypes>
 [-Credential] <PSCredential> [<CommonParameters>]
```

## DESCRIPTION
The **Add-WmsSystem** cmdlet enables the local computer to remotely manage a computer with either the MultiPoint role or MultiPoint connector installed.

## EXAMPLES


## PARAMETERS

### -ComputerName
Specifies an array of host names of MultiPoint systems to add.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Specifies the Administrator credentials for the computer to add.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedSystemsType
Specifies the type of managed systems.
The acceptable values for this parameter are: MultiPointServers, PersonalComputers.

```yaml
Type: ManagedSystemTypes
Parameter Sets: (All)
Aliases:
Accepted values: MultiPointServers, PersonalComputers

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### string[]
The input is an array of fully qualified host names of the computers that should have remote management enabled.

## OUTPUTS

### WmsSystem
For each computer added a **WmsSystem** object is returned which contains specific information about the configuration and state of the MultiPoint system on that computer.

## NOTES

## RELATED LINKS

[Get-WmsSystem](./Get-WmsSystem.md)

[Remove-WmsSystem](./Remove-WmsSystem.md)

[Restart-WmsSystem](./Restart-WmsSystem.md)

[Search-WmsSystem](./Search-WmsSystem.md)

[Set-WmsSystem](./Set-WmsSystem.md)

[Stop-WmsSystem](./Stop-WmsSystem.md)

