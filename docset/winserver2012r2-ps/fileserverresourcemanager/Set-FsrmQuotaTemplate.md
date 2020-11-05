---
external help file: FsrmQuotaTemplate.cdxml-help.xml
Module Name: FileServerResourceManager
online version: 
schema: 2.0.0
title: Set-FsrmQuotaTemplate
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 1517E303-B084-4BE8-BF3B-89808FA98777
---

# Set-FsrmQuotaTemplate

## SYNOPSIS
Changes configuration settings for FSRM quota templates.

## SYNTAX

### Query (cdxml) (Default)
```
Set-FsrmQuotaTemplate [-Name] <String[]> [-Description <String>] [-Size <UInt64>] [-SoftLimit] [-UpdateDerived]
 [-UpdateDerivedMatching] [-Threshold <CimInstance[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-FsrmQuotaTemplate -InputObject <CimInstance[]> [-Description <String>] [-Size <UInt64>] [-SoftLimit]
 [-UpdateDerived] [-UpdateDerivedMatching] [-Threshold <CimInstance[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
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
Parameter Sets: InputObject (cdxml)
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
Parameter Sets: Query (cdxml)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMQuotaTemplate

## NOTES

## RELATED LINKS

[Get-FsrmQuotaTemplate](./Get-FsrmQuotaTemplate.md)

[New-FsrmQuotaTemplate](./New-FsrmQuotaTemplate.md)

[Remove-FsrmQuotaTemplate](./Remove-FsrmQuotaTemplate.md)

[New-FsrmQuotaThreshold](./New-FsrmQuotaThreshold.md)

