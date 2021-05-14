---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssremotewebaccesslogo?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WssRemoteWebAccessLogo

## SYNOPSIS
Sets the path and filename of the logo image for the Remote Web Access website.

## SYNTAX

```
Set-WssRemoteWebAccessLogo -ImagePath <String>
```

## DESCRIPTION
The **Set-WssRemoteWebAccessLogo** cmdlet sets the path and filename of the logo for the Remote Web Access website in sbs_sbs8_2.
The logo image customizes the appearance of the Remote Web Access website.

## EXAMPLES

### Example 1: Set the name of the logo file
```
PS C:\> Set-WssRemoteWebAccessLogon -ImagePath "D:\Contoso-Logo.png"
```

This command sets the filename for the logo image displayed on the Remote Web Access website.

## PARAMETERS

### -ImagePath
Specifies the file path of the logo image.
To obtain the best results, use an image that is 32x32 pixels.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssRemoteWebAccessLogo](./Get-WssRemoteWebAccessLogo.md)

