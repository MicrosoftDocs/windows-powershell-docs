---
author: Kateyanne
external help file: NFS_Cmdlets.xml
manager: dansimp
Module Name: NFS
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/nfs/set-nfsserverconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NfsServerConfiguration

## SYNOPSIS
Changes configuration settings for an NFS server.

## SYNTAX

```
Set-NfsServerConfiguration [-AlwaysOpenByName <Boolean>] [-AsJob] [-AuthenticationRenewalIntervalSec <UInt32>]
 [-CharacterTranslationFile <String>] [-CimSession <CimSession[]>] [-ClearMappingCache]
 [-DirectoryCacheSize <UInt32>] [-EnableAuthenticationRenewal <Boolean>] [-EnableNFSV2 <Boolean>]
 [-EnableNFSV3 <Boolean>] [-EnableNFSV4 <Boolean>] [-GracePeriodSec <UInt32>]
 [-HideFilesBeginningInDot <Boolean>] [-InputObject <CimInstance[]>] [-LeasePeriodSec <UInt32>]
 [-LogActivity <String[]>] [-MapServerProtocol <String[]>] [-MountProtocol <String[]>]
 [-NetgroupCacheTimeoutSec <UInt32>] [-Nfsprotocol <String[]>] [-NisProtocol <String[]>]
 [-NlmGracePeriodSec <UInt32>] [-NlmProtocol <String[]>] [-NsmProtocol <String[]>] [-OnlineTimeoutSec <UInt32>]
 [-PassThru] [-PortmapProtocol <String[]>] [-PreserveInheritance <Boolean>] [-ThrottleLimit <Int32>]
 [-UnmappedUserAccount <String>] [-WorldAccount <String>] [-Confirm] [-WhatIf]
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
PS C:\> Set-NfsServerConfiguration -EnableNfsv2 $false -EnableNfsv4 $true -EnableNfsv3 $true
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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -AuthenticationRenewalIntervalSec
Specifies an interval, in seconds, when an NFS server renews authentication.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

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
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectoryCacheSize
Specifies the size of the directory cache, in kilobytes.
This value is a multiple of 4.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

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
Aliases: 

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
Aliases: 

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
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GracePeriodSec
Specifies a grace period, in seconds, for an NFS server.
During this period, clients can reclaim file locks.
The value must be at least twice the value specified in the **LeasePeriodSec** parameter.

The grace period applies to clients connected via the NFS v4.1 protocol.

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

### -HideFilesBeginningInDot
Specifies whether an NFS server creates files that have names that begin with a dot (.) as hidden files.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

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
Aliases: 

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
Aliases: 

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
Aliases: 

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
Aliases: 

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
Aliases: 

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
Aliases: 

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

### -UnmappedUserAccount
Specifies the Windows account that an NFS server uses to represent users who have no mapping configured in the mapping store.
By default, an NFS server uses NT AUTHORITY\Anonymous.

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

### -WorldAccount
Specifies the Windows account that an NFS server uses to represent World/Other permissions on files when it uses AUTH_UNIX security.
By default, the NFS server uses the BUILTIN\Everyone account.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsServerConfig

## NOTES

## RELATED LINKS

[Get-NfsServerConfiguration](./Get-NfsServerConfiguration.md)

