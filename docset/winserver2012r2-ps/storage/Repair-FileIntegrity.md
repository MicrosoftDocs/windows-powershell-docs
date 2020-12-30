---
external help file: FileIntegrity.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: Repair-FileIntegrity
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 9F95D964-20B5-484D-8EF8-E205E8DC3BBE
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Repair-FileIntegrity

## SYNOPSIS
Repairs a corrupted file on an NTFS or ReFS volume.

## SYNTAX

```
Repair-FileIntegrity [-FileName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-FileIntegrity** cmdlet repairs a corrupted file on an NTFS file system volume or a Resilient File System (ReFS) volume.
For the cmdlet to repair a file, the file must be on a storage volume that provides redundancy, and the file must have integrity turned on.
This cmdlet does not repair corrupted file metadata.

## EXAMPLES

### Example 1: Repair a file
```
PS C:\>Repair-FileIntegrity -FileName 'H:\Temp\Text Document.txt'
```

This command repairs a file.
Because the repair proceeds without error, the cmdlet does not display any message.

### Example 2: Attempt to repair a file that cannot be repaired
```
PS C:\>Repair-FileIntegrity -FileName 'J:\Temp\Text Document.txt'
Repair-FileIntegrity : The storage device does not provide redundancy.
```

This command attempts to repair a file.
In this example, the cmdlet cannot repair the file and therefore displays an explanation.

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

### -FileName
Specifies a file name.
The cmdlet attempts to repair the file that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 0
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

### System.IO.FileInfo
To obtain a **FileInfo** object, use the Get-Itemhttp://go.microsoft.com/fwlink/?LinkID=290495 cmdlet for a specified file name.
The cmdlet uses the **FullName** property as the value of the **FileName** parameter.

### System.IO.DirectoryInfo
To obtain a **DirectoryInfo** object, use **Get-Item** for a specified directory name.
The cmdlet uses the **FullName** property as the value of the **FileName** parameter.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-Item](https://go.microsoft.com/fwlink/?LinkID=290495)

[Get-FileIntegrity](./Get-FileIntegrity.md)

[Set-FileIntegrity](./Set-FileIntegrity.md)

