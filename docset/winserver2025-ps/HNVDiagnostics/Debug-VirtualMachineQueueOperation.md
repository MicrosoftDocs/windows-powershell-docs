---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Debug-VirtualMachineQueueOperation.psm1-help.xml
Module Name: HNVDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hnvdiagnostics/debug-virtualmachinequeueoperation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-VirtualMachineQueueOperation
---

# Debug-VirtualMachineQueueOperation

## SYNOPSIS
Debugs VMQ/VMMQ traffic.

## SYNTAX

```
Debug-VirtualMachineQueueOperation [[-HostName] <String>] [[-MgmtIp] <String>] [[-Creds] <PSCredential>]
 [-VMName] <String> [-VMNetworkAdapterName] <String> [[-SampleCount] <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
The **Debug-VirtualMachineQueueOperation** cmdlet analyzes virtual machine queue (VMQ) and VMMQ traffic.
You can use this cmdlet to identify whether VMQ/VMMQ is degrading throughput or is contributing to high utilization on some cores.

## EXAMPLES

### Example 1: Debug VMMQ on a remote computer
```
PS C:\> $Cred = Get-Credential
PS C:\> Debug-VirtualMachineQueueOperation -HostName "NCHost.corp.com" -MgmtIp "10.123.176.108" -Creds $Cred -VMName "MuxVM" -VMNetworkAdapterName "Ethernet"
```

The first command gets the credentials for the current user, and then stores them in the $Cred variable.

The second command gets debug information for VMMQ on a remote computer.

### Example 2: Debug VMMQ on the local host
```
PS C:\> $Cred = Get-Credential
PS C:\> Debug-VirtualMachineQueueOperation -VMName "MuxVM" -VMNetworkAdapterName "Ethernet" -SampleCount 90
```

The first command gets the credentials for the current user, and then stores them in the $Cred variable.

The second command gets debug information for VMMQ on the local host.

## PARAMETERS

### -Creds
Specifies the credentials to use to connect to a remote host.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName
Specifies the remote host on which to run the diagnostics.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MgmtIp
Specifies the management IP address of the remote host.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SampleCount
Specifies the number of seconds to analyze network traffic.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine to analyze.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkAdapterName
Specifies the name of the virtual machine network adapter to analyze.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

