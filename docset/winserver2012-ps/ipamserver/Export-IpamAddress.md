---
external help file: IpamServer_Cmdlets.xml
Module Name: IpamServer
online version: https://docs.microsoft.com/powershell/module/ipamserver/export-ipamaddress?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Export-IpamAddress

## SYNOPSIS
Exports all of the IP addresses of the specified address family from the computer running the IP Address Management (IPAM) server as a comma-separated value (.csv) file or as an array of Windows PowerShell® objects or both.

## SYNTAX

```
Export-IpamAddress [-AddressFamily] <String> [-Force] [-PassThru] [-Path <String>]
```

## DESCRIPTION
The **Export-IpamAddress** cmdlet exports all of the IP addresses of the specified address family from the computer running the IP Address Management (IPAM) server as a comma-separated value (.csv) file or as an array of Windows PowerShell® objects or both.

Either the **Path** or **PassThru** parameter must be specified with the cmdlet.
The object array returned using **PassThru** parameter can be pipelined for further filtering, if required.
The **Force** parameter can be used with the cmdlet, to overwrite an existing .csv file with the same name as specified in the **Path** parameter, during export.

Unlike the localized object export from computer running the IPAM client user interface (UI), the field header names and the enum value names of IP address objects exported by Windows PowerShell have English names and are not be localized in the language used by the server.
The field header names follow the Windows PowerShell property naming conventions.

Note: The format of date and time values of the exported objects are in the localized format of the computer running the IPAm server and not in UTC.

The IPAM client UI and IPAM Windows PowerShell support interoperability between import and export functionality of English and localized .csv files, provided that the language and locale of the computers running the IPAM server and associated UI that are importing and exporting are the same.
In other words a localized .csv file exported from the computer running the IPAM client UI can be imported using IPAM Windows PowerShell and an English .csv file exported from IPAM Windows PowerShell can be imported from computer running the IPAM client UI provided the language and locale of the computers running the IPAM client and IPAM server are the same.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Export-IpamAddress -AddressFamily IPv4 -Path "C:\addresses_v4.csv"
```

This example outputs all of the **IPv4** addresses in the file C:\addresses_v4.csv.

### EXAMPLE 2
```
PS C:\> Export-IpamAddress -AddressFamily IPv6 -Path "C:\addresses_v6.csv" -Force
```

This example outputs all of the IPv6 addresses in the file C:\addresses_v6.csv, and overwrites the file if it already exists.

### EXAMPLE 3
```
PS C:\> Export-IpamAddress -AddressFamily IPv4 -PassThru
IPAddress       IPAddressState    AssignmentType   ManagedByService    ServiceInstance 
---------       --------------    --------------   ----------------    --------------- 
2.2.2.15        In-Use            Static           IPAM                Localhost 
10.10.0.10      In-Use            Static           IPAM                Localhost 
12.13.14.15     Reserved          Dynamic          MS DHCP             s2-infra.contoso.com 
5.5.0.1         Reserved          Dynamic          MS DHCP             s2-infra.contoso.com
```

This example outputs all of the IPv4 address objects.

### EXAMPLE 4
```
PS C:\> Export-IpamAddress -AddressFamily IPv4 -PassThru | Where-Object -FilterScript { $_.ExpiryStatus -Eq "Expired" }
IPAddress       IPAddressState    AssignmentType   ManagedByService    ServiceInstance 
---------       --------------    --------------   ----------------    --------------- 
2.2.2.15        In-Use            Static           IPAM                Localhost
```

This example filters all of the expired IPv4 address objects.

### EXAMPLE 5
```
PS C:\> Export-IpamAddress -AddressFamily IPv4 -PassThru | Where-Object -FilterScript { $_.ExpiryStatus -Eq "Expired" } | Export-Csv -Path "C:\expired.csv"
```

This example filters all of the expired IPv4 address objects and exports those objects into the file C:\expired.csv.

### EXAMPLE 6
```
PS C:\> Export-IpamAddress -AddressFamily IPv4 -Path C:\addresses.csv -PassThru
IPAddress       IPAddressState    AssignmentType   ManagedByService    ServiceInstance 
---------       --------------    --------------   ----------------    --------------- 
2.2.2.15        In-Use            Static           IPAM                Localhost 
10.10.0.10      In-Use            Static           IPAM                Localhost 
12.13.14.15     Reserved          Dynamic          MS DHCP             s2-infra.contoso.com 
5.5.0.1         Reserved          Dynamic          MS DHCP             s2-infra.contoso.com
```

This example outputs all of the IPv4 addresses in the file C:\addresses.csv and also displays the exported addresses.

## PARAMETERS

### -AddressFamily
Specifies the address family of the IP address objects being exported.
The acceptable values for this parameter are: IPv4 or IPv6. 

                        
This parameter specifies if IPv4 or IPv6 records need to be exported.
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
Specifies that the new .csv file generated by export must overwrite the existing .csv file (if present), as specified in the **Path** parameter.

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

                        
This parameter is used to export all IP address objects in a .csv file format.

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

### Microsoft.Windows.Ipam.Commands.IpamIPAddressPSObject[]
This array of objects contains IPAM IP addresses.

## NOTES

## RELATED LINKS

[Export-Csv](https://go.microsoft.com/fwlink/p/?LinkId=113299)

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkId=113423)

[Import-IpamAddress](./Import-IpamAddress.md)

