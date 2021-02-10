---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Set-VMSan
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 78CAC821-04DF-474B-902B-050593D99279
---

# Set-VMSan

## SYNOPSIS
Configures a virtual storage area network (SAN) on one or more Hyper-V hosts.

## SYNTAX

### HbaObject (Default)
```
Set-VMSan [-Name] <String> [-HostBusAdapter <CimInstance[]>] [-Note <String>] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### StringWwn
```
Set-VMSan [-ComputerName <String[]>] [-Name] <String> -WorldWideNodeName <String[]>
 -WorldWidePortName <String[]> [-Note <String>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMSan** cmdlet configures a virtual storage area network (SAN) on one or more Hyper-V hosts.

## EXAMPLES

### Example 1
```
PS C:\>Set-VMSan -Name Production -WorldWideNodeName C003FF0000FFFF22 -WorldWidePortName C003FF5778E50024
```

Configures a virtual storage area network (SAN) named Production with the specified WorldWideNodeName and WorldWidePortName values.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual storage area network (SAN) is to be configured.
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostBusAdapter
Specifies the Fibre Channel host bus adapter to be associated with the virtual storage area network (SAN).

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
Specifies the name of the virtual storage area network (SAN) to be configured.

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

### -Note
Specifies the note to be associated with the virtual storage area network (SAN).

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

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the configured virtual storage area network (SAN).

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
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWideNodeName
The World Wide Node name of the Fibre Channel host bus adapter to be associated with this virtual storage area network (SAN).

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
The World Wide Port name of the Fibre Channel host bus adapter to be associated with this virtual storage area network (SAN).

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
None by default; **Microsoft.HyperV.PowerShell.SAN** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

