---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/test-wssalertemail?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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

