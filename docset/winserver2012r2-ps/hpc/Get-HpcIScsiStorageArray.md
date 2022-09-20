---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/get-hpciscsistoragearray?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcScsiStorageArray
---

# Get-HpcIScsiStorageArray

## SYNOPSIS
Gets HpcIScsiStorageArray objects.

## SYNTAX

```
Get-HpcIScsiStorageArray [[-Name] <String[]>] [-IpAddresses <String[]>] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcIScsiStorageArray** cmdlet gets **HpcIScsiStorageArray** objects for the iSCSI storage arrays with the specified names and management IP addresses, or it gets all of the iSCSI storage arrays for the HPC cluster if no names or management IP addresses are specified.

## EXAMPLES

### Example 1: Get an iSCSI storage array by name
```
PS C:\>Get-HpcIScsiStorageArray -Name "Windows Storage Server"
```

This command displays information about the iSCSI storage array named Windows Storage Server.

### Example 2: Get iSCSI storage arrays by IP address
```
PS C:\>Get-HpcIScsiStorageArray -IpAddresses 10.0.0.*
```

This command displays information about the iSCSI storage arrays that have a management IP address that starts with 10.0.0 and has any value between 0 and 255 for the last part of the address.

### Example 3: Get an iSCSI storage array and modify it
```
PS C:\>Get-HpcIScsiStorageArray -IpAddresses 10.0.0.10 | Set-HpcIScsiStorageArray -Description "First Storage Array"
```

This command gets an **HpcIScsiStorageArray** object for the iSCSI storage array that has a management IP address of 10.0.0.10, and then redirects this object as input to the Set-HpcIScsiStorageArray cmdlet to set the description for the storage array to First Storage Array.

## PARAMETERS

### -IpAddresses
Specifies an array of management IP addresses for one or more iSCSI storage arrays for which you want to get information.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names of iSCSI storage arrays for which you want to get information.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster for which you want to get information about iSCSI storage arrays.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

```yaml
Type: String[]
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

### HpcIScsiStorageArray[]

## NOTES
* If you specify the *Name* and *IpAddresses* parameters, the **Get-HpcIScsiStorageArray** cmdlet gets information or **HpcIScsiStorageArray** objects for only iSCSI storage arrays that match both one of the specified names and one of the specified management IP addresses. For example, if the HPC cluster has an iSCSI storage array with a name of Array 1 and a management IP address of 10.0.0.10, the `Get-HpcIScsiStorageArray -Name "Array 1","Array 2" -IpAddresses 10.0.0.10,10.0.0.11` cmdlet gets information about that iSCSI storage array, but the `Get-HpcIScsiStorageArray -Name "Array 2" -IpAddresses 10.0.0.10,10.0.0.11` and `Get-HpcIScsiStorageArray -Name "Array 1","Array 2" -IpAddresses 10.0.0.11` cmdlets do not.
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Add-HpcIScsiStorageArray](./Add-HpcIScsiStorageArray.md)

[Remove-HpcIScsiStorageArray](./Remove-HpcIScsiStorageArray.md)

[Set-HpcIScsiStorageArray](./Set-HpcIScsiStorageArray.md)

[Validate-HpcIScsiStorageArray](./Validate-HpcIScsiStorageArray.md)
