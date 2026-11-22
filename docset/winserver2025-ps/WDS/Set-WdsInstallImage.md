---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsInstallImage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/set-wdsinstallimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WdsInstallImage
---

# Set-WdsInstallImage

## SYNOPSIS
Modifies the properties of an install image.

## SYNTAX

### StopTransmission
```
Set-WdsInstallImage [-NewImageName <String>] [-NewDescription <String>] [-DisplayOrder <UInt32>]
 [-UserFilter <String>] [-UnattendFile <String>] [-OverwriteUnattend] [-ImageGroup <String>]
 [-FileName <String>] -ImageName <String> [-StopMulticastTransmission] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### StartTransmission
```
Set-WdsInstallImage [-NewImageName <String>] [-NewDescription <String>] [-DisplayOrder <UInt32>]
 [-UserFilter <String>] [-UnattendFile <String>] [-OverwriteUnattend] [-ImageGroup <String>]
 [-FileName <String>] -ImageName <String> [-StartScheduledCast] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### SingleImage
```
Set-WdsInstallImage [-NewImageName <String>] [-NewDescription <String>] [-DisplayOrder <UInt32>]
 [-UserFilter <String>] [-UnattendFile <String>] [-OverwriteUnattend] [-ImageGroup <String>]
 [-FileName <String>] -ImageName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ManualStart
```
Set-WdsInstallImage [-NewImageName <String>] [-NewDescription <String>] [-DisplayOrder <UInt32>]
 [-UserFilter <String>] [-UnattendFile <String>] [-OverwriteUnattend] [-ImageGroup <String>]
 [-FileName <String>] -ImageName <String> [-Multicast] [-TransmissionName <String>] [-ManualStart]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### AutoStart
```
Set-WdsInstallImage [-NewImageName <String>] [-NewDescription <String>] [-DisplayOrder <UInt32>]
 [-UserFilter <String>] [-UnattendFile <String>] [-OverwriteUnattend] [-ImageGroup <String>]
 [-FileName <String>] [-ClientCount <UInt32>] [-StartTime <DateTime>] -ImageName <String> [-Multicast]
 [-TransmissionName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-WdsInstallImage** cmdlet modifies the properties of an install image in the Windows Deployment Services image store.
Use this cmdlet to do any of the following:

- Change the name of an install image.
- Change the description of an install image.
- Set the display order of an install image in the image menu.
- Specify an answer file for unattended setup of an install image.
- Set permissions for users or groups to access the image.

When you work with multicast transmissions that use an install image as content, you can:

- Create and name an AutoCast transmission.
- Create and name a ScheduledCast transmission which starts when a preset number of clients are ready to start, at a specific time, or both.
- Create a manually started ScheduledCast transmission.
- Start a ScheduledCast transmission.
- Stop a multicast transmission in progress, and then either disconnect clients immediately, or allow for them to finish, but not allow for any new clients to join.

An AutoCast transmission is a multicast transmission.
When a client requests an install image, the multicast transmission starts.
Clients that request the same image are joined to the multicast transmission.

A ScheduledCast transmission is a multicast transmission.
When a specified number of clients request an image, or a specified time of day is reached, the multicast transmission starts.
If you do not specify either of these conditions, you must manually start the transmission.

Specify the install image by using the image name and image group name.
If the image name and image group name do not uniquely identify the install image, specify the file name.

## EXAMPLES

### Example 1: Modify an install image
```
PS C:\> Set-WdsInstallImage -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName "install-3.wim" -DisplayOrder 0 -NewImageName "Fabrikam Latest with LOB v2.0 apps" -UnattendFile "D:\images\unattend\FabrikamwLOB.xml" -OverwriteUnattend -UserFilter "O:BAG:DUD:(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)(A;OICI;0x1200a9;;;AU)(A;OICI;FA;;;S-1-5-80-1688844526-3235337491-1375791646-891369040-3692469510)"
```

This command modifies an install image for automatic installation.

### Example 2: Modify an install image for multicast transmission
```
PS C:\>Set-WdsInstallImage -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName "install-3.wim" -Multicast -TransmissionName "Fabrikam Latest AutoCast"
```

This command modifies an install image for multicast transmission.

### Example 3: Modify start time and client count conditions for an install image
```
PS C:\>Set-WdsInstallImage -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName "install-3.wim" -Multicast -ClientCount 50 -StartTime 2014/12/01:11:00 -TransmissionName "Fabrikam Latest ScheduledCast with automatic start"
```

This command modifies an install image by using the *ClientCount* and *StartTime* parameters.

### Example 4: Modify an install image for manual start
```
PS C:\>Set-WdsInstallImage -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName "install-3.wim" -Multicast -ManualStart -TransmissionName "Fabrikam Latest ScheduledCast with manual start"
```

This command modifies an install image by using the *ManualStart* parameter.

### Example 5: Modify an install image to start
```
PS C:\>Set-WdsInstallImage -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName "install-3.wim" -StartScheduledCast
```

This command modifies an install image to begin a scheduled transmission.

### Example 6: Modify an install image to stop a transmission
```
PS C:\>Set-WdsInstallImage -ImageName "Fabrikam Latest with LOB apps" -ImageGroup "Fabrikam Latest Images" -FileName "install-3.wim" -StopMulticastTransmission
```

This command stops a multicast transmission for an install image.

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
If you also specify the *MulticastTransmission* parameter, the client count specifies the number of clients that must connect to the ScheduledCast transmission for it to begin.
Use the *StartScheduledCast* parameter to begin a transmission before reaching the client count.
If you specify the *ClientCount* parameter and the *StartTime* parameter, the transmission starts when either a sufficient number of clients have connected or at the time specified by the *StartTime* parameter.

You may not specify this parameter together with the *ManualStart* parameter.

```yaml
Type: UInt32
Parameter Sets: AutoStart
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

