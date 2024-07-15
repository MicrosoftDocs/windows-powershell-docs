---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsInstallImage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/import-wdsinstallimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-WdsInstallImage
---

# Import-WdsInstallImage

## SYNOPSIS
Imports an install image to an image store.

## SYNTAX

### SingleImageManualStart
```
Import-WdsInstallImage [-SkipVerify] [-ImageGroup <String>] [-DisplayOrder <UInt32>] [-UnattendFile <String>]
 -Path <String> [-NewImageName <String>] [-NewDescription <String>] [-NewFileName <String>]
 [-ImageName <String>] [-TransmissionName <String>] [-Multicast] [-ManualStart] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### SingleImageAutoStart
```
Import-WdsInstallImage [-SkipVerify] [-ImageGroup <String>] [-DisplayOrder <UInt32>] [-UnattendFile <String>]
 -Path <String> [-NewImageName <String>] [-NewDescription <String>] [-NewFileName <String>]
 [-ImageName <String>] [-ClientCount <UInt32>] [-StartTime <DateTime>] [-TransmissionName <String>]
 [-Multicast] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### SingleImage
```
Import-WdsInstallImage [-SkipVerify] [-ImageGroup <String>] [-DisplayOrder <UInt32>] [-UnattendFile <String>]
 -Path <String> [-NewImageName <String>] [-NewDescription <String>] [-NewFileName <String>]
 [-ImageName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Import-WdsInstallImage** cmdlet imports an install image to an image store.
You can import a single image from a WIM file, all images from a WIM file, or a VHD image.
If you add a single image, you can also specify a new name, description, and file name for the image.

When you work with multicast transmissions that use a single install image as content you can do any of the following:

- Create and name an AutoCast transmission.
- Create and name a ScheduledCast transmission which starts when a preset number of clients are ready to start, at a specific time, or both.
- Create a manually started ScheduledCast transmission.

An AutoCast transmission is a multicast transmission.
When a client requests an install image, the multicast transmission starts.
Clients that request the same image are joined to the multicast transmission.

A ScheduledCast transmission is a multicast transmission.
When a specified number of clients request an image, or a specified time of day is reached, the multicast transmission starts.
If you do not specify either of these conditions, you must manually start the transmission.

If you add multiple images, they will be added to the same image group.
You can associate an answer file for unattended install with the images that you import.
Specify the image to import by using the full path of the image file.

## EXAMPLES

### Example 1: Import an image
```
PS C:\> Import-WdsInstallImage -Path "D:\images\install.wim" -ImageGroup "Fabrikam Latest Images" -SkipVerify
```

This command imports an install image and skips the verification of the image.

### Example 2: Import an install image by using an unattend file
```
PS C:\>Import-WdsInstallImage -Path "D:\images\install.wim" -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -DisplayOrder 0 -NewImageName "Fabrikam Latest with LOB v2.0 apps" -UnattendFile "D:\images\unattend\FabrikamLatestwLOB.xml"
```

This command imports an install image by using an answer file that is named FabrikamLatestwLOB.xml.

### Example 3: Import an install image and create a multicast transmission
```
PS C:\>Import-WdsInstallImage -Path "D:\images\install.wim" -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -Multicast -TransmissionName "Fabrikam Latest AutoCast"
```

This command imports an install image and creates a multicast transmission.

### Example 4: Import an install image and create a multicast transmission with a start time
```
PS C:\>Import-WdsInstallImage -Path "D:\images\install.wim" -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -Multicast -ClientCount 50 -StartTime 2014/12/01:11:00 -TransmissionName "Fabrikam Latest ScheduledCast with automatic start"
```

This command imports an install image and create a multicast transmission with an automatic start time.

### Example 5: Import an install image and create a multicast transmission with manual start
```
PS C:\>Import-WdsInstallImage -Path "D:\images\install.wim" -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -Multicast -ManualStart -TransmissionName "Fabrikam Latest ScheduledCast with manual start"
```

This command imports an install image and creates a multicast transmission with a manual start.

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

### -ClientCount
Specifies the number of clients that must connect to a transmission.
If you also specify *MulticastTransmission*, this parameter specifies the number of clients that must connect to the ScheduledCast transmission for it to begin.
The *StartScheduledCast* parameter can start a transmission before reaching the client count.
If you specify the *ClientCount* parameter with the *StartTime* parameter, the transmission starts when either a sufficient number of clients connect, or at the time specified by the *StartTime* parameter.

D not use this parameter together with the *ManualStart* parameter.

```yaml
Type: UInt32
Parameter Sets: SingleImageAutoStart
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayOrder
Specifies the order in which images appear in the boot menu on Pre-Boot Execution Environment (PXE) clients.
The menu lists the boot images in ascending order, smallest number to largest number.

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

### -ImageGroup
Specifies the name of an image group.
This image group contains the image to import.
If you do not specify an image group, and only one image group exists on the server, the cmdlet uses that image group by default.
If more than one image group exists on the server, you must specify the image group.

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

### -ImageName
Specifies the name of an image.
This is the name of the image to import.
This parameter does not support VHD images.

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

### -ManualStart
Indicates that the transmission uses a manual start.
If you also specify the *MulticastTransmission* parameter, the cmdlet creates a ScheduledCast transmission that does not begin until a StartScheduledCast command is given.

```yaml
Type: SwitchParameter
Parameter Sets: SingleImageManualStart
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Multicast
Indicates that the cmdlet enables an AutoCast transmission on the image.
If you do not specify a name by using the *TransmissionName* parameter, the multicast transmission uses the image name.

```yaml
Type: SwitchParameter
Parameter Sets: SingleImageManualStart, SingleImageAutoStart
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewDescription
Specifies a new description for the install image to create in the import operation.

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
Specifies a new file name for the install image to create in the import operation.
If you do not specify a name, the cmdlet uses the display name of the source image.
The file name must be unique.
If you add more than one image, a number is appended to the file name.

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
Specifies a new name for the image file to create in the import operation.

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
Specifies a fully-qualified path that is available to the Windows Deployment Services server.

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

### -StartTime
Specifies a day and time, in MM/DD/YYYY.hh:mm:ss format, that denotes the start time.
When you specify the *MulticastTransmission* parameter, this parameter denotes the time the ScheduledCast transmission starts.
The StartScheduledCast command can start a transmission before reaching the client count.
If you specify both the *StartTime* parameter and the *ClientCount* parameter, the transmission starts when either a sufficient number of clients connect, or the time specified in this parameter is reached.
Do not specify this parameter together with the *ManualStart* parameter.

```yaml
Type: DateTime
Parameter Sets: SingleImageAutoStart
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

```yaml
Type: String
Parameter Sets: SingleImageManualStart, SingleImageAutoStart
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnattendFile
Specifies the full path of the answer file associated with the image.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsInstallImage

## NOTES

## RELATED LINKS

[Copy-WdsInstallImage](./Copy-WdsInstallImage.md)

[Disable-WdsInstallImage](./Disable-WdsInstallImage.md)

[Enable-WdsInstallImage](./Enable-WdsInstallImage.md)

[Export-WdsInstallImage](./Export-WdsInstallImage.md)

[Get-WdsInstallImage](./Get-WdsInstallImage.md)

[Remove-WdsInstallImage](./Remove-WdsInstallImage.md)

[Set-WdsInstallImage](./Set-WdsInstallImage.md)

