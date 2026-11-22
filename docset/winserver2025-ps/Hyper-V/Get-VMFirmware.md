---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmfirmware?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMFirmware
---

# Get-VMFirmware

## SYNOPSIS
Gets the firmware configuration of a virtual machine.

## SYNTAX

### VMName (Default)
```
Get-VMFirmware [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [<CommonParameters>]
```

### VMObject
```
Get-VMFirmware [-VM] <VirtualMachine[]> [<CommonParameters>]
```

### VMSnapshot
```
Get-VMFirmware [-VMSnapshot] <VMSnapshot> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMFirmware** cmdlet gets the firmware configuration of a virtual machine.
Note: This cmdlet is supported only on Generation 2 virtual machines.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMFirmware "Test VM"
```

This example returns a virtual machine firmware object for the virtual machine "Test VM".

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of Hyper-V hosts.
The cmdlet gets the virtual machine firmware from the hosts you specify.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies an array of virtual machine objects.
The cmdlet gets the firmware configuration for the virtual machines you specify.
To obtain a virtual machine object, use the **Get-VM** cmdlet.

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
Specifies an array of names of virtual machines.
The cmdlet gets the firmware configuration for the virtual machines you specify.

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

### -VMSnapshot
Specifies the virtual machine snapshot to be used with the VM when retrieving the firmware configuration.

```yaml
Type: VMSnapshot
Parameter Sets: VMSnapshot
Aliases: VMCheckpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMFirmware

## NOTES
* Note: This cmdlet is supported only on Generation 2 virtual machines.

## RELATED LINKS

[Set-VMFirmware](./Set-VMFirmware.md)

