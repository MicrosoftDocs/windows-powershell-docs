---
external help file: MSFT_WdsInstallImage_v1.0.cdxml-help.xml
Module Name: WDS
online version: 
schema: 2.0.0
title: Remove-WdsInstallImage
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 3C6DCA6C-A525-42EA-908C-61695AF4D4B8
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-WdsInstallImage

## SYNOPSIS
Removes an install image from an image store.

## SYNTAX

```
Remove-WdsInstallImage [-ImageGroup <String>] -ImageName <String> [-FileName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WdsInstallImage** cmdlet removes an install image from an image store.
Once you remove the image, you cannot recover it unless you add it again from its original source.
Specify the install image with the image name and image group name.
You must specify the file name if the image name and image group name do not uniquely identify the install image.

## EXAMPLES

### Example 1: Remove an install image
```
PS C:\> Remove-WdsInstallImage -InstallImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName install-3.wim
```

This command removes an install image named install3.wim.

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
Use this parameter to specify the file name for the install image if the install image name does not uniquely identify the image.

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
This image group contains the image to remove..
If you do not specify an image group, and only one image group exists on the server, the cmdlet uses that image group by default.
If more than one image group exists on the server, you must specify the image group.

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
This is the name of the image to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

## NOTES

## RELATED LINKS

[Copy-WdsInstallImage](./Copy-WdsInstallImage.md)

[Disable-WdsInstallImage](./Disable-WdsInstallImage.md)

[Export-WdsInstallImage](./Export-WdsInstallImage.md)

[Get-WdsInstallImage](./Get-WdsInstallImage.md)

[Import-WdsInstallImage](./Import-WdsInstallImage.md)

[Set-WdsInstallImage](./Set-WdsInstallImage.md)

