---
external help file: MSFT_Printer_v1.0.cdxml-help.xml
Module Name: PrintManagement
online version: 
schema: 2.0.0
title: Rename-Printer
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 9B460E62-2F2F-43F9-89F3-D296D6F1F0D2
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Rename-Printer

## SYNOPSIS
Renames the specified printer.

## SYNTAX

### name
```
Rename-Printer [-Name] <String> [-NewName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### object
```
Rename-Printer [-NewName] <String> [-InputObject] <CimInstance> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Rename-Printer** cmdlet renames the specified printer on a computer.
You can specify the printer to rename by using either a printer object retrieved by Get-Printer, or by specifying a printer name.

You cannot use wildcard characters with **Rename-Printer**.
You can use **Rename-Printer** in a Windows PowerShell remoting session.

You need administrator privileges to use **Rename-Printer**.

## EXAMPLES

### Example 1: Rename a printer
```
PS C:\> Rename-Printer -Name "Microsoft XPS Document Writer" -NewName "MXDW"
```

This command renames the "Microsoft XPS Document Writer" printer name as "MXDW".

### Example 2: Rename a printer by using a printer object
```
PS C:\>$Printer = Get-Printer -Name "Microsoft XPS Document Writer"


PS C:\>Rename-Printer -InputObject $Printer -NewName "MXDW"
```

This set of commands retrieves a printer object into a variable ($Printer) using Get-Printer, and then passes the contents of the variable to **Rename-Printer**.

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

### -InputObject
Specifies the object which contains the printer to rename.

```yaml
Type: CimInstance
Parameter Sets: object
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the printer to rename.

```yaml
Type: String
Parameter Sets: name
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -NewName
Specifies the new name of the printer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_Printer
This cmdlet accepts one printer object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-Printer](./Add-Printer.md)

[Remove-Printer](./Remove-Printer.md)

[Get-Printer](./Get-Printer.md)

[Set-Printer](./Set-Printer.md)

