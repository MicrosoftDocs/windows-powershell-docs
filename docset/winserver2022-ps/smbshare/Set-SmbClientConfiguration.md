---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbClientConfiguration.cdxml-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/smbshare/set-smbclientconfiguration?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SmbClientConfiguration
---

# Set-SmbClientConfiguration

## SYNOPSIS
Sets the SMB client configuration.

## SYNTAX

```
Set-SmbClientConfiguration [-SkipCertificateCheck <Boolean>] [-ConnectionCountPerRssNetworkInterface <UInt32>]
 [-DirectoryCacheEntriesMax <UInt32>] [-DirectoryCacheEntrySizeMax <UInt32>] [-DirectoryCacheLifetime <UInt32>]
 [-DormantFileLimit <UInt32>] [-EnableBandwidthThrottling <Boolean>]
 [-EnableByteRangeLockingOnReadOnlyFiles <Boolean>] [-EnableInsecureGuestLogons <Boolean>]
 [-EnableLargeMtu <Boolean>] [-EnableLoadBalanceScaleOut <Boolean>] [-EnableMultiChannel <Boolean>]
 [-EnableSecuritySignature <Boolean>] [-ExtendedSessionTimeout <UInt32>] [-FileInfoCacheEntriesMax <UInt32>]
 [-FileInfoCacheLifetime <UInt32>] [-FileNotFoundCacheEntriesMax <UInt32>]
 [-FileNotFoundCacheLifetime <UInt32>] [-ForceSMBEncryptionOverQuic <Boolean>] [-KeepConn <UInt32>]
 [-MaxCmds <UInt32>] [-MaximumConnectionCountPerServer <UInt32>] [-OplocksDisabled <Boolean>]
 [-RequireSecuritySignature <Boolean>] [-SessionTimeout <UInt32>] [-UseOpportunisticLocking <Boolean>]
 [-WindowSizeThreshold <UInt32>] [-DisableCompression <Boolean>] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SmbClientConfiguration** cmdlet sets the Server Message Block (SMB) client configuration.

## EXAMPLES

### Example 1: Set the SMB client configuration
```
PS C:\>Set-SmbClientConfiguration -ConnectionCountPerRssNetworkInterface 8
Confirm 
Are you sure you want to perform this action? 
Performing operation 'Modify' on Target 'SMB Client Configuration'. 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

This command sets the SMB client configuration.

### Example 2: Set the SMB client configuration without confirmation
```
PS C:\>Set-SmbClientConfiguration -ConnectionCountPerRssNetworkInterface 4 -Force
```

This command sets the SMB client configuration without user confirmation.

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

### -DisableCompression
Specifies that the SMB client ignores all requests for compression from applications or SMB servers.

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

### -EnableInsecureGuestLogons
Indicates whether SMB client will allow insecure guest logons to an SMB server.

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
Specifies the extended session time-out.

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

### -ForceSMBEncryptionOverQuic
Specifies that the SMB client uses SMB encryption inside of the SMB over QUIC TLS 1.3 encrypted tunnel even if the SMB server does not require it.

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
Specifies the session time-out.

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

### -SkipCertificateCheck
Specifies that the SMB client not trust the SMB over QUIC SMB server certificate issuer. Required when using a self-signed certificate.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-SmbClientConfiguration](./Get-SmbClientConfiguration.md)

