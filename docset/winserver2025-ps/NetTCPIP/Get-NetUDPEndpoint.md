---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetUDPEndpoint.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-netudpendpoint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetUDPEndpoint
---

# Get-NetUDPEndpoint

## SYNOPSIS
Gets current UDP endpoint statistics.

## SYNTAX

```
Get-NetUDPEndpoint [[-LocalAddress] <String[]>] [[-LocalPort] <UInt16[]>] [-OwningProcess <UInt32[]>]
 [-CreationTime <DateTime[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetUDPEndpoint** cmdlet gets current statistics for a UDP endpoint.
The cmdlet returns UDP end point properties, such as local and remote UDP ports.
If you do not specify any parameters, the cmdlet gets statistics for all UDP end points.

## EXAMPLES

### Example 1: Get statistics for all UDP endpoints
```
PS C:\>Get-NetUDPEndpoint
```

This example gets current statistics for all UDP endpoints.

### Example 2: Get statistics for UDP traffic
```
PS C:\>Get-NetUDPEndpoint -LocalAddress 127.0.0.1
```

This command gets statistics for recent UDP traffic that was sent and received on the IPv4 loopback address.

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

### -CreationTime
Specifies an array of **DateTime** objects.
To get a **DateTime** object, use the Get-Date cmdlet.

```yaml
Type: DateTime[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalAddress
Specifies an array of local IP addresses.
The cmdlet gets the UDP endpoint statistics that have these values.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalPort
Specifies an array of local ports.
The cmdlet gets the UDP endpoint statistics that have these values.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OwningProcess
Specifies the PID of the owning process of a bound UDP socket.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetUDPEndpoint
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetUDPSetting](./Get-NetUDPSetting.md)

[Get-NetUDPEndpoint](./Get-NetUDPEndpoint.md)

