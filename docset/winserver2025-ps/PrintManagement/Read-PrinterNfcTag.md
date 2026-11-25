---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_PrinterNfcTagTasks_v1.0.cdxml-help.xml
Module Name: PrintManagement
ms.date: 09/20/2021
online version: https://learn.microsoft.com/powershell/module/printmanagement/read-printernfctag?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Read-PrinterNfcTag
---

# Read-PrinterNfcTag

## SYNOPSIS
Reads information about printers from an NFC tag.

## SYNTAX

```
Read-PrinterNfcTag [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Read-PrinterNfcTag** cmdlet reads information about printers from the near field communication (NFC) tag that anyone taps against the default NFC reader for the system.
The cmdlet returns the printer information that it reads as a table that contains the value of the **SharePath** property and the value and the **wsdAddress** property for the printers.

## EXAMPLES

### Example 1: Read an NFC tag
```
$Tag = Read-PrinterNfcTag
Write-PrinterNfcTag $Tag
```

This first command reads printer connection data from the next NFC tag that someone taps against the NFC reader.
The command stores the printer information in the $Tag variable.

The second command uses the Write-PrinterNfcTag to write the printer connection information stored in $Tag to an NFC tag.

### Example 2: Modify the share path of a printer connection
```
$Tag = Read-PrinterNfcTag
$Tag.SharePaths = "\\ntprint\b27-3697-b"
```

This first command reads printer connection information from the next NFC tag that someone taps against the NFC reader.
The command stores the printer information in the $Tag variable.

The second command changes the share path of the shared printers stored in $Tag.
The command uses standard dot syntax to access the **SharePaths** property of the object stored in $Tag.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[Write-PrinterNfcTag](./Write-PrinterNfcTag.md)

