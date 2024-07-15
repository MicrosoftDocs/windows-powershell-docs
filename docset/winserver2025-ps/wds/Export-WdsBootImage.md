---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsBootImage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/export-wdsbootimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-WdsBootImage
---

# Export-WdsBootImage

## SYNOPSIS
Exports an existing boot image from an image store.

## SYNTAX

```
Export-WdsBootImage [-NewDescription <String>] -Destination <String> [-NewImageName <String>] [-Force]
 -ImageName <String> -Architecture <Architecture> [-FileName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Export-WdsBootImage** cmdlet exports a boot image from the Windows Deployment Services image store to a Windows image file (.wim).
You can use the *Force* parameter to overwrite the image file if you export an image to a file that already exists.

Specify the boot image by using the *ImageName* and *Architecture* parameters.
If the image name and architecture do not uniquely identify the image, also specify the *FileName* parameter.

## EXAMPLES

### Example 1: Export a boot image
```
PS C:\> Export-WdsBootImage -Architecture x86 -Destination "D:\images\exported.wim" -ImageName "Fabrikam LOB setup (x86)" -NewDescription "Fabrikam LOB exported from server" -Force
```

This command exports the boot image named Fabrikam LOB setup (x86) for the x86 architecture.
The command exports the image to the file that is named exported.wim.
The command specifies a description for the exported image.
The *Force* parameter specifies that the cmdlet overwrites a file that has the same name without prompting you for confirmation.

## PARAMETERS

### -Architecture
Specifies an architecture.
This is the architecture of the boot image.
Because you can use the same image name for boot images in different architectures, specify this parameter to make sure that you export the correct image.
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

### -Destination
Specifies the fully qualified path of the exported image.
The path must available to the Windows Deployment Services server.

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
Indicates that the cmdlet overwrites an image file if the file is in the path that you specify.

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

### -ImageName
Specifies the name of an image.
This is the name of the image to export.

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
If you do not specify this parameter, the cmdlet uses the name of the source image for the name of the exported image.

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

[Import-WdsBootImage](./Import-WdsBootImage.md)

