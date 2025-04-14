---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbBandwidthLimit.cdxml-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/get-smbbandwidthlimit?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmbBandwidthLimit
---

# Get-SmbBandwidthLimit

## SYNOPSIS
Gets the list of SMB bandwidth caps for each traffic category.

## SYNTAX

```
Get-SmbBandwidthLimit [[-Category] <BandwidthLimitCategory[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmbBandwidthLimit** cmdlet gets the list of Server Message Block (SMB) bandwidth caps for each traffic category.
SMB bandwidth caps limit the amount of data that the server can send for each traffic category.

## EXAMPLES

### Example 1: Get SMB bandwidth caps for all categories
```
PS C:\> Get-SmbBandwidthLimit
```

This command gets the SMB bandwidth caps for all traffic categories.

### Example 2: Get SMB bandwidth caps for a category
```
PS C:\> Get-SmbBandWidthLimit -Category LiveMigration
```

This command gets the SMB bandwidth cap for Live Migration traffic.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -Category
Specifies an array of categories of SMB bandwidth limits to get.
The acceptable values for this parameter are:

- Default
- VirtualMachine
- LiveMigration

```yaml
Type: BandwidthLimitCategory[]
Parameter Sets: (All)
Aliases: 
Accepted values: Default, VirtualMachine, LiveMigration, StorageReplication

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* Before you can use this cmdlet, you must enable the feature by using the following command: 
`Install-WindowsFeature -Name FS-SMBBW`
For more information, type `Get-Help Install-WindowsFeature`. When you enable the feature, the SMB server creates a new SMB performance counter set that has an **instance per** category. The performance counters in this set use the same counters as the SMB Client Shares performance counters.

## RELATED LINKS

[Install-WindowsFeature](/powershell/module/servermanager/install-windowsfeature)

[Set-SmbBandwidthLimit](./Set-SmbBandwidthLimit.md)

[Remove-SmbBandwidthLimit](./Remove-SmbBandwidthLimit.md)

