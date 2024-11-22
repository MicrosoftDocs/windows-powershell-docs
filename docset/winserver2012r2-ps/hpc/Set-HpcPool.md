---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/set-hpcpool?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HpcPool
---

# Set-HpcPool

## SYNOPSIS
Sets the weight of a resource pool.

## SYNTAX

### pool (Default)
```
Set-HpcPool -Pool <HpcPool> [-Weight <Int32>]  [-Scheduler <String[]>]
 [<CommonParameters>]
```

### name
```
Set-HpcPool -Name <String> [-Weight <Int32>]  [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-HpcPool** cmdlet sets the weight of an HPC resource pool.
This cmdlet returns an error if the specified pool does not exist, or if the specified weight is less than 0 or greater than 999,999.

## EXAMPLES

### Example 1: Set the weight of a resource pool
```
PS C:\>Set-HpcPool -Name "Pool01" -Weight 10
```

This command sets the weight of an existing pool using the pool name and weight parameters.

## PARAMETERS

### -Name
Specifies the name of the resource pool that you will be setting the weight on.
You cannot specify both the *Name* and the *Pool* parameters.

```yaml
Type: String
Parameter Sets: name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pool
Specifies the **HpcPool** object.
You cannot specify both the *Name* and the *Pool* parameters.

```yaml
Type: HpcPool
Parameter Sets: pool
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that contains the resource pool.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.

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

### -Weight
Specifies the pool weight.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
This cmdlet was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2). It is not supported in previous versions.

## RELATED LINKS

[Add-HpcPool](/powershell/module/hpcpack2016/add-hpcpool?view=hpc16-ps)

[Get-HpcPool](/powershell/module/hpcpack2016/get-hpcpool?view=hpc16-ps)

[Remove-HpcPool](/powershell/module/hpcpack2016/remove-hpcpool?view=hpc16-ps)
