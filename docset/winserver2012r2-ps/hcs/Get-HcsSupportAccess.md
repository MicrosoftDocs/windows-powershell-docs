---
author: Kateyanne
description: 
external help file: Microsoft.HCS.Management.dll-Help.xml
manager: jasgro
Module Name: HCS
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hcs/get-hcssupportaccess?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HcsSupportAccess
---

# Get-HcsSupportAccess

## SYNOPSIS
Gets the encrypted password that Customer Service and Support uses to access the device.

## SYNTAX

```
Get-HcsSupportAccess [<CommonParameters>]
```

## DESCRIPTION
The **Get-HcsSupportAccess** cmdlet gets the encrypted support password that Microsoft Customer Service and Support uses to access the device.

If remote access is not enabled, this cmdlet tells you that it is not enabled.
For more information, see the Enable-HcsSupportAccess cmdlet.

## EXAMPLES

### Example 1: Get an encrypted password
```
PS C:\> Get-HcsSupportAccess
UAAAAEQAMABCADYAMgAyADYAMgBBAEEANgA3A1AgRAcDADUANgA2ADYAQQAxAEMARQA1ADUAQQAyADcANgAwADkARQAyADgANgBDADAAMgBBAEYAgoxuZpw
TpD1x6hq1lcc1zD50jtklqRC0pyacDn33ztFBRRQYlG1lHNoRQ7t4s4XTnnF4/oxW16nQLstc0gSL0W4dpJYtlCRXSQbGrHEUCbkpoH78OTci0QcCHIEG3q
Vhinu39/AGGr5VUVa+BGz43JW/xDey+inHHhnu4TRHQf2rniX9Ihkv8g2Q6Y352zW1hUX3qA5VYgNsYLHiFrG09SKfxvBOjnNrHm0fUITneKjoM9+UQu6wc
UJ6Ug8TKdMtfs0Slxdq6Jpqt9dkOq4eLb5ZL6FphvmVwqJ2+xL1Fwa+5zl+4Sdqtq5/ddzWJjYR2oZUVuo71a7WyP//vQE3/g==
```

This command gets the encrypted password for the device.
Share the result with Customer Service and Support.
They can decrypt it to get a temporary support access password to your device.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-HcsSupportAccess](./Disable-HcsSupportAccess.md)

[Enable-HcsSupportAccess](./Enable-HcsSupportAccess.md)

