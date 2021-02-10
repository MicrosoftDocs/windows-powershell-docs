---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Close-WmsApp
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 050C6E96-D91B-4020-B752-859BEA975416
ms.reviewer:
ms.author: v-kaunu
---

# Close-WmsApp

## SYNOPSIS
Closes the specified application in the specified session.

## SYNTAX

```
Close-WmsApp -SessionId <UInt32> -ProcessId <UInt32> -WindowId <UInt64> [-TimeoutInSecond <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Close-WmsApp cmdlet closes the specified application using the process ID and the window ID that is provided in the cmdlet.
The cmdlet attempts to close the application first.
If it fails, it forces the application to close.

## EXAMPLES

### Example
```
PS C:\> Close-WmsApp -SessionId 3 -ProcessId 852 -WindowId 65854 -CreateTime 45689009809823

No output.
```

The application running on the session is closed. 

 Use Get-WmsApp to get a list of applications with the ProcessId and WindowId.

### 1:
```
PS C:\>
```

## PARAMETERS

### -ProcessId
Specifies a process using process ID (PID).

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SessionId
Specifies a Remote Desktop Session (RDS) using SessionID.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TimeoutInSecond
The timeout value in seconds before the operation is aborted.

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

### -WindowId
The main Window handle of the specified process.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### None

## NOTES

## RELATED LINKS

