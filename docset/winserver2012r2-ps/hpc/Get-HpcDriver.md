---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/get-hpcdriver?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcDriver
---

# Get-HpcDriver

## SYNOPSIS
Gets device drivers.

## SYNTAX

```
Get-HpcDriver [[-Name] <String[]>] [-Scheduler <String[]>][<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcDriver** cmdlet gets one or more specified device drivers, or gets all of the device drivers for the HPC cluster if you do not specify any device drivers.
You specify the device drivers by using the file names of the setup information (.inf) files for the device drivers.

## EXAMPLES

### Example 1: Get a device driver by name
```
PS C:\>Get-HpcDriver -Name "MyDriver.inf"
```

This command gets the device driver with the file name MyDriver.inf.

### Example 2: Get device drivers by head node
```
PS C:\>Get-HpcDriver -Name "Driver1.inf,Driver2.inf" -Scheduler "HeadNode"
```

This command gets the device drivers with the file names Driver1.inf and Driver2.inf for the HPC cluster that has a head node named HeadNode.

## PARAMETERS

### -Name
Specifies an array of the file names for the setup information (.inf) files for the device drivers that you want to get.
Do not include the paths for the .inf files.

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
Specifies the host name or IP address of the head node for the cluster that includes the device drivers.
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

### HpcDriver
This cmdlet returns one or more **HpcDriver** objects.

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Add-HpcDriver](./Add-HpcDriver.md)

[Remove-HpcDriver](./Remove-HpcDriver.md)
