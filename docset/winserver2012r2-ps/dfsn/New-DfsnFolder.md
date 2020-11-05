---
external help file: DfsNamespaceFolder.cdxml-help.xml
Module Name: DFSN
online version: 
schema: 2.0.0
title: New-DfsnFolder
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A66E433F-6431-4DE3-8202-EAA9ACA21B1E
---

# New-DfsnFolder

## SYNOPSIS
Creates a folder in a DFS namespace.

## SYNTAX

```
New-DfsnFolder [-Path] <String> [-TargetPath] <String> [[-EnableInsiteReferrals] <Boolean>]
 [[-EnableTargetFailback] <Boolean>] [[-State] <State>] [[-TimeToLiveSec] <UInt32>] [[-Description] <String>]
 [[-TargetState] <State>] [[-ReferralPriorityClass] <ReferralPriorityClass>] [[-ReferralPriorityRank] <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-DfsnFolder** cmdlet creates a folder in a Distributed File System (DFS) namespace.
Specify the path and a path for a folder target for the new folder.

A DFS namespace folder has one or more folder targets that are shared folders on computers.
When a client attempts to connect to a folder, the DFS namespace server provides a list of folder targets, called referrals.
The server determines the order for referrals and clients attempt to connect to a folder target in the order that the server provides.

You can specify settings for the new folder.
You can use this cmdlet to enable or disable the following settings: 

- In-site referrals. 
- Target failback.

You can also add a descriptive comment, select the state of the folder and folder target, and set the Time to Live (TTL) interval for referrals.

Finally, you can specify the priority class and priority rank for referrals.

For more information about DFS namespaces, see Overview of DFS Namespaceshttp://technet.microsoft.com/library/cc730736 (http://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Create a DFS namespace folder
```
PS C:\> New-DfsnFolder -Path "\\Contoso\AccountingResources\LegacySoftware" -TargetPath "\\Contoso-FS\AccountingLegacy" -EnableTargetFailback $True -Description "Folder for legacy software."
```

This command creates a folder called LegacySoftware in the \\\\Contoso\AccountingResources namespace.
The folder target is \\\\Contoso-FS\AccountingLegacy.
The command enables target failback for the folder.
The command includes a description for the new folder.

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

### -Description
Specifies a description for a DFS namespace folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: desc

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableInsiteReferrals
Indicates whether a DFS namespace server provides a client only with referrals that are in the same site as the client.
If this value is $True, the DFS namespace server provides only in-site referrals.
If this value is $False, the DFS namespace server provides in-site referrals first, then other referrals.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: insite

Required: False
Position: 2
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableTargetFailback
Indicates whether a DFS namespace uses target failback.
If a client attempts to access a target on a server and that server is not available, the client fails over to another referral.
If this value is $True, once the first server becomes available again, the client fails back to the first server.
If this value is $False, the DFS namespace server does not require the client to fail back to the preferred server.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: failback, TargetFailback

Required: False
Position: 3
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies a path for the folder.
This path must be unique.
This path cannot be the name of an existing DFS namespace folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DfsPath, FolderPath, NamespacePath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReferralPriorityClass
Specifies the target priority class for a DFS namespace folder.
Target priority offers you the ability to classify and rank in-site targets.
You can specify targets to receive the highest or lowest preference, and you can divide the remaining targets based on their site cost for a DFS client to connect to them.
The acceptable values for this parameter are:

- GlobalHigh.
The highest priority class for a DFS target.
Targets assigned this class receive global preference. 
- SiteCostHigh.
The highest site cost priority class for a DFS target.
Targets assigned this class receive the most preference among targets of the same site cost for a given DFS client.
- SiteCostNormal.
The middle or normal site cost priority class for a DFS target.
- SiteCostLow.
The lowest site cost priority class for a DFS target.
Targets assigned this class receive the least preference among targets of the same site cost for a given DFS client.
- GlobalLow.
The lowest level of priority class for a DFS target.
Targets assigned this class receive the least preference globally.

```yaml
Type: ReferralPriorityClass
Parameter Sets: (All)
Aliases: PriorityClass, Class
Accepted values: sitecostnormal, globalhigh, sitecosthigh, sitecostlow, globallow

Required: False
Position: 8
Default value: Sitecost-normal
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReferralPriorityRank
Specifies the priority rank, as an integer, for a target in the DFS namespace.
Lower values have greater preference.
A value of zero (0) is the greatest preference.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: PriorityRank, Rank

Required: False
Position: 9
Default value: 0
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
Specifies the state of the DFS namespace folder.
The acceptable values for this parameter are:

- Online
- Offline

Clients do not receive referrals for a DFS namespace folder that is offline.

```yaml
Type: State
Parameter Sets: (All)
Aliases: 
Accepted values: Offline, Online

Required: False
Position: 4
Default value: ONLINE
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetPath
Specifies a path for a target for the DFS namespace folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Target, DfsTarget, FolderTarget

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetState
Specifies the state of the DFS namespace folder target.
The acceptable values for this parameter are:

- Online
- Offline

Clients do not receive referrals for a DFS namespace folder target that is offline.

```yaml
Type: State
Parameter Sets: (All)
Aliases: 
Accepted values: Offline, Online

Required: False
Position: 7
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

### -TimeToLiveSec
Specifies a TTL interval, in seconds, for referrals.
Clients store referrals to targets for this length of time.
The default TTL interval for folder referrals is 1800 seconds (30 minutes).

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: ttl, TimeToLive

Required: False
Position: 5
Default value: 300
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_DfsNamespaceFolder

## NOTES

## RELATED LINKS

[Get-DfsnFolder](./Get-DfsnFolder.md)

[Move-DfsnFolder](./Move-DfsnFolder.md)

[Remove-DfsnFolder](./Remove-DfsnFolder.md)

[Set-DfsnFolder](./Set-DfsnFolder.md)

