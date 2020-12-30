---
external help file: SmbClientConfiguration.cdxml-help.xml
Module Name: SmbShare
online version: 
schema: 2.0.0
title: Set-SmbClientConfiguration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: B239F11D-1F32-4D2E-8663-965AF7FED24A
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-SmbClientConfiguration

## SYNOPSIS
Sets the Server Message Block (SMB) client configuration.

## SYNTAX

```
Set-SmbClientConfiguration [-ConnectionCountPerRssNetworkInterface <UInt32>]
 [-DirectoryCacheEntriesMax <UInt32>] [-DirectoryCacheEntrySizeMax <UInt32>] [-DirectoryCacheLifetime <UInt32>]
 [-EnableBandwidthThrottling <Boolean>] [-EnableByteRangeLockingOnReadOnlyFiles <Boolean>]
 [-EnableLargeMtu <Boolean>] [-EnableMultiChannel <Boolean>] [-DormantFileLimit <UInt32>]
 [-EnableSecuritySignature <Boolean>] [-ExtendedSessionTimeout <UInt32>] [-FileInfoCacheEntriesMax <UInt32>]
 [-FileInfoCacheLifetime <UInt32>] [-FileNotFoundCacheEntriesMax <UInt32>]
 [-FileNotFoundCacheLifetime <UInt32>] [-KeepConn <UInt32>] [-MaxCmds <UInt32>]
 [-MaximumConnectionCountPerServer <UInt32>] [-OplocksDisabled <Boolean>] [-RequireSecuritySignature <Boolean>]
 [-SessionTimeout <UInt32>] [-UseOpportunisticLocking <Boolean>] [-WindowSizeThreshold <UInt32>]
 [-EnableLoadBalanceScaleOut <Boolean>] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SmbClientConfiguration** cmdlet sets the Server Message Block (SMB) client configuration.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-SmbClientConfiguration -ConnectionCountPerRssNetworkInterface 8
Confirm 
Are you sure you want to perform this action? 
Performing operation 'Modify' on Target 'SMB Client Configuration'. 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

This example sets the SMB client configuration.

### EXAMPLE 2
```
PS C:\>Set-SmbClientConfiguration -ConnectionCountPerRssNetworkInterface 4 -Force
```

This example sets the SMB client configuration without user confirmation.

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

### -ConnectionCountPerRssNetworkInterface
Specifies the SMB connection count per each RSS network interface.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectoryCacheEntriesMax
Specifies the maximum cache entries that can be in the directory cache.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectoryCacheEntrySizeMax
Specifies the maximum size of directory cache entry.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectoryCacheLifetime
Specifies the directory cache lifetime.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DormantFileLimit
Specifies the dormant file limit.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableBandwidthThrottling
Indicates that bandwidth throttling is enabled.

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

### -EnableByteRangeLockingOnReadOnlyFiles
Indicates that byte range locking on read-only files is enabled.

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

### -EnableLargeMtu
Indicates that large MTU is enabled.

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

### -EnableLoadBalanceScaleOut
Indicates whether load balance scale out is enabled.

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

### -EnableMultiChannel
Indicates that multi-channel is enabled.

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

### -EnableSecuritySignature
Indicates that the security signature is enabled.

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

### -ExtendedSessionTimeout
Specifies the extended session timeout.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileInfoCacheEntriesMax
Specifies the maximum number entries that can be in the file information cache.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileInfoCacheLifetime
Specifies the file information cache lifetime.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileNotFoundCacheEntriesMax
Specifies the maximum number entries that can be in the file not found cache.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileNotFoundCacheLifetime
Specifies the file not found cache lifetime.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -KeepConn
Specifies the time, in seconds, before the SMB client session is automatically disconnected.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxCmds
Specifies the maximum number of concurrent outstanding network requests that the SMB client supports.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumConnectionCountPerServer
Specifies the maximum connection count per server.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OplocksDisabled
Indicates that opportunistic locks are disabled.

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

### -RequireSecuritySignature
Indicates that the security signature is required.

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

### -SessionTimeout
Specifies the session timeout.

```yaml
Type: UInt32
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

### -UseOpportunisticLocking
Indicates that opportunistic locks are used.

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

### -WindowSizeThreshold
Specifies the window size threshold.

```yaml
Type: UInt32
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

### None

## NOTES

## RELATED LINKS

[Get-SmbClientConfiguration](./Get-SmbClientConfiguration.md)

