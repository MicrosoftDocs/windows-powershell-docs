---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: New-VMSan
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 696D66E7-6489-4DCB-A3CA-52BB9E13F8EB
---

# New-VMSan

## SYNOPSIS
Creates a new virtual storage area network (SAN) on a Hyper-V host.

## SYNTAX

### HbaObject (Default)
```
New-VMSan [-ComputerName <String>] [-Name] <String> [-Note <String>] [-HostBusAdapter <CimInstance[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StringWwn
```
New-VMSan [-ComputerName <String>] [-Name] <String> [-Note <String>] -WorldWideNodeName <String[]>
 -WorldWidePortName <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-VMSan** cmdlet creates a new virtual storage area network (SAN) on a Hyper-V host.

## EXAMPLES

### Example 1
```
PS C:\>New-VMSan -Name Production -Note "Production SAN" -WorldWideNodeName C003FF0000FFFF00 -WorldWidePortName C003FF5778E50002
```

Creates a new virtual storage area network (SAN) with the specified Name, Note, WorldWideNodeName, and WorldWidePortName.

## PARAMETERS

### -ComputerName
Specifies the friendly name of a Hyper-V host on which the new virtual storage area network (SAN) is to be created.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
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

### -HostBusAdapter
Specifies the host bus adapter (HBA) to be associated with the virtual storage area network (SAN) to be created.
This can be retrieved by running the Get-InitiatorPort cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: HbaObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of the virtual storage area network (SAN) to be created.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SanName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Note
Specifies a note to be associated with the virtual storage area network (SAN) to be created.

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

### -WorldWideNodeName
Specifies the world wide node name (WWNN) of the host bus adapters to be associated with the virtual storage area network (SAN) to be created.

```yaml
Type: String[]
Parameter Sets: StringWwn
Aliases: Wwnn, NodeName, Wwnns, NodeNames, WorldWideNodeNames, NodeAddress

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortName
Specifies the world wide port name (WWPN) of the host bus adapters to be associated with the virtual storage area network (SAN) to be created.

```yaml
Type: String[]
Parameter Sets: StringWwn
Aliases: Wwpn, PortName, Wwpns, PortNames, WorldWidePortNames, PortAddress

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMSan

## NOTES

## RELATED LINKS

