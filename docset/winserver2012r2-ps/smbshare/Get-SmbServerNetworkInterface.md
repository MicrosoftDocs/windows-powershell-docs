---
external help file: SmbServerNetworkInterface.cdxml-help.xml
Module Name: SmbShare
online version: 
schema: 2.0.0
title: Get-SmbServerNetworkInterface
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: D0052C35-1789-4FF7-A349-AE9D98A13946
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-SmbServerNetworkInterface

## SYNOPSIS
Retrieves the network interfaces used by the Server Message Block (SMB) server.

## SYNTAX

```
Get-SmbServerNetworkInterface [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmbServerNetworkInterface** cmdlet retrieves the network interfaces used by the Server Message Block (SMB) server.

## EXAMPLES

### Example 1: Get network interfaces
```
PS C:\>Get-SmbServerNetworkInterface
Scope Name          Interface Index     RSS Capable         RDMA Capable        Speed               IpAddress 
----------          ---------------     -----------         ------------        -----               --------- 
Contoso-FS          14                  False               False               1 Gbps              192.168.100.22 
Contoso-FS          12                  True                True                32 Gbps             192.168.101.22 
Contoso-FS          15                  True                True                32 Gbps             192.168.102.22 
*                   15                  True                True                32 Gbps             192.168.102.22 
*                   15                  True                True                32 Gbps             192.168.102.11 
*                   14                  False               False               1 Gbps              192.168.100.22 
*                   14                  False               False               1 Gbps              192.168.100.11 
*                   13                  False               False               1 Gbps              172.30.182.8 
*                   12                  True                True                32 Gbps             192.168.101.22 
*                   12                  True                True                32 Gbps             192.168.101.11 
Contoso-SO          15                  True                True                32 Gbps             192.168.102.11 
Contoso-SO          14                  False               False               1 Gbps              192.168.100.11 
Contoso-SO          12                  True                True                32 Gbps             192.168.101.11 
FE80::C8C0:F65D:... 13                  False               False               1 Gbps              172.30.182.8
```

This command retrieves the network interfaces that are used by the SMB server.

### Example 2: Get network interfaces that match a property
```
PS C:\>Get-SmbServerNetworkInterface | Where-Object -Property LinkSpeed -Gt 10GB
Scope Name          Interface Index     RSS Capable         RDMA Capable        Speed               IpAddress 
----------          ---------------     -----------         ------------        -----               --------- 
Contoso-FS          12                  True                True                32 Gbps             192.168.101.22 
Contoso-FS          15                  True                True                32 Gbps             192.168.102.22 
*                   15                  True                True                32 Gbps             192.168.102.22 
*                   15                  True                True                32 Gbps             192.168.102.11 
*                   12                  True                True                32 Gbps             192.168.101.22 
*                   12                  True                True                32 Gbps             192.168.101.11 
Contoso-SO          15                  True                True                32 Gbps             192.168.102.11 
Contoso-SO          12                  True                True                32 Gbps             192.168.101.11
```

This command retrieves the network interfaces that are used by the SMB server that have the link speed of 10 gigabits or faster.

### Example 3: Get network interfaces for a specific server
```
PS C:\>Get-SmbServerNetworkInterface | Where-Object -Property ScopeName -Eq Contoso-FS
Scope Name          Interface Index     RSS Capable         RDMA Capable        Speed               IpAddress 
----------          ---------------     -----------         ------------        -----               --------- 
Contoso-FS          14                  False               False               1 Gbps              192.168.100.22 
Contoso-FS          12                  True                True                32 Gbps             192.168.101.22 
Contoso-FS          15                  True                True                32 Gbps             192.168.102.22
```

This command retrieves the network interfaces that are used by the SMB server named Contoso-FS.

### Example 4: Get properties of network interfaces of an SMB server
```
PS C:\>Get-SmbServerNetworkInterface | Where-Object -Property ScopeName -Eq Contoso-FS | Select-Object -Property *
FriendlyName          : Internal 
InterfaceIndex        : 14 
IpAddress             : 192.168.100.22 
LinkSpeed             : 1000000000 
RdmaCapable           : False 
RssCapable            : False 
ScopeName             : Contoso-FS 
PSComputerName        : 
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbServerNetworkInterface 
CimInstanceProperties : {FriendlyName, InterfaceIndex, IpAddress, LinkSpeed...} 
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties 

FriendlyName          : RDMA1 
InterfaceIndex        : 12 
IpAddress             : 192.168.101.22 
LinkSpeed             : 32000000000 
RdmaCapable           : True 
RssCapable            : True 
ScopeName             : Contoso-FS 
PSComputerName        : 
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbServerNetworkInterface 
CimInstanceProperties : {FriendlyName, InterfaceIndex, IpAddress, LinkSpeed...} 
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties 

FriendlyName          : RDMA2 
InterfaceIndex        : 15 
IpAddress             : 192.168.102.22 
LinkSpeed             : 32000000000 
RdmaCapable           : True 
RssCapable            : True 
ScopeName             : Contoso-FS 
PSComputerName        : 
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbServerNetworkInterface 
CimInstanceProperties : {FriendlyName, InterfaceIndex, IpAddress, LinkSpeed...} 
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command retrieves all properties of the network interfaces that are used by the SMB server named Contoso-FS.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbServerNetworkInterface
The MSFT_SmbServerNetworkInterface object represents the network interfaces of the SMB server.

## NOTES

## RELATED LINKS

[Get-SmbClientNetworkInterface](/.Get-SmbClientNetworkInterface.md)

