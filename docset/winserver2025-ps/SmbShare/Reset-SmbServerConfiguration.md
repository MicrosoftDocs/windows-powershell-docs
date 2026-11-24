---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbServerConfiguration.cdxml-help.xml
Module Name: SmbShare
ms.date: 02/22/2024
online version: https://learn.microsoft.com/powershell/module/smbshare/reset-smbserverconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-SmbServerConfiguration
---

# Reset-SmbServerConfiguration

## SYNOPSIS
Resets the Server Message Block (SMB) server configuration parameters to their default values.

## SYNTAX

```
Reset-SmbServerConfiguration [-All] [-AnnounceComment] [-AnnounceServer] [-AsynchronousCredits]
 [-AuditClientCertificateAccess] [-AuditClientDoesNotSupportEncryption]
 [-AuditClientDoesNotSupportSigning] [-AuditInsecureGuestLogon] [-AuditSmb1Access]
 [-AutoShareServer] [-AutoShareWorkstation] [-CachedOpenLimit] [-DisableCompression]
 [-DisableSmbEncryptionOnSecureConnection] [-DurableHandleV2TimeoutInSeconds]
 [-EnableDirectoryHandleLeasing] [-EnableDownlevelTimewarp] [-EnableLeasing] [-EnableMailslots]
 [-EnableMultiChannel] [-EnableOplocks] [-EnableSMB2Protocol] [-EnableSMBQUIC]
 [-EnableStrictNameChecking] [-EncryptData] [-EncryptionCiphers] [-IrpStackSize] [-KeepAliveTime]
 [-MaxChannelPerSession] [-MaxMpxCount] [-MaxSessionPerConnection] [-MaxThreadsPerQueue]
 [-MaxWorkItems] [-NullSessionShares] [-OplockBreakWait] [-PendingClientTimeoutInSeconds]
 [-RejectUnencryptedAccess] [-RequestCompression] [-RestrictNamedpipeAccessViaQuic] [-ServerHidden]
 [-Smb2CreditsMax] [-Smb2CreditsMin] [-Smb2DialectMax] [-Smb2DialectMin]
 [-SmbServerNameHardeningLevel] [-TreatHostAsStableStorage] [-ValidateAliasNotCircular]
 [-ValidateShareScope] [-ValidateShareScopeNotAliased] [-ValidateTargetName] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Reset-SmbServerConfiguration` cmdlet resets SMB server configuration parameters to their
default values. For more information on SMB server and protocol specifications, see
[Overview of file sharing using the SMB 3 protocol in Windows Server](/windows-server/storage/file-server/file-server-smb-overview)
and [[MS-SMB2]:Server Message Block (SMB) Protocol Versions 2 and 3](/openspecs/windows_protocols/ms-smb2/5606ad47-5ee0-437a-817e-70c366052962).

## EXAMPLES

### Example 1: Reset the unencrypted access behavior

```powershell
Reset-SmbServerConfiguration -RejectUnencryptedAccess -Confirm:$false
```

This commands resets only the unencrypted access behavior to its default value without user
confirmation.

## PARAMETERS

### -All

Resets all the SMB server configuration parameters to their default values.

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

### -AnnounceComment

Resets the SMB server announce comment to its default value.

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

### -AnnounceServer

Resets the SMB server announce server to its default value.

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

### -AsynchronousCredits

Resets the asynchronous credits to its default value.

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

### -AuditClientCertificateAccess

Resets the SMB over QUIC client access control audit events to its default value.

> [!NOTE]
> Devices running Windows 11 version 22H2 and earlier may not have access to this parameter.

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

### -AuditClientDoesNotSupportEncryption

Resets auditing of the clients attempts to connect without encryption to the server to its default
value.

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

### -AuditClientDoesNotSupportSigning

Resets auditing of SMB clients that don't support signing to its default value.

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

### -AuditSmb1Access

Resets the auditing of SMB version 1 protocol behavior to its default value.

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

### -AutoShareServer

Resets the automatic sharing behavior for default server shares to its default value.

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

### -AutoShareWorkstation

Resets the automatic sharing behavior for default workstation shares to its default value.

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

### -CachedOpenLimit

Resets the cache open file limit to its default value.

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

### -DisableSmbEncryptionOnSecureConnection

Resets the disable SMB encryption on secure connection behavior to its default value.

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

### -DurableHandleV2TimeoutInSeconds

Resets the durable handle v2 time-out period value to its default value.

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

### -EnableDirectoryHandleLeasing

Resets the directory handle leasing on the server to its default value.

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

### -EnableDownlevelTimewarp

Resets the down-level timewarp support behavior to its default value.

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

### -EnableLeasing

Resets the enable leasing behavior to its default value.

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

To learn more about remote mailslot deprecation, see [Features removed or no
longer developed starting with Windows Server
2025](/windows-server/get-started/removed-deprecated-features-windows-server-2025).

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

Resets the enable multi-channel behavior to its default value.

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

### -EnableOplocks

Resets the opportunistic locks behavior to its default value.

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

### -EnableSMB2Protocol

Resets the SMB2 protocol to its default value.

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

Resets the SMB over QUIC protocol to its default value.

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

### -EnableStrictNameChecking

Resets the strict name checking on incoming connections behavior to its default value.

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

### -EncryptData

Resets the session encryption behavior to its default value.

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

### -IrpStackSize

Resets the IRP stack size default to its default value.

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

### -KeepAliveTime

Resets the keep alive time to its default value.

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

### -MaxChannelPerSession

Resets the maximum channels per session to its default value.

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

### -MaxMpxCount

Resets the maximum MPX count for SMB1 to its default value.

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

### -MaxSessionPerConnection

Resets the maximum sessions per connection to its default value.

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

### -MaxThreadsPerQueue

Resets the maximum threads per queue to its default value.

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

### -MaxWorkItems

Resets the maximum SMB1 work items to its default value.

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

### -NullSessionShares

Resets the null session pipes to its default value.

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

### -OplockBreakWait

Resets how long the create caller waits for an opportunistic lock break to its default value.

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

### -PendingClientTimeoutInSeconds

Resets the pending client time-out period to its default value.

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

### -RejectUnencryptedAccess

Resets the unencrypted access behavior to its default value.

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

Resets the SMB server request compression value to its default value.

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

### -RestrictNamedpipeAccessViaQuic

Resets the named pipes behavior when using SMB over QUIC to its default value.

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

### -ServerHidden

Resets whether the server announces itself to its default value.

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

### -Smb2CreditsMax

Resets the maximum SMB2 credits to its default value.

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

### -Smb2CreditsMin

Resets the minimum SMB2 credits to its default value.

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

Resets the maximum version of the SMB protocol to its default value.

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

Resets the minimum version of the SMB protocol to its default value.

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

### -SmbServerNameHardeningLevel

Resets the SMB Service name hardening level to its default value.

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

### -TreatHostAsStableStorage

Resets whether the host is treated as the stable storage to its default value.

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

### -ValidateAliasNotCircular

Resets whether the aliases that aren't circular are validated to its default value.

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

### -ValidateShareScope

Resets whether the existence of share scopes is checked during share creation to its default value.

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

### -ValidateShareScopeNotAliased

Resets whether the share scope being aliased is validated to its default value.

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

### -ValidateTargetName

Resets whether the target name is validated to its default value.

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
Default value: None
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

[Get-SmbServerConfiguration](Get-SmbServerConfiguration.md)

[Set-SmbServerConfiguration](Set-SmbServerConfiguration.md)
