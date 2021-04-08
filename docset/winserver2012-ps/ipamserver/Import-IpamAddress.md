---
author: Kateyanne
external help file: IpamServer_Cmdlets.xml
manager: dansimp
Module Name: IpamServer
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/ipamserver/import-ipamaddress?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Import-IpamAddress

## SYNOPSIS
Imports one or more IP address objects from the specified comma-separated values (.csv) file into the computer running the IP Address Management (IPAM) server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Import-IpamAddress [-Path] <String> [-AddressFamily] <String> [-ErrorPath <String>] [-Force] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Import-IpamAddress [-Path] <String> [-AddressFamily] <String> [-ManagedByService] <String>
 [-ServiceInstance] <String> [-NetworkId] <String> [-EndIPAddress <IPAddress>] [-ErrorPath <String>] [-Force]
 [-StartIPAddress <IPAddress>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Import-IpamAddress** cmdlet imports one or more IP address objects from the specified comma-separated values (.csv) file into the computer running the IP Address Management (IPAM) server.
Any objects that fail being imported during the operation are logged in the appropriate error log file for further analysis.

The cmdlet supports two parameter sets.
The default invocation of the cmdlet adds new IP address objects from the .csv file into the computer running the IPAM server and edits the existing address objects with updated information specified in the .csv file.

The second parameter set can be used to periodically import and update all of the IP address objects that belong ,or map, to the IP address range identified by the unique combination of the **NetworkId**, **ManagedByService**, **ServiceInstance**, **StartIPAddress**, and **EndIPAddress** parameters, in the computer running the IPAM server.
Along with adding new addresses and editing existing addresses, this operation also deletes those addresses from the computer running the IPAM server which map to the specified IP address range, but are not present in the .csv file being imported.
If not specified, then the computer running the IPAM server auto calculates the **StartIPAddress** and **EndIPAddress** parameter values, at the default address boundaries of the range as specified by the **NetworkId** parameter.
If explicitly specified, then both the **StartIpAddress** and **EndIpAddress** parameter values must be provided together.
The import and update operation of IP addresses for the IP address range succeeds only if the range is already present in the computer running the IPAM server at the time of import.

The only mandatory field required to be present in the .csv file being imported for IPAM addresses is the IP address itself.
Any other address specific basic field or custom field can be specified in any order in the .csv file for import.
Sample format of the import .csv file, can be generated using IPAM export functionality from IPAM UI (localized format) or IPAM Windows PowerShell® (English format).

Note: The IPAM Windows PowerShell import supports both the English as well as the server localized .csv file.
The computer running the IPAM server uses the presence of the field name `IPAddress` (without spaces) in the .csv file to determine that the file must be processed in English format.
Otherwise the .csv file is processed in the server localized format for the various field names and enumeration values.
The format of date and time values of the imported objects are always interpreted in the localized format of the computer running the IPAM server and not in UTC.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Import-IpamAddress -AddressFamily IPv4 -Path "C:\addressv4.csv" -Force
```

This example imports the IPv4 addresses from the file C:\addressv4.csv into the computer running the IPAM server.
The new addresses are added and existing addresses are edited.
The errors, if any, are recorded in the Documents folder of the user in .csv file format.
The default confirmation text is suppressed in this example.

### EXAMPLE 2
```
PS C:\>Import-IpamAddress -AddressFamily IPv4 -Path "C:\addressv4.csv" -ErrorPath "C:\" -Force
```

This example imports IPv4 addresses from the file C:\addressv4.csv into the computer running the IPAM server.
The new addresses are added and existing addresses are edited.
The errors, if any, are recorded in .csv file format at the path C:\.
The default confirmation text is suppressed in this example.

### EXAMPLE 3
```
PS C:\>Import-IpamAddress -AddressFamily IPv4 -Path "C:\addressupdatev4.csv" -ManagedByService "IPAM" -ServiceInstance "localhost" -NetworkId 10.10.10.0/24
Confirm 
 
Imports a csv file as an update of all IP address records that belong to the specified IP address range. Along with adding new addresses and editing existing addresses, this operation also deletes addresses belonging to the specified IP address range from IPAM database, that are not present in the csv file update being imported. 
 
 
Continue with this operation? 
 
[Y] Yes  [N] No  [?] Help  :Y
```

This example imports and updates all of the IPv4 addresses belonging to the range specified by the network ID 10.10.10.0/24, the managing service IPAM, and the service instance Localhost, from the file C:\addressupdatev4.csv into the computer running the IPAM server.
The starting IP address and ending IP address of the range are automatically calculated as 10.10.10.1 and 10.10.10.254 respectively since the values are not explicitly specified.
The new addresses are added, existing addresses are edited, and addresses belonging to the specified range, which are not in the .csv file, are deleted from the computer running the IPAM server.
The errors, if any, are recorded in the documents folder of the user in .csv file format.
Note: By default, host IDs that contain all zeros (0) and all ones (1) are skipped for IPv4 address ranges while calculating the starting and ending IP address.

### EXAMPLE 4
```
PS C:\>Import-IpamAddress -AddressFamily IPv4 -Path "C:\addressupdatev4.csv" -ManagedByService "IPAM" -ServiceInstance "localhost" -NetworkId 10.10.10.0/24 -StartIpAddress 10.10.10.1 -EndIpAddress 10.10.10.50 -Force
```

This example imports and updates all of the IPv4 addresses belonging to the range specified by the network ID 10.10.10.0/24, the starting IP address 10.10.10.1, the ending IP address 10.10.10.50, the managing service IPAM, and the service instance Localhost, from the file C:\addressupdatev4.csv into the computer running the IPAM server.
The new addresses are added, existing addresses are edited, and addresses belonging to the specified range, which are not in the .csv file, are deleted from the computer running the IPAM server.
The errors, if any, are recorded in the Documents folder of the user in .csv file format.
The default confirmation text is suppressed in this example.

## PARAMETERS

### -AddressFamily
Specifies the address family of the records being imported.
The acceptable values for this parameter are: IPv4 or IPv6.
Only one address family at a time can be specified with this cmdlet and the records in the .csv file should match the address family specified by this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndIPAddress
Specifies the ending IP address of the IP address range for which the addresses are being imported.
This parameter uniquely identifies a range along with the values of the **ManagedByService**, **ServiceInstance**, **NetworkId**, and **StartIpAddress** parameters.
The default value of this parameter aligns to the end of the address range as specified by the **NetworkId** parameter; but for IPv4 networks, a host ID of all ones (`1`) is not used while calculating the default starting IP address.
An example with a default starting IP address for an IPv4 network auto-calculates the value for this parameter to be `220.0.0.254` for the **NetworkId** parameter value of `220.0.0.0/24`.
Both the **StartIpAddress** parameter and this parameter must be explicitly specified together.
This parameter must fall within the subnet specified by the **NetworkId** parameter.

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: End address of the valid address range specified by NetworkId
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ErrorPath
Specifies the literal path, and not the name, of the error .csv file which are created if one or more records fail to get imported. 

                        
The file name is generated automatically by the computer running the IPAM server by pre-pending `Error_` and appending the timestamp of the operation to the file name specified in the **Path** parameter.
The default value of this parameter is the Documents folder of the user.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 'Documents' folder of the user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Suppresses the default confirmation text.
This parameter can be used with this cmdlet, to suppress the default confirmation text for the cmdlet.

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

### -ManagedByService
Specifies the value of the managing service of the IP address range for which the addresses are being imported and updated.
This parameter uniquely identifies a range along with the values of the **ServiceInstance**, **NetworkId**, **StartIpAddress**, and **EndIpAddress** parameters.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkId
Specifies the IP subnet of the IP address range for which addresses are being imported in the format: `\<Subnet Id\>/\<Prefix Length\>` such as `220.0.0.0/24`.
This parameter uniquely identifies a range along with the values of the **ManagedByService**, **ServiceInstance**, **StartIpAddress**, and **EndIpAddress** parameters.
This parameter is used to determine the default values of the **StartIpAddress** and **EndIpAddress** parameters unless explicitly specified.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the literal path and name of the .csv file to import.

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

### -ServiceInstance
Specifies the value of the service instance of the IP address range for which the addresses are being imported and updated.
This parameter uniquely identifies a range along with the values of the **ManagedByService**, **NetworkId**, **StartIpAddress**, and **EndIpAddress** parameters.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartIPAddress
Specifies the starting IP address of the IP address range for which the addresses are being imported.
This parameter uniquely identifies a range along with the value of the **ManagedByService**, **ServiceInstance**, **NetworkId**, and **EndIpAddress** parameters.
The default value of this parameter aligns to the start of the address range as specified by the **NetworkId** parameter; but for IPv4 networks, a host ID of all zeros (0) is not used while calculating the default start IP address.
An example with a default starting IP address for an IPv4 network auto-calculates the value for this parameter to be `220.0.0.1` for the **NetworkId** parameter value of `220.0.0.0/24`.
Both the **StartIpAddress** and **EndIpAddress** parameters must be explicitly specified together.
This parameter must fall within the subnet specified by the **NetworkId** parameter.

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: Start address of the valid address range specified by NetworkId
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### System.String
A detailed summary of the steps performed by this cmdlet.
The message can be one of the following: 
`Import of \<AddressFamily\> objects is complete.
\<y\> out of \<y\> objects successfully imported.\<AddressFamily\>\<y\>\<y\>`

                        
OR 
`Import of \<AddressFamily\> objects is complete.
\<x\> out of \<y\> objects successfully imported.
\<z\> out of \<y\> objects failed to get imported.
Failures recorded in the file: \<ErrorFilename\>\<AddressFamily\>\<x\>\<y\>\<z\>\<y\>\<ErrorFilename\>`

## NOTES

## RELATED LINKS

[Export-IpamAddress](./Export-IpamAddress.md)

