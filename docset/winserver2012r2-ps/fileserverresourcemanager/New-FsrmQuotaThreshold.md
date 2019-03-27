---
external help file: FSRMQuotaThreshold.cdxml-help.xml
Module Name: FileServerResourceManager
online version: 
schema: 2.0.0
title: New-FsrmQuotaThreshold
ms.author: kenwith
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 2877A218-A85C-48C1-B77F-FAD1F4BEBB34
---

# New-FsrmQuotaThreshold

## SYNOPSIS
Returns a quota threshold object.

## SYNTAX

```
New-FsrmQuotaThreshold [-Percentage] <UInt32> [-Action <CimInstance[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmQuotaThreshold** cmdlet returns a threshold object.
You can use a threshold object to create File Server Resource Manager (FSRM) quotas and quota templates.

## EXAMPLES

### Example 1: Create a quota threshold
```
PS C:\>$Action = New-FsrmAction -Type Command -Command "c:\windows\system32\cmd.exe" -CommandParameters "echo [source file path] >> c:\log.txt" -ShouldLogError
PS C:\> New-FsrmQuotaThreshold -Percentage 90 -Action $Action
```

The first command creates an FSRM action object and stores the results in the **$Action** variable.
The action indicates that when an associated event occurs, the server runs Cmd.exe and uses the specified parameters.
The command specifies that the server records errors codes from the command in the error log.

The second command returns a threshold object.
The command specifies that at 90 percent of the quota limit, the server runs the action stored in the **$Action** variable.

## PARAMETERS

### -Action
Specifies an array of FSRM actions.
You can create an action by using the New-FsrmAction cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Percentage
Specifies the percentage of the quota limit at which to run the action.
The maximum value you can set is 259.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMQuotaThreshold

## NOTES

## RELATED LINKS

[New-FsrmQuota](./New-FsrmQuota.md)

[Set-FsrmQuota](./Set-FsrmQuota.md)

[New-FsrmQuotaTemplate](./New-FsrmQuotaTemplate.md)

[Set-FsrmQuotaTemplate](./Set-FsrmQuotaTemplate.md)

[New-FsrmAction](./New-FsrmAction.md)

