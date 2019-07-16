---
external help file: FsrmQuota.cdxml-help.xml
Module Name: FileServerResourceManager
online version: 
schema: 2.0.0
title: Get-FsrmQuota
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 4362C85B-0053-45C5-830A-4E6E1227868A
---

# Get-FsrmQuota

## SYNOPSIS
Gets FSRM quotas on the server.

## SYNTAX

```
Get-FsrmQuota [[-Path] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-FsrmQuota** cmdlet gets a File Server Resource Manager (FSRM) quota or all FSRM quotas on the server.

## EXAMPLES

### Example 1: Get all quotas on the server
```
PS C:\>Get-FsrmQuota
```

This command gets all quotas applied to folders on the server.

### Example 2: Get quotas by using a path
```
PS C:\>Get-FsrmQuota -Path "C:\Shares\*"
```

This command gets the quota on C:\Shares plus all of the quotas in all subfolders of C:\Shares.

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

### -Path
Specifies the local folder that contains the quota.

This parameter supports recursive and wildcard paths.
To specify a recursive path one level deep, add an asterisk (*) to a path.
For example, C:\Share\* indicates the quota in C:\Share plus all the quotas in any and all subfolders of C:\Share\ .
To specify a wildcard in a path, you can add the asterisk (*) and the question mark (?) to a path.
For example, C:\Share01\A* indicates the quota in C:\Share plus all the quotas in subfolders of C:\Share\ that have a name that begins with the letter A.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMQuota

## NOTES

## RELATED LINKS

[Set-FsrmQuotaTemplate](./Set-FsrmQuotaTemplate.md)

[New-FsrmQuotaTemplate](./New-FsrmQuotaTemplate.md)

[Remove-FsrmQuotaTemplate](./Remove-FsrmQuotaTemplate.md)

