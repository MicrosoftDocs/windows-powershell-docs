---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/set-wssreportemailsetting?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssReportEmailSetting
---

# Set-WssReportEmailSetting

## SYNOPSIS
Configures the email settings of health report.

## SYNTAX

### Enable (Default)
```
Set-WssReportEmailSetting [-Enable] -From <String> -To <String> -SmtpServer <String> -Port <Int32> [-UseSsl]
 [-UseAuthentication] [-Credential <PSCredential>] [<CommonParameters>]
```

### Disable
```
Set-WssReportEmailSetting [-Disable] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssReportEmailSetting** cmdlet configures the email settings of a health report.

## EXAMPLES

### Example 1: Set report email settings
```
PS C:\> $UserName = "ContosoUser"
PS C:\> $Password = ConvertTo-SecureString "passw0rd" -AsPlainText -Force
PS C:\> $Cred = New-Object System.Management.Automation.PSCredential($UserName, $Password)
PS C:\> Set-WssReportEmailSetting -Enable -From "Contoso-Admin@contoso.com" -SMTPServer "smtphost" -Port 25 -UseAuthentication -Credential $Cred
```

The first command creates a $UserName variable.

The second command creates a password for the user by using a secure string conversion cmdlet.

The third command creates a credential for the user by using the New-Object cmdlet.

The last command sets the report email settings.

## PARAMETERS

### -Credential
Specifies a credential for SMTP authentication.
To obtain a credential object, use the **Get-Credential** cmdlet.

```yaml
Type: PSCredential
Parameter Sets: Enable
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disable
Indicates that the email setting is disabled.

```yaml
Type: SwitchParameter
Parameter Sets: Disable
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enable
Indicates that the email setting is enabled.

```yaml
Type: SwitchParameter
Parameter Sets: Enable
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -From
Specifies the sender address of the health report.
The sender of the email is the email address that you specify.

```yaml
Type: String
Parameter Sets: Enable
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies the TCP port number of SMTP service.
The SMTP service listens on the port you specify.

```yaml
Type: Int32
Parameter Sets: Enable
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SmtpServer
Specifies the SMTP server name.

```yaml
Type: String
Parameter Sets: Enable
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -To
Specifies the email addresses of recipients, separated by a semicolon (;).
The recipients of the email are the email addresses that you specify.

```yaml
Type: String
Parameter Sets: Enable
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseAuthentication
Indicates that the SMTP server requires authentication.

```yaml
Type: SwitchParameter
Parameter Sets: Enable
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSsl
Use this when SSL is required.

```yaml
Type: SwitchParameter
Parameter Sets: Enable
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Management.Automation.PSCredential,System.Management.Automation.SwitchParameter,System.Management.Automation.SwitchParameter,System.String,System.Int32,System.String,System.String,System.Management.Automation.SwitchParameter,System.Management.Automation.SwitchParameter
Email settings

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssReportEmailSetting](./Get-WssReportEmailSetting.md)

