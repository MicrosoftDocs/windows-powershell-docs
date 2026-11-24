---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamAddress.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/find-ipamfreeaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Find-IpamFreeAddress
---

# Find-IpamFreeAddress

## SYNOPSIS
Gets one or more free IP addresses from a range of IP addresses in IPAM.

## SYNTAX

```
Find-IpamFreeAddress [-InputObject] <CimInstance> [[-NumAddress] <UInt32>] [-TestReachability]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Find-IpamFreeAddress** cmdlet gets one or more free IP addresses from a range of IP addresses in IP Address Management (IPAM).
If you specify the *NumAddress* parameter, the cmdlet returns the requested number of free IPv4 addresses.
If you do not specify the *NumAddress* parameter, the cmdlet returns a single free IP address.
The maximum number of free IP addresses that the cmdlet returns is 1024.
The cmdlet does not include exclusion address ranges, reservations, and assigned addresses among the free IP addresses.
If the requested number of free IP addresses could not be found, a warning occurs.
If you specify the *TestReachability* parameter, IPAM returns a ping status and a Domain Name System (DNS) record status for each of the IP address that it returns.

## EXAMPLES

### Example 1: Find a free IP address
```
PS C:\> Get-IpamRange -StartIPAddress "10.12.3.1" -EndIPAddress "10.12.3.254" | Find-IpamFreeAddress

IpAddress       : 10.12.3.1

PingStatus      : Undetected

DnsRecordStatus : Undetected
```

This command gets a range of IP addresses through the **Get-IpamRange** cmdlet then finds a free IP address.
By default, IPAM does not test the reachability of the address or the existence of a corresponding DNS record.

### Example 2: Find a free IP address and test the reachability of the address
```
PS C:\> $FreeIPs = Get-IpamRange -StartIPAddress "10.12.3.1" -EndIPAddress "10.12.3.254" | Find-IpamFreeAddress -NumAddress 10 -TestReachability
PS C:\> $FreeIPs[0]
IpAddress       : 10.12.3.1

PingStatus      : NoReply

DnsRecordStatus : NotFound
```

The first command uses the **Get-IpamRange** cmdlet to get a range of IP addresses and then uses the **Find-IpamFreeAddress** cmdlet to find 10 free IP addresses.
The first command then checks if the IP addresses are reachable and whether there is a corresponding DNS record.
The first command then stores the result in the variable named $FreeIPs.

The second command then outputs the results stored in the variable named $FreeIPs.

## PARAMETERS

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NumAddress
Specifies the number of free addresses that this cmdlet gets.
The cmdlet will warn you if the number of free addresses returned is less than the number requested.
If you do not specify this parameter, the cmdlet returns a single free address.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestReachability
Indicates that the cmdlet tests the reachability of the IP addresses.

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

### IpamFreeAddress
This cmdlet returns an object that represents an unallocated IP address in IPAM server.
Along with the IP address, the object also contains flags that specify whether IPAM server was able to ping the IP address and whether IPAM server found an associated DNS record.

## NOTES

## RELATED LINKS

[Get-IpamRange](./Get-IpamRange.md)

