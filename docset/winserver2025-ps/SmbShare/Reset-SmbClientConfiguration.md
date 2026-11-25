---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbClientConfiguration.cdxml-help.xml
Module Name: SmbShare
ms.date: 02/22/2024
online version: https://learn.microsoft.com/powershell/module/smbshare/reset-smbclientconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-SmbClientConfiguration
---

# Reset-SmbClientConfiguration

## SYNOPSIS
Resets the Server Message Block (SMB) client configuration parameters to their default values.

## SYNTAX

```
Reset-SmbClientConfiguration [-All] [-AuditInsecureGuestLogon]
 [-AuditServerDoesNotSupportEncryption] [-AuditServerDoesNotSupportSigning] [-BlockNTLM]
 [-CompressibilitySampling] [-ConnectionCountPerRssNetworkInterface] [-DirectoryCacheEntriesMax]
 [-DirectoryCacheEntrySizeMax] [-DirectoryCacheLifetime] [-DisableCompression] [-DormantFileLimit]
 [-EnableBandwidthThrottling] [-EnableByteRangeLockingOnReadOnlyFiles] [-EnableLargeMtu]
 [-EnableLoadBalanceScaleOut] [-EnableMailslots] [-EnableMultiChannel] [-EnableSMBQUIC]
 [-EncryptionCiphers] [-ExtendedSessionTimeout] [-FileInfoCacheEntriesMax] [-FileInfoCacheLifetime]
 [-FileNotFoundCacheEntriesMax] [-FileNotFoundCacheLifetime] [-ForceSMBEncryptionOverQuic]
 [-InvalidAuthenticationCacheLifetime] [-KeepConn] [-MaxCmds] [-MaximumConnectionCountPerServer]
 [-OplocksDisabled] [-RequestCompression] [-RequireEncryption] [-SessionTimeout]
 [-SkipCertificateCheck] [-Smb2DialectMax] [-Smb2DialectMin] [-UseOpportunisticLocking]
 [-WindowSizeThreshold] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Reset-SmbClientConfiguration` cmdlet resets SMB client configuration parameters to their
default values.

> [!NOTE]
> The **EnableSMBQUIC** parameter is available starting with Windows 11 Insider Preview
> build 26090 and later.

## EXAMPLES

### Example 1: Reset the large MTU behavior

```powershell
Reset-SmbClientConfiguration -EnableLargeMtu -Confirm:$false
```

This commands resets only the large MTU behavior to its default value without user confirmation.

## PARAMETERS

### -All

Resets all the SMB client configuration parameters to their default values.

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

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

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

### -AuditInsecureGuestLogon

Resets whether to audit insecure guest logon attempts to its default value.

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

### -AuditServerDoesNotSupportEncryption

Resets whether to audit when a server doesn't support encryption to its default value.

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

### -AuditServerDoesNotSupportSigning

Resets whether to audit when a server doesn't support message signing to its default value.

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

### -BlockNTLM

Resets whether to block NT LAN Manager (NTLM) authentication to its default value.

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

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession)
or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
current session on the local computer.

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

### -CompressibilitySampling

Resets the compression sampling behavior to its default value.

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

### -ConnectionCountPerRssNetworkInterface

Resets the SMB connection count for each RSS network interface to its default value.

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

### -DirectoryCacheEntriesMax

Resets the maximum cache entries that can be in the directory cache to its default value.

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

### -DirectoryCacheEntrySizeMax

Resets the maximum size of directory cache entry value to its default value.

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

### -DirectoryCacheLifetime

Resets the directory cache lifetime to its default value.

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

### -DisableCompression

Resets the SMB compression behavior to its default value.

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

### -DormantFileLimit

Resets the dormant file limit to its default value.

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

### -EnableBandwidthThrottling

Resets the bandwidth throttling behavior to its default value.

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

### -EnableByteRangeLockingOnReadOnlyFiles

Resets the enabled byte range locking behavior on read-only file to its default value.

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

### -EnableLargeMtu

Resets the enable large MTU value to its default value.

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

### -EnableLoadBalanceScaleOut

Resets the enable load balance scale out value to its default value.

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

### -EnableMailslots

Resets mailslots to its default value.

Beginning with Windows Server 2025 and Windows 11 Insider Preview Build 25314, remote mailslots are
disabled by default.

To learn more about remote mailslot deprecation, see [Features removed or no longer developed
starting with Windows Server 2025](/windows-server/get-started/removed-deprecated-features-windows-server-2025).

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

### -EnableMultiChannel

Resets the enable multi-channel value to its default value.

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

### -EnableSMBQUIC

Resets the SMB over QUIC client protocol to its default value.

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

### -EncryptionCiphers

Resets the encryption ciphers used by the SMB client to its default value and order.

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

### -ExtendedSessionTimeout

Resets the extended session time-out value to its default value.

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

### -FileInfoCacheEntriesMax

Resets the maximum number entries that can be in the file information cache to its default value.

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

### -FileInfoCacheLifetime

Resets the file information cache lifetime value to its default value.

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

### -FileNotFoundCacheEntriesMax

Resets the maximum number entries that can be in the file not found cache to its default value.

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

### -FileNotFoundCacheLifetime

Resets the file not found cache lifetime value to its default value.

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

Resets the for SMB encryption over QUIC value to its default value.

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

### -InvalidAuthenticationCacheLifetime

Resets the length of time (in seconds) that an invalid authentication cache entry should be kept
before being removed to its default value.

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

Reset the time, in seconds, before the SMB client session is automatically disconnected to its
default value.

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

### -MaxCmds

Resets the maximum number of concurrent outstanding network requests that the SMB client supports to
its default value.

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

### -MaximumConnectionCountPerServer

Resets the maximum connection count per server to its default value.

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

### -OplocksDisabled

Resets the opportunistic locks disabled value to its default value.

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

### -RequestCompression

Resets the SMB client request compression value to its default value.

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

### -RequireEncryption

Specifies whether or not encryption should be required for all SMB traffic. When this parameter is
set to `$true`, all SMB traffic must be encrypted. If it is set to `$false` (the default),
encryption is not required, but may still be negotiated if both the client and server support it.

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

### -SessionTimeout

Resets the session time-out value to its default value.

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

### -SkipCertificateCheck

Resets the skip certificate check value to its default value.

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

### -Smb2DialectMax

Resets the maximum version of the SMB protocol to be used back to its default value.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Accepted values: None, SMB202, SMB210, SMB300, SMB302, SMB311

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Smb2DialectMin

Resets the minimum version of the SMB protocol to be used back to its default value.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Accepted values: None, SMB202, SMB210, SMB300, SMB302, SMB311

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

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

Resets the use opportunistic locks value to its default value.

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

### -WindowSizeThreshold

Resets the window size threshold value to its default value.

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
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[Get-SmbClientConfiguration](Get-SmbClientConfiguration.md)

[Set-SmbClientConfiguration](Set-SmbClientConfiguration.md)
