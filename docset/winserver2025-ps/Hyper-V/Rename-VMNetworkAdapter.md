---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/rename-vmnetworkadapter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-VMNetworkAdapter
---

# Rename-VMNetworkAdapter

## SYNOPSIS
Renames a virtual network adapter on a virtual machine or on the management operating system.

## SYNTAX

### VMName (Default)
```
Rename-VMNetworkAdapter [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [[-Name] <String>] [-NewName] <String> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ResourceObject
```
Rename-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-NewName] <String> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ManagementOS
```
Rename-VMNetworkAdapter [-ManagementOS] [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [[-Name] <String>] [-NewName] <String> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Rename-VMNetworkAdapter [-VM] <VirtualMachine[]> [[-Name] <String>] [-NewName] <String> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Rename-VMNetworkAdapter** cmdlet renames a virtual network adapter on a virtual machine or on the management operating system.

## EXAMPLES

### Example 1
```
PS C:\> Rename-VMNetworkAdapter -VMName Redmond -NewName CoreNet
```

This example renames all the virtual network adapters of virtual machine Redmond to CoreNet.

### Example 2
```
PS C:\> Rename-VMNetworkAdapter -VMName Kirkland -Name Private -NewName CoreNet
```

This example renames the virtual network adapter Private to CoreNet in virtual machine Kirkland.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName, ManagementOS
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual network adapter is to be renamed.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, ManagementOS
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
Parameter Sets: VMName, ManagementOS
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies that you want to rename a virtual network adapter that belongs to the management operating system.

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

### -Name
Specifies the existing name of the virtual network adapter.

```yaml
Type: String
Parameter Sets: VMName, ManagementOS, VMObject
Aliases: VMNetworkAdapterName

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName
Specifies the new name for the virtual network adapter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual network adapter to be renamed.
This is a **Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter** object, if ManagementOS is specified; otherwise it is a **Microsoft.HyperV.PowerShell.VMNetworkAdapter** object.

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

### -VM
Specifies the virtual machine that has the virtual network adapter you want to rename.

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
Specifies the name of the virtual machine that has the virtual network adapter you want to rename.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual network adapter to be renamed.

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

By default, this cmdlet doesn't return any output.

### Microsoft.HyperV.PowerShell.VMNetworkAdapter

When you use the **PassThru** parameter, this cmdlet returns a **Microsoft.HyperV.PowerShell.VMNetworkAdapter** object.

### Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter

When you use the **PassThru** and **-ManagementOS** parameters, this cmdlet returns a **Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter** object.

## NOTES

## RELATED LINKS

