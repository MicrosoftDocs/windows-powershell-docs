---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Connect-VMNetworkAdapter
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 5695D079-D582-4CF5-9821-0E7AFE5ACFA1
---

# Connect-VMNetworkAdapter

## SYNOPSIS
Connects a virtual network adapter to a virtual switch.

## SYNTAX

### Name_SwitchName (Default)
```
Connect-VMNetworkAdapter [-VMName] <String[]> [-ComputerName <String[]>] [[-Name] <String[]>]
 [-SwitchName] <String> [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Name_SwitchObject
```
Connect-VMNetworkAdapter [-VMName] <String[]> [[-Name] <String[]>] [-VMSwitch] <VMSwitch> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Name_UseAutomaticConnection
```
Connect-VMNetworkAdapter [-VMName] <String[]> [-ComputerName <String[]>] [[-Name] <String[]>]
 [-UseAutomaticConnection] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object_UseAutomaticConnection
```
Connect-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapter[]> [-UseAutomaticConnection] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object_SwitchObject
```
Connect-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapter[]> [-VMSwitch] <VMSwitch> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Object_SwitchName
```
Connect-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapter[]> [-SwitchName] <String> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Connect-VMNetworkAdapter** cmdlet connects a virtual network adapter to a virtual switch.

## EXAMPLES

### Example 1
```
PS C:\>Connect-VMNetworkAdapter -VMName Test1,Test2 -Name Internet -SwitchName InternetAccess
```

Connects a virtual network adapter named Internet in virtual machines Test1 and Test2 to a virtual switch InternetAccess.

### Example 2
```
PS C:\>Get-VMNetworkAdapter -VMName Test1 | Connect-VMNetworkAdapter -SwitchName InternetAccess
```

Connects a virtual network adapter in virtual machine Test1 to virtual switch InternetAccess.

### Example 3
```
PS C:\>Get-VMSwitch InternetAccess | Connect-VMNetworkAdapter -VMName Test1
```

Connects a virtual network adapter in virtual machine Test1 to switch InternetAccess.

## PARAMETERS

### -ComputerName
Specifies one or more virtual machine hosts on which the virtual network adapter is to be connected.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Name_SwitchName, Name_UseAutomaticConnection
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

### -Name
Specifies the name of the virtual network adapter to be connected.

```yaml
Type: String[]
Parameter Sets: Name_SwitchName, Name_SwitchObject, Name_UseAutomaticConnection
Aliases: VMNetworkAdapterName

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.VMNetworkAdapter** object is to be passed through to the pipeline representing the virtual network adapter to be connected.

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

### -SwitchName
Specifies the name of the virtual switch to which the virtual network adapter is to be connected.

```yaml
Type: String
Parameter Sets: Name_SwitchName, Object_SwitchName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseAutomaticConnection
Specifies that the network adapter is to be connected to any virtual switch in the resource pool, rather than to a specific virtual switch.

```yaml
Type: SwitchParameter
Parameter Sets: Name_UseAutomaticConnection, Object_UseAutomaticConnection
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine in which the network adapter is to be connected.

```yaml
Type: String[]
Parameter Sets: Name_SwitchName, Name_SwitchObject, Name_UseAutomaticConnection
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual network adapter to be connected.

```yaml
Type: VMNetworkAdapter[]
Parameter Sets: Object_UseAutomaticConnection, Object_SwitchObject, Object_SwitchName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSwitch
Specifies the virtual switch to which the virtual network adapter is to be connected.

```yaml
Type: VMSwitch
Parameter Sets: Name_SwitchObject, Object_SwitchObject
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
None by default; **Microsoft.HyperV.PowerShell.VMNetworkAdapter** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

