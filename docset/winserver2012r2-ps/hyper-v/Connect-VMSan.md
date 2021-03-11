---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Connect-VMSan
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: DA01E844-1462-4284-B2BA-CC9BCB9E0990
---

# Connect-VMSan

## SYNOPSIS
Associates a host bus adapter with a virtual storage area network (SAN).

## SYNTAX

### StringWwn (Default)
```
Connect-VMSan [-ComputerName <String[]>] [-Name] <String> -WorldWideNodeName <String[]>
 -WorldWidePortName <String[]> [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HbaObject
```
Connect-VMSan [-Name] <String> -HostBusAdapter <CimInstance[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Connect-VMSan** cmdlet associates a host bus adapter with a virtual storage area network (SAN).

## EXAMPLES

### Example 1
```
PS C:\>Connect-VMSan -Name Production -WorldWideNodeName C003FF0000FFFF00 -WorldWidePortName C003FF5778E50002
```

Associates the virtual storage area network (SAN) named Production with the host bus adapter having the specified world wide node name and world wide port name.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts where the host bus adapter is to be associated with the virtual storage area network (SAN).
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: StringWwn
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
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
Specifies the host bus adapter to be associated with the virtual storage area network (SAN).

```yaml
Type: CimInstance[]
Parameter Sets: HbaObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual storage area network (SAN) with which the host bus adapter is to be associated.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SanName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.Powershell.VMSan** object is to be passed through to the pipeline representing the virtual storage area network (SAN) to be associated with the host bus adapter.

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
Specifies the world wide node name of the host bus adapter to be associated with the virtual storage area network (SAN).

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
The port world wide name of the host bus adapter to be associated with the virtual storage area network (SAN).

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

###  
None by default; **Microsoft.HyperV.Powershell.VMSan** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

