---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbServerConfiguration.cdxml-help.xml
Module Name: SmbShare
ms.date: 02/22/2024
online version: https://learn.microsoft.com/powershell/module/smbshare/set-smbserverconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SmbServerConfiguration
---

# Set-SmbServerConfiguration

## SYNOPSIS
Sets the Server Message Block (SMB) server configuration.

## SYNTAX

```
Set-SmbServerConfiguration [-AnnounceComment <String>] [-AnnounceServer <Boolean>]
 [-AsynchronousCredits <UInt32>] [-AuditClientCertificateAccess <Boolean>]
 [-AuditClientDoesNotSupportEncryption <Boolean>] [-AuditClientDoesNotSupportSigning <Boolean>]
 [-AuditInsecureGuestLogon <Boolean>] [-AuditSmb1Access <Boolean>]
 [-AutoDisconnectTimeoutInMinutesV1 <UInt32>] [-AutoDisconnectTimeoutInSecondsV2 <UInt32>]
 [-AutoShareServer <Boolean>] [-AutoShareWorkstation <Boolean>] [-CachedOpenLimit <UInt32>]
 [-EnableDirectoryHandleLeasing <Boolean>] [-DisableCompression <Boolean>]
 [-DisableSmbEncryptionOnSecureConnection <Boolean>] [-DurableHandleV2TimeoutInSeconds <UInt32>]
 [-EnableAuthenticateUserSharing <Boolean>] [-EnableDownlevelTimewarp <Boolean>]
 [-EnableForcedLogoff <Boolean>] [-EnableLeasing <Boolean>] [-EnableMailslots <Boolean>]
 [-EnableMultiChannel <Boolean>] [-EnableOplocks <Boolean>] [-EnableSecuritySignature <Boolean>]
 [-EnableSMB1Protocol <Boolean>] [-EnableSMB2Protocol <Boolean>] [-EnableSMBQUIC <Boolean>]
 [-EnableStrictNameChecking <Boolean>] [-EncryptData <Boolean>] [-EncryptionCiphers <String>]
 [-InvalidAuthenticationDelayTimeInMs <UInt32>] [-IrpStackSize <UInt32>] [-KeepAliveTime <UInt32>]
 [-MaxChannelPerSession <UInt32>] [-MaxMpxCount <UInt32>] [-MaxSessionPerConnection <UInt32>]
 [-MaxThreadsPerQueue <UInt32>] [-MaxWorkItems <UInt32>] [-NullSessionPipes <String>]
 [-NullSessionShares <String>] [-OplockBreakWait <UInt32>]
 [-PendingClientTimeoutInSeconds <UInt32>] [-RejectUnencryptedAccess <Boolean>]
 [-RequestCompression <Boolean>] [-RequireSecuritySignature <Boolean>]
 [-RestrictNamedpipeAccessViaQuic <Boolean>] [-ServerHidden <Boolean>] [-Smb2CreditsMax <UInt32>]
 [-Smb2CreditsMin <UInt32>] [-Smb2DialectMax <Smb2DialectMax>] [-Smb2DialectMin <Smb2DialectMin>]
 [-SmbServerNameHardeningLevel <UInt32>] [-TreatHostAsStableStorage <Boolean>]
 [-ValidateAliasNotCircular <Boolean>] [-ValidateShareScope <Boolean>]
 [-ValidateShareScopeNotAliased <Boolean>] [-ValidateTargetName <Boolean>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Set-SmbServerConfiguration` cmdlet sets the Server Message Block (SMB) Service configuration.
For more information on SMB server and protocol specifications, see
[Overview of file sharing using the SMB 3 protocol in Windows Server](/windows-server/storage/file-server/file-server-smb-overview)
and [[MS-SMB2]:Server Message Block (SMB) Protocol Versions 2 and
3](/openspecs/windows_protocols/ms-smb2/5606ad47-5ee0-437a-817e-70c366052962).

## EXAMPLES

### Example 1: Set the SMB Service configuration

```powershell
Set-SmbServerConfiguration -MaxChannelPerSession 16 -Confirm:$false
```

This command sets the SMB Service configuration without user confirmation.

### Example 2: Turn on SMB signing and encryption

```powershell
$Parameters = @{
    RequireSecuritySignature = $true
    EnableSecuritySignature = $true
    EncryptData = $true
    Confirm = $false
}
Set-SmbServerConfiguration @Parameters
```

