---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 08/27/2021
online version: https://docs.microsoft.com/powershell/module/hyper-v/set-vmhostpartitionablegpu?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMHostPartitionableGpu
---

# Set-VMHostPartitionableGpu

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### Name (Default)
```
Set-VMHostPartitionableGpu [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-Passthru] [-Name <String>] [-PartitionCount <UInt16>] [<CommonParameters>]
```

### Object
```
Set-VMHostPartitionableGpu [-HostPartitionableGpu] <VMHostPartitionableGpu[]> [-Passthru]
 [-PartitionCount <UInt16>] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
{{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-v hosts. NetBIOS names, IP addresses, and fully qualified domain names
are allowable. The default is the local computer. Use localhost or a dot (.) to specify the local
computer explicitly.

```yaml
Type: String[]
Parameter Sets: Name
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
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostPartitionableGpu
{{ Fill HostPartitionableGpu Description }}

```yaml
Type: VMHostPartitionableGpu[]
Parameter Sets: Object
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
{{ Fill Name Description }}

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionCount
{{ Fill PartitionCount Description }}

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the configured partitionable GPU.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.VMHostPartitionableGpu[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMHostPartitionableGpu

## NOTES

## RELATED LINKS
