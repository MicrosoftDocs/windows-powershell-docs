---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmresourcepool?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMResourcePool
---

# Get-VMResourcePool

## SYNOPSIS
Gets the resource pools on one or more virtual machine hosts.

## SYNTAX

```
Get-VMResourcePool [[-Name] <String[]>] [[-ResourcePoolType] <VMResourcePoolType[]>]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMResourcePool** cmdlet gets the resource pools on one or more virtual machine hosts.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMResourcePool * VHD
```

Get all VHD resource pools on the local virtual machine host.

### Example 2
```
PS C:\> Get-VMResourcePool Test*
```

Get all resource pools on the local virtual machine host having a name that starts with Test.

### Example 3
```
PS C:\> Get-VMResourcePool "test resource pool" VHD
```

Get all VHD resource pools on the local virtual machine host named test resource pool.

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
Specifies one or more Hyper-V hosts on which the resource pools are to be retrieved.
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

### -Name
Specifies the name of the resource pool or pools to be retrieved.
Wildcards are allowed.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourcePoolType
Specifies the type of the resource pool or pools to be retrieved.

```yaml
Type: VMResourcePoolType[]
Parameter Sets: (All)
Aliases:
Accepted values: Memory, Processor, Ethernet, VHD, ISO, VFD, FibreChannelPort, FibreChannelConnection, PciExpress

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMResourcePool

## NOTES

## RELATED LINKS

