---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsInstallImage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/export-wdsinstallimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-WdsInstallImage
---

# Export-WdsInstallImage

## SYNOPSIS
Exports an existing install image from an image store.

## SYNTAX

```
Export-WdsInstallImage -Destination <String> [-NewImageName <String>] [-NewDescription <String>] [-Append]
 [-Force] -ImageName <String> [-ImageGroup <String>] [-FileName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Export-WdsInstallImage** cmdlet exports an existing install image from an image store to a file.
If an image file already is in that location, you may overwrite it, append the new image to a file, or leave it in place.
Specify the install image with the image name and image group name.
You must specify the file name if the image name and image group name do not uniquely identify the install image.

## EXAMPLES

### Example 1: Export an image
```
PS C:\> Export-WdsInstallImage -Append -Destination "D:\images\exported.wim" -ImageName "Windows Latest with LOB apps" -FileName "install-3.wim" -ImageGroup "Fabrikam Latest Images" -NewImageName "Fabrikam Latest"
```

This command exports an image and appends the image to an existing file, if it exists.

## PARAMETERS

### -Append
Indicates that the cmdlet appends an image to an existing image file.
The cmdlet creates a new file that has the image if there is no existing image file.

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
Specifies a fully qualified path that is available to the Windows Deployment Service server.

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
This is the file name of the install image.
Specifies the file name of the install image.
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
Forces the command to run without asking for user confirmation.

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

### -ImageGroup
Specifies the name of an image group.
This image group contains the image to export.
If you do not specify an image group, and only one image group exists on the server, the cmdlet uses that image group by default.
If more than one image group exists on the server, you must specify the image group

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
Specifies a new description for the install image to create in the export operation

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
Specifies a new name for the image file to create in the export operation.
If you do not specify a name, the cmdlet uses the display name of the source image.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsInstallImage

## NOTES

## RELATED LINKS

[Copy-WdsInstallImage](./Copy-WdsInstallImage.md)

[Disable-WdsInstallImage](./Disable-WdsInstallImage.md)

[Enable-WdsInstallImage](./Enable-WdsInstallImage.md)

[Get-WdsInstallImage](./Get-WdsInstallImage.md)

[Import-WdsInstallImage](./Import-WdsInstallImage.md)

[Remove-WdsInstallImage](./Remove-WdsInstallImage.md)

[Set-WdsInstallImage](./Set-WdsInstallImage.md)

