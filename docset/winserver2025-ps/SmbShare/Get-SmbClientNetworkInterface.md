---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbClientNetworkInterface.cdxml-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/get-smbclientnetworkinterface?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmbClientNetworkInterface
---

# Get-SmbClientNetworkInterface

## SYNOPSIS
Retrieves the network interfaces used by the SMB client.

## SYNTAX

```
Get-SmbClientNetworkInterface [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmbClientNetworkInterface** cmdlet retrieves the network interfaces used by the Server Message Block (SMB) client.

## EXAMPLES

### Example 1: Get network interfaces used by an SMB client
```
PS C:\>Get-SmbClientNetworkInterface
Interface Index     RSS Capable         RDMA Capable        Speed               IpAddresses         Friendly Name
---------------     -----------         ------------        -----               -----------         -------------
12                  True                True                32 Gbps             {192.168.101.13}    RDMA1
15                  True                True                32 Gbps             {192.168.102.13}    RDMA2
17                  False               False               0  bps              {fe80::5efe:192.... isatap.{EF722F0D...
18                  False               False               0  bps              {fe80::5efe:192.... isatap.{BD3C4A04...
19                  False               False               0  bps              {fe80::5efe:192.... isatap.{597B0A73...
20                  False               False               0  bps              {fe80::6065:ddbf... Local Area Conne...
32                  False               False               10 Gbps             {172.30.182.10}     ExternalVirtual
16                  False               False               3  Gbps             {2001:4898:0:fff... isatap.corp.cont...
14                  False               False               1  Gbps             {192.168.100.13}    Internal
```

This command retrieves the network interfaces used by the SMB client.

### Example 2: Get network interfaces used by an SMB client for a specified link speed
```
PS C:\>Get-SmbClientNetworkInterface | Where-Object -Property LinkSpeed -Gt 10GB
Interface Index     RSS Capable         RDMA Capable        Speed               IpAddresses         Friendly Name
---------------     -----------         ------------        -----               -----------         -------------
12                  True                True                32 Gbps             {192.168.101.13}    RDMA1
15                  True                True                32 Gbps             {192.168.102.13}    RDMA2
```

This command retrieves the network interfaces used by the SMB client that match the link speed of 10 gigabits or more.

### Example 3: Display details for network interfaces
```
PS C:\>Get-SmbClientNetworkInterface | Where-Object -Property LinkSpeed -Gt 10GB | Select-Object -Property *
FriendlyName          : RDMA1
InterfaceIndex        : 12
IpAddresses           : {192.168.101.13}
LinkSpeed             : 32000000000
RdmaCapable           : True
RssCapable            : True
PSComputerName        :
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbClientNetworkInterface
CimInstanceProperties : {FriendlyName, InterfaceIndex, IpAddresses, LinkSpeed...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties

FriendlyName          : RDMA2
InterfaceIndex        : 15
IpAddresses           : {192.168.102.13}
LinkSpeed             : 32000000000
RdmaCapable           : True
RssCapable            : True
PSComputerName        :
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbClientNetworkInterface
CimInstanceProperties : {FriendlyName, InterfaceIndex, IpAddresses, LinkSpeed...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command displays all of the information retrieved from the network interfaces used by the SMB client that match the link speed of 10 gigabits or more.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbClientNetworkInterface
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
This cmdlet returns a **MSFT_SmbClientNetworkInterface** object that represents the network interfaces used by the SMB client.

## NOTES

## RELATED LINKS

[Get-SmbServerNetworkInterface](./Get-SmbServerNetworkInterface.md)

