---
author: Kateyanne
description: 
external help file: IpamAddress.cdxml-help.xml
manager: jasgro
Module Name: IpamServer
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/ipamserver/export-ipamaddress?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-IpamAddress
---

# Export-IpamAddress

## SYNOPSIS
Exports IP addresses from IPAM.

## SYNTAX

```
Export-IpamAddress -AddressFamily <AddressFamily> [-NetworkType <VirtualizationType>] [-Path <String>]
 [-PassThru] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Export-IpamAddress** cmdlet exports all of the IP addresses from an address family in IP Address Management (IPAM).
The cmdlet exports the IP addresses as a comma-separated value (CSV) file.

The field header names and the enumerated values of IP address objects that this cmdlet exports have English names that are culture-independent (invariant) and are not in the localized language that the server uses.
The field header names follow the Windows PowerShell property naming conventions.
The format of date and time values of the exported objects are in the localized format of the computer that runs the IPAM server and not in Coordinated Universal Time (UTC).

The IPAM client console and IPAM Server cmdlets in Windows PowerShell support interoperability between import and export functionality of English and localized CSV files, provided that the language and locale of the computers that run the IPAM server that import and export IP addresses are the same.
You can import a localized CSV file that you export from a computer that runs the IPAM client UI by using IPAM Windows PowerShell.
You can import an English CSV file that you exported by using IPAM Windows PowerShell from a computer that runs the IPAM client provided the language and locale of the computers that run the IPAM client and IPAM server are the same.

## EXAMPLES

### Example 1: Export all IPv4 addresses
```
PS C:\> Export-IpamAddress -AddressFamily IPv4 -Path "C:\Addresses_v4.csv"
```

This command exports all the IPv4 addresses in the IPAM server to the specified path.

### Example 2: Export all IPv6 addresses
```
PS C:\> Export-IpamAddress -AddressFamily IPv6 -Path "C:\addresses_v6.csv" -Force
```

This command exports all the IPv6 addresses in IPAM to the specified path.
The command overwrites the file without prompting the user if it already exists.

### Example 3: Output all IPv4 addresses
```
PS C:\> Export-IpamAddress -AddressFamily IPv4 -PassThru
IPAddress       IPAddressState    AssignmentType   ManagedByService    ServiceInstance 
---------       --------------    --------------   ----------------    --------------- 
172.22.2.15     In-Use            Static           IPAM                Localhost 
10.10.0.10      In-Use            Static           IPAM                Localhost 
172.17.14.15    Reserved          Dynamic          MS DHCP             s2-infra.contoso.com 
192.168.0.1     Reserved          Dynamic          MS DHCP             s2-infra.contoso.com
```

This command outputs all the IPv4 address objects in IPAM.

### Example 4: Output all expired IPv4 addresses
```
PS C:\> Export-IpamAddress -AddressFamily IPv4 -PassThru | Where-Object -FilterScript { $_.ExpiryStatus -Eq "Expired" }
IPAddress         IPAddressState    AssignmentType   ManagedByService    ServiceInstance 
---------         --------------    --------------   ----------------    --------------- 
10.155.155.155    In-Use            Static           IPAM                Localhost
```

This command filters and outputs all of the expired IPv4 address in IPAM.

### Example 5: Export all expired IPv4 addresses
```
PS C:\> Export-IpamAddress -AddressFamily IPv4 -PassThru | Where-Object -FilterScript { $_.ExpiryStatus -Eq "Expired" } | Export-Csv -Path "C:\expired.csv"
```

This command filters and exports all the expired IPv4 addresses in IPAM to the specified path.

### Example 6: Export and output all expired IPv4 addresses
```
PS C:\> Export-IpamAddress -AddressFamily IPv4 -Path "C:\Addresses.csv" -PassThru
IPAddress       IPAddressState    AssignmentType   ManagedByService    ServiceInstance 
---------       --------------    --------------   ----------------    --------------- 
172.22.2.15     In-Use            Static           IPAM                Localhost 
10.10.0.10      In-Use            Static           IPAM                Localhost 
172.17.14.15    Reserved          Dynamic          MS DHCP             s2-infra.contoso.com 
192.168.0.1     Reserved          Dynamic          MS DHCP             s2-infra.contoso.com
```

This command exports all of the IPv4 Addresses in IPAM and outputs the exported addresses.

## PARAMETERS

### -AddressFamily
Specifies an address family of IP addresses.The acceptable values for this parameter are:

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

### -Force
Indicates that the cmdlet overwrites a CSV file that has the same name that you specify for the **Path** parameter.

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
Specifies an IPv4 or IPv6 network prefix, in Classless InterDomain Routing (CIDR) notation.
This parameter specifies the IP subnet of the IP address range for which to import the addresses.

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
Specifies the absolute path of the exported CSV file.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Windows.Ipam.Commands.IpamIPAddressPSObject[]
This array of objects contains IPAM IP addresses.

## NOTES

## RELATED LINKS

[Import-IpamAddress](./Import-IpamAddress.md)

[Add-IpamAddress](./Add-IpamAddress.md)

[Get-IpamAddress](./Get-IpamAddress.md)

[Set-IpamAddress](./Set-IpamAddress.md)

[Remove-IpamAddress](./Remove-IpamAddress.md)

[Import-IpamAddress](./Import-IpamAddress.md)

