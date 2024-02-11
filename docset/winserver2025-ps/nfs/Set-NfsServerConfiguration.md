---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NfsServerConfig.cmdletDefinition.cdxml-help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/set-nfsserverconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NfsServerConfiguration
---

# Set-NfsServerConfiguration

## SYNOPSIS
Changes configuration settings for an NFS server.

## SYNTAX

```
Set-NfsServerConfiguration [-InputObject <CimInstance[]>] [-PortmapProtocol <String[]>]
 [-MountProtocol <String[]>] [-Nfsprotocol <String[]>] [-NlmProtocol <String[]>] [-NsmProtocol <String[]>]
 [-MapServerProtocol <String[]>] [-NisProtocol <String[]>] [-EnableNFSV2 <Boolean>] [-EnableNFSV3 <Boolean>]
 [-EnableNFSV4 <Boolean>] [-EnableAuthenticationRenewal <Boolean>] [-AuthenticationRenewalIntervalSec <UInt32>]
 [-DirectoryCacheSize <UInt32>] [-CharacterTranslationFile <String>] [-HideFilesBeginningInDot <Boolean>]
 [-NlmGracePeriodSec <UInt32>] [-LogActivity <String[]>] [-GracePeriodSec <UInt32>]
 [-NetgroupCacheTimeoutSec <UInt32>] [-PreserveInheritance <Boolean>] [-UnmappedUserAccount <String>]
 [-WorldAccount <String>] [-AlwaysOpenByName <Boolean>] [-LeasePeriodSec <UInt32>] [-ClearMappingCache]
 [-OnlineTimeoutSec <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NfsServerConfig** cmdlet changes the configuration settings for an existing Network File System (NFS) server.

For some changes to take effect, you must restart Services for NFS.
The cmdlet prompts you to restart if necessary.

## EXAMPLES

### Example 1: Set a grace period on a local NFS server
```
PS C:\> Set-NfsServerConfiguration -NlmGracePeriodSec 45 -GracePeriodSec 240
```

This command sets the grace period for the NLM protocol to 45 seconds and sets the grace period for NFS v4.1 to 240 seconds on a local NFS server.

### Example 2: Set NFS versions on a local NFS server
```
PS C:\> Set-NfsServerConfiguration -EnableNfsv2 $False -EnableNfsv4 $True -EnableNfsv3 $True
```

This command disables versions 2 and 3 of the NFS protocol and enables NFS v4.1 on a local NFS server.

## PARAMETERS

### -AlwaysOpenByName
Specifies whether an NFS server opens files and directories by name, instead of opening by file ID.
You can enable this setting for compatibility with filter drivers that intercept requests for opening files and directories by file name, or for applications that rely on directory change notifications to work with NFS shares.

The default value is $False.
By default, an NFS server opens files and directories by ID to improve performance.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: OpenByName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Indicates that this cmdlet runs the command as a background job on a remote computer.
Use this parameter to run commands that take an extensive time to finish.

When you use the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.
You can continue to work in the session while the job finishes.
To manage the job, use the **Job** cmdlets.
To get the job results, use the Receive-Job cmdlet.

The *AsJob* parameter resembles using the Invoke-Command cmdlet to run a Start-Job command remotely.
However, with *AsJob*, the job is created on the local computer, even though the job runs on a remote computer, and the results of the remote job are automatically returned to the local computer.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251) and [about_Remote_Jobs](https://go.microsoft.com/fwlink/?LinkID=135184).

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

### -AuthenticationRenewalIntervalSec
Specifies an interval, in seconds, when an NFS server renews authentication.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: interval, renewauthinterval, AuthRenewalInterval, AuthenticationRenewalInterval

Required: False
Position: Named
Default value: 600
Accept pipeline input: False
Accept wildcard characters: False
```

### -CharacterTranslationFile
Specifies a path for a file that an NFS server uses for character translation.

