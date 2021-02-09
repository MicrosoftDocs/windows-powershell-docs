---
external help file: MSFT_WdsInstallImageGroup_v1.0.cdxml-help.xml
Module Name: WDS
online version: 
schema: 2.0.0
title: Remove-WdsInstallImageGroup
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C09D8B54-6768-434D-A840-D47868CBD3DB
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-WdsInstallImageGroup

## SYNOPSIS
Removes an install image group.

## SYNTAX

```
Remove-WdsInstallImageGroup -Name <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WdsInstallImageGroup** cmdlet removes an install image group and all the images it contains.
When you remove an image group, the Windows Deployment Services does not offer the images in the image group to clients.

## EXAMPLES

### Example 1: Remove an install image group
```
PS C:\> Remove-WdsInstallImageGroup -Name "Fabrikam LOB Images"
```

This command removes the image group named Fabrikam LOB Images.

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

### -Name
Specifies a name.
This is the name of an install image group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: GroupName

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

[Get-WdsInstallImageGroup](./Get-WdsInstallImageGroup.md)

[Set-WdsInstallImageGroup](./Set-WdsInstallImageGroup.md)

[New-WdsInstallImageGroup](./New-WdsInstallImageGroup.md)

[Remove-WdsInstallImageGroup](./Remove-WdsInstallImageGroup.md)

