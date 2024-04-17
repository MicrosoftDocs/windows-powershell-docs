---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamAddress.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/import-ipamaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-IpamAddress
---

# Import-IpamAddress

## SYNOPSIS
Imports IP address into the IPAM server.

## SYNTAX

### Import (Default)
```
Import-IpamAddress -Path <String> -AddressFamily <AddressFamily> [-ErrorPath <String>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InventoryImport
```
Import-IpamAddress -Path <String> -AddressFamily <AddressFamily> [-ErrorPath <String>] [-Force]
 -ManagedByService <String> -ServiceInstance <String> -NetworkId <String> [-StartIpAddress <IPAddress>]
 [-EndIpAddress <IPAddress>] [-NetworkType <VirtualizationType>] [-AddressSpace <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-IpamAddress** cmdlet imports IP addresses from a comma-separated values (CSV) file into the IP Address Management (IPAM) server.

The cmdlet supports two parameter sets.
The Import parameter set adds IP address objects from the CSV file into the IPAM server and updates the existing address objects with updated information specified in the CSV file.

Use the *InventoryImport* parameter set to periodically import and update all of the IP address objects that map to the IP address range that you specify by using the unique combination of the *NetworkId*, *ManagedByService*, *ServiceInstance*, *StartIPAddress*, and *EndIPAddress* parameters.
In addition to adding new addresses and changing existing addresses, this operation also removes the addresses which map to the IP address range that you specify but do not exist in the .csv file that you import.
The import and update operations of IP addresses for an IP address range succeed only if the range exists the IPAM server.

The only field required in the CSV file that you import is the IP address.
Other address-specific fields or custom fields can be specified in any order in the import CSV file.

The IPAM Windows PowerShell import supports both the English and server localized .csv files.
The IPAM server uses the presence of the field name IPAddress in the CSV file to determine that the file must be processed in English format.
If the field name IPAddress is not present in the CSV file, the CSV file is processed in the server localized format for the field names and enumeration values.
The format of date and time values of the imported objects are interpreted in the localized format of the computer that runs the IPAM server and not in Coordinated Universal Time (UTC).

## EXAMPLES

### Example 1: Import IPv4 addresses
```
PS C:\> Import-IpamAddress -AddressFamily IPv4 -Path "C:\Addressv4.csv" -Force
```

This command imports the IPv4 addresses from the file C:\Addressv4.csv into the IPAM server.
The new addresses are added and existing addresses are edited.
The errors, if any, are recorded in the Documents folder of the user in CSV file format.
The command runs without user confirmation.

### Example 2: Import IPv4 addresses and record errors
```
PS C:\> Import-IpamAddress -AddressFamily IPv4 -Path "C:\addressv4.csv" -ErrorPath "C:\" -Force
```

This command imports IPv4 addresses from the file C:\Addressv4.csv into the IPAM server.
The command adds new addresses and modifies and existing addresses.
The command records errors that occur during the import a CSV file at the path C:\.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 3: Import and update IPv4 addresses in a range
```
PS C:\> Import-IpamAddress -AddressFamily IPv4 -Path "C:\addressupdatev4.csv" -ManagedByService "IPAM" -ServiceInstance "Localhost" -NetworkId "10.10.10.0/24"
Confirm

Imports a csv file as an update of all IP address records that belong to the specified IP address range. Along with adding new addresses and editing existing addresses, this operation also deletes addresses belonging to the specified IP address range from IPAM database, that are not present in the csv file update being imported.


Continue with this operation?

[Y] Yes  [N] No  [?] Help  :Y
```

This command imports and updates all of the IPv4 addresses from the specified path that belong to the range specified by the network ID 10.10.10.0/24, the managing service IPAM, and the service instance Localhost.
The cmdlet calculates the start IP address as 10.10.10.1 and the end IP address as 10.10.10.254.
The cmdlet adds new addresses, changes existing addresses, and removes addresses that belong to the specified range which are not in the CSV file.
By default, host IDs that contain all zeros (0) and all ones (1) are skipped for IPv4 address ranges while calculating the starting and ending IP address.

### Example 4: Import and update IPv4 addresses that have a start and end address
```
PS C:\> Import-IpamAddress -AddressFamily IPv4 -Path "C:\Addressupdatev4.csv" -ManagedByService "IPAM" -ServiceInstance "Localhost" -NetworkId "10.10.10.0/24" -StartIpAddress 10.10.10.1 -EndIpAddress 10.10.10.50 -Force
```

This command imports and updates all of the IPv4 addresses from the file C:\Addressupdatev4.csv that belong to the range specified by the network ID 10.10.10.0/24, the start IP address 10.10.10.1, the end IP address 10.10.10.50, the managing service IPAM, and the service instance Localhost.
The command adds new addresses, changes existing addresses, and removes addresses that belong to the specified range which are not in the CSV file.
The command records errors that occur in CSV file in the Documents folder of the user.

## PARAMETERS

### -AddressFamily
Specifies the address family of the IP address records in the import file.
The IP address records in the CSV file must belong to the address family that you specify for this parameter.

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

### -AddressSpace
Specifies the name of an address space.
If you do not specify this parameter, the cmdlet imports the IP addresses into the Default address space.
If you specify this parameter, you must specify the *AddressFamily* parameter.

```yaml
Type: String
Parameter Sets: InventoryImport
Aliases:

Required: False
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

### -EndIpAddress
Specifies the end address for the IP address block.
If you do not specify this parameter, the cmdlet uses the last IP address of the network that you specify for the *NetworkId* parameter.
If you specify this parameter, you must specify the *StartIPAddress* parameter.

```yaml
Type: IPAddress
Parameter Sets: InventoryImport
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ErrorPath
Specifies the literal path of the error CSV files that IPAM generates if one or more IP address records fail to import.

The file name is generated automatically by the computer that runs the IPAM server by prepending `Error_` and appending the timestamp of the operation to the file name specified in the *Path* parameter.
The default value of this parameter is the **Documents** folder of the user.

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
Specifies the value of the service that manages the IP address range for which you import and update IP addresses.
Specify this parameter and the *ServiceInstance*, *NetworkId*, *StartIpAddress*, and *EndIpAddress* parameters to uniquely identify a range.

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

### -NetworkId
Specifies an IPv4 or IPv6 network prefix, in Classless InterDomain Routing (CIDR) notation.
This parameter specifies the IP subnet of the IP address range for which you import the addresses.

Specify this parameter and the *ManagedByService*, *ServiceInstance*, *StartIpAddress*, and *EndIpAddress* parameters to uniquely identify a range.

```yaml
Type: String
Parameter Sets: InventoryImport
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkType
Specifies an IPv4 or IPv6 network prefix, in Classless InterDomain Routing (CIDR) notation.
This parameter specifies the IP subnet of the IP address range for which to export the addresses.

Specify this parameter and the *ManagedByService*, *ServiceInstance*, *StartIpAddress*, and *EndIpAddress* parameters to uniquely identify an address range.

```yaml
Type: VirtualizationType
Parameter Sets: InventoryImport
Aliases:
Accepted values: NonVirtualized, Provider, Customer

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the literal path and name of the CSV file to import.

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
Specifies the value of the service instance of the IP address range for which you are importing and updating IP addresses.
Specify this parameter and the *ManagedByService*, *NetworkId*, *StartIpAddress*, and *EndIpAddress* parameters to uniquely identify a range.

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

### -StartIpAddress
Specifies the start address for the IP address block.
If you do not specify this parameter, the cmdlet uses the first address of the network that you specify for the *NetworkId* parameter.
If you specify this parameter, you must specify the *EndIpAddress* parameter.

```yaml
Type: IPAddress
Parameter Sets: InventoryImport
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
This cmdlet returns a string that contains a detailed summary of the steps that the cmdlet performed.
The message is one of the following:

- Import of \<AddressFamily\> objects is complete.
\<y\> out of \<y\> objects successfully imported.

- Import of \<AddressFamily\> objects is complete.
\<x\> out of \<y\> objects successfully imported.
\<z\> out of \<y\> objects failed to get imported.
Failures recorded in the file: \<ErrorFilename\>

## NOTES

## RELATED LINKS

[Export-IpamAddress](./Export-IpamAddress.md)

