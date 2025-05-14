---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsBootImage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/import-wdsbootimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-WdsBootImage
---

# Import-WdsBootImage

## SYNOPSIS
Imports a boot image to the image store.

## SYNTAX

### ImageFile
```
Import-WdsBootImage [-NewImageName <String>] [-NewDescription <String>] [-DisplayOrder <UInt32>] [-SkipVerify]
 [-NewFileName <String>] -Path <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### AutoStart
```
Import-WdsBootImage [-NewImageName <String>] [-NewDescription <String>] [-DisplayOrder <UInt32>] [-SkipVerify]
 [-NewFileName <String>] [-TransmissionName <String>] [-Multicast] -Path <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Import-WdsBootImage** cmdlet imports a boot image from a Windows image file (.wim) to the Windows Deployment Services image store.
You can assign the name, description, and file name of the image that you import.
You can also enable a multicast transmission for the image.

## EXAMPLES

### Example 1: Import a boot image
```
PS C:\> Import-WdsBootImage -Path "E:\sources\boot.wim" -NewImageName "Fabrikam LOB setup (x86)" -NewDescription "Choose this image to install Fabrikam LOB on computers with x86 processors." -NewFileName "Fabrikamx86boot.wim" -SkipVerify
```

This command imports a boot image named boot.wim.
The command specifies a new image name, description, and file name for the imported image.
The command specifies that Windows Deployment Services does not verify the source image file before it adds it to the image store.

### Example 2: Import a boot image and enable multicast
```
PS C:\>Import-WdsBootImage -Path "D:\Images\BootImages\winpe.wim" -DisplayOrder 3 -Multicast -TransmissionName "Custom LOB multicast"
```

This command imports a boot image named winpe.wim.
The command specifies the order in which boot images appear in the menu on PXE clients.
The command enables a multicast transmission of the image and specifies the name for the multicast transmission.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -DisplayOrder
Specifies the order in which images appear in the menu on Pre-Boot Execution Environment (PXE) clients.
The menu lists the boot images in ascending order, smallest number to largest number.

If two boot images have the same display order, the imported images appear in alphabetical order of file name.
If you do not specify this parameter, the imported images appear in the middle of the list.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Multicast
Indicates that the cmdlet enables an autocast transmission of the image.
If you do not specify the *TransmissionName* parameter, Windows Deployment Services uses the image name of the imported image for the multicast.

```yaml
Type: SwitchParameter
Parameter Sets: AutoStart
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewDescription
Specifies a new description.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewFileName
Specifies a new file name for the image file.
Windows Deployment Services verifies that the source image file is unique before it adds it to the image store.

If you do not specify this parameter, Windows Deployment Services uses the file name of the source image file for the imported image file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewImageName
Specifies a name for the image.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the fully qualified path of the file that contains the boot image.
The path must available to the Windows Deployment Services server.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SkipVerify
Indicates that Windows Deployment Services does not verify the source image file before it adds it to the image store.

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

### -TransmissionName
Specifies a name for the multicast transmission.
If you do not specify this parameter, Windows Deployment Services uses the image name of the imported image for the multicast.

```yaml
Type: String
Parameter Sets: AutoStart
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsBootImage

## NOTES

## RELATED LINKS

[Get-WdsBootImage](./Get-WdsBootImage.md)

[Set-WdsBootImage](./Set-WdsBootImage.md)

[Enable-WdsBootImage](./Enable-WdsBootImage.md)

[Disable-WdsBootImage](./Disable-WdsBootImage.md)

[Remove-WdsBootImage](./Remove-WdsBootImage.md)

[Export-WdsBootImage](./Export-WdsBootImage.md)

