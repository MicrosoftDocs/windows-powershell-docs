---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: processmitigations.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2017-03-29
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-ProcessMitigation
---

# Set-ProcessMitigation

## SYNOPSIS
Commands to enable and disable process mitigations or set them in bulk from an XML file.

## SYNTAX

### ProcessPolicy
```
Set-ProcessMitigation [[-Name] <String>] [-Disable <String[]>] [-Enable <String[]>] [<CommonParameters>]
```

### FullPolicy
```
Set-ProcessMitigation [-File <String>] [<CommonParameters>]
```

## DESCRIPTION
Used to turn on and off various process mitigation settings.
Can also apply an XML file to apply settings for many processes at once.

## EXAMPLES

### Example 1
```
PS C:\>  set-ProcessMitigation -Name Notepad.exe -Enable SEHOP -Disable MandatoryASLR
```

Gets the current process mitigation for "notepad.exe" from the registry and then enables SEHOP, and disables MandatoryASLR.

### Example 2
```
PS C:\> set-ProcessMitigation -file settings.xml
```

Applies all settings inside settings.xml

## PARAMETERS

### -Disable
Comma separated list of mitigations to disable.
Disable list takes priority over enable list.
If specified in both, it will be disabled.

```yaml
Type: String[]
Parameter Sets: ProcessPolicy
Aliases: d
Accepted values: DEP, DisableATL, SEHOP, ForceRelocate, BottomUpASLR, CFG, HighEntropyASLR, StrictHandleCheck, AllowThreadOptOut, SystemCallDisable, ExtensionPointDisable, ProhibitDynamicCode, MicrosoftSignedOnly, StoreSignOnly, FontDisable, AuditNonSystemFonts, NoRemoteImages, NoLowLabel, PreferSystem32

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enable
Comma separated list of mitigations to enable.
Disable list takes priority over enable list.
If specified in both, it will be disabled.

```yaml
Type: String[]
Parameter Sets: ProcessPolicy
Aliases: e
Accepted values: DEP, DisableATL, SEHOP, MandatoryASLR, BottomUpASLR, CFG, HighEntropyASLR, StrictHandleCheck, AllowThreadOptOut, SystemCallDisable, ExtensionPointDisable, ProhibitDynamicCode, MicrosoftSignedOnly, StoreSignOnly, FontDisable, AuditNonSystemFonts, NoRemoteImages, NoLowLabel, PreferSystem32

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -File
An XML file with mitigation settings for many processes that is applied to the registry

```yaml
Type: String
Parameter Sets: FullPolicy
Aliases: x

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Name of the process to apply mitigation settings to.
Can be in the format "notepad" or "notepad.exe"

```yaml
Type: String
Parameter Sets: ProcessPolicy
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

