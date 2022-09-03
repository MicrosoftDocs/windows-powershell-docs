---
external help file: SmbShare_Cmdlets.xml
Module Name: SmbShare
online version: https://docs.microsoft.com/powershell/module/smbshare/set-smbserverconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-SmbServerConfiguration

## SYNOPSIS
Sets the Server Message Block (SMB) server configuration.

## SYNTAX

```
Set-SmbServerConfiguration [-AnnounceComment <String>] [-AnnounceServer <Boolean>] [-AsJob]
 [-AsynchronousCredits <UInt32>] [-AutoDisconnectTimeout <UInt32>] [-AutoShareServer <Boolean>]
 [-AutoShareWorkstation <Boolean>] [-CachedOpenLimit <UInt32>] [-CimSession <CimSession[]>]
 [-DurableHandleV2TimeoutInSeconds <UInt32>] [-EnableAuthenticateUserSharing <Boolean>]
 [-EnableDownlevelTimewarp <Boolean>] [-EnableForcedLogoff <Boolean>] [-EnableLeasing <Boolean>]
 [-EnableMultiChannel <Boolean>] [-EnableOplocks <Boolean>] [-EnableSecuritySignature <Boolean>]
 [-EnableSMB1Protocol <Boolean>] [-EnableSMB2Protocol <Boolean>] [-EnableStrictNameChecking <Boolean>]
 [-EncryptData <Boolean>] [-Force] [-IrpStackSize <UInt32>] [-KeepAliveTime <UInt32>]
 [-MaxChannelPerSession <UInt32>] [-MaxMpxCount <UInt32>] [-MaxSessionPerConnection <UInt32>]
 [-MaxThreadsPerQueue <UInt32>] [-MaxWorkItems <UInt32>] [-NullSessionPipes <String>]
 [-NullSessionShares <String>] [-OplockBreakWait <UInt32>] [-PendingClientTimeoutInSeconds <UInt32>]
 [-RejectUnencryptedAccess <Boolean>] [-RequireSecuritySignature <Boolean>] [-ServerHidden <Boolean>]
 [-Smb2CreditsMax <UInt32>] [-Smb2CreditsMin <UInt32>] [-SmbServerNameHardeningLevel <UInt32>]
 [-ThrottleLimit <Int32>] [-TreatHostAsStableStorage <Boolean>] [-ValidateAliasNotCircular <Boolean>]
 [-ValidateShareScope <Boolean>] [-ValidateShareScopeNotAliased <Boolean>] [-ValidateTargetName <Boolean>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-SmbServerConfiguration** cmdlet sets the Server Message Block (SMB) server configuration. For more information on SMB server and protocol specifications, see [Server Message Block Overview](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831795(v=ws.11)). For protocol specification, see [[MS-SMB2]: Server Message Block (SMB) Protocol Versions 2 and 3](/openspecs/windows_protocols/ms-smb2/5606ad47-5ee0-437a-817e-70c366052962).


## EXAMPLES

### Example 1: Set the SMB Service configuration
```powershell
PS C:\>Set-SmbServerConfiguration -MaxChannelPerSession 16
```
```output
Confirm
Are you sure you want to perform this action?
Performing operation 'Modify' on Target 'SMB Service Configuration'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

This command sets the SMB Service configuration.

### Example 2: Set the SMB Service configuration without confirmation
```powershell
PS C:\>Set-SmbServerConfiguration -MaxChannelPerSession 32 -Force
```

This command sets the SMB Service configuration without user confirmation.

### Example 3: Turn on SMB singing and encryption
```powershell
PS C:\>Set-SmbServerConfiguration -RequireSecuritySignature $True -EnableSecuritySignature $True -EncryptData $True -Confirm:$false
```

This command turns on SMB signing and encryption.

### Example 4: Turn off the default server and workstations shares
```powershell
PS C:\>Set-SmbServerConfiguration -AutoShareServer $False -AutoShareWorkstation $False -Confirm:$false
```

This command turns off the default server and workstations shares.

### Example 5: Turn off server announcements
```powershell
PS C:\>Set-SmbServerConfiguration -ServerHidden $False -AnnounceServer $False -Confirm:$false
```

This command turns off server announcements.

### Example 6: Turn off SMB1
```powershell
PS C:\>Set-SmbServerConfiguration -EnableSMB1Protocol $false
```

This command disables SMB1 on the SMB server.

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
Indicates that this server announces itself via browser announcements.

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

### -AuditSmb1Access
Enables auditing of SMB version 1 protocol in Windows Event Log.

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

### -AutoDisconnectTimeout
Specifies the auto disconnect timeout.

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
Indicate that the default workstation shares are shared out.

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
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DurableHandleV2TimeoutInSeconds
Specifies the durable handle v2 timeout, in seconds.

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
Indicates that authenticate user sharing is enabled.

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
Indicates that down-level timewarp support is disabled.

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
Indicates that forced logoff is enabled.

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
Indicates that leasing is disabled.

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
Indicates that multi-channel is disabled.

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
Indicates that the opportunistic locks are enabled.

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

### -EnableSMB1Protocol
Indicates that the SMB1 protocol is enabled.

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
Indicates that the SMB2 protocol is enabled.

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
Indicates that the server should perform strict name checking on incoming connects.

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
Indicates that the sessions established on this server are encrypted.

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
Specifies how long the create caller will wait on an opportunistic lock break.

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
Specifies the pending client timeout, in seconds.

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
Indicates that the client that does not support encryption is denied access if it attempts to connect to an encrypted share.

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

### -ServerHidden
Indicates that the server announces itself.

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

### -SmbServerNameHardeningLevel
Specifies the SMB server name hardening level.

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

### -TreatHostAsStableStorage
Indicates that the host is treated as the stable storage.

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
Indicates that the aliases that are not circular are validated.

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
Indicates that the share scope being aliased will be validated.

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
Indicates that the target name will be validated.

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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-SmbServerConfiguration](./Get-SmbServerConfiguration.md)
