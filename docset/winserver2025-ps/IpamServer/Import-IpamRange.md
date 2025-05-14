---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamRange.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/import-ipamrange?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-IpamRange
---

# Import-IpamRange

## SYNOPSIS
Imports one or more IP address range objects from the specified file into the IPAM server.

## SYNTAX

### Import (Default)
```
Import-IpamRange -Path <String> -AddressFamily <AddressFamily> [-ErrorPath <String>] [-CreateSubnetIfNotFound]
 [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InventoryImport
```
Import-IpamRange -Path <String> -AddressFamily <AddressFamily> [-ErrorPath <String>] [-CreateSubnetIfNotFound]
 [-Force] -ManagedByService <String> -ServiceInstance <String> [-AddManagedByService] [-AddServiceInstance]
 [-DeleteMappedAddresses] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Import-IpamRange** cmdlet imports IP address range objects from the specified comma-separated values (.csv) file into the IP Address Management (IPAM) server.
IPAM server does not support import of IP address ranges that have the *ServiceInstance* parameter value of `MS DHCP`.
This is reserved for Dynamic Host Configuration Protocol (DHCP) scopes automatically discovered by the IPAM server from the managed computers that run Microsoft DHCP server services.
Any objects that fail to import during the operation are logged in the appropriate error log file for further analysis.

This cmdlet supports two parameter sets.
The default invocation of the cmdlet adds new IP address range objects from the .csv file into the IPAM server and edits the existing address ranges with updated information specified in the .csv file.

The second parameter set can be used to periodically import and update all IP address range objects that belong to the specified unique combination of the *ManagedByService* and *ServiceInstance* parameters, in the IPAM server.
In addition to add and edit operations to existing ranges, this import operation also deletes those ranges from the IPAM server which have the same value as the *ManagedByService* and *ServiceInstance* parameters but are not present in the .csv file that is imported.
This parameter set provides you with the option to delete the IP addresses that map to the IP address ranges that are deleted during import through the *DeleteMappedAddresses* parameter.

The import and update of IP address ranges for the specified *ManagedByService* and *ServiceInstance* parameter values succeeds if these values are present on the IPAM server at the time of import.
The *AddManagedByService* and *AddServiceInstance* can be used to create the specified *ManagedByService* and *ServiceInstance* parameter values within the IPAM server at run-time before the import operation, if required.

The network identifier (ID) field is required to import IPAM ranges to the .csv file.
Any other range specific basic field or custom field can be specified in any order in the .csv file for import.
Sample format of import .csv file, can be generated using IPAM export functionality from IPAM UI (localized format) or IPAM Windows PowerShell® (English format).

The IPAM Windows PowerShell import supports both English as well as server localized .csv file.
The IPAM server uses presence of the field named **NetworkId** (without spaces) in the .csv file to ascertain that the file must be processed in English format.
Otherwise the file is processed in the server localized format for the various field names and enumeration values.
The format of date and time values of the imported objects are always interpreted in the localized format of the IPAM server and not in Universal Time Coordinate (UTC).

## EXAMPLES

### Example 1: Import address ranges
```
PS C:\> Import-IpamRange -AddressFamily IPv4 -Path "C:\Rangev4.csv" -Force
```

This command imports IPv4 address ranges from the file named Rangev4.csv  into the IPAM server.
The new ranges are added and existing ranges are edited.
The errors, if any, are recorded in the Documents folder of the user in .csv file format.

This command includes the *Force* parameter, so it suppresses the default confirmation message.

### Example 2: Import IPv4 address ranges and log errors
```
PS C:\> Import-IpamRange -AddressFamily IPv4 -Path "C:\Rangev4.csv" -ErrorPath "C:\" -Force
```

This command imports IPv4 address ranges from the file named Rangev4.csv into the IPAM server.
The new ranges are added and existing ranges are edited.
The errors, if any, are recorded in .csv file format at the path C:\.

This command includes the *Force* parameter, so it suppresses the default confirmation message.

### Example 3: Import and update address ranges
```
PS C:\> Import-IpamRange -AddressFamily IPv4 -Path "C:\Rangeupdatev4.csv" -ManagedByService "IPAM" -ServiceInstance "localhost"
Confirm

Imports a csv file as an update of all IP address ranges that belong to the specified combination of ManagedByService and ServiceInstance values. Along with adding new ranges and editing existing ranges, this operation also deletes ranges belonging to the specified combination of ManagedByService and ServiceInstance from IPAM database, that are not present in the csv file being imported.
Continue with this operation?

[Y] Yes  [N] No  [?] Help  <default is "Y">:Y
```

This command imports and updates all of the IPv4 address ranges managed by the IPAM service  and the Localhost service instance, from the file named C:\Rangeupdatev4.csv into IPAM.
The new ranges are added, existing ranges are edited, and ranges belonging to the specified combination of the *ManagedByService* and *ServiceInstance* parameters, which are not in the .csv file, are deleted from the IPAM server.
The errors, if any, are recorded in the Documents folder of the user in .csv file format.

### Example 4: Import and update address ranges and log errors
```
PS C:\> Import-IpamRange -AddressFamily IPv4 -Path "C:\Rangeupdatev4.csv" -ManagedByService "IPAM" -ServiceInstance "localhost" -ErrorPath "C:\" -Force
```

