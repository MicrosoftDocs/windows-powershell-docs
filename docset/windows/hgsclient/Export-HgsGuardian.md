---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: HgsClient-help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: HgsClient
ms.assetid: 54809486-1104-45F8-B108-1EE07863B1AD
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Export-HgsGuardian
ms.reviewer:
---

# Export-HgsGuardian

## SYNOPSIS
Exports a guardian that contains public keys.

## SYNTAX

```
Export-HgsGuardian [-InputObject] <CimInstance> [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Export-HgsGuardian** cmdlet exports a guardian that contains public keys to an .xml file.

## EXAMPLES

### Example 1: Export a guardian
```
PS C:\> Get-HgsGuardian -Name "Guardian11" | Export-HGsGuardian -Path "C:\LocalHGSFiles\Guardian11.xml"
```

This command uses the **Get-HgsGuardian** cmdlet to get the guardian named Guardian11, and then passes the object to the current cmdlet by using the pipeline operator.
That cmdlet exports the guardian to the specified file.

## PARAMETERS

### -InputObject
Specifies the input to this cmdlet. 
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases: Guardian

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies the path to the file to write an XML representation of the guardian.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FilePath

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-HgsGuardian](./Get-HgsGuardian.md)

[Import-HgsGuardian](./Import-HgsGuardian.md)

[New-HgsGuardian](./New-HgsGuardian.md)

[Remove-HgsGuardian](./Remove-HgsGuardian.md)

