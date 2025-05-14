---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_PrinterNfcTagTasks_v1.0.cdxml-help.xml
Module Name: PrintManagement
ms.date: 09/20/2021
online version: https://learn.microsoft.com/powershell/module/printmanagement/write-printernfctag?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Write-PrinterNfcTag
---

# Write-PrinterNfcTag

## SYNOPSIS
Writes printer connection data to an NFC tag.

## SYNTAX

### ManualSpecification
```
Write-PrinterNfcTag [[-SharePath] <String[]>] [[-WsdAddress] <String[]>] [-Lock] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### PrinterNfcTag
```
Write-PrinterNfcTag [-InputObject] <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Write-PrinterNfcTag** cmdlet writes a near field communication (NFC) tag with printer connection data.
You can use NFC tags to program shared printers and Web Services for Devices (WSD) printers.
If multiple print shares or WSD device addresses support the same device, the cmdlet writes the NFC tag in the order of the print shares or WSD device addresses that you specify.
This cmdlet requires that the system have an NFC radio available.

Specify the printer connection data for this cmdlet by specifying the paths of shared printers or the IP addresses WSD printers, or by using the *InputObject* parameter to specify a printer object as input to this cmdlet.

## EXAMPLES

### Example 1: Write printer connection data to an NFC tag
```
Write-PrinterNfcTag -SharePath "\\ServerName\PrinterName01","\\AlternateServerName\PrinterName02" -WsdAddress "PrinterHost01"
```

This command writes printer connection data to an NFC tag for the specified shared printers and the WSD printer that has the host name PrinterHost01.

### Example 2: Copy an NFC tag
```
Read-PrinterNfcTag | Write-PrinterNfcTag
```

This command uses the Read-PrinterNfcTag cmdlet to read the printer connection data from the next NFC tag that someone taps against the NFC reader.
The command passes the printer connection data to the next cmdlet by using the pipeline operator.
The command then writes the printer connection data to an NFC tag when a user taps the tag against the NFC radio.

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

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: PrinterNfcTag
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lock
Indicates that the NFC tags cannot be modified after you write the NFC tags.
You cannot unlock a locked NFC tag.

```yaml
Type: SwitchParameter
Parameter Sets: ManualSpecification
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SharePath
Specifies an array of paths of shared printers.
Use the following format: `\\\\printServer\shareName`.
The cmdlet writes the path of the shared printers to an NFC tag.

```yaml
Type: String[]
Parameter Sets: ManualSpecification
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -WsdAddress
Specifies an array of IP addresses of WSD printers.
The cmdlet writes the IP addresses of the of WSD printers to a printer NFC tag.
The acceptable values for this parameter are: an IPv4 or IPv6 IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN) or Hostname.

```yaml
Type: String[]
Parameter Sets: ManualSpecification
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.Management.Automation.SwitchParameter

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Read-PrinterNfcTag](./Read-PrinterNfcTag.md)

