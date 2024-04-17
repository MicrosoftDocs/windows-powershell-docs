---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Mpio-help.xml
Module Name: MPIO
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/mpio/set-mpiosetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-MPIOSetting
---

# Set-MPIOSetting

## SYNOPSIS
Changes MPIO settings.

## SYNTAX

```
Set-MPIOSetting [[-NewPathVerificationPeriod] <Int32>] [[-NewPathVerificationState] <String>]
 [[-NewPDORemovePeriod] <Int32>] [[-NewRetryCount] <Int32>] [[-NewRetryInterval] <Int32>]
 [[-NewDiskTimeout] <Int32>] [[-CustomPathRecovery] <String>] [[-NewPathRecoveryInterval] <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-MPIOSetting** cmdlet changes Microsoft Multipath I/O (MPIO) settings.
The settings are as follows:

- PathVerificationState
- PathVerificationPeriod
- PDORemovePeriod
- RetryCount
- RetryInterval
- UseCustomPathRecoveryTime
- CustomPathRecoveryTime
- DiskTimeoutValue

You may be prompted to restart the computer for your changes to take effect.

## EXAMPLES

### Example 1: Change the disk time-out
```
PS C:\> Set-MPIOSetting -NewDiskTimeout 30
```

This command sets the disk time-out value to 30 seconds.
The system prompts you to restart after you change settings.

You can use the **Get-MPIOSetting** cmdlet to verify the change.

## PARAMETERS

### -CustomPathRecovery
Specifies whether MPIO performs custom path recovery.
The acceptable values for this parameter are: Enabled and Disabled.
The default value is Disabled.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewDiskTimeout
Specifies the disk time-out value, in seconds.
This value is the length of time the server waits before it marks the I/O request as timed out.
The default value for DiskTimeoutValue is 120.
We recommend a maximum value of 30.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewPDORemovePeriod
Specifies a physical device object (PDO) removal period, in seconds.
This period is the length of time the server waits after all paths to a PDO have failed before it removes the PDO.
The default value is 20.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewPathRecoveryInterval
Specifies a custom path recovery time, in seconds.
This is the length of time before the server tries path recovery.
The default value is 40.
This parameter is not relevant unless you specify Enabled for the *CustomPathRecovery* parameter.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewPathVerificationPeriod
Specifies a path verification period, in seconds.
This is the length of time for the server to verify every path.
This parameter is not relevant unless the path verification state has a value of Enabled.
The default value is 30.

You can set the path verification state by using the *NewPathVerificationState* parameter.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewPathVerificationState
Specifies whether to enable path verification.
The acceptable values for this parameter are: Enabled and Disabled.
The default value is Disabled.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewRetryCount
Specifies the number of times to retry an I/O request.
The default value is three times.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewRetryInterval
Specifies a retry interval, in seconds.
This is the length of time after which the server retries a failed I/O request.
The default value is one second.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MPIOSetting](./Get-MPIOSetting.md)

