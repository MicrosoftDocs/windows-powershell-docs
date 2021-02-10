---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMSwitchExtensionPortFeature
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 8F459438-9A97-4AD0-B88F-CE84369B004C
---

# Get-VMSwitchExtensionPortFeature

## SYNOPSIS
Gets the features configured on a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Get-VMSwitchExtensionPortFeature [-FeatureName <String[]>] [-FeatureId <Guid[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-ComputerName <String[]>] [-Passthru]
 [-VMNetworkAdapterName <String>] [-VMName] <String[]> [<CommonParameters>]
```

### ExternalPort
```
Get-VMSwitchExtensionPortFeature [-FeatureName <String[]>] [-FeatureId <Guid[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-ComputerName <String[]>] [-ExternalPort]
 [-SwitchName] <String> [-Passthru] [<CommonParameters>]
```

### ManagementOS
```
Get-VMSwitchExtensionPortFeature [-FeatureName <String[]>] [-FeatureId <Guid[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-ComputerName <String[]>] [-Passthru]
 [-ManagementOS] [-VMNetworkAdapterName <String>] [<CommonParameters>]
```

### ResourceObject
```
Get-VMSwitchExtensionPortFeature [-FeatureName <String[]>] [-FeatureId <Guid[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-Passthru]
 [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [<CommonParameters>]
```

### VMObject
```
Get-VMSwitchExtensionPortFeature [-FeatureName <String[]>] [-FeatureId <Guid[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-Passthru] [-VMNetworkAdapterName <String>]
 [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMSwitchExtensionPortFeature** cmdlet gets the features configured on a virtual network adapter.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSwitchExtensionPortFeature -VMName VM2 -FeatureName "Ethernet Switch Port Security Settings"
```

Gets the feature configured on virtual machine VM2 by name Ethernet Switch Port Security Settings.

## PARAMETERS

### -ComputerName
Specifies one or more virtual machine hosts on which the features configured on a virtual network adapter are to be retrieved.
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
Specifies the virtual switch extension.

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
Specifies the name of the virtual switch extension.

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
Specifies that the features are to be retrieved from the management (i.e.
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
Specifies that an object is to be passed through to the pipeline representing the features configured on a virtual switch.

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
Specifies the virtual machine on which the features configured on a virtual switch are to be retrieved.

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
Specifies the name of the virtual machine on which the features configured on a virtual switch are to be retrieved.

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
Specifies the network adapter.

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
Specifies the name of the network adapter.

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

