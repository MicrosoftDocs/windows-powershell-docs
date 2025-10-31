---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamSubnet.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/export-ipamsubnet?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-IpamSubnet
---

# Export-IpamSubnet

## SYNOPSIS
Exports the IP address subnets of an address family on the computer that runs IPAM.

## SYNTAX

```
Export-IpamSubnet -AddressFamily <AddressFamily> [-NetworkType <VirtualizationType>] [-Path <String>]
 [-PassThru] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Export-IpamSubnet** cmdlet exports all of the IP address subnets of an address family on the computer that runs IP Address Management (IPAM).
The output is a comma-separated value (.csv) file, or an array of Windows PowerShell objects, or both.
Use this cmdlet to export non-virtualized and virtualized address subnets.

You must specify either the *Path* parameter or the *PassThru* parameter.
The object array returned when using the *PassThru* parameter can be pipelined for additional filtering.
The *Force* parameter can be used to overwrite an existing .csv file with the same name as specified in the *Path* parameter.

Unlike the localized object export from a computer running the IPAM client user interface (UI), the field header names and the enum value names of IP address subnet objects exported by Windows PowerShell have English names and are not localized in the language used by the server.
The field header names follow the Windows PowerShell property naming conventions.

The cmdlet outputs the date and time values of the exported objects in the localized format of the computer that runs IPAM, and not in UTC.

## EXAMPLES

### Example 1: Export all IPv4 address subnets
```
PS C:\> Export-IpamSubnet -AddressFamily IPv4 -AddressSpace Default -Path "C:\Subnets_v4.csv"
```

This command exports all of the IPv4 address subnets that belong to the default address space to the file C:\subnets_v4.csv.

### Example 2: Export all IPv6 address subnets
```
PS C:\> Export-IpamRange -AddressFamily IPv6 -Path "C:\Ranges_v6.csv" -Force
```

This command exports all IPv6 address ranges to the file Ranges_v6.csv, and overwrites the file if it already exists.

### Example 3: Export all IPv4 address subnets for an address space
```
PS C:\> Export-IpamSubnet -AddressFamily IPv4 -AddressSpace ContosoDataCenter -NetworkType Provider -Path "C:\Subnets_v4.csv"
```

This command exports all IPv4 address subnets of network type Provider that belong to the ContosoDataCenter address space.
The cmdlet writes the output to the file C:\subnets_v4.csv.

## PARAMETERS

### -AddressFamily
Specifies an address family of IP address range objects that this cmdlet gets.
The acceptable values for this parameter are:

- IPv4
- IPv6

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
Forces the command to run without asking for user confirmation.

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
Specifies the type of network for the given IP subnet.

The acceptable values for this parameter are:

- Provider
 --  Customer
 --  NonVirtualized

If the value of the *AddressSpace* parameter is Default, then this parameter can take the value Provider or NonVirtualized.
If the value of the *AddressSpace* parameter is Provider, then the value of this parameter, if specified, must be Provider.
Specifying any other value for this parameter will result in an error.
Similarly, if the value of the *AddressSpace* parameter is Customer, then the value of this parameter, if specified, must be Customer.
Specifying any other value for this parameter will result in an error.If you specify the *NetworkType* parameter but do not specify the *AddressSpace*, the cmdlet returns all IP address ranges of the given network type.

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
Specifies the fully qualified path and name of the file that this cmdlet creates.
Use this parameter to export all IP address subnet objects to a .csv file format.

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

## OUTPUTS

### CimInstance#ROOT/microsoft/ipam/MSFT_IPAM_Subnet
This cmdlet returns an object that represents a set of IP subnets in IPAM datastore.

## NOTES

## RELATED LINKS

[Export-IpamSubnet](./Export-IpamSubnet.md)

[Get-IpamSubnet](./Get-IpamSubnet.md)

[Import-IpamSubnet](./Import-IpamSubnet.md)

[Remove-IpamSubnet](./Remove-IpamSubnet.md)

[Set-IpamSubnet](./Set-IpamSubnet.md)

