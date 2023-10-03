---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/set-hpciscsistoragearray?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HpcIScsiStorageArray
---

# Set-HpcIScsiStorageArray

## SYNOPSIS
Sets an iSCSI storage array for an HPC cluster.

## SYNTAX

```
Set-HpcIScsiStorageArray -HpcIScsiStorageArray <HpcIScsiStorageArray> [-Name <String>] [-IpAddress <String>]
 [-Description <String>] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HpcIScsiStorageArray** cmdlet sets the name, description, or IP address of the specified Internet SCSI (iSCSI) storage array for an HPC cluster.

## EXAMPLES

### Example 1: Set the description for an iSCSI storage array
```
PS C:\>Get-HpcIScsiStorageArray -IpAddresses 10.0.0.10 | Set-HpcIScsiStorageArray -Description "First Storage Array"
```

This command gets an **HpcIScsiStorageArray** object for the iSCSI storage array that has a management IP address of 10.0.0.10, and then redirects this object as input to the **Set-HpcIScsiStorageArray** cmdlet to set its description to First Storage Array.

### Example 2: Modify an iSCSI storage array stored as a variable
```
PS C:\>$SA = Get-HpcIScsiStorageArray -IpAddresses 10.0.0.11
PS C:\> Set-HpcIScsiStorageArray -HpcIScsiStorageArray $SA -Name "Storage Array 2" -Description "Second Storage Array"
```

Gets an **HpcIScsiStorageArray** object for the iSCSI storage array that has a management IP address of 10.0.0.11, and then saves the object in a variable.

The second command sets the name and description for the iSCSI storage array in $SA.

## PARAMETERS

### -Description
Specifies a new description for the iSCSI storage array.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HpcIScsiStorageArray
Specifies the iSCSI storage array in the HPC cluster that you want to modify.
Use the Get-HpcIScsiStorageArray cmdlet to get an **HpcIScsiStorageArray** for an iSCSI storage array in an HPC cluster.

```yaml
Type: HpcIScsiStorageArray
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies a new name for the iSCSI storage array.
The maximum length of the name is 400 characters.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or the IP address of the head node for the HPC cluster that contains the storage array for which you want to set the name or description.
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

### -IpAddress
Specifies a new IP address for the iSCSI storage array.

```yaml
Type: String
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

### HpcIScsiStorageArray

## OUTPUTS

### None

## NOTES
* Although the *HpcIScsiStorageArray* parameter accepts pipeline input, this cmdlet can only successfully set the name or IP address for the first **HpcIScsiStorageArray** object that is received through the pipeline, because multiple storage arrays cannot have the same name or IP address. So, if you redirect the output of a Get-HpcIScsiStorageArray cmdlet that gets multiple **HpcIScsiStorageArray** objects to the **Set-HpcIScsiStorageArray** cmdlet, you should not specify the *Name* or *IpAddress* parameters for the **Set-HpcIScsiStorageArray** cmdlet.
* You must be a cluster administrator to run this cmdlet successfully.
* This parameter was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Add-HpcIScsiStorageArray](./Add-HpcIScsiStorageArray.md)

[Get-HpcIScsiStorageArray](./Get-HpcIScsiStorageArray.md)

[Remove-HpcIScsiStorageArray](./Remove-HpcIScsiStorageArray.md)

[Validate-HpcIScsiStorageArray](./Validate-HpcIScsiStorageArray.md)
