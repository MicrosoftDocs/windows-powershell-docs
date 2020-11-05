---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 82ADFB6B-5090-4228-B7CA-B716E446D121
manager: dansimp
---

# Test-WssAlertEmail

## SYNOPSIS
Sends a test alert email.

## SYNTAX

```
Test-WssAlertEmail
```

## DESCRIPTION
The **Test-WssAlertEmail** cmdlet sends a test alert email.
You can use this cmdlet to check that your current email settings are correct.
This cmdlet sends an email even if there are no alerts currently on the system.
You can use the Set-WssAlertEmailSetting cmdlet to change settings for alert email notification.

## EXAMPLES

### Example 1: Send a test alert email
```
PS C:\> Test-WssAlertEmail
```

This command sends a test alert email that uses the current email settings.

## PARAMETERS

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssAlertEmailSetting](./Get-WssAlertEmailSetting.md)

[Set-WssAlertEmailSetting](./Set-WssAlertEmailSetting.md)

