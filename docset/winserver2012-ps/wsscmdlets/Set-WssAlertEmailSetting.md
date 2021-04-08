---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssalertemailsetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WssAlertEmailSetting

## SYNOPSIS
Changes settings for alert email notification.

## SYNTAX

```
Set-WssAlertEmailSetting [-Setting] <AlertEmailSettings>
```

## DESCRIPTION
The **Set-WssAlertEmailSetting** cmdlet changes settings for alert email notification.
Use the **Setting** parameter to enable or disable alert email notification, configure the SMTP account, and specify the recipients of notification.

## EXAMPLES

### Example 1: Change settings for alert email notification
```
PS C:\> $Setting = Get-WssAlertEmailSettings PS C:\>$Setting.Enabled = $false; PS C:\>$Setting.SmtpServerHost ="smtp.contosoemailhost.com" PS C:\>$Setting.SmtpPort="587" PS C:\>$Setting.EmailAddress="john@contoso.com" PS C:\>$Setting.Recipients="recipient@contoso.com" PS C:\>Set-WssAlertEmailSetting -Setting $Setting
```

The first command gets the current settings for alert email notification and stores the results in the **$Setting** variable.

The second command disables alert email notification.

The third command sets the SMTP server host to the current server.

The fourth command sets the port for the SMTP server host to 587.

The fourth command specifies the default email address from which the server sends email notification.

The fifth command specifies a semicolon-separated list of email addresses to which the server sends notification.

The sixth command saves the email notification settings.

## PARAMETERS

### -Setting
Specifies the settings for alert email notification.

```yaml
Type: AlertEmailSettings
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssAlertEmailSetting](./Get-WssAlertEmailSetting.md)

[Test-WssAlertEmail](./Test-WssAlertEmail.md)

