---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: PKI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pki/get-certificatenotificationtask?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CertificateNotificationTask
---

# Get-CertificateNotificationTask

## SYNOPSIS
Returns all registered certificate notification tasks.

## SYNTAX

```
Get-CertificateNotificationTask [<CommonParameters>]
```

## DESCRIPTION

The `Get-CertificateNotificationTask` cmdlet returns all certificate notification tasks currently
registered by the `New-CertificateNotificationTask` cmdlet.

## EXAMPLES

### EXAMPLE 1

```powershell
Get-CertificateNotificationTask
```

This example gets all certificate notification tasks currently registered by the
`New-CertificateNotificationTask` cmdlet.

## PARAMETERS

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

None

## OUTPUTS

### Microsoft.CertificateServices.Command.CertificateNotificationTask

This cmdlet returns a **CertificateNotificationTask** object for each certificate notification task
that is currently registered by the `New-CertificateNotificationTask` cmdlet.

## NOTES

## RELATED LINKS

[New-CertificateNotificationTask](./New-CertificateNotificationTask.md)

[Remove-CertificateNotificationTask](./Remove-CertificateNotificationTask.md)

[Switch-Certificate](./Switch-Certificate.md)
