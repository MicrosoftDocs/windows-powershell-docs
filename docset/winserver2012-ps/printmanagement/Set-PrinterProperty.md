---
author: Kateyanne
external help file: PrintMgmt_Cmdlets.xml
manager: dansimp
Module Name: PrintManagement
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/printmanagement/set-printerproperty?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-PrinterProperty

## SYNOPSIS
Modifies the printer properties for the specified printer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-PrinterProperty [-PrinterName] <String> [-PropertyName] <String> [-Value] <String> [-AsJob]
 [-CimSession <CimSession>] [-ComputerName <String>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-PrinterProperty [-InputObject] <CimInstance> [-AsJob] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-PrinterProperty [-PrinterObject] <CimInstance> [-PropertyName] <String> [-Value] <String> [-AsJob]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-PrinterProperty** cmdlet modifies the printer properties for the specified printer.

You cannot use wildcard characters with **Set-PrinterProperty**.
You can use **Set-PrinterProperty** in a wps-2 remoting session.

You need administrator privileges to use **Set-PrinterProperty**.

## EXAMPLES

### Example 1: Set a printer property
```
PS C:\>Set-PrinterProperty -PrinterName printer2 -PropertyName "Config:PropertyName" -Value True
```

This command sets the Config:PropertyName property of the printer named printer2 to True.

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
Type: CimSession
Parameter Sets: (All)
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the printer property object which contains the printer property to modify.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -PrinterName
Specifies the name of the printer for which to modify the properties.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrinterObject
Specifies the printer object for which to update the printer properties.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -PropertyName
Specifies the property name to update.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_Printer
This cmdlet accepts one printer object.

## OUTPUTS

### 
This cmdlet produces no output.

## NOTES

## RELATED LINKS

[Get-PrinterProperty](./Get-PrinterProperty.md)

