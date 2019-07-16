---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbServerConfiguration.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-SmbServerConfiguration
ms.reviewer:
ms.assetid: 8B5FF5C0-5D2F-4030-8F8E-C2C3B3E8906E
---

# Set-SmbServerConfiguration

## SYNOPSIS
Sets the SMB Service configuration.

## SYNTAX

```
Set-SmbServerConfiguration [-AnnounceComment <String>] [-AnnounceServer <Boolean>]
 [-AsynchronousCredits <UInt32>] [-AuditSmb1Access <Boolean>] [-AutoDisconnectTimeout <UInt32>]
 [-AutoShareServer <Boolean>] [-AutoShareWorkstation <Boolean>] [-CachedOpenLimit <UInt32>]
 [-DurableHandleV2TimeoutInSeconds <UInt32>] [-EnableAuthenticateUserSharing <Boolean>]
 [-EnableDownlevelTimewarp <Boolean>] [-EnableForcedLogoff <Boolean>] [-EnableLeasing <Boolean>]
 [-EnableMultiChannel <Boolean>] [-EnableOplocks <Boolean>] [-EnableSecuritySignature <Boolean>]
 [-EnableSMB1Protocol <Boolean>] [-EnableSMB2Protocol <Boolean>] [-EnableStrictNameChecking <Boolean>]
 [-EncryptData <Boolean>] [-IrpStackSize <UInt32>] [-KeepAliveTime <UInt32>] [-MaxChannelPerSession <UInt32>]
 [-MaxMpxCount <UInt32>] [-MaxSessionPerConnection <UInt32>] [-MaxThreadsPerQueue <UInt32>]
 [-MaxWorkItems <UInt32>] [-NullSessionPipes <String>] [-NullSessionShares <String>]
 [-OplockBreakWait <UInt32>] [-PendingClientTimeoutInSeconds <UInt32>] [-RejectUnencryptedAccess <Boolean>]
 [-RequireSecuritySignature <Boolean>] [-ServerHidden <Boolean>] [-Smb2CreditsMax <UInt32>]
 [-Smb2CreditsMin <UInt32>] [-SmbServerNameHardeningLevel <UInt32>] [-TreatHostAsStableStorage <Boolean>]
 [-ValidateAliasNotCircular <Boolean>] [-ValidateShareScope <Boolean>]
 [-ValidateShareScopeNotAliased <Boolean>] [-ValidateTargetName <Boolean>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SmbServerConfiguration** cmdlet sets the Server Message Block (SMB) Service configuration.

## EXAMPLES

### Example 1: Set the SMB Service configuration
```
PS C:\>Set-SmbServerConfiguration -MaxChannelPerSession 16
Confirm 
Are you sure you want to perform this action? 
Performing operation 'Modify' on Target 'SMB Service Configuration'. 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

This command sets the SMB Service configuration.

### Example 2: Set the SMB Service configuration without confirmation
```
PS C:\>Set-SmbServerConfiguration -MaxChannelPerSession 32 -Force
```

This command sets the SMB Service configuration without user confirmation.

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
Specifies the auto disconnect time-out.

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
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Indicates whether the client that does not support encryption is denied access if it attempts to connect to an encrypted share.

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

### -SmbServerNameHardeningLevel
Specifies the SMB Service name hardening level.

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
Indicates whether the aliases that are not circular are validated.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-SmbServerConfiguration](./Get-SmbServerConfiguration.md)

