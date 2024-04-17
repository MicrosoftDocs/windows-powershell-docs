---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/search-wmssystem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Search-WmsSystem
---

# Search-WmsSystem

## SYNOPSIS
Gets MultiPoint servers or personal computers running MultiPoint Connector in the same network.

## SYNTAX

```
Search-WmsSystem [-ManagedSystemsType] <ManagedSystemTypes> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Search-WmsSystem** cmdlet gets other MultiPoint servers or personal computers running MultiPoint Connector in the same network.
The operation takes 10 seconds to complete.

## EXAMPLES

### Example 1: Search for MultiPoint servers on a subnet
```
PS C:\> Search-WmsSystem -ManagedSystemsType MultiPointServers
Test2
Test3
```

The cmdlet gets peer Windows MultiPoint servers in the same subnet.
The query takes 10 seconds to complete and uses the Microsoft Web Services on Devices API (WSDAPI) to discover peer MultiPoint servers in the network.

## PARAMETERS

### -ManagedSystemsType
Specifies the managed system type.
The acceptable values for this parameter are: PersonalComputers, MultiPointServers.

```yaml
Type: ManagedSystemTypes
Parameter Sets: (All)
Aliases:
Accepted values: MultiPointServers, PersonalComputers

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### System.String

## NOTES

## RELATED LINKS

[Add-WmsSystem](./Add-WmsSystem.md)

[Get-WmsSystem](./Get-WmsSystem.md)

[Remove-WmsSystem](./Remove-WmsSystem.md)

[Restart-WmsSystem](./Restart-WmsSystem.md)

[Set-WmsSystem](./Set-WmsSystem.md)

[Stop-WmsSystem](./Stop-WmsSystem.md)

