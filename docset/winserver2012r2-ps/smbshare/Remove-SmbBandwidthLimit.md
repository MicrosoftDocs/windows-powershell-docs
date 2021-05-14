---
external help file: SmbBandwidthLimit.cdxml-help.xml
Module Name: SmbShare
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/smbshare/remove-smbbandwidthlimit?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-SmbBandwidthLimit
---

# Remove-SmbBandwidthLimit

## SYNOPSIS
Removes SMB bandwidth caps.

## SYNTAX

### Query (cdxml) (Default)
```
Remove-SmbBandwidthLimit [[-Category] <BandwidthLimitCategory[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-SmbBandwidthLimit -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SmbBandwidthLimit** cmdlet removes Server Message Block (SMB) bandwidth caps for the traffic categories that you specify.
SMB bandwidth caps limit the amount of data that the server can send for each traffic category.

## EXAMPLES

### Example 1: Remove SMB bandwidth caps for all categories
```
PS C:\> Remove-SmbBandwidthLimit
```

This command removes defined limits for SMB traffic for all categories.

### Example 2: Remove SMB bandwidth caps for a category
```
PS C:\> Remove-SmbBandwidthLimit -Category LiveMigration
```

This command removes the limit for SMB traffic for Live Migration category.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Specifies an array of categories of the SMB bandwidth limits to remove.
The acceptable values for this parameter are:

- Default
- VirtualMachine
- LiveMigration

```yaml
Type: BandwidthLimitCategory[]
Parameter Sets: Query (cdxml)
Aliases: 
Accepted values: Default, VirtualMachine, LiveMigration

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* Before you can use this cmdlet, you must enable the feature by using the following command: 
`Add-WindowsFeature -Name FS-SMBBW`
For more information, type `Get-Help Install-WindowsFeature`. When you enable the feature, the SMB server creates a new SMB performance counter set that has an **instance per** category. The performance counters in this set use the same counters as the SMB Client Shares performance counters.

## RELATED LINKS

[Install-WindowsFeature](../servermanager/Install-WindowsFeature.md)

[Get-SmbBandwidthLimit](./Get-SmbBandwidthLimit.md)

[Set-SmbBandwidthLimit](./Set-SmbBandwidthLimit.md)

