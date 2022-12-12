---
external help file: MSFT_PrinterConfiguration_v1.0.cdxml-help.xml
Module Name: PrintManagement
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/printmanagement/set-printconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PrintConfiguration
---

# Set-PrintConfiguration

## SYNOPSIS
Sets the configuration information for the specified printer.

## SYNTAX

### PrinterObject
```
Set-PrintConfiguration [-Collate <Boolean>] [-Color <Boolean>] [-DuplexingMode <DuplexingModeEnum>]
 [-PaperSize <PaperSizeEnum>] [-PrintTicketXml <String>] [-PrinterObject] <CimInstance>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PrinterName
```
Set-PrintConfiguration [-Collate <Boolean>] [-Color <Boolean>] [-DuplexingMode <DuplexingModeEnum>]
 [-PaperSize <PaperSizeEnum>] [-PrintTicketXml <String>] [-ComputerName <String>] [-PrinterName] <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PrintConfigObject
```
Set-PrintConfiguration [-InputObject] <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-PrintConfiguration** cmdlet sets the printer configuration for the specified printer. 
Using the **Set-PrintConfiguration** cmdlet, you can manage the configuration of the following features:

? Collate

? Color

? Duplexing Mode

? N-Up

? Paper Size

The **Set-PrintConfiguration** cmdlet also accepts print configuration objects using Get-PrintConfiguration cmdlet.

You cannot use wildcard characters with **Set-PrintConfiguration**.
You can use **Set-PrintConfiguration** in a Windows PowerShell remoting session.

You need administrator privileges to use **Set-PrintConfiguration**.

## EXAMPLES

### Example 1: Set the default paper size
```
PS C:\> Set-PrintConfiguration -PrinterName "Microsoft XPS Document Writer" -PaperSize A4
```

This command sets the default paper size of the printer named "Microsoft XPS Document Writer" printer to A4.

### Example 2: Set the default paper size using print configuration object
```
PS C:\>$PrintConfiguration = Get-PrintConfiguration -PrinterName "Microsoft XPS Document Writer"


PS C:\>$PrintConfiguration.paperSize = A4


PS C:\>Set-PrintConfiguration -InputObject $PrintConfiguration
```

This set of commands retrieves a print configuration object into a variable ($PrintConfiguration) using Get-PrintConfiguration, sets the paper size in the printer configuration object to A4 and then passes the contents of the variable to **Set-PrintConfiguration**.

### Example 3: Set the default paper size of all printers
```
PS C:\>$printers = get-printer * foreach ($printer in $printers){     Set-printconfiguration -printerName $printer.name -PaperSize A4}
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
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Collate
Specifies whether or not to collate the output of the printer by default.

```yaml
Type: Boolean
Parameter Sets: PrinterObject, PrinterName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Color
Specifies whether the printer should use either color or grayscale printing by default.

```yaml
Type: Boolean
Parameter Sets: PrinterObject, PrinterName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of the computer on which the printer is located.

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

### -DuplexingMode
Specifies the duplexing mode the printer uses by default.

```yaml
Type: DuplexingModeEnum
Parameter Sets: PrinterObject, PrinterName
Aliases: Duplex, Duplexing
Accepted values: OneSided, TwoSidedLongEdge, TwoSidedShortEdge

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the object which contains the printer configuration settings to set.

```yaml
Type: CimInstance
Parameter Sets: PrintConfigObject
Aliases: ConfigObject

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PaperSize
Specifies the paper size the printer uses by default.

```yaml
Type: PaperSizeEnum
Parameter Sets: PrinterObject, PrinterName
Aliases: 
Accepted values: Custom, Letter, LetterSmall, Tabloid, Ledger, Legal, Statement, Executive, A3, A4, A4Small, A5, B4, B5, Folio, Quarto, Sheet10x14, Sheet11x17, Note, Envelope9, Envelope10, Envelope11, Envelope12, Envelope14, CSheet, DSheet, ESheet, EnvelopeDL, EnvelopeC5, EnvelopeC3, EnvelopeC4, EnvelopeC6, EnvelopeC65, EnvelopeB4, EnvelopeB5, EnvelopeB6, EnvelopeItaly, EnvelopeMonarch, EnvelopePersonal, FanfoldUS, FanfoldStandardGerman, FanfoldLegalGerman, ISOB4, JapanesePostcard, Sheet9x11, Sheet10x11, Sheet15x11, EnvelopeInvite, Reserved48, Reserved49, LetterExtra, LegalExtra, TabloidExtra, A4Extra, LetterTransverse, A4Transverse, LetterExtraTransverse, APlus, BPlus, LetterPlus, A4Plus, A5Transverse, B5Transverse, A3Extra, A5Extra, B5Extra, A2, A3Transverse, A3ExtraTransverse, JapaneseDoublePostcard, A6, JapaneseEnvelopeKaku2, JapaneseEnvelopeKaku3, JapaneseEnvelopeChou3, JapaneseEnvelopeChou4, LetterRotated, A3Rotated, A4Rotated, A5Rotated, B4JISRotated, B5JISRotated, JapanesePostcardRotated, JapaneseDoublePostcardRotated, A6Rotated, JapaneseEnvelopeKaku2Rotated, JapaneseEnvelopeKaku3Rotated, JapaneseEnvelopeChou3Rotated, JapaneseEnvelopeChou4Rotated, B6JIS, B6JISRotated, Sheet12x11, JapaneseEnvelopeYou4, JapaneseEnvelopeYou4Rotated, PRC16K, PRC32K, PRC32KBig, PRCEnvelope1, PRCEnvelope2, PRCEnvelope3, PRCEnvelope4, PRCEnvelope5, PRCEnvelope6, PRCEnvelope7, PRCEnvelope8, PRCEnvelope9, PRCEnvelope10, PRC16KRotated, PRC32KRotated, PRC32KBigRotated, PRCEnvelope1Rotated, PRCEnvelope2Rotated, PRCEnvelope3Rotated, PRCEnvelope4Rotated, PRCEnvelope5Rotated, PRCEnvelope6Rotated, PRCEnvelope7Rotated, PRCEnvelope8Rotated, PRCEnvelope9Rotated, PRCEnvelope10Rotated

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrintTicketXml
Specifies the print ticket XML defining the default print settings for this printer.

```yaml
Type: String
Parameter Sets: PrinterObject, PrinterName
Aliases: PrintTicket, PT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrinterName
Specifies the printer on which to set the configuration information.

```yaml
Type: String
Parameter Sets: PrinterName
Aliases: PN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PrinterObject
Specifies the object which contains the printer on which to change the configuration settings.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

###  
This cmdlet produces no output objects.

## NOTES

## RELATED LINKS

[Get-PrintConfiguration](./Get-PrintConfiguration.md)


