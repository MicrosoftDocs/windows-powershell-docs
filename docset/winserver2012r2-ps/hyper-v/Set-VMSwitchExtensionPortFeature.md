---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/set-vmswitchextensionportfeature?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMSwitchExtensionPortFeature
---

# Set-VMSwitchExtensionPortFeature

## SYNOPSIS
Configures a feature on a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Set-VMSwitchExtensionPortFeature -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]>
 [-ComputerName <String[]>] [-Passthru] [-VMNetworkAdapterName <String>] [-VMName] <String[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ExternalPort
```
Set-VMSwitchExtensionPortFeature -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]>
 [-ComputerName <String[]>] [-ExternalPort] [-SwitchName] <String> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ManagementOS
```
Set-VMSwitchExtensionPortFeature -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]>
 [-ComputerName <String[]>] [-Passthru] [-ManagementOS] [-VMNetworkAdapterName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ResourceObject
```
Set-VMSwitchExtensionPortFeature -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Passthru]
 [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Set-VMSwitchExtensionPortFeature -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Passthru]
 [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMSwitchExtensionPortFeature** cmdlet configures a feature on a virtual network adapter.
The feature must have been configured previously on the virtual network adapter.

## EXAMPLES

### Example 1
```
PS C:\>$ModifiedFeature = Get-VMSwitchExtensionPortFeature -VMName VM2 -FeatureName "Ethernet Switch Port Security Settings"
PS C:\>$ModifiedFeature.SettingData.EnableDhcpGuard = $false
PS C:\>Set-VMSwitchExtensionPortFeature -VMName VM2 -VMSwitchExtensionFeature $ModifiedFeature
```

Configures the feature on a virtual network adapter(s) on virtual machine VM2.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a feature on a virtual network adapter is to be configured.
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

### -ManagementOS
Specifies the management (e.g.
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
Specifies that a **Microsoft.HyperV.PowerShell.VMSwitchExtensionPortFeature** object is to be passed through to the pipeline representing the feature to be configured.

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
Specifies the virtual machine on which the feature is to be configured.

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
Specifies the name of the virtual machine on which the feature is to be configured.

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
Specifies the virtual network adapter.

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
Specifies the name of the virtual network adapter.

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
Specifies the feature to be configured.

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

