---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbServerConfiguration.cdxml-help.xml
manager: jasgro
Module Name: smbshare
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/smbshare/get-smbserverconfiguration?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmbServerConfiguration
---

# Get-SmbServerConfiguration

## SYNOPSIS
Retrieves the SMB server configuration.

## SYNTAX

```
Get-SmbServerConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmbServerConfiguration** cmdlet retrieves the Server Message Block (SMB) server configuration.

## EXAMPLES

### Example 1: Get SMB server configuration
```
PS C:\>Get-SmbServerConfiguration
AnnounceServer                  : False 
AsynchronousCredits             : 64 
AutoShareServer                 : True 
AutoShareWorkstation            : True 
CachedOpenLimit                 : 5 
AnnounceComment                 : 
EnableDownlevelTimewarp         : False 
EnableLeasing                   : True 
EnableMultiChannel              : True 
EnableStrictNameChecking        : True 
AutoDisconnectTimeout           : 0 
DurableHandleV2TimeoutInSeconds : 30 
EnableAuthenticateUserSharing   : False 
EnableForcedLogoff              : True 
EnableOplocks                   : True 
EnableSecuritySignature         : False 
ServerHidden                    : True 
IrpStackSize                    : 15 
KeepAliveTime                   : 2 
MaxChannelPerSession            : 32 
MaxMpxCount                     : 50 
MaxSessionPerConnection         : 16384 
MaxThreadsPerQueue              : 20 
MaxWorkItems                    : 1 
NullSessionPipes                : 
NullSessionShares               : 
OplockBreakWait                 : 35 
PendingClientTimeoutInSeconds   : 120 
RequireSecuritySignature        : False 
EnableSMB1Protocol              : True 
EnableSMB2Protocol              : True 
Smb2CreditsMax                  : 2048 
Smb2CreditsMin                  : 128 
SmbServerNameHardeningLevel     : 0 
TreatHostAsStableStorage        : False 
ValidateAliasNotCircular        : True 
ValidateShareScope              : True 
ValidateShareScopeNotAliased    : True 
ValidateTargetName              : True 
EncryptData                     : False 
RejectUnencryptedAccess         : True
```

This command retrieves the SMB server configuration.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbServerConfiguration
The **MSFT_SmbServerConfiguration** object represents the configuration of the SMB server.

## NOTES

## RELATED LINKS

[Set-SmbServerConfiguration](./Set-SmbServerConfiguration.md)

