---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/add-hpcdriver?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-HpcDriver
---

# Add-HpcDriver

## SYNOPSIS
Adds device drivers to all of the operating system images in an HPC cluster.

## SYNTAX

```
Add-HpcDriver [-Path] <String[]> [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-HpcDriver** cmdlet adds one or more specified device drivers into all of the operating system images in an HPC cluster.

## EXAMPLES

### Example 1: Add a driver to all operating system images in a cluster
```
PS C:\>Add-HpcDriver -Path "C:\MyDrivers\MyDriver.inf"
```

This command adds the device driver with a setup information (.inf) file located at C:\MyDrivers\MyDriver.inf to all of the operating system images in the HPC cluster.

### Example 2: Add drivers to operating system images in a specified head node
```
PS C:\>Add-HpcDriver -Scheduler "HeadNode" -Path "C:\MyDrivers\Driver1.inf,C:\MyDrivers\Driver2.inf"
```

This command adds the device drivers with setup information (.inf) files located at C:\MyDrivers\Driver1.inf and C:\MyDrivers\Driver2.inf to all of the operating system images in the HPC cluster with a head node named HeadNode.

## PARAMETERS

### -Path
Specifies an array of file names and paths for the setup information (.inf) files for the device drivers that you want to add to the device driver store and the operating system images for the HPC cluster.
Include relative or full paths for the files if the files are not in the current working directory.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster to which you want to add the device drivers.
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

### HpcDriver[]

## NOTES
* The **Add-HpcDriver** cmdlet adds folders and copies of the setup information (.inf) files for the device drivers to the Data\InstallShare\Drivers subfolder of the folder where you have HPC Pack installed.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcDriver](./Get-HpcDriver.md)

[Remove-HpcDriver](./Remove-HpcDriver.md)
