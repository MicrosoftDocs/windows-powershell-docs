---
external help file: IpamServer_Cmdlets.xml
Module Name: IpamServer
online version: https://learn.microsoft.com/powershell/module/ipamserver/export-ipamrange?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Export-IpamRange

## SYNOPSIS
Exports all of the IP address ranges of the specified address family from the computer running the IP Address Management (IPAM) server as a comma-separated values (.csv) file or as an array of Windows PowerShell® objects or both.

## SYNTAX

```
Export-IpamRange [-AddressFamily] <String> [-Force] [-PassThru] [-Path <String>]
```

## DESCRIPTION
The **Export-IpamRange** cmdlet exports all of the IP address ranges of the specified address family from the computer running the IP Address Management (IPAM) server as a comma-separated values (.csv) file or as an array of Windows PowerShell® objects or both.

At least one of the **Path** or **PassThru** parameters must be specified with the cmdlet.
The object array returned using the **PassThru** parameter can be pipelined for further filtering, if required.

Unlike localized object export from IPAM client user interface (UI), the field header names and the enumeration value names of IP address range objects exported by Windows PowerShell have English names and are not be localized in the language used by the computer running the IPAM server.
The field header names must follow the Windows PowerShell property naming conventions.

Note: The format of date and time values of the exported objects are in localized format of the computer running the IPAM server and not in UTC.

The IPAM client UI and IPAM Windows PowerShell support interoperability between import and export functionality of English and localized .csv files, provided that the language and locale of importing and exporting computers running the IPAM servers and associated UI is the same.
In other words a localized .csv file exported from IPAM client UI can be imported using IPAM Windows PowerShell and an English .csv file exported from IPAM Windows PowerShell can be imported from IPAM client UI provided the language and locale of the computers running the IPAM client and IPAM server are the same.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Export-IpamRange -AddressFamily IPv4 -Path "C:\ranges_v4.csv"
```

This example outputs all of the IPv4 address ranges in the file C:\ranges_v4.csv.

### EXAMPLE 2
```
PS C:\> Export-IpamRange -AddressFamily IPv6 -Path "C:\ranges_v6.csv" -Force
```

This example outputs all of the IPv6 address ranges in the file C:\ranges_v6.csv, and overwrites the file if it already exists.

### EXAMPLE 3
```
PS C:\> Export-IpamRange -AddressFamily IPv4 -PassThru
NetworkId       StartIPAddress    EndIPAddress    PercentageUtilized    ManagedByService    ServiceInstance 
---------       --------------    ------------    ------------------    ----------------    --------------- 
2.2.2.0/24      2.2.2.1           2.2.2.254       20.00                 IPAM                Localhost 
10.10.0.0/24    10.10.0.1         10.10.0.254     0.00                  IPAM                Localhost 
12.13.14.0/24   12.13.14.1        12.13.14.254    85.00                 MS DHCP             s2-infra.contoso.com 
5.5.0.0/16      5.5.0.1           5.5.255.254     48.75                 MS DHCP             s2-infra.contoso.com
```

This example outputs all of the IPv4 address range objects.

### EXAMPLE 4
```
PS C:\> Export-IpamRange -AddressFamily IPv4 -PassThru | Where-Object -FilterScript { $_.Utilization -Eq "Over" }
NetworkId       StartIPAddress    EndIPAddress    PercentageUtilized    ManagedByService    ServiceInstance 
---------       --------------    ------------    ------------------    ----------------    --------------- 
12.13.14.0/24   12.13.14.1        12.13.14.254    85.00                 MS DHCP             s2-infra.contoso.com
```

This example filters all of the over-utilized IPv4 address range objects.

### EXAMPLE 5
```
PS C:\> Export-IpamRange -AddressFamily IPv4 -PassThru | Where-Object -FilterScript { $_.Utilization -Eq "Over" } | Export-Csv -Path "C:\overutilized.csv"
```

This example filters all of the over utilized IPv4 address range objects and exports the objects in a file C:\overutilized.csv.

### EXAMPLE 6
```
PS C:\> Export-IpamRange -AddressFamily IPv4 -Path C:\ranges.csv -PassThru
NetworkId       StartIPAddress    EndIPAddress    PercentageUtilized    ManagedByService    ServiceInstance 
---------       --------------    ------------    ------------------    ----------------    --------------- 
2.2.2.0/24      2.2.2.1           2.2.2.254       20.00                 IPAM                Localhost 
10.10.0.0/24    10.10.0.1         10.10.0.254     0.00                  IPAM                Localhost 
12.13.14.0/24   12.13.14.1        12.13.14.254    85.00                 MS DHCP             s2-infra.contoso.com 
5.5.0.0/16      5.5.0.1           5.5.255.254     48.75                 MS DHCP             s2-infra.contoso.com
```

This example outputs all of the IPv4 address ranges in the file **C:\ranges.csv** and also displays the exported ranges.

## PARAMETERS

### -AddressFamily
Specifies the address family of IP address range objects being exported.
The acceptable values for this parameter are: IPv4 or IPv6. 

                        
This parameter specifies whether the IPv4 or IPv6 records need to be exported.
Only one address family at a time can be specified with this cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Specifies that new .csv file generated by export must overwrite the existing .csv file (if present), as specified in the **Path** parameter.

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

## INPUTS

### None

## OUTPUTS

### Microsoft.Windows.Ipam.Commands.IpamIPRangePSObject[]
This array of objects contains an IPAM IP address range.

## NOTES

## RELATED LINKS

[Export-Csv](https://go.microsoft.com/fwlink/p/?LinkId=113299)

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkId=113423)

[Import-IpamRange](./Import-IpamRange.md)

