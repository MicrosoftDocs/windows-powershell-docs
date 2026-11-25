---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsInstallImage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/copy-wdsinstallimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-WdsInstallImage
---

# Copy-WdsInstallImage

## SYNOPSIS
Copies install images within an image group.

## SYNTAX

### SingleImageManualStart
```
Copy-WdsInstallImage [-NewDescription <String>] [-ImageGroup <String>] [-FileName <String>] -ImageName <String>
 -NewFileName <String> -NewImageName <String> [-TransmissionName <String>] [-Multicast] [-ManualStart]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### SingleImageAutoStart
```
Copy-WdsInstallImage [-NewDescription <String>] [-ImageGroup <String>] [-FileName <String>] -ImageName <String>
 -NewFileName <String> -NewImageName <String> [-StartTime <DateTime>] [-ClientCount <UInt32>]
 [-TransmissionName <String>] [-Multicast] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### SingleImage
```
Copy-WdsInstallImage [-NewDescription <String>] [-ImageGroup <String>] [-FileName <String>] -ImageName <String>
 -NewFileName <String> -NewImageName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Copy-WdsInstallImage** cmdlet copies install images in an image group.
You can only copy images that are in the same image group.
To copy images between image groups, use the Export-WdsInstallImage and Import-WdsInstallImage cmdlets.

When you work with multicast transmissions that use an install image as content you can do the following:

- Create and name an AutoCast transmission.
- Create and name a ScheduledCast transmission which starts when a preset number of clients are ready to start, at a specific time, or both.
- Create a ScheduledCast transmission that must be manually started.

An AutoCast transmission is a multicast transmission.
When a client requests an install image, the multicast transmission starts.
Clients that request the same image are joined to the multicast transmission.

A ScheduledCast transmission is a multicast transmission.
When a specified number of clients request an image, or a specified time of day is reached, the multicast transmission starts.
If you do not specify either of these conditions, you must manually start the transmission.

When you copy an image, specify the install image by the image name and image group name.
You must specify the file name if the image name and image group name do not uniquely identify the install image.

## EXAMPLES

### Example 1: Copy an install image
```
PS C:\> Copy-WdsInstallImage -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName "install-3.wim" -NewImageName "Fabrikam Latest with LOB v2.0 apps" -NewDescription "This Fabrikam Latest image contains the second wave of our line of business applications." -NewFileName "install-4.wim"
```

This command copies an install image.

### Example 2: Copy an install image as a multicast transmission
```
PS C:\>Copy-WdsInstallImage -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName "install-3.wim" -NewImageName "Fabrikam Latest with LOB v2.0 apps" -Multicast -TransmissionName "Fabrikam Latest AutoCast"
```

### Example 3:Copy an install image as a multicast transmission with a client count and start time
```
PS C:\>Copy-WdsInstallImage -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName "install-3.wim" -NewImageName "Fabrikam Latest with LOB v2.0 apps" -Multicast -ClientCount 50 -StartTime 2014/12/01:11:00 -TransmissionName "Fabrikam Latest ScheduledCast with automatic start"
```

### Example 4: Copy an install image as a multicast transmission with a manual start
```
PS C:\>Copy-WdsInstallImage -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName "install-3.wim" -NewImageName "Fabrikam Latest with LOB v2.0 apps" -Multicast -ManualStart -TransmissionName "Fabrikam Latest ScheduledCast with manual start"
```

This command copies an install image as a multicast transmission with a manual start.

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
If you also specify *MulticastTransmission*, this parameter specifies the number of clients that must connect to the ScheduledCast transmission for it to start.
The *StartScheduledCast* parameter can start a transmission before reaching the client count.
If you specify the *ClientCount* parameter with the *StartTime* parameter, the transmission starts when either a sufficient number of clients connect, or at the time specified by the *StartTime* parameter.

You may not use this parameter together with the *ManualStart* parameter.

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
This image group contains the image to copy.
If you do not specify an image group, and only one image group exists on the server, that image group will be used by default.
If more than one image group exists on the server, you must specify an image group.

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
This is the name of the image to copy.
You must provide a new image name.

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

### -ManualStart
Indicates that the transmission uses a manual start.
If you also specify the *MulticastTransmission* parameter with this parameter, the cmdlet creates a ScheduledCast transmission that does not start until a StartScheduledCast command is given.

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
Specifies a new description for the install image to create in the copy operation.

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
Specifies a new name for the image file to create in the copy operation.

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

### -NewImageName
Specifies a new name for the image to create in the copy operation.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsInstallImage

## NOTES

## RELATED LINKS

[Disable-WdsInstallImage](./Disable-WdsInstallImage.md)

[Enable-WdsInstallImage](./Enable-WdsInstallImage.md)

[Export-WdsInstallImage](./Export-WdsInstallImage.md)

[Get-WdsInstallImage](./Get-WdsInstallImage.md)

[Import-WdsInstallImage](./Import-WdsInstallImage.md)

[Remove-WdsInstallImage](./Remove-WdsInstallImage.md)

[Set-WdsInstallImage](./Set-WdsInstallImage.md)

