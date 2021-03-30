---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Get-VMNetworkAdapterPortId-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-VMNetworkAdapterPortId
ms.reviewer:
ms.assetid: 1FF810CC-CC66-405E-94CA-E3865275B478
---

# Get-VMNetworkAdapterPortId

## SYNOPSIS
Gets the VFP/VSwitch port ID.

## SYNTAX

```
Get-VMNetworkAdapterPortId [[-VMName] <String>] [[-VMNetworkAdapterName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMNetworkAdapterPortId** cmdlet gets the VFP/VSwitch port ID for a virtual machine or infrastructure port.
This cmdlet also returns the friendly name of the virtual switch to which the port is attached and the port name.

## EXAMPLES

### Example 1: Get the port ID for a virtual machine network adapter
```
PS C:\> ($switchName, $portId, $portName) = Get-VMNetworkAdapterPortId -VMName "vm1" -VMNetworkAdapterName "VMAdapter"
```

### Example 2: Get the port ID for an infrastructure port
```
PS C:\> ($switchName, $portId, $portName) = Get-VMNetworkAdapterPortId -VMNetworkAdapterName "HostAdapter"
```

This command gets the port ID for an infrastructure port, and then saves it to the specified variables.

## PARAMETERS

### -VMName
Specifies the name of the virtual machine for which to retrieve the port ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkAdapterName
Specifies the name of the virtual machine network adapter for which to retrieve the port ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

