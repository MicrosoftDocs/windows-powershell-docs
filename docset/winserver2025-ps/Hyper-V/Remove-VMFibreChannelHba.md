---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vmfibrechannelhba?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMFibreChannelHba
---

# Remove-VMFibreChannelHba

## SYNOPSIS
Removes a Fibre Channel host bus adapter from a virtual machine.

## SYNTAX

### VMFibreChannelHba (Default)
```
Remove-VMFibreChannelHba [-VMFibreChannelHba] <VMFibreChannelHba[]> [-Passthru] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMName and WWN
```
Remove-VMFibreChannelHba [-VMName] <String> [-WorldWideNodeNameSetA] <String> [-WorldWidePortNameSetA] <String>
 [-WorldWideNodeNameSetB] <String> [-WorldWidePortNameSetB] <String> [-Passthru] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMFibreChannelHba** cmdlet removes a Fibre Channel host bus adapter from a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMFibreChannelHba -VMName MyVM | Remove-VMFibreChannelHba
```

Removes a Fibre Channel host bus adapter from a virtual machine MyVM.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the Fibre Channel host bus adapter is to be removed.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to be pipeline representing the removed Fibre Channel host bus adapter.

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

### -VMFibreChannelHba
Specifies one or more Fibre Channel host bus adapters to be removed from a virtual machine.

```yaml
Type: VMFibreChannelHba[]
Parameter Sets: VMFibreChannelHba
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the virtual machine from which the Fibre Channel host bus adapters are to be removed.

```yaml
Type: String
Parameter Sets: VMName and WWN
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
Specifies the World Wide Node name of address set A associated with the Fibre Channel host bus adapter to be removed.

```yaml
Type: String
Parameter Sets: VMName and WWN
Aliases: Wwnn1

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWideNodeNameSetB
Specifies the World Wide Node name of address set B associated with the Fibre Channel host bus adapter to be removed.

```yaml
Type: String
Parameter Sets: VMName and WWN
Aliases: Wwnn2

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortNameSetA
Specifies the World Wide Port name of address set A associated with the Fibre Channel host bus adapter to be removed.

```yaml
Type: String
Parameter Sets: VMName and WWN
Aliases: Wwpn1

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorldWidePortNameSetB
Specifies the World Wide Port name of address set B associated with the Fibre Channel host bus adapter to be removed.

```yaml
Type: String
Parameter Sets: VMName and WWN
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

### None
Default

### Microsoft.HyperV.PowerShell.VMFibreChannelHba
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

