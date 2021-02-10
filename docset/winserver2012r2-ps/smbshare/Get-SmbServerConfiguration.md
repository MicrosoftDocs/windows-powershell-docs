---
external help file: SmbServerConfiguration.cdxml-help.xml
Module Name: SmbShare
online version: 
schema: 2.0.0
title: Get-SmbServerConfiguration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: B2F207DD-BAB1-4544-9D2F-AC1C5B7249C8
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-SmbServerConfiguration

## SYNOPSIS
Retrieves the Server Message Block (SMB) server configuration.

## SYNTAX

```
Get-SmbServerConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmbServerConfiguration** cmdlet retrieves the Server Message Block (SMB) server configuration.

## EXAMPLES

### EXAMPLE 1
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

This example retrieves the SMB server configuration.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbServerConfiguration
The MSFT_SmbServerConfiguration object represents the configuration of the SMB server.

## NOTES

## RELATED LINKS

[Set-SmbServerConfiguration](./Set-SmbServerConfiguration.md)