```yaml
Type: String
Parameter Sets: (All)
Aliases: translationfile

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

### -ClearMappingCache
Specifies whether to clear the mapping and netgroup cache of an NFS server.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: clearmapcache

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

### -DirectoryCacheSize
Specifies the size of the directory cache, in kilobytes.
This value is a multiple of 4.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: dircache, dcache

Required: False
Position: Named
Default value: 128
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAuthenticationRenewal
Specifies whether an NFS server renews authentication when cached credentials expire.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: renewauth, EnableAuthRenewal

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableNFSV2
Specifies whether an NFS server can export shares via the NFS v2 protocol.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: v2, nfsv2

Required: False
Position: Named
Default value: 3
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableNFSV3
Specifies whether an NFS server can export shares via the NFS v3 protocol.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: v3, nfsv3

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableNFSV4
Specifies whether an NFS server can export shares via the NFS v4.1 protocol.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: v4, nfsv4

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GracePeriodSec
Specifies a grace period, in seconds, for an NFS server.
During this period, clients can reclaim file locks.
The value must be at least twice the value specified in the *LeasePeriodSec* parameter.

The grace period applies to clients connected via the NFS v4.1 protocol.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: nfsv4graceperiod, GracePeriod

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HideFilesBeginningInDot
Specifies whether an NFS server creates files that have names that begin with a dot (.) as hidden files.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: hidedotfiles, dotfileshidden

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LeasePeriodSec
Specifies a lease period, in seconds, for an NFS server.
The minimum value is 5.
The maximum value is 300.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Lease, LeasePeriod

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogActivity
Specifies the activities that an NFS server logs for audit purposes.
The acceptable values for this parameter are:

- Mount
- Unmount
- Read
- Write
- Create
- Delete
- Lock
- Unlock
- All
- None

You can specify multiple values.
Specify All to log all activities or None to log none of these activities.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: audit
Accepted values: mount, unmount, read, write, create, delete, lock, unlock, none, all

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MapServerProtocol
Specifies one or more preferred underlying transport protocols that an NFS server uses for the User Name Mapping server (MAPSVR) protocol.
You must specify at least one of these two values: Tcp and Udp.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: MapsvrProtocol
Accepted values: tcp, udp

Required: False
Position: Named
Default value: 3
Accept pipeline input: False
Accept wildcard characters: False
```

### -MountProtocol
Specifies one or more preferred underlying transport protocols that an NFS server uses for the Mount protocol.
You must specify at least one of these two values: Tcp and Udp.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:
Accepted values: tcp, udp

Required: False
Position: Named
Default value: 3
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetgroupCacheTimeoutSec
Specifies a time-out period, in seconds, for an NFS server.
An NFS server enforces this time-out on entries in its netgroup cache.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: NetgroupTimeout, NetgroupCacheTimeout

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nfsprotocol
Specifies one or more preferred underlying transport protocols that an NFS server uses for the NFS protocol.
You must specify at least one of these two values: Tcp and Udp.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:
Accepted values: tcp, udp

Required: False
Position: Named
Default value: 3
Accept pipeline input: False
Accept wildcard characters: False
```

### -NisProtocol
Specifies one or more preferred underlying transport protocols that an NFS server uses for the Network Information System (NIS) protocol.
You must specify at least one of these two values: Tcp and Udp.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:
Accepted values: tcp, udp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NlmGracePeriodSec
Specifies a grace period, in seconds, that an NFS server enforces for the Network Lock Manager (NLM) protocol.
The default value is 45.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: lockperiod, nlmgrace, NlmGracePeriod

Required: False
Position: Named
Default value: 45
Accept pipeline input: False
Accept wildcard characters: False
```

### -NlmProtocol
Specifies one or more preferred underlying transport protocols that an NFS server uses for the NLM protocol.
You must specify at least one of these two values: Tcp and Udp.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:
Accepted values: tcp, udp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NsmProtocol
Specifies one or more preferred underlying transport protocols that an NFS server uses for the Network Status Manager (NSM) protocol.
You must specify at least one of these two values: Tcp and Udp.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:
Accepted values: tcp, udp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnlineTimeoutSec
Specifies a time-out value, in seconds, for an NFS server.
An NFS server waits for this length of time for a resource to come online before it processes an incoming request.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: onlinetimeout, OnlineTimeoutInSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -PortmapProtocol
Specifies one or more preferred underlying transport protocols that an NFS server uses for the Portmap protocol.
You must specify at least one of these two values: Tcp and Udp.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:
Accepted values: tcp, udp

Required: False
Position: Named
Default value: 3
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreserveInheritance
Specifies whether an NFS server creates inheritable access control entries (ACEs).
These ACEs apply to newly created files and folders on NFS shares.
The default value is $False for non-inheritable ACEs.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: Inheritance

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

### -UnmappedUserAccount
Specifies the Windows account that an NFS server uses to represent users who have no mapping configured in the mapping store.
By default, an NFS server uses NT AUTHORITY\Anonymous.

```yaml
Type: String
Parameter Sets: (All)
Aliases: UnmappedAccount

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

### -WorldAccount
Specifies the Windows account that an NFS server uses to represent World/Other permissions on files when it uses AUTH_UNIX security.
By default, the NFS server uses the BUILTIN\Everyone account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: World

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsServerConfig

## NOTES

## RELATED LINKS

[Get-NfsServerConfiguration](./Get-NfsServerConfiguration.md)