This command imports and updates all of the IPv4 address ranges with the managing service named IPAM and the service instance named Localhost, from the file named C:\Rangeupdatev4.csv into the IPAM server.
The new ranges are added, existing ranges are edited, and ranges belonging to the specified combination of the *ManagedByService* and *ServiceInstance* parameters, which are not in the .csv file, are deleted from the IPAM server.
The errors, if any, are recorded in .csv file format at the path C:\.

This command includes the *Force* parameter, so it suppresses the default confirmation message.

### Example 5: Import, update, and delete address ranges
```
PS C:\> Import-IpamRange -AddressFamily IPv4 -Path "C:\Rangeupdatev4.csv" -ManagedByService "Others" -ServiceInstance "DHCPServer1" -AddServiceInstance -Force
```

This command adds DHCPServer1 as a new value of the custom field ServiceInstance, if this value is not already present in the IPAM server.
This cmdlet imports and updates all of the IPv4 address ranges with managing service Others and service instance DHCPServer1, from the file named C:\Rangeupdatev4.csv into the IPAM server.
The new ranges are added, existing ranges are edited, and ranges belonging to the specified combination of the *ManagedByService* and *ServiceInstance* parameters, which are not in the .csv file, are deleted from the IPAM server.
The errors, if any are recorded in the Documents folder of the user in .csv file format.

This command includes the *Force* parameter, so it suppresses the default confirmation message.

### Example 6: Add a custom value and import address ranges
```
PS C:\> Import-IpamRange -AddressFamily IPv4 -Path "C:\Rangeupdatev4.csv" -ManagedByService "MyDHCPType" -ServiceInstance "DHCPServer1" -AddServiceInstance -AddManagedByService -Force
```

This command adds DHCPServer1 as a new value of the custom field ServiceInstance, if this value is not already present in the IPAM server.
This cmdlet also adds MyDHCPType as a new value of the custom field ManagedByService, if this value is not already present in the IPAM server.
This cmdlet imports and updates all of the IPv4 address ranges with managing service MyDHCPType and service instance DHCPServer1, from the file named C:\rangeupdatev4.csv into IPAM server.
The new ranges are added, existing ranges are edited, and ranges belonging to the specified combination of the *ManagedByService* and *ServiceInstance* parameters, which are not in the .csv file, are deleted from the IPAM server.
The errors, if any, are recorded in the Documents folder of the user in .csv file format.

This command includes the *Force* parameter, so it suppresses the default confirmation message.

## PARAMETERS

### -AddManagedByService
Indicates that the cmdlet adds the specified *ManagedByService*  parameter value to the custom field that matches this parameter name, if not already present.

```yaml
Type: SwitchParameter
Parameter Sets: InventoryImport
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddServiceInstance
Indicates that the cmdlet adds the specified *ServiceInstance* parameter value to the custom field that matches this parameter name, if not already present.

```yaml
Type: SwitchParameter
Parameter Sets: InventoryImport
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddressFamily
Specifies the address family of records that this cmdlet imports.

The acceptable values for this parameter are:

- IPv4
- IPv6.

Only one address family at a time can be specified with this cmdlet and the records in the .csv file should match the specified address.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateSubnetIfNotFound
Indicates that the cmdlet creates a parent subnet for this range of addresses.
If you specify this parameter, the cmdlet automatically creates a parent subnet for this range, if no parent subnet exists.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeleteMappedAddresses
Indicates that all of the IP addresses that belong, or map, to the IP address ranges being deleted during the import and update operation, are also deleted.

```yaml
Type: SwitchParameter
Parameter Sets: InventoryImport
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ErrorPath
Specifies the fully qualified path, and not the name, of the error .csv files which are created if one or more records fail to import.

The file name is generated automatically by the IPAM server by pre-pending `Error_` and appending the timestamp of the operation to the file name specified in the *Path* parameter.
The default value of this parameter is the Documents folder of the user.

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

### -ManagedByService
Specifies the value of the managing service of the IP address ranges being imported and updated.
Import of `MS DHCP` ranges is not supported by IPAM.

```yaml
Type: String
Parameter Sets: InventoryImport
Aliases: MB

Required: True
Position: Named
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
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServiceInstance
Specifies an array of service instances that manage the address ranges to import.

```yaml
Type: String
Parameter Sets: InventoryImport
Aliases: SI

Required: True
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.String
This cmdlet returns a string that contains a detailed summary of the steps performed by this command.
The message can be one of the following:

- Import of \<AddressFamily\> objects is complete.
\<y\> out of \<y\> objects successfully imported.\<AddressFamily\>\<y\>\<y\>.

- Import of \<AddressFamily\> objects is complete.
\<x\> out of \<y\> objects successfully imported.
\<z\> out of \<y\> objects failed to get imported.
Failures recorded in the file: \<ErrorFilename\> \<AddressFamily\>\<x\>\<y\>\<z\>\<y\>\<ErrorFilename\>

## NOTES

## RELATED LINKS

[Export-IpamRange](./Export-IpamRange.md)

