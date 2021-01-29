---
external help file: MSFT_NetUDPSetting.cdxml-help.xml
Module Name: NetTCPIP
online version: 
schema: 2.0.0
title: Get-NetUDPSetting
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 8BA3F61D-C548-46FA-9083-92124842800B
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-NetUDPSetting

## SYNOPSIS
Gets UDP settings.

## SYNTAX

```
Get-NetUDPSetting [[-DynamicPortRangeStartPort] <UInt16[]>] [[-DynamicPortRangeNumberOfPorts] <UInt16[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetUDPSetting** cmdlet gets UDP settings for the IP interface.
The cmdlet gets the starting port and the number of ports for a dynamic port range that the IP interface uses to send and receive UDP traffic.
Use this cmdlet with the Set-NetUDPSetting to specify a dynamic port range to modify.
If you do not specify any parameters, the cmdlet gets all dynamic port ranges for UDP from the IP interface.

## EXAMPLES

### Example 1: Get all dynamic port ranges for UDP
```
PS C:\>Get-NetUDPSetting
```

This command gets all UDP settings.
The command gets all dynamic port ranges for UDP from the IP interface.

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

### -DynamicPortRangeNumberOfPorts
Specifies an array of values for the number of ports for a dynamic port range that starts from the port that you specify for the **DynamicPortRangeStartPort** parameter.
The cmdlet gets the UDP settings that have these values.

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

### -DynamicPortRangeStartPort
Specifies an array of values for the starting port of the dynamic port range.
The cmdlet gets the UDP settings that have these values.
The acceptable values for this parameter are:1 through 65535.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetUDPSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetTransportFilter](./Get-NetTransportFilter.md)

[Set-NetTCPSetting](./Set-NetTCPSetting.md)

[Set-NetUDPSetting](./Set-NetUDPSetting.md)

