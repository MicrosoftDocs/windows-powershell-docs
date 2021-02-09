---
external help file: SyncShare.cdxml-help.xml
Module Name: SyncShare
online version: 
schema: 2.0.0
title: Get-SyncShare
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 696CBD26-2DF1-4FC5-8C8B-B43E5FC0AFB2
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-SyncShare

## SYNOPSIS
Retrieves  Sync Shares.

## SYNTAX

```
Get-SyncShare [[-Name] <String[]>] [-Scope <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SyncShare** cmdlet retrieves one or more Sync Shares and displays their settings.

## EXAMPLES

### Example 1: Retrieve all Sync Shares on a server
```
PS C:\> Get-SyncShare
ConflictResolutionPolicy : KeepBoth
Description              : 
DevicePolicy             : t1
Enabled                  : True
ExclusiveAccessToUser    : True
Name                     : t1
Path                     : c:\t1
StagingFolder            : c:\EcsStagingArea\t1
StagingQuota             : 1099511627776
StagingQuotaPerUser      : 10737418240
Type                     : User Data
User                     : {users}
UserFolderName           : %username%
PSComputerName           : 
ConflictResolutionPolicy : KeepBoth
Description              : 
DevicePolicy             : Contoso-share01
Enabled                  : True
ExclusiveAccessToUser    : True
Name                     : Contoso-share01
Path                     : K:\Share1
StagingFolder            : K:\EcsStagingArea\Contoso-share01
StagingQuota             : 1099511627776
StagingQuotaPerUser      : 10737418240
Type                     : User Data
User                     : {EngGroup}
UserFolderName           : %username%
PSComputerName           :
```

This command retrieves all of the Sync Shares on the server.

### Example 2: Retrieve a specific  Sync Share
```
PS C:\> Get-SyncShare Contoso-share01
ConflictResolutionPolicy : KeepBoth
Description              : 
DevicePolicy             : Contoso-share01
Enabled                  : True
ExclusiveAccessToUser    : True
Name                     : Contoso-share01
Path                     : K:\Share01
StagingFolder            : K:\EcsStagingArea\Contoso-share01
StagingQuota             : 1099511627776
StagingQuotaPerUser      : 10737418240
Type                     : User Data
User                     : {EngGroup}
UserFolderName           : %username%
PSComputerName           :
```

This command retrieves the Sync Share named Contoso-share01.

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

### -Name
Specifies an array of names of Sync Shares.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Scope
Specifies a Virtual Computer Object (VCO), if the server is part of a cluster.
Use this parameter to return the Sync Shares that belong to a VCO.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### SyncShare

## NOTES

## RELATED LINKS

[Disable-SyncShare](./Disable-SyncShare.md)

[Enable-SyncShare](./Enable-SyncShare.md)

[New-SyncShare](./New-SyncShare.md)

[Remove-SyncShare](./Remove-SyncShare.md)

[Set-SyncShare](./Set-SyncShare.md)

