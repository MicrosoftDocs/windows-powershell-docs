---
external help file: IpamConfiguration.cdxml-help.xml
Module Name: IpamServer
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamConfiguration
---

# Get-IpamConfiguration

## SYNOPSIS
Gets the configuration for the computer that runs IPAM.

## SYNTAX

```
Get-IpamConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamConfiguration** cmdlet gets the configuration for the computer that runs the IP Address Management (IPAM) server.
The cmdlet gets the software version number and the TCP port number over which the computer that runs the IPAM Remote Server Administration Tools (RSAT) client connects and communicates with the computer that runs the IPAM server.

## EXAMPLES

### Example 1: Get the IPAM configuration
```
PS C:\> Get-IpamServerConfiguration
Version : 1.3 
Port    : 48885
```

This command gets the configuration for the computer that runs the IPAM server, including the software version number and the TCP port number.

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

### Microsoft.Windows.Ipam.Commands.IpamConfiguration
This object contains an IPAM configuration.

## NOTES

## RELATED LINKS

[Set-IpamConfiguration](./Set-IpamConfiguration.md)

