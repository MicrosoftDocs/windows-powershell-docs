---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmfibrechannelhba?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMFibreChannelHba
---

# Set-VMFibreChannelHba

## SYNOPSIS
Configures a Fibre Channel host bus adapter on a virtual machine.

## SYNTAX

### VMName And Only SAN (Default)
```
Set-VMFibreChannelHba [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String> [-WorldWideNodeNameSetA] <String> [-WorldWidePortNameSetA] <String>
 [-WorldWideNodeNameSetB] <String> [-WorldWidePortNameSetB] <String> -SanName <String> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMName And Generate WWN
```
Set-VMFibreChannelHba [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String> [-WorldWideNodeNameSetA] <String> [-WorldWidePortNameSetA] <String>
 [-WorldWideNodeNameSetB] <String> [-WorldWidePortNameSetB] <String> [-GenerateWwn] [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMName And Manual WWN
```
Set-VMFibreChannelHba [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String> [-WorldWideNodeNameSetA] <String> [-WorldWidePortNameSetA] <String>
 [-WorldWideNodeNameSetB] <String> [-WorldWidePortNameSetB] <String> [-NewWorldWideNodeNameSetA <String>]
 [-NewWorldWidePortNameSetA <String>] [-NewWorldWideNodeNameSetB <String>] [-NewWorldWidePortNameSetB <String>]
 [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object And Generate WWN
```
Set-VMFibreChannelHba [-VMFibreChannelHba] <VMFibreChannelHba> [-GenerateWwn] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Object And Manual WWN
```
Set-VMFibreChannelHba [-VMFibreChannelHba] <VMFibreChannelHba> [-NewWorldWideNodeNameSetA <String>]
 [-NewWorldWidePortNameSetA <String>] [-NewWorldWideNodeNameSetB <String>] [-NewWorldWidePortNameSetB <String>]
 [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object And Only SAN
```
Set-VMFibreChannelHba [-VMFibreChannelHba] <VMFibreChannelHba> -SanName <String> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMFibreChannelHba** cmdlet configures a Fibre Channel host bus adapter on a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMFibreChannelHba -VMName MyVM | Set-VMFibreChannelHba -GenerateWwn
```

Configures a Fibre Channel host bus adapter on a virtual machine named MyVM, with World Wide Names to be generated automatically.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName And Only SAN, VMName And Generate WWN, VMName And Manual WWN
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which a Fibre Channel host bus adapter is to be configured.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName And Only SAN, VMName And Generate WWN, VMName And Manual WWN
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
Parameter Sets: VMName And Only SAN, VMName And Generate WWN, VMName And Manual WWN
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GenerateWwn
Specifies that the World Wide Names for sets A and B are to be generated automatically.
When this parameter is specified, parameters **WorldWideNodeNameSetA**, **WorldWideNodeNameSetB**, **WorldWidePortNameSetA**, and **WorldWidePortNameSetB** cannot be used.

```yaml
Type: SwitchParameter
Parameter Sets: VMName And Generate WWN, Object And Generate WWN
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewWorldWideNodeNameSetA
Specifies the World Wide Node name of address set A to be associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: VMName And Manual WWN, Object And Manual WWN
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewWorldWideNodeNameSetB
Specifies the World Wide Node name of address set B to be associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: VMName And Manual WWN, Object And Manual WWN
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewWorldWidePortNameSetA
Specifies the World Wide Port name of address set A to be associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: VMName And Manual WWN, Object And Manual WWN
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewWorldWidePortNameSetB
Specifies the World Wide Port name of address set B to be associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: VMName And Manual WWN, Object And Manual WWN
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the configured Fibre Channel host bus adapter.

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

### -SanName
Specifies the name of the virtual storage area network (SAN) to be associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: VMName And Only SAN, Object And Only SAN
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMFibreChannelHba
Specifies the Fibre Channel host bus adapter to be configured.

```yaml
Type: VMFibreChannelHba
Parameter Sets: Object And Generate WWN, Object And Manual WWN, Object And Only SAN
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine to which the virtual Fibre Channel host bus adapter parameters are to be set.

```yaml
Type: String
Parameter Sets: VMName And Only SAN, VMName And Generate WWN, VMName And Manual WWN
Aliases:

Required: True
Position: 0
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

### -WorldWideNodeNameSetA
Specifies the World Wide Node name of address set A that is associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: VMName And Only SAN, VMName And Generate WWN, VMName And Manual WWN
Aliases: Wwnn1

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWideNodeNameSetB
Specifies the World Wide Node name of address set B that is associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: VMName And Only SAN, VMName And Generate WWN, VMName And Manual WWN
Aliases: Wwnn2

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortNameSetA
Specifies the World Wide Port name of address set A that is associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: VMName And Only SAN, VMName And Generate WWN, VMName And Manual WWN
Aliases: Wwpn1

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortNameSetB
Specifies the World Wide Port name of address set B that is associated with the Fibre Channel host bus adapter.

```yaml
Type: String
Parameter Sets: VMName And Only SAN, VMName And Generate WWN, VMName And Manual WWN
Aliases: Wwpn2

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMFibreChannelHba

## NOTES

## RELATED LINKS

