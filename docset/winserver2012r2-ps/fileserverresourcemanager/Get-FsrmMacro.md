---
external help file: FsrmMacro.cdxml-help.xml
Module Name: FileServerResourceManager
online version: 
schema: 2.0.0
title: Get-FsrmMacro
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
ms.assetid: DFF2B870-70FE-4708-A513-C28E3BA64CD1
---

# Get-FsrmMacro

## SYNOPSIS
Gets FSRM-supported macros.

## SYNTAX

```
Get-FsrmMacro [-Type <FsrmMacroTypeEnum[]>] [-Name <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-FsrmMacro** cmdlet gets one or more macros that File Server Resource Manager (FSRM) supports for configuration options.
This cmdlet gets the FSRM-supported macros for the FSRM object that you specify in the **Type** parameter.

## EXAMPLES

### Example 1: Get FSRM-supported macros for quotas
```
PS C:\>Get-FsrmMacro -Type Quota
```

This command gets all the FSRM-supported macros for quotas.

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
Specifies an array of macro names.

```yaml
Type: String[]
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

### -Type
Specifies an array of FSRM object types.
The acceptable values for this parameter are:
- Quota
- FileScreen
- FileManagementJob
- ADR

```yaml
Type: FsrmMacroTypeEnum[]
Parameter Sets: (All)
Aliases: 
Accepted values: Quota, FileScreen, FileManagementJob, Adr

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMMacro

## NOTES

## RELATED LINKS

[Get-FsrmQuota](./Get-FsrmQuota.md)

[Get-FsrmFileScreen](./Get-FsrmFileScreen.md)

[Get-FsrmFileManagementJob](./Get-FsrmFileManagementJob.md)

[Get-FsrmAdrSetting](./Get-FsrmAdrSetting.md)

