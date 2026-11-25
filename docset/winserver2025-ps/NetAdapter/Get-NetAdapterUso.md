---
description: Gets the USO properties of the network adapter.
external help file: MSFT_NetAdapterUso.cdxml-help.xml
Module Name: NetAdapter
ms.date: 09/20/2021
online version: https://learn.microsoft.com/powershell/module/netadapter/get-netadapteruso?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetAdapterUso
---

# Get-NetAdapterUso

## SYNOPSIS
Gets the USO properties of the network adapter.

## SYNTAX

### ByName (Default)
```
Get-NetAdapterUso [[-Name] <String[]>] [-IncludeHidden] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByInstanceID
```
Get-NetAdapterUso -InterfaceDescription <String[]> [-IncludeHidden] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetAdapterUso** cmdlet gets the UDP Segmentation Offload (USO) that enables network interface cards (NICs) to offload the segmentation of UDP datagrams that are larger than the maximum transmission unit (MTU) of the network medium. By doing so, Windows reduces CPU utilization associated with per-packet TCP/IP processing. For more information, see [UDP Segmentation Offload (USO)](/windows-hardware/drivers/network/udp-segmentation-offload-uso-).

## EXAMPLES

### Example 1: Get the USO properties for the specified network adapter
```powershell
PS> Get-NetAdapterUso -Name "MyAdapter"
```

This command gets the USO properties of the network adapter named MyAdapter.

### Example 2: Display all the USO properties for the specified network adapter
```
PS> Get-NetAdapterUso -Name "MyAdapter" | Format-List -Property "*"
```

This command displays all of the USO properties of the network adapter named MyAdapter.

### Example 3: Get all network adapters that have USO enabled
```
PS> Get-NetAdapterUso -Name "*" | Where-Object -FilterScript { $_.Enabled }
```

This command gets all network adapters with USO enabled.


## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -IncludeHidden
Indicates that this cmdlet includes both visible and hidden network adapters. By
default only visible network adapters are included. If a wildcard character is
used in identifying a network adapter and this parameter has been specified,
then the wildcard string is matched against both hidden and visible network
adapters.

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

### -InterfaceDescription
Specifies an array of network adapter interface descriptions. For a physical
network adapter this is typically the name of the vendor of the network adapter
followed by a part number and description, such as
`Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: ByInstanceID
Aliases: ifDesc, InstanceID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies an array of network adapter names.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to
run the cmdlet. If this parameter is omitted or a value of `0` is entered, then
Windows PowerShell calculates an optimum throttle limit for the cmdlet based on
the number of CIM cmdlets that are running on the computer. The throttle limit
applies only to the current cmdlet, not to the session or to the computer.

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

### System.String[]
## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance
### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterUsoSettingData
## NOTES

## RELATED LINKS
