---
external help file: IpamAddressUtilizationThreshold.cdxml-help.xml
Module Name: IpamServer
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/ipamserver/get-ipamaddressutilizationthreshold?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamAddressUtilizationThreshold
---

# Get-IpamAddressUtilizationThreshold

## SYNOPSIS
Gets the threshold configuration for address utilization alerts.

## SYNTAX

```
Get-IpamAddressUtilizationThreshold [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamAddressUtilizationThreshold** cmdlet retrieves the configuration for address overutilization and underutilization thresholds.
IP address management (IPAM) generates an alert when a block, subnet or range utilization exceeds or drops below the overutilization and underutilization thresholds.

## EXAMPLES

### Example 1: Retrieve address utilization thresholds
```
PS C:\> Get-IpamAddressUtilizationThreshold
UnderUtilizationThreshold                                   OverUtilizationThreshold

-------------------------                                   ------------------------

20                                                          80
```

This command retrieves all address utilization thresholds configured in IPAM.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamAddressUtilizationThreshold
Represents thresholds that generate utilization alerts in IPAM.

## NOTES

## RELATED LINKS

[Set-IpamAddressUtilizationThreshold](./Set-IpamAddressUtilizationThreshold.md)

