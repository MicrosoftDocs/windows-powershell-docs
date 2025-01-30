---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/validate-hpciscsistoragearray?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Validate-HpcIScsiStorageArray
---

# Validate-HpcIScsiStorageArray

## SYNOPSIS
Validates that the head node of the HPC cluster can communicate with an iSCSI storage array.

## SYNTAX

```
Validate-HpcIScsiStorageArray -HpcIScsiStorageArray <HpcIScsiStorageArray>
  [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Validate-HpcIScsiStorageArray** cmdlet validates that the head node of the HPC cluster can communicate with the specified Internet SCSI (iSCSI) storage array.

## EXAMPLES

### Example 1: Add an iSCSI storage array to a cluster and validate it
```
PS C:\>$New_SA = Add-HpcIScsiStorageArray -Name "Storage Array 1" -IpAddress "10.0.0.10" -Description "First Storage Array"
PS C:\> Validate-HpcIScsiStorageArray -HpcIScsiStorageArray $New_SA
```

The first command adds the iSCSI storage array with a management IP address of 10.0.0.10 to the HPC cluster, assigns the name Storage Array 1 and the description First Storage Array to that iSCSI storage array, and then saves the **HpcIScsiStorageArray** object for that iSCSI storage array to the $New_SA variable.

The second command uses the **Validate-HpcIScsiStorageArray** cmdlet to validate that the head node for the HPC cluster can connect to the iSCSI storage array in $New_SA.

### Example 2: Add an iSCSI storage array to a cluster and validate it
```
PS C:\>Add-HpcIScsiStorageArray -Name "Storage Array 2" -IpAddress "10.0.0.11" -Description "Second Storage Array" | Validate-HpcIScsiStorageArray
```

This command adds the iSCSI storage array with a management IP address of 10.0.0.11 to the HPC cluster, and then assigns the name Storage Array 2 and the description Second Storage Array to that iSCSI storage array.

The command then redirects the **HpcIScsiStorageArray** object that is the output of the Add-HpcIScsiStorageArray cmdlet to become input to the **Validate-HpcIScsiStorageArray** cmdlet.
This validates that the head node for the HPC cluster can connect to the iSCSI storage array.

## PARAMETERS

### -HpcIScsiStorageArray
Specifies the **HpcIScsiStorageArray** object for which you want to validate connectivity.
Typically, you specify the **HpcIScsiStorageArray** object that the Add-HpcIScsiStorageArray cmdlet returns when you add an iSCSI storage array to an HPC cluster.

You can also use the Get-HpcIScsiStorageArray cmdlet to get an **HpcIScsiStorageArray** object for an iSCSI storage array that already is part of the HPC cluster.

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

### -Scheduler
Specifies the host name or IP address of the head node for which you want to validate connectivity to the iSCSI storage array.
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

### HpcIScsiStorageArray

## OUTPUTS

### None

## NOTES
* If validation fails, perform the following checks:

  - Ensure that the head node has the necessary permissions to communicate with and make changes on the storage arrays.
You must provide the necessary permissions to the head node computer so that the HPC services that run on the head node can configure the storage arrays.

  - Review the IP address that you specified, ensure that the storage arrays are configured properly, and then try to validate the connection again.

  - Open Event Viewer, and under Application and Service Logs, click Windows HPC Server.
Look for the most recent Error event that has an ID of 6100 and a source of HpcManagement.
The message for this event provides more information about the failure.

* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Add-HpcIScsiStorageArray](/powershell/module/hpcpack2016/add-hpciscsistoragearray?view=hpc16-ps)

[Get-HpcIScsiStorageArray](/powershell/module/hpcpack2016/get-hpciscsistoragearray?view=hpc16-ps)

[Remove-HpcIScsiStorageArray](/powershell/module/hpcpack2016/remove-hpciscsistoragearray?view=hpc16-ps)

[Set-HpcIScsiStorageArray](/powershell/module/hpcpack2016/set-hpciscsistoragearray?view=hpc16-ps)
