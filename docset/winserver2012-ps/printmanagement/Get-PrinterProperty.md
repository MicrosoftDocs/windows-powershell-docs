---
author: Kateyanne
external help file: PrintMgmt_Cmdlets.xml
manager: dansimp
Module Name: PrintManagement
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/printmanagement/get-printerproperty?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-PrinterProperty

## SYNOPSIS
Retrieves printer properties for the specified printer.

## SYNTAX

```
Get-PrinterProperty [-PrinterName] <String> [[-PropertyName] <String>] [-AsJob] [-CimSession <CimSession>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-PrinterProperty** cmdlet retrieves one or more printer properties for the specified printer.

You cannot use wildcard characters with **Get-PrinterProperty**.
You can use **Get-PrinterProperty** in a Windows PowerShell remoting session.

You need administrator privileges to use **Get-PrinterProperty**.

## EXAMPLES

### -------------------------- Example 1: Get printer properties-------------------------- 
xample:Get printer properties
```
PS C:\> Get-PrinterProperty -PrinterName "Printer name"
```

This command returns a list of properties for the printer specified by **PrinterName**.

### Example 2: Get printer properties for all installed printers
```
PS C:\>$printers = get-printer * 
foreach ($printer in $printers)
{ 
    get-printerproperty -printerName $printer.name 
}
```

This command gets all the printers into a variable $printers and then loops through all the printers and displays the properties.

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
Specifies the name of the computer from which to retrieve the printer properties.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrinterName
Specifies the name of the printer from which to retrieve the printer properties.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PropertyName
Specifies the property name to retrieve.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_PrinterProperty
This cmdlet returns a printer property object.

## NOTES

## RELATED LINKS

[Set-PrinterProperty](./Set-PrinterProperty.md)

