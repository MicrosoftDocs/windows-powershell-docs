---
external help file: MSFT_PrinterPort_v1.0.cdxml-help.xml
Module Name: PrintManagement
online version: 
schema: 2.0.0
title: Get-PrinterPort
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: B6173813-10C8-4649-B116-FC2AD2C63059
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-PrinterPort

## SYNOPSIS
Retrieves a list of printer ports installed on the specified computer.

## SYNTAX

```
Get-PrinterPort [[-Name] <String[]>] [-ComputerName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PrinterPort** cmdlet retrieves a list of printer ports that are installed on the specified computer.

You can use wildcard characters with **Get-PrinterPort**.
You can use **Get-PrinterPort** in a Windows PowerShell remoting session.

You do not need administrator privileges to use **Get-PrinterPort**.

## EXAMPLES

### Example 1: Get a list of printer ports
```
PS C:\> Get-PrinterPort
```

This command retrieves a list of all the printer ports installed on the local computer.

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

### -ComputerName
Specifies the name of the computer from which to retrieve the list of printer ports.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: Local machine name
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the printer port about which to retrieve information.
You can use wildcard characters to specify the printer port name.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_PrinterPort
This cmdlet returns one or more printer port objects.

## NOTES

## RELATED LINKS

[Add-PrinterPort](./Add-PrinterPort.md)

[Remove-PrinterPort](./Remove-PrinterPort.md)

