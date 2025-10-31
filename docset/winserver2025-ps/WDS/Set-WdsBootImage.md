---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsBootImage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/set-wdsbootimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WdsBootImage
---

# Set-WdsBootImage

## SYNOPSIS
Modifies settings of a boot image.

## SYNTAX

### StopMulticastTransmission
```
Set-WdsBootImage [-NewImageName <String>] [-NewDescription <String>] [-DisplayOrder <UInt32>]
 -ImageName <String> -Architecture <Architecture> [-FileName <String>] [-StopMulticastTransmission] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### AutoStart
```
Set-WdsBootImage [-NewImageName <String>] [-NewDescription <String>] [-DisplayOrder <UInt32>]
 -ImageName <String> -Architecture <Architecture> [-FileName <String>] [-Multicast]
 [-TransmissionName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### BootImageName
```
Set-WdsBootImage [-NewImageName <String>] [-NewDescription <String>] [-DisplayOrder <UInt32>]
 -ImageName <String> -Architecture <Architecture> [-FileName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WdsBootImage** cmdlet modifies information associated with a boot image in the Windows Deployment Services image store.
You can use the cmdlet to change the name and description of the boot image, set the display order in the boot menu, and enable the boot image for multicast transmissions.

Specify the boot image by using the *ImageName* and *Architecture* parameters.
If the image name and architecture do not uniquely identify the image, also specify the *FileName* parameter.

## EXAMPLES

### Example 1: Change boot image settings
```
PS C:\> Set-WdsBootImage -Architecture x86 -ImageName " Fabrikam LOB setup (x86)" -DisplayOrder 2 -NewImageName " Fabrikam LOB setup with re-partitioning (x86)" -NewDescription "Choose this image to re-partition the disk, and install Fabrikam LOB on computers with x86 processors."
```

This command changes the settings of the boot image named Fabrikam LOB setup (x86) for the x86 architecture.
The command sets the display order of the boot image on the boot menu on PXE clients, and specifies a new name and description for the boot image.

### Example 2: Start a multicast transmission of a boot image
```
PS C:\> Set-WdsBootImage -Architecture x86 -ImageName " Fabrikam LOB setup (x86)" -Multicast -TransmissionName "Custom WinPE multicast"
```

This command starts a multicast transmission of the boot image named Fabrikam LOB setup (x86) for the x86 architecture.
The command specifies that the multicast transmission is named Custom WinPE multicast.

### Example 3: Stop a multicast transmission of a boot image
```
PS C:\> Set-WdsBootImage -Architecture x86 -ImageName "Fabrikam LOB setup (x86)" -StopMulticastTransmission -Force
```

This command stops a multicast transmission of the boot image named Fabrikam LOB setup (x86) for the x86 architecture.
The *Force* parameter specifies that the cmdlet disconnects any clients connected to the multicast transmission.

## PARAMETERS

### -Architecture
Specifies an architecture.
This is the architecture of the boot image.
Because you can use the same image name for boot images in different architectures, specify this parameter to make sure that you modify the correct image.
The acceptable values for this parameter are:

- ARM
- ia64
- x64
- x86

```yaml
Type: Architecture
Parameter Sets: (All)
Aliases:
Accepted values: X86, Ia64, X64, Arm

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Specifies the order in which images appear in the boot menu on Pre-Boot Execution Environment (PXE) clients.
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

### -FileName
Specifies a file name.
This is the file name of the boot image.
Use this parameter to specify the file name for the boot image if the boot image name does not uniquely identify the image.

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
Forces the command to run without asking for user confirmation.

If you specify this parameter, the cmdlet disconnects any clients connected to the multicast transmission.
If you do not specify this parameter, and you specified the *Multicast* parameter to enable an autocast transmission of the image, existing clients finish receiving the content, but no additional clients can join the multicast transmission.

```yaml
Type: SwitchParameter
Parameter Sets: StopMulticastTransmission
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -StopMulticastTransmission
Indicates that the cmdlet stops the multicast transmission of the image.

If you specify the *Force* parameter, the cmdlet disconnects any clients connected to the multicast transmission.
If you do not specify the *Force* parameter, and the transmission is autocast, current clients finish receiving the content, but no additional clients can join the transmission.

```yaml
Type: SwitchParameter
Parameter Sets: StopMulticastTransmission
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

[Enable-WdsBootImage](./Enable-WdsBootImage.md)

[Disable-WdsBootImage](./Disable-WdsBootImage.md)

[Remove-WdsBootImage](./Remove-WdsBootImage.md)

[Import-WdsBootImage](./Import-WdsBootImage.md)

[Export-WdsBootImage](./Export-WdsBootImage.md)

