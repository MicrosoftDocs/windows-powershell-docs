---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/set-wssremotewebaccessbackgroundimage?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WssRemoteWebAccessBackgroundImage

## SYNOPSIS
Sets the background image for a Remote Web Access website.

## SYNTAX

```
Set-WssRemoteWebAccessBackgroundImage -ImagePath <String>
```

## DESCRIPTION
The **Set-WssRemoteWebAccessBackgroundImage** cmdlet sets a background image on the logon page of a Remote Web Access website.

## EXAMPLES

### Example 1: Set the background image
```
PS C:\> Set-WssRemoteWebAccessBackgroundImage -ImagePath "D:\Contoso-image.png"
```

This command sets the background image of the logon page.

## PARAMETERS

### -ImagePath
Specifies the path to an image file.
Use any of the following image types: 
- Bitmap (*.bmp, *.dib, *.rle) 
- GIF (*.gif) 
- PNG (*.png) 
- JPG (*.jpg)

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

[Get-WssRemoteWebAccessBackgroundImage](./Get-WssRemoteWebAccessBackgroundImage.md)

