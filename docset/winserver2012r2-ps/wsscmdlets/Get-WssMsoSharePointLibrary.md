---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssmsosharepointlibrary?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssMsoSharePointLibrary
---

# Get-WssMsoSharePointLibrary

## SYNOPSIS
Retrieves a sp_online_2 library.

## SYNTAX

```
Get-WssMsoSharePointLibrary [[-Name] <String>] [[-Site] <SharePointSite>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssMsoSharePointLibrary** cmdlet retrieves a sp_online_1 library.
A office_365_1 site stores the sp_online_2 library.

## EXAMPLES

### Example 1: Get a SharePoint library
```
PS C:\> $Site = Get-WssMsoSharePointSite | Select-Object -First 1
PS C:\> Get-WssMsoSharePointLibrary -Name "Documents" -Site $Site
```

The first command uses the Get-WssMsoSharePointSite cmdlet to get a site, and stores the result in the $Site variable.

The second command gets the SharePoint Online library for the site specified in the $Site variable.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Name
Specifies the name of a sp_online_2 library.
The cmdlet gets the library for the name that you specify.
If you do not specify the **Name** parameter, the cmdlet returns libraries in the default team site that match other parameters.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Site
Specifies a sp_2013_1 site.
The cmdlet gets the library for the site that you specify.
If you do not specify the **Site** parameter, the cmdlet returns libraries in the default team site that match other parameters.

```yaml
Type: SharePointSite
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
Name

Type: System.String

Description: Name of the SharePoint library

## OUTPUTS

### SharePointLibrary[]

## NOTES

## RELATED LINKS

[New-WssMsoSharePointLibrary](./New-WssMsoSharePointLibrary.md)

[Remove-WssMsoSharePointLibrary](./Remove-WssMsoSharePointLibrary.md)

[Set-WssMsoSharePointLibrary](./Set-WssMsoSharePointLibrary.md)

