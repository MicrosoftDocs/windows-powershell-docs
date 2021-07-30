---
external help file: FSRM_Cmdlets.xml
Module Name: FileServerResourceManager
online version: https://docs.microsoft.com/powershell/module/fileserverresourcemanager/set-fsrmquotatemplate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-FsrmQuotaTemplate

## SYNOPSIS
Changes configuration settings for FSRM quota templates.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-FsrmQuotaTemplate [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-Description <String>]
 [-PassThru] [-Size <UInt64>] [-SoftLimit] [-Threshold <CimInstance[]>] [-ThrottleLimit <Int32>]
 [-UpdateDerived] [-UpdateDerivedMatching] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-FsrmQuotaTemplate [-AsJob] [-CimSession <CimSession[]>] [-Description <String>] [-PassThru]
 [-Size <UInt64>] [-SoftLimit] [-Threshold <CimInstance[]>] [-ThrottleLimit <Int32>] [-UpdateDerived]
 [-UpdateDerivedMatching] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-FsrmQuotaTemplate** cmdlet changes configuration settings for one or more File Server Resource Manager (FSRM) quota templates.

When you make changes to a quota template, you have the option of extending those changes to existing quotas that are derived from the quota template.
You can specify the **UpdateDerivedMatching** parameter to modify only those quotas that still match the original quota template, or you can specify the **UpdateDerived** parameter to modify all quotas that are derived from the quota template, regardless of any modifications that you made to the quotas since you created them.

## EXAMPLES

### Example 1: Change the size limit of a quota template
```
PS C:\>Set-FsrmQuotaTemplate -Name "1GB limit" -Description "limit usage to 1.5 GB." -Size 1.5GB
```

This command changes the quota template named "1GB limit" to have a 1.5GB limit, and adds a description to the quota template.

### Example 2: Change the size limit of all quotas that are derived from a quota template
```
PS C:\>Set-FsrmQuotaTemplate "1GB limit" -Description "limit usage to 1.5 GB." -Size 1.5GB -UpdateDerived
```

This command changes the quota template named "1GB limit" to have a 1.5GB limit.
The **UpdateDerived** parameter indicates that this command updates all quotas on the server that are derived from the quota template to have a 1.5GB limit.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -Description
Specifies a description for the quota.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of quota templates.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### -Size
Specifies the size limit that the quota enforces.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SoftLimit
Indicates that the quota reports on the disk usage with respect to the size limit and run thresholds, but does not enforce the size limit.

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

### -Threshold
Specifies an array of threshold objects.

The threshold object defines a percentage of used space from the available space that can be reached during a file operation, and a set of actions that the server takes when a quota reaches the threshold.
To perform the action when the quota is exceeded, set the threshold to 100 (percent).
You can use the New-FsrmQuotaThreshold cmdlet to create a threshold object.

```yaml
Type: CimInstance[]
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

### -UpdateDerived
Indicates that the server modifies all quotas that are derived from the quota template.
If you specify this parameter, you cannot specify the **UpdateDerivedMatching** parameter.

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

### -UpdateDerivedMatching
Indicates that the server updates only the quotas that are derived from the quota template that you have not modified since you created the quotas.
Specify this parameter if you have quotas that have been modified since they were automatically generated, and you do not want to change them.

If you specify this parameter, you cannot specify the **UpdateDerived** parameter.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMQuotaTemplate

## NOTES

## RELATED LINKS

[Get-FsrmQuotaTemplate](./Get-FsrmQuotaTemplate.md)

[New-FsrmQuotaTemplate](./New-FsrmQuotaTemplate.md)

[Remove-FsrmQuotaTemplate](./Remove-FsrmQuotaTemplate.md)

[New-FsrmQuotaThreshold](./New-FsrmQuotaThreshold.md)

