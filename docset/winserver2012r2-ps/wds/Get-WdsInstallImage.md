---
external help file: MSFT_WdsInstallImage_v1.0.cdxml-help.xml
Module Name: WDS
online version: 
schema: 2.0.0
title: Get-WdsInstallImage
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: EF9CAFCE-E308-4B3B-9382-EF3176931F67
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WdsInstallImage

## SYNOPSIS
Gets properties of install images from an image store.

## SYNTAX

```
Get-WdsInstallImage [-FileName <String>] [-ImageGroup <String>] [-ImageName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WdsInstallImage** cmdlet gets the properties of install images in a Windows Deployment Services image store.
Specify the install image by using the image name and image group name.
If no parameter is specified, it will get the properties of all install images.
If the image name and architecture do not uniquely identify an image, the command will return all images that meet the criteria.

## EXAMPLES

### Example 1: Retrieve images
```
PS C:\> Get-WdsInstallImage -InstallImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName install-3.wim
```

This command retrieves install images named Fabrikam Latest with LOB apps.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileName
Specifies a file name.
This is the file name of the install image.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ImageGroup
Specifies the name of an image group.
This image group contains the image to retrieve.
If you do not specify an image group, the cmdlet returns images from all image groups.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ImageName
Specifies the name of an image.
This is the name of the image to retrieve.
If you do not specify an image name, the cmdlet returns images from all image groups.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsInstallImage

## NOTES

## RELATED LINKS

[Copy-WdsInstallImage](./Copy-WdsInstallImage.md)

[Disable-WdsInstallImage](./Disable-WdsInstallImage.md)

[Enable-WdsInstallImage](./Enable-WdsInstallImage.md)

[Export-WdsInstallImage](./Export-WdsInstallImage.md)

[Import-WdsInstallImage](./Import-WdsInstallImage.md)

[Remove-WdsInstallImage](./Remove-WdsInstallImage.md)

[Set-WdsInstallImage](./Set-WdsInstallImage.md)

