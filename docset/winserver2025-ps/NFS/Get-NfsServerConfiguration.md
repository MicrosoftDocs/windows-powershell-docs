---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NfsServerConfig.cmdletDefinition.cdxml-help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/get-nfsserverconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NfsServerConfiguration
---

# Get-NfsServerConfiguration

## SYNOPSIS
Gets configuration settings for an NFS server.

## SYNTAX

```
Get-NfsServerConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NfsServerConfiguration** cmdlet gets a configuration object for a Network File System (NFS) server.
You can use the Set-NfsServerConfiguration cmdlet to change NFS server settings.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsServerConfig

## NOTES

## RELATED LINKS

[Set-NfsServerConfiguration](./Set-NfsServerConfiguration.md)

