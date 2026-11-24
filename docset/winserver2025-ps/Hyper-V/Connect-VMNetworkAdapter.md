---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/connect-vmnetworkadapter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-VMNetworkAdapter
---

# Connect-VMNetworkAdapter

## SYNOPSIS
Connects a virtual network adapter to a virtual switch.

## SYNTAX

### Name_SwitchName (Default)
```
Connect-VMNetworkAdapter [[-Name] <String[]>] [-SwitchName] <String> [-Passthru] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-VMName] <String[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Object_SwitchName
```
Connect-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapter[]> [-SwitchName] <String> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Object_SwitchObject
```
Connect-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapter[]> [-VMSwitch] <VMSwitch> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Object_UseAutomaticConnection
```
Connect-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapter[]> [-UseAutomaticConnection] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Name_SwitchObject
```
Connect-VMNetworkAdapter [[-Name] <String[]>] [-VMSwitch] <VMSwitch> [-Passthru] [-VMName] <String[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Name_UseAutomaticConnection
```
Connect-VMNetworkAdapter [[-Name] <String[]>] [-UseAutomaticConnection] [-Passthru]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-VMName] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Connect-VMNetworkAdapter** cmdlet connects a virtual network adapter to a virtual switch.

## EXAMPLES

### Example 1
```
PS C:\> Connect-VMNetworkAdapter -VMName Test1,Test2 -Name Internet -SwitchName InternetAccess
```

Connects a virtual network adapter named Internet in virtual machines Test1 and Test2 to a virtual switch InternetAccess.

### Example 2
```
PS C:\> Get-VMNetworkAdapter -VMName Test1 | Connect-VMNetworkAdapter -SwitchName InternetAccess
```

Connects a virtual network adapter in virtual machine Test1 to virtual switch InternetAccess.

### Example 3
```
PS C:\> Get-VMSwitch InternetAccess | Connect-VMNetworkAdapter -VMName Test1
```

Connects a virtual network adapter in virtual machine Test1 to switch InternetAccess.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: Name_SwitchName, Name_UseAutomaticConnection
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more virtual machine hosts on which the virtual network adapter is to be connected.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Name_SwitchName, Name_UseAutomaticConnection
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
Parameter Sets: Name_SwitchName, Name_UseAutomaticConnection
Aliases:

Required: False
Position: Named
Default value: None
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
Parameter Sets: Object_UseAutomaticConnection, Name_UseAutomaticConnection
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
Parameter Sets: Object_SwitchName, Object_SwitchObject, Object_UseAutomaticConnection
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
Parameter Sets: Object_SwitchObject, Name_SwitchObject
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.VMNetworkAdapter
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

