---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Remove-VMSwitchExtensionPortFeature
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
ms.assetid: A3D98FF5-CAC6-4A2A-8962-FF47944D33F1
---

# Remove-VMSwitchExtensionPortFeature

## SYNOPSIS
Removes a feature from a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Remove-VMSwitchExtensionPortFeature -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]>
 [-ComputerName <String[]>] [-Passthru] [-VMNetworkAdapterName <String>] [-VMName] <String[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ExternalPort
```
Remove-VMSwitchExtensionPortFeature -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]>
 [-ComputerName <String[]>] [-ExternalPort] [-SwitchName] <String> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ManagementOS
```
Remove-VMSwitchExtensionPortFeature -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]>
 [-ComputerName <String[]>] [-Passthru] [-ManagementOS] [-VMNetworkAdapterName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ResourceObject
```
Remove-VMSwitchExtensionPortFeature -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Passthru]
 [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Remove-VMSwitchExtensionPortFeature -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Passthru]
 [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMSwitchExtensionPortFeature** removes a feature from a virtual network adapter.
The feature must have already been configured on the virtual network adapter.

## EXAMPLES

### Example 1
```
PS C:\>$feature = Get-VMSwitchExtensionPortFeature -VMName VM2 -FeatureId 776e0ba7-94a1-41c8-8f28-951f524251b5
PS C:\>Remove-VMSwitchExtensionPortFeature VM2 -VMSwitchExtensionFeature $feature
```

Removes a feature configured on the virtual network adapter(s) on a virtual machine.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the feature is to be removed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, ExternalPort, ManagementOS
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

### -ExternalPort
Specifies the external port on the virtual switch that binds to a physical network adapter.

```yaml
Type: SwitchParameter
Parameter Sets: ExternalPort
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies that the feature is to be removed from the management (e.g.
the parent, or host) operating system.

```yaml
Type: SwitchParameter
Parameter Sets: ManagementOS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.VMSwitchExtensionPortFeature** is to be passed through to the pipeline representing the feature to be removed.

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
Specifies the name of the virtual switch from which the feature is to be removed.

```yaml
Type: String
Parameter Sets: ExternalPort
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine from which the feature is to be removed.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine from which the feature is to be removed.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual machine network adapter from which the feature is to be removed.

```yaml
Type: VMNetworkAdapterBase[]
Parameter Sets: ResourceObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapterName
Specifies the name of the virtual network adapter from which the feature is to be removed.

```yaml
Type: String
Parameter Sets: VMName, ManagementOS, VMObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSwitchExtensionFeature
Specifies the feature to be removed.

```yaml
Type: VMSwitchExtensionPortFeature[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
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
None by default; **Microsoft.HyperV.PowerShell.VMSwitchExtensionPortFeature** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

