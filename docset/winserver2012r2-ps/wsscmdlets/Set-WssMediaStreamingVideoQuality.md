---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/set-wssmediastreamingvideoquality?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssMediaStreamingVideoQuality
---

# Set-WssMediaStreamingVideoQuality

## SYNOPSIS
Modifies the video streaming quality of videos that are streamed from the server.

## SYNTAX

```
Set-WssMediaStreamingVideoQuality [-Quality] <VideoQuality> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssMediaStreamingVideoQuality** cmdlet modifies the video streaming quality of videos that are streamed from the server.

## EXAMPLES

### Example 1: Set the video streaming quality
```
PS C:\>Set-WssMediaStreamingVideoQuality
```

This command sets the video streaming quality on the server on which you run the cmdlet.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Quality
Specifies the video quality.
The cmdlet sets the video quality value that you specify.

```yaml
Type: VideoQuality
Parameter Sets: (All)
Aliases: 
Accepted values: Low, Medium, High, Best

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsServerSolutions.MediaStreaming.VideoQuality

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMediaStreamingVideoQuality](./Get-WssMediaStreamingVideoQuality.md)

