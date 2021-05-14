---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hyper-v/restart-vm?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-VM
---

# Restart-VM

## SYNOPSIS
Restarts a virtual machine.

## SYNTAX

### Name (Default)
```
Restart-VM [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String[]> [-Force] [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameWait
```
Restart-VM [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String[]> [-Force] [-AsJob] [-Passthru] [-Wait] [-For <WaitVMTypes>] [-Delay <UInt16>]
 [-Timeout <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Restart-VM [-VM] <VirtualMachine[]> [-Force] [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObjectWait
```
Restart-VM [-VM] <VirtualMachine[]> [-Force] [-AsJob] [-Passthru] [-Wait] [-For <WaitVMTypes>]
 [-Delay <UInt16>] [-Timeout <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Restart-VM** cmdlet restarts a virtual machine.
Running this cmdlet results in a "hard" restart, like powering the computer down, then back up again.
This can result in data loss in the virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Restart-VM Win7
Confirm
Are you sure you want to restart virtual machine "win7"?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
```

Performs a hard restart of virtual machine Win7.
This is equivalent to turning off the power to the virtual machine and then restarting it.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: Name, NameWait
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual machine is to be restarted.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Name, NameWait
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
Parameter Sets: Name, NameWait
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Delay


```yaml
Type: UInt16
Parameter Sets: NameWait, VMObjectWait
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -For


```yaml
Type: WaitVMTypes
Parameter Sets: NameWait, VMObjectWait
Aliases: 
Accepted values: Heartbeat, IPAddress

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Specifies that no prompt for confirmation is to appear before the virtual machine is restarted.

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

### -Name
Specifies the name of the virtual machine to be restarted.

```yaml
Type: String[]
Parameter Sets: Name, NameWait
Aliases: VMName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual machine to be restarted.

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

### -Timeout


```yaml
Type: Int32
Parameter Sets: NameWait, VMObjectWait
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine to be restarted.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject, VMObjectWait
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Wait


```yaml
Type: SwitchParameter
Parameter Sets: NameWait, VMObjectWait
Aliases: 

Required: True
Position: Named
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
None by default, **Microsoft.HyperV.Powershell.VirtualMachine** if *PassThru* is specified.

## NOTES

## RELATED LINKS

