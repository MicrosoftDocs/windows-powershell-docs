---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_PrinterProperty_v1.0.cdxml-help.xml
Module Name: PrintManagement
ms.date: 09/20/2021
online version: https://learn.microsoft.com/powershell/module/printmanagement/set-printerproperty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PrinterProperty
---

# Set-PrinterProperty

## SYNOPSIS
Modifies the printer properties for the specified printer.

## SYNTAX

### PrinterName
```
Set-PrinterProperty [-PrinterName] <String> [-PropertyName] <String> [-Value] <String> [-ComputerName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PrinterObject
```
Set-PrinterProperty [-PropertyName] <String> [-Value] <String> [-PrinterObject] <CimInstance>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PrinterPropertyObject
```
Set-PrinterProperty [-InputObject] <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-PrinterProperty** cmdlet modifies the printer properties for the specified printer.

You cannot use wildcard characters with **Set-PrinterProperty**.
You can use **Set-PrinterProperty** in a Windows PowerShell remoting session.

You need administrator credentials to run **Set-PrinterProperty**.

## EXAMPLES

### Example 1: Set a printer property
```
Set-PrinterProperty -PrinterName "Printer02" -PropertyName "Config:PropertyName" -Value True
```

This command sets the **Config:PropertyName** property of the printer named Printer02 to True.

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

### -ComputerName
Specifies the computer name for which to modify the printer properties.

```yaml
Type: String
Parameter Sets: PrinterName
Aliases: Computer, CN

Required: False
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

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: PrinterPropertyObject
Aliases: PropertyObject

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PrinterName
Specifies the name of the printer for which to modify the properties.

```yaml
Type: String
Parameter Sets: PrinterName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrinterObject
Specifies the printer object for which to update the printer properties.

```yaml
Type: CimInstance
Parameter Sets: PrinterObject
Aliases: Printer

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PropertyName
Specifies the property name to update.

```yaml
Type: String
Parameter Sets: PrinterName, PrinterObject
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

### -Value
Specifies the new value of the printer property.

```yaml
Type: String
Parameter Sets: PrinterName, PrinterObject
Aliases:

Required: True
Position: 2
Default value: None
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Get-PrinterProperty](./Get-PrinterProperty.md)

