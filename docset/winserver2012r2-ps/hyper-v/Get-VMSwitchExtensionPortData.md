---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMSwitchExtensionPortData
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 9D93AEBA-506C-4407-9128-A2DFCB993A2B
---

# Get-VMSwitchExtensionPortData

## SYNOPSIS
Retrieves the status of a virtual switch extension feature applied to a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Get-VMSwitchExtensionPortData [-FeatureName <String[]>] [-FeatureId <Guid[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-ComputerName <String[]>] [-Passthru]
 [-VMNetworkAdapterName <String>] [-VMName] <String[]> [<CommonParameters>]
```

### ExternalPort
```
Get-VMSwitchExtensionPortData [-FeatureName <String[]>] [-FeatureId <Guid[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-ComputerName <String[]>] [-ExternalPort]
 [-SwitchName] <String> [-Passthru] [<CommonParameters>]
```

### ManagementOS
```
Get-VMSwitchExtensionPortData [-FeatureName <String[]>] [-FeatureId <Guid[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-ComputerName <String[]>] [-Passthru]
 [-ManagementOS] [-VMNetworkAdapterName <String>] [<CommonParameters>]
```

### ResourceObject
```
Get-VMSwitchExtensionPortData [-FeatureName <String[]>] [-FeatureId <Guid[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-Passthru]
 [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [<CommonParameters>]
```

### VMObject
```
Get-VMSwitchExtensionPortData [-FeatureName <String[]>] [-FeatureId <Guid[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-Passthru] [-VMNetworkAdapterName <String>]
 [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMSwitchExtensionPortData** cmdlet retrieves the status of a virtual switch extension feature applied to a virtual network adapter.
This port feature data surfaces runtime information and statistics on a per-port basis.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSwitchExtensionPortData VM1 -FeatureId eb29f0f2-f5dc-45c6-81bb-3cd9f219bbbb
```

Gets the port feature data with ID eb29f0f2-f5dc-45c6-81bb-3cd9f219bbbb from the sample forwarding extension on the virtual network adapter in virtual machine VM1.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the status of a virtual switch extension applied to a virtual network adapter is to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, ExternalPort, ManagementOS
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Extension
Specifies the virtual switch extension for which status is to be retrieved.

```yaml
Type: VMSwitchExtension[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtensionName
Specifies the name of the virtual switch extension for which status is to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalPort
Specifies the virtual switch port connected to the external network interface card.

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

### -FeatureId
Specifies the unique identifier of the feature supported by the virtual switch extension.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FeatureName
Specifies the name of the feature supported by the virtual switch extension.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies that the status is to be retrieved from the management (i.e.
parent, or host) operating system.

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
Specifies that an object is to be passed through to the pipeline representing the status to be retrieved.

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
Specifies the name of the virtual switch.

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
Specifies an array of virtual machine objects.
The cmdlet gets the status of the virtual switch extension for the virtual machines that you specify.
To obtain a virtual machine object, use the Get-VM cmdlet.

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
Specifies the name of the virtual machine.

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
Specifies the virtual machine network adapter.

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
Specifies the name of the virtual machine network adapter.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

