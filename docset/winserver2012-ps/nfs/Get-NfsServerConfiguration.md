---
author: Kateyanne
external help file: NFS_Cmdlets.xml
manager: dansimp
Module Name: NFS
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/nfs/get-nfsserverconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NfsServerConfiguration

## SYNOPSIS
Gets configuration settings for an NFS server.

## SYNTAX

```
Get-NfsServerConfiguration [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NfsServerConfiguration** cmdlet gets a configuration object for a Network File System (NFS) server.
You can use the **Set-NfsServerConfiguration** cmdlet to change NFS server settings.

## EXAMPLES

### Example 1: Get local NFS server settings
```
PS C:\> Get-NfsServerConfiguration
State                                      : Running
LogActivity                                :
CharacterTranslationFile                   : Not Configured
DirectoryCacheSize                         : 128
HideFilesBeginningInDot                    : Disabled
EnableNFSV2                                : Enabled
EnableNFSV3                                : Enabled
EnableNFSV4                                : Enabled
EnableAuthenticationRenewal                : Enabled
AuthenticationRenewalIntervalSec           : 600
NlmGracePeriodSec                          : 45
MountProtocol                              : {TCP, UDP}
NfsProtocol                                : {TCP, UDP}
NisProtocol                                : {TCP, UDP}
NlmProtocol                                : {TCP, UDP}
NsmProtocol                                : {TCP, UDP}
PortmapProtocol                            : {TCP, UDP}
MapServerProtocol                          : {TCP, UDP}
PreserveInheritance                        : False
NetgroupCacheTimeoutSec                    : 30
UnmappedUserAccount                        :
WorldAccount                               : Everyone
AlwaysOpenByName                           : False
GracePeriodSec                             : 240
LeasePeriodSec                             : 120
OnlineTimeoutSec                           : 180
```

This command gets the configuration settings for a local NFS server.

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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsServerConfig

## NOTES

## RELATED LINKS

[Set-NfsServerConfiguration](./Set-NfsServerConfiguration.md)