This command turns on SMB signing and encryption without user confirmation. This example uses
splatting to pass parameter values from the `$Parameters` variable to the command. Learn more about
[Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

### Example 3: Turn off the default server and workstations shares

```powershell
Set-SmbServerConfiguration -AutoShareServer $false -AutoShareWorkstation $false -Confirm:$false
```

This command turns off the default server and workstations shares without user confirmation.

### Example 4: Turn off server announcements

```powershell
Set-SmbServerConfiguration -ServerHidden $false -AnnounceServer $false -Confirm:$false
```

This command turns off server announcements without user confirmation.

### Example 5: Turn off SMB1

```powershell
Set-SmbServerConfiguration -EnableSMB1Protocol $false -Confirm:$false
```

This command disables SMB1 on the SMB server without user confirmation.

### Example 6: Specify encryption ciphers

```powershell
Set-SmbServerConfiguration -EncryptionCiphers "AES_128_GCM, AES_256_GCM" -Confirm:$false
```

This command specifies the encryption ciphers used by the SMB client, and the preferred order
without user confirmation.

## PARAMETERS

### -AnnounceComment

Specifies the announce comment string.

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

### -AnnounceServer

Indicates that this server announces itself by using browser announcements.

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

Specifies the asynchronous credits.

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

### -AuditClientCertificateAccess

Enables SMB over QUIC client access control audit events. There are three possible events: access
allowed, access denied, and error. The access allowed and access denied events list properties of
the client certificate chain and any allow and deny access control entries that apply to the
client certificates.

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

Enables auditing of SMB clients that don't support encryption. Clients that connect and don't list
SMB encryption in their supported capabilities will be recorded in the Windows event log.

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

### -AuditClientDoesNotSupportSigning

Enables auditing of the clients attempts to connect without signing to the server. The server logs
an audit event when a client attempts to connect to the server without using message signing.

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

### -AuditInsecureGuestLogon

Specifies whether to audit insecure guest logon attempts. When enabled insecure guest logons will
appear in Windows Event Viewer.

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

### -AuditSmb1Access

Enables the auditing of SMB version 1 protocol behavior.

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

### -AutoDisconnectTimeoutInMinutesV1

Specifies the v1 auto disconnect time-out period, in minutes.

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

### -AutoDisconnectTimeoutInSecondsV2

Specifies the v2 auto disconnect time-out period, in seconds.

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

### -AutoShareServer

Indicates that the default server shares are shared out.

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

### -AutoShareWorkstation

Indicates whether the default workstation shares are shared out.

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

### -CachedOpenLimit

Specifies the maximum number of cached open files.

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

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or
[Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
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

Indicates that the SMB server should never compress files even if client or application requested
it.

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

### -DisableSmbEncryptionOnSecureConnection

Specifies that SMB encryption will also be used if configured on the SMB server. By default, QUIC
encryption only is used in order to avoid double encryption affecting performance unnecessarily. If
a client requires SMB encryption using
`Set-SmbClientConfiguration -ForceSMBEncryptionOverQuic $true` then the
**DisableSmbEncryptionOnSecureConnection** value is ignored and SMB encryption occurs.

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

### -DurableHandleV2TimeoutInSeconds

Specifies the durable handle v2 time-out period, in seconds.

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

### -EnableAuthenticateUserSharing

Indicates whether authenticate user sharing is enabled.

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

### -EnableDirectoryHandleLeasing

Enables directory handle leasing on the server. When directory handle leasing is enabled, the
server can cache directory handles for a longer period of time, which can improve performance for
certain workloads. This can be particularly useful in scenarios where there are a large number of
directory operations being performed on the server.

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

### -EnableDownlevelTimewarp

Indicates whether down-level timewarp support is disabled.

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

### -EnableForcedLogoff

Indicates whether forced logoff is enabled.

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

### -EnableLeasing

Indicates whether leasing is disabled.

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

### -EnableMailslots

Specifies whether to enable mailslots. If this parameter is specified, mailslots will be enabled.
Beginning with Windows Server 2025 and Windows 11 Insider Preview Build 25314, remote mailslots are
disabled by default.

To learn more about remote mailslot deprecation, see [Features removed or no
longer developed starting with Windows Server
2025](/windows-server/get-started/removed-deprecated-features-windows-server-2025).

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

Indicates whether multi-channel is disabled.

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

### -EnableOplocks

Indicates whether the opportunistic locks are enabled.

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

Indicates whether the security signature is enabled.

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

### -EnableSMB1Protocol

Indicates whether the SMB1 protocol is enabled.

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

### -EnableSMB2Protocol

Indicates whether the SMB2 protocol is enabled.

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

### -EnableSMBQUIC

Indicates whether the SMB over QUIC protocol is enabled.

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

### -EnableStrictNameChecking

Indicates whether the server should perform strict name checking on incoming connects.

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

### -EncryptData

Indicates whether the sessions established on this server are encrypted.

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

### -EncryptionCiphers

Specifies the encryption ciphers used by the SMB server and the preferred order.

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

### -InvalidAuthenticationDelayTimeInMs

Specifies the length of time in milliseconds that the server should delay before responding to an
authentication request that has been deemed invalid, such as an incorrect user name or password.

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

### -IrpStackSize

Specifies the default IRP stack size.

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

### -KeepAliveTime

Specifies the keep alive time.

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

### -MaxChannelPerSession

Specifies the maximum channels per session.

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

### -MaxMpxCount

Specifies the maximum MPX count for SMB1.

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

### -MaxSessionPerConnection

Specifies the maximum sessions per connection.

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

### -MaxThreadsPerQueue

Specifies the maximum threads per queue.

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

### -MaxWorkItems

Specifies the maximum SMB1 work items.

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

### -NullSessionPipes

Specifies the null session pipes.

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

### -NullSessionShares

Specifies the null session shares.

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

### -OplockBreakWait

Specifies how long the create caller waits for an opportunistic lock break.

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

### -PendingClientTimeoutInSeconds

Specifies the pending client time-out period, in seconds.

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

### -RejectUnencryptedAccess

Indicates whether the client that doesn't support encryption is denied access if it attempts to
connect to an encrypted share.

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

### -RequestCompression

Indicates if SMB server should always request compression even if client or application didn't
specify it.

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

Indicates whether the security signature is required.

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

### -RestrictNamedpipeAccessViaQuic

Specifies that named pipes are allowed when using SMB over QUIC. A value of `$true` prevents use of
named pipes and is the default.

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

### -ServerHidden

Indicates whether the server announces itself.

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

### -Smb2CreditsMax

Specifies the maximum SMB2 credits.

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

### -Smb2CreditsMin

Specifies the minimum SMB2 credits.

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

### -Smb2DialectMax

This parameter specifies the maximum version of the SMB protocol to be used. Acceptable values are:

- None – There is no maximum protocol version specified, the server can use any supported version.
- SMB202 – SMB 2.0.2 is the maximum version accepted by the SMB Server
- SMB210 - SMB 2.1.0 is the maximum version accepted by the SMB Server
- SMB300 - SMB 3.0.0 is the maximum version accepted by the SMB Server
- SMB302 - SMB 3.0.2 is the maximum version accepted by the SMB Server
- SMB311 - SMB 3.1.1 is the maximum version accepted by the SMB Server

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

This parameter specifies the minimum version of the SMB protocol to be used. Acceptable values are:

- None – There is no maximum protocol version specified, the server can use any supported version.
- SMB202 – SMB 2.0.2 is the maximum version accepted by the SMB Server
- SMB210 - SMB 2.1.0 is the maximum version accepted by the SMB Server
- SMB300 - SMB 3.0.0 is the maximum version accepted by the SMB Server
- SMB302 - SMB 3.0.2 is the maximum version accepted by the SMB Server
- SMB311 - SMB 3.1.1 is the maximum version accepted by the SMB Server

```yaml
Type: Smb2DialectMin
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

Controls the level of validation that a server performs on the service principal name (SPN) that is
provided by the client device when the client establishes a session using Server Message Block
(SMB). The acceptable values are:

- `0`: Don't enforce SPN check.
- `1`: Allow clients who didn't provide the target, but fail those who do provide the target and it
  doesn't match.
- `2`: Only allow clients who supply matching targets.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:
Accepted values: 0, 1, 2

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
computer.

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

### -TreatHostAsStableStorage

Indicates whether the host is treated as the stable storage.

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

### -ValidateAliasNotCircular

Indicates whether the aliases that aren't circular are validated.

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

### -ValidateShareScope

Indicates that the existence of share scopes is checked during share creation.

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

### -ValidateShareScopeNotAliased

Indicates whether the share scope being aliased is validated.

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

### -ValidateTargetName

Indicates whether the target name is validated.

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

### System.Object

## NOTES

## RELATED LINKS

[Get-SmbServerConfiguration](Get-SmbServerConfiguration.md)

[Reset-SmbServerConfiguration](Reset-SmbServerConfiguration.md)
