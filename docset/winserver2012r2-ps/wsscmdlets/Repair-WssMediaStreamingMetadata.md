---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/repair-wssmediastreamingmetadata?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Repair-WssMediaStreamingMetadata
---

# Repair-WssMediaStreamingMetadata

## SYNOPSIS
Repairs the database that stores information for media streaming.

## SYNTAX

```
Repair-WssMediaStreamingMetadata [<CommonParameters>]
```

## DESCRIPTION
The **Repair-WssMediaStreamingMetadata** cmdlet repairs the database that stores information for media streaming.
Use this cmdlet only when you see symptoms of data corruption.

## EXAMPLES

### Example 1: Repair media streaming metadata
```
PS C:\>Repair-WssMediaStreamingMetadata
```

This command repairs the database that contains media streaming metadata.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMediaLibraryName](./Get-WssMediaLibraryName.md)

[Set-WssMediaLibraryName](./Set-WssMediaLibraryName.md)

