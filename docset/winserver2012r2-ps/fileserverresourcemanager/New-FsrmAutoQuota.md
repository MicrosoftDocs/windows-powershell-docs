---
external help file: FSRMAutoQuota.cdxml-help.xml
Module Name: FileServerResourceManager
online version: 
schema: 2.0.0
title: New-FsrmAutoQuota
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
ms.assetid: D7BC9017-AEC8-4C89-B58E-A2C98674F3FB
---

# New-FsrmAutoQuota

## SYNOPSIS
Creates an auto apply quota.

## SYNTAX

```
New-FsrmAutoQuota [-Path] <String> [-Template <String>] [-Disabled] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmAutoQuota** cmdlet creates an auto apply quota.
By using auto apply quotas, you can assign a quota template to a parent volume or folder.
File Server Resource Manager (FSRM) automatically generates quotas that are based on that template.
The server generates quotas for each of the existing subfolders and for subfolders that you create in the future.

You can verify all automatically generated quotas by using the Get-FsrmAutoQuota cmdlet.
Get-FsrmAutoQuota returns an individual quota for each subfolder and the auto apply quota profile in the parent volume or folder.

## EXAMPLES

### Example 1: Create an auto apply quota on a folder
```
PS C:\>New-FsrmAutoQuota -Path "C:\Shares\CtrShare03" -Template "250 MB Extended Limit"
```

This command creates an auto apply quota on the folder named C:\Shares\CtrShare03.
The server generates quotas based on the "250 MB Extended Limit" template for each of the existing subfolders in C:\Shares\CtrShare03 and for subfolders that you create in C:\Shares\CtrShare03.

### Example 2: Create an inactive auto apply quota
```
PS C:\>New-FsrmAutoQuota -Path "C:\Shares\CtrShare03" -Template "100 MB Limit" -Disabled
```

This command creates an auto apply quota on the folder C:\Shares\CtrShare03 and applies the "100 MB Limit" template to the quota.
The command disables the auto apply quota, which means that the server does not generate quotas for subfolders in C:\Shares\CtrShare03.

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

### -Disabled
Indicates that the server does not track quota data for the quota and does not run any action associated with quota thresholds.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies a valid local path to a folder.
The server applies the auto apply quota to each of the subfolders (current and future) in this folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Template
Specifies a name of a quota template on the server.

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

## NOTES

## RELATED LINKS

[Get-FsrmAutoQuota](./Get-FsrmAutoQuota.md)

[Set-FsrmAutoQuota](./Set-FsrmAutoQuota.md)

[Update-FsrmAutoQuota](./Update-FsrmAutoQuota.md)

[Remove-FsrmAutoQuota](./Remove-FsrmAutoQuota.md)

