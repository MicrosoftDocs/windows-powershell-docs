---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamRange.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/export-ipamrange?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-IpamRange
---

# Export-IpamRange

## SYNOPSIS
Exports all of the IP address ranges as a file or as an array of objects or both.

## SYNTAX

```
Export-IpamRange -AddressFamily <AddressFamily> [-NetworkType <VirtualizationType>] [-Path <String>]
 [-PassThru] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Export-IpamRange** cmdlet exports all of the IP address ranges of the specified address family from the computer running the IP Address Management (IPAM) server as a comma-separated values (.csv) file or as an array of Windows PowerShell® objects or both.

At least one of the *Path* or *PassThru* parameters must be specified with the cmdlet.
The object array returned using the *PassThru* parameter can be pipelined for further filtering, if required.

Unlike localized object export from IPAM client user interface (UI), the field header names and the enumeration value names of IP address range objects exported by Windows PowerShell have English names and are not be localized in the language used by the computer running the IPAM server.
The field header names must follow the Windows PowerShell property naming conventions.

The format of date and time values of the exported objects are in localized format of the computer running the IPAM server and not in Universal Time Coordinate (UTC).

The IPAM client UI and IPAM Windows PowerShell support interoperability between import and export functionality of English and localized .csv files, provided that the language and locale of importing and exporting computers running the IPAM servers and associated UI is the same.
In other words a localized .csv file exported from IPAM client UI can be imported using IPAM Windows PowerShell and an English .csv file exported from IPAM Windows PowerShell can be imported from IPAM client UI provided the language and locale of the computers running the IPAM client and IPAM server are the same.

## EXAMPLES

### Example 1: Export IPv4 address range to a file
```
PS C:\> Export-IpamRange -AddressFamily IPv4 -Path "C:\Ranges_v4.csv"
```

This command outputs all of the IPv4 address ranges to the file named Ranges_v4.csv.

### Example 2: Export IPv6 address range to a file
```
PS C:\> Export-IpamRange -AddressFamily IPv6 -Path "C:\Ranges_v6.csv" -Force
```

This command outputs all of the IPv6 address ranges to the file Ranges_v6.csv, and overwrites the file if it already exists.

### Example 3: Export IPv4 address range
```
PS C:\> Export-IpamRange -AddressFamily IPv4 -PassThru
NetworkId       StartIPAddress    EndIPAddress    PercentageUtilized    ManagedByService    ServiceInstance
---------       --------------    ------------    ------------------    ----------------    ---------------
172.22.2.0/24      172.22.2.1      172.22.2.254       20.00                 IPAM                Localhost
10.10.0.0/24       10.10.0.1       10.10.0.254        0.00                  IPAM                Localhost
172.17.14.0/24     172.17.14.1     172.17.14.254      85.00                 MS DHCP             s2-infra.contoso.com
192.168.0.0/16     192.168.0.1     192.168.255.254    48.75                 MS DHCP             s2-infra.contoso.com
```

This command outputs all of the IPv4 address range objects.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 4: Export over-utilized IPv4 address range objects
```
PS C:\> Export-IpamRange -AddressFamily IPv4 -PassThru | Where-Object -FilterScript { $_.Utilization -Eq "Over" }
NetworkId       StartIPAddress    EndIPAddress    PercentageUtilized    ManagedByService    ServiceInstance
---------       --------------    ------------    ------------------    ----------------    ---------------
172.17.14.0/24  172.17.14.1       172.17.14.254   85.00                 MS DHCP             s2-infra.contoso.com
```

This command filters all of the over-utilized IPv4 address range objects.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 5: Export over-utilized IPv4 address range objects to a file
```
PS C:\> Export-IpamRange -AddressFamily IPv4 -PassThru | Where-Object -FilterScript { $_.Utilization -Eq "Over" } | Export-Csv -Path "C:\overutilized.csv"
```

This command filters all of the over-utilized IPv4 address range objects and exports the objects to the specified file name.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 6: Export address ranges from a file
```
PS C:\> Export-IpamRange -AddressFamily IPv4 -Path "C:\Ranges.csv" -PassThru
NetworkId       StartIPAddress    EndIPAddress    PercentageUtilized    ManagedByService    ServiceInstance
---------       --------------    ------------    ------------------    ----------------    ---------------
172.22.2.0/24     172.22.2.1       172.22.2.254       20.00                 IPAM                Localhost
10.10.0.0/24      10.10.0.1        10.10.0.254        0.00                  IPAM                Localhost
172.17.14.0/24    172.17.14.1      172.17.14.254      85.00                 MS DHCP             s2-infra.contoso.com
192.168.0.0/16    192.168.0.1      192.168.255.254    48.75                 MS DHCP             s2-infra.contoso.com
```

This command outputs all of the IPv4 address ranges in the file named C:\Ranges.csv and also displays the exported ranges.

The command includes the *PassThru* parameter, so it displays results to the console.

## PARAMETERS

### -AddressFamily
Specifies the address family of IP address range objects being exported.
The acceptable values for this parameter are:

- IPv4
- IPv6

This parameter specifies whether the IPv4 or IPv6 records need to be exported.
Only one address family at a time can be specified with this cmdlet.

```yaml
Type: AddressFamily
Parameter Sets: (All)
Aliases:
Accepted values: IPv4, IPv6

Required: True
Position: Named
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

### -Force
Specifies that new .csv file generated by export must overwrite the existing .csv file (if present), as specified in the *Path* parameter.

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

### -NetworkType
Specifies the type of network of the given IP subnet.

The acceptable values for this parameter are:

- Provider
- Customer
- NonVirtualized

If the address space specified by the *AddressSpace* parameter is Default, specify a value of Provider or NonVirtualized.
If the address space specified by *AddressSpace* parameter is of type Provider, if you specify this parameter, specify a value of Provider.
Specifying any other value for this parameter causes an error.
If the address space specified by the *AddressSpace*  parameter is of type Customer, then, if you specify this parameter, specify a value of Customer.
Specifying any other value for this parameter causes an error.
If you do not specify this parameter, the cmdlet uses a network type NonVirtualized.

```yaml
Type: VirtualizationType
Parameter Sets: (All)
Aliases:
Accepted values: NonVirtualized, Provider, Customer

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Path
Specifies the literal path and name of the .csv file which are created during export.

This parameter is used to export all of the IP address range objects in a .csv file format.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### None

## OUTPUTS

### Microsoft.Windows.Ipam.Commands.IpamIPRangePSObject[]
This cmdlet returns an array of objects that contain an IPAM IP address range.

## NOTES

## RELATED LINKS

[Import-IpamRange](./Import-IpamRange.md)

