---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterStorageSpacesDirect.cdxml-help.xml
Module Name: FailoverClusters
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-clusterstoragespacesdirectdisk?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ClusterStorageSpacesDirectDisk
---

# Set-ClusterStorageSpacesDirectDisk

## SYNOPSIS
Configures the system to enable S2D to claim or not claim specific physical disks.

## SYNTAX

```
Set-ClusterStorageSpacesDirectDisk [-CanBeClaimed <Boolean>] [-PhysicalDiskIds <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ClusterStorageSpacesDirectDisk** cmdlet configures the system to enable Storage Spaces Direct (S2D) to claim or not claim specific physical disks.
Disks marked to be not claimed by S2D remain untouched so that they can be used for other purposes.

To avoid possible clean up and warnings, we recommend that you run this cmdlet before you enable S2D.
Alternatively, you can run this cmdlet after you enable S2D.

## EXAMPLES

### Example 1: Configure disks not to be claimed
```
PS C:\> Set-ClusterStorageSpacesDirectDisk -CimSession "K0619-C1.contoso.com" -CanBeClaimed:$False -PhysicalDiskIds "55CD2E404B75A3FC","50014EE05950DD7C"
```

This command configures the system that physical disks that have the IDs 55CD2E404B75A3FC and 50014EE05950DD7C cannot be claimed by S2D.
In this example, the *CanBeClaimed* parameter is explicitly specified as $False.
Omitting that parameter indicates that the specified physical disks can be claimed.

## PARAMETERS

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

### -CanBeClaimed
Indicates that S2D can claim the physical disks specified by the *PhysicalDiskIds* parameter.
If you do not specify this parameter, this cmdlet indicates that the specified physical disks can be claimed.

```yaml
Type: Boolean
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

### -PhysicalDiskIds
Specifies an array of unique IDs of physical disks.
This cmdlet set S2D to claim or not claim the specified disks.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-ClusterStorageSpacesDirect](./Disable-ClusterStorageSpacesDirect.md)

[Enable-ClusterStorageSpacesDirect](./Enable-ClusterStorageSpacesDirect.md)

[Get-ClusterStorageSpacesDirect](./Get-ClusterStorageSpacesDirect.md)

[Repair-ClusterStorageSpacesDirect](./Repair-ClusterStorageSpacesDirect.md)

