---
author: Kateyanne
external help file: NetTCPIP_Cmdlets.xml
manager: dansimp
Module Name: NetTCPIP
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/nettcpip/get-netudpendpoint?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetUDPEndpoint

## SYNOPSIS
Gets information about current UDP endpoint statistics.

## SYNTAX

```
Get-NetUDPEndpoint [[-LocalAddress] <String[]>] [[-LocalPort] <UInt16[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetUDPEndpoint** cmdlet gets information about current UDP end point statistics.
This includes UDP end point properties such as local and remote UDP ports.
Used without parameters, it gets information about all UDP end points.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetUDPEndpoint
```

This example gets information about current UDP endpoint statistics.
Used without parameters, it gets information about all UDP endpoints.

### EXAMPLE 2
```
PS C:\>Get-NetUDPEndpoint -LocalAddress 127.0.0.1
```

This example gets information about recent UDP traffic that was sent and received on the IPv4 loopback address.

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalAddress
Gets TCP connection information only about connections from a specific local IP address.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalPort
Gets TCP connection information only about connections from a specific local TCP port.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetUDPEndpoint
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetUDPSetting](./Get-NetUDPSetting.md)

