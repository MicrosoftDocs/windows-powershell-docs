---
external help file: NetTCPIP_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 8BA3F61D-C548-46FA-9083-92124842800B
manager: dansimp
---

# Get-NetUDPSetting

## SYNOPSIS
Gets information about UDP settings and configuration.

## SYNTAX

```
Get-NetUDPSetting [[-DynamicPortRangeStartPort] <UInt16[]>] [[-DynamicPortRangeNumberOfPorts] <UInt16[]>]
 [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetUDPSetting** cmdlet gets information for UDP settings.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetUDPSetting
```

This example gets information about UDP settings and configuration.

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

### -DynamicPortRangeNumberOfPorts
Gets UDP setting information only for a specific DynamicPortRangeNumberOfPorts.
DynamicPortRangeNumberOfPorts specifies the number of ports for the dynamic port range starting from the DynamicPortRangeStartPort.

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

### -DynamicPortRangeStartPort
Gets TCP setting information only for a specific DynamicPortRangeStartPort.
DynamicPortRangeStartPort specifies the starting port to send UDP traffic.
The acceptable values for this parameter are: 1 through 65535.

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetUDPSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetTransportFilter](./Get-NetTransportFilter.md)

[Set-NetTCPSetting](./Set-NetTCPSetting.md)

[Set-NetUDPSetting](./Set-NetUDPSetting.md)