### -Force
Indicates that the cmdlet disconnects any clients currently connected to the multicast transmission.
If you do not specify this parameter for an AutoCast transmission, existing clients finish receiving the content, but no new clients join.

```yaml
Type: SwitchParameter
Parameter Sets: StopTransmission
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageGroup
Specifies the name of an image group.
This image group contains the image to modify.
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
This is the name of the image to modify.

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
If you also specify the *MulticastTransmission* parameter, the cmdlet creates a ScheduledCast transmission that does not begin until a StartScheduledCast command is given.

```yaml
Type: SwitchParameter
Parameter Sets: ManualStart
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Multicast
Indicates that the cmdlet enables an AutoCast transmission on the image.
If you do not specify a name by using the *TransmissionName* parameter, the multicast transmission uses the image name

```yaml
Type: SwitchParameter
Parameter Sets: ManualStart, AutoStart
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewDescription
Specifies a new description for the install image to create in the set operation.

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
Specifies a new name for the image file to create in the set operation.

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

### -OverwriteUnattend
Indicates that the cmdlet can overwrite an existing answer file.
If you specify the **UnattendFile** parameter, the cmdlet overwrites an existing answer file associated with the image.

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

### -StartScheduledCast
Indicates that the cmdlet enables and starts a ScheduledCast transmission on the image.
If there are no clients connected to the transmission, the transmission does not start.

```yaml
Type: SwitchParameter
Parameter Sets: StartTransmission
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies a day and time, in MM/DD/YYYY.hh:mm:ss format, that denotes the start time.
If you specify the *MulticastTransmission* parameter, this parameter denotes the time the ScheduledCast transmission starts.
The StartScheduledCast command can start a transmission before reaching the client count.
If you specify both the *StartTime* parameter and the *ClientCount* parameter, the transmission starts when either a sufficient number of clients connect, or the time specified in this parameter is reached.
Do not specify this parameter together with the *ManualStart* parameter.

```yaml
Type: DateTime
Parameter Sets: AutoStart
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StopMulticastTransmission
Indicates that Windows Deployment Services stop the multicast transmission of the image.
If you specify the *Force* parameter, the cmdlet disconnects any clients connected to the multicast transmission.
If you do not specify the *Force* parameter, and the transmission is autocast, current clients finish receiving the content, but no additional clients can join the transmission.

```yaml
Type: SwitchParameter
Parameter Sets: StopTransmission
Aliases:

Required: True
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
Parameter Sets: ManualStart, AutoStart
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnattendFile
Specifies the full path for the answer file associated with the image.

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

### -UserFilter
Specifies the access controls on the image, in Security Descriptor Definition Language (SDDL) format.
To restrict access to the file resources, and access to all images in an image group, set access controls on the image group itself.

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

[Export-WdsInstallImage](./Export-WdsInstallImage.md)

[Get-WdsInstallImage](./Get-WdsInstallImage.md)

[Import-WdsInstallImage](./Import-WdsInstallImage.md)

[Remove-WdsInstallImage](./Remove-WdsInstallImage.md)

