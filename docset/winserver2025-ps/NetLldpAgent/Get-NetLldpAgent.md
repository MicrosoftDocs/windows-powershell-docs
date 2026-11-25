---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetLldpAgent.cdxml-help.xml
Module Name: NetLldpAgent
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netlldpagent/get-netlldpagent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetLldpAgent
---

# Get-NetLldpAgent

## SYNOPSIS
Gets the settings of the LLDP agent on a network interface on a host computer.

## SYNTAX

### ByName (Default)
```
Get-NetLldpAgent [[-NetAdapterName] <String[]>] [[-AddressScope] <AddressScope[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByIfIndex
```
Get-NetLldpAgent [[-AddressScope] <AddressScope[]>] [[-InterfaceIndex] <UInt32[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetLldpAgent** cmdlet gets the settings of the Logical Link Discovery Protocol (LLDP) agent on a network interface on a host computer.

## EXAMPLES

### Example 1: Get LLDP agent settings on the local computer
```
PS C:\>Get-NetLldpAgent -NetAdapterName "Ethernet1"
```

This command gets LLDP agent settings on a network interface named Ethernet1 on the local computer.

## PARAMETERS

### -AddressScope
Specifies an array of neighbor scopes of the adapter for which this cmdlet gets the LLDP agent settings.
The acceptable values for this parameter are:

- NearestNeighbor
- NearestNonTpmrBridge
- NearestCustomerBridge

```yaml
Type: AddressScope[]
Parameter Sets: (All)
Aliases:
Accepted values: NearestBridge, NearestNonTpmrBridge, NearestCustomerBridge

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -InterfaceIndex
Specifies an array of indexes for which this cmdlet gets LLDP agent settings.

```yaml
Type: UInt32[]
Parameter Sets: ByIfIndex
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetAdapterName
Specifies an array of names of the interfaces for which this cmdlet gets LLDP agent settings.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_NetSettingData/MSFT_NetLldpMsap/MSFT_NetLldpAgent
This cmdlet retrieves the following settings:

- Interface Alias
- Interface Index
- Scope
- MAC address

## NOTES

## RELATED LINKS

[Disable-NetLldpAgent](./Disable-NetLldpAgent.md)

[Enable-NetLldpAgent](./Enable-NetLldpAgent.md)

