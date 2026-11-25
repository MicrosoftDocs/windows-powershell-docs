---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/add-vmswitchextensionportfeature?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VMSwitchExtensionPortFeature
---

# Add-VMSwitchExtensionPortFeature

## SYNOPSIS
Adds a feature to a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Add-VMSwitchExtensionPortFeature [-VMName] <String[]> [-VMNetworkAdapterName <String>]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ResourceObject
```
Add-VMSwitchExtensionPortFeature [-VMNetworkAdapter] <VMNetworkAdapterBase[]>
 -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ManagementOS
```
Add-VMSwitchExtensionPortFeature [-ManagementOS] [-VMNetworkAdapterName <String>] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ExternalPort
```
Add-VMSwitchExtensionPortFeature [-ExternalPort] [-SwitchName <String>] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Add-VMSwitchExtensionPortFeature [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]>
 -VMSwitchExtensionFeature <VMSwitchExtensionPortFeature[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-VMSwitchExtensionPortFeature** cmdlet adds a feature supported by a virtual switch extension to a virtual machine network adapter.
This cmdlet also configures built-in virtual switch features.

## EXAMPLES

### Example 1
```
PS C:\> $feature = Get-VMSystemSwitchExtensionPortFeature -FeatureName "Ethernet Switch Port Security Settings"
PS C:\> $feature.SettingData.EnableDhcpGuard = $true
PS C:\> $feature.SettingData.EnableRouterGuard = $true
PS C:\> Add-VMSwitchExtensionPortFeature -VMName VM2 -VMSwitchExtensionFeature $feature
```

Adds a feature to virtual machine VM2.
The feature here is a port security feature supported by the extension Microsoft Virtual Ethernet Switch Native Extension.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName, ManagementOS, ExternalPort
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which a feature is to be added to a virtual network adapter.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, ManagementOS, ExternalPort
Aliases:

Required: False
Position: Named
Default value: None
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

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName, ManagementOS, ExternalPort
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalPort
Specifies the virtual switch port connected to the external network adapter.

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
Specifies that the feature is to be added in the management (i.e.
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
Specifies that an object is to be passed through to the pipeline representing the feature to be added.

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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine in which the feature is to be added.

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
Specifies the name of the virtual machine in which the feature is to be added.

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
Specifies the virtual machine network adapter for which the feature is to be added.

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
Specifies the name of the virtual machine network adapter for which the feature is to be added.

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
Specifies the feature to be added to the virtual switch.
You can get such a feature object from Get-VMSystemSwitchExtensionPortFeature to add a new configuration to a virtual network adapter, or from the **Get-VMSwitchExtensionPortFeature** cmdlet to update an existing configuration.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.VMSwitchExtensionPortFeature
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

