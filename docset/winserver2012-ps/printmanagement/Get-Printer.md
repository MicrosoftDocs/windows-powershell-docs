---
external help file: PrintMgmt_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 8CAA8567-4F79-45B4-A49B-9707973D830B
manager: dansimp
---

# Get-Printer

## SYNOPSIS
Retrieves a list of printers installed on a computer.

## SYNTAX

```
Get-Printer [[-Name] <String>] [-AsJob] [-CimSession <CimSession>] [-ComputerName <String>] [-Full]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-Printer** cmdlet retrieves a list of printers installed on a computer.
You can also use **Get-Printer** to retrieve the properties of a single printer, and then use that information as input into other cmdlets.

You can use wildcard characters with **Get-Printer**.
You can use a **Get-Printer** in a Windows PowerShell remoting session.

You do not need administrator privileges to use **Get-Printer**.

## EXAMPLES

### -------------------------- Example XAMPLE 1: GetReturn a list of printers and printer connections -------------------------- xample : Get a list of printers
```
PS C:\> Get-Printer
```

This command retrieves a list of printers and printer connections on the local computer.

### Example 2: Get the information for a specific printer
```
PS C:\>Get-Printer -Name "Microsoft XPS Document Writer"
```

This command retrieves information for one specific printer named "Microsoft XPS Document Writer".

### Example 3: Get the detailed information for a specific printer
```
PS C:\>Get-Printer -Name "Microsoft XPS Document Writer" | Format-List
```

This command retrieves detailed information for one specific printer named "Microsoft XPS Document Writer".

### Example 4: Get a list of printers on a remote computer
```
PS C:\>Get-Printer -ComputerName PrintServer
```

This command retrieves a list of printers from the computer named PrintServer.

### Example 5: Get a list of printer objects and then rename the printers
```
PS C:\>$Printer = Get-Printer -Name "Microsoft XPS Document Writer"



PS C:\>Rename-Printer -InputObject $printer "MXDW"
```

This set of commands retrieves a printer object into a variable ($Printer) and then passes the contents of the variable to Rename-Printer.

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
Specifies the name of the computer from which to retrieve the printer information.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Local machine name
Accept pipeline input: False
Accept wildcard characters: False
```

### -Full
Specifies all the printer parameters to retrieve including **RenderingMode** and **PermissionSDDL**.

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

### -Name
Specifies the name of the printer about which to retrieve information.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_Printer
This cmdlet outputs one or more printer objects.

## NOTES

## RELATED LINKS

[Add-Printer](./Add-Printer.md)

[Set-Printer](./Set-Printer.md)

[Remove-Printer](./Remove-Printer.md)

[Rename-Printer](./Rename-Printer.md)



