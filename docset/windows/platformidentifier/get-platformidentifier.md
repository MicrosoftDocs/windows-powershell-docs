---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_PlatformIdentifier.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-PlatformIdentifier
ms.reviewer:
ms.assetid: 301339D3-87F6-4B55-B412-C293D5482738
---

# Get-PlatformIdentifier

## SYNOPSIS
Gathers computer identifiers into an XML document.

## SYNTAX

```
Get-PlatformIdentifier [-Name] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-PlatformIdentifier** cmdlet gathers identifiers into an XML document.
These items can identify a computer.
These identifiers are the MAC addresses, SMBIOS GUID, computer serial number, the Trusted Platform Module (TPM) public endorsement key, and a name that you supply.

## EXAMPLES

### Example 1: Get identifiers
```
PS C:\>Get-PlatformIdentifier -Name "Computer03"
```

The command gets the properties that identify a computer, and returns them in an XML document, which includes the specified name.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -Name
Specifies a name that this cmdlet adds to the XML that it creates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### XmlDocument
This cmdlet returns an **XmlDocument** object that contains several fields that uniquely identify a computer.

## NOTES

## RELATED LINKS

