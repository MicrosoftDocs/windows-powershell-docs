---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsBootImage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/remove-wdsbootimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WdsBootImage
---

# Remove-WdsBootImage

## SYNOPSIS
Removes a boot image from the image store.

## SYNTAX

```
Remove-WdsBootImage -ImageName <String> -Architecture <Architecture> [-FileName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WdsBootImage** cmdlet removes a boot image from the Windows Deployment Services image store.
When you remove a boot image, the boot image is not available in the Windows Deployment Services image store, and you cannot use the image to boot a client computer into to perform an operating system installation.
After you remove a boot image, you cannot recover the image unless you import it to the Windows Deployment Services image store from its original source.

Specify the boot image by using the *ImageName* and *Architecture* parameters.
If the image name and architecture do not uniquely identify the image, also specify the *FileName* parameter.

## EXAMPLES

### Example 1: Remove a boot image
```
PS C:\> Remove-WdsBootImage -Architecture x86 -ImageName "Fabrikam LOB setup (x86)"
```

This command removes the boot image named Fabrikam LOB setup (x86) for the x86 architecture.

## PARAMETERS

### -Architecture
Specifies an architecture.
This is the architecture of the boot image.
Because you can use the same image name for boot images in different architectures, specify this parameter to make sure that you remove the correct image.
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WdsBootImage](./Get-WdsBootImage.md)

[Set-WdsBootImage](./Set-WdsBootImage.md)

[Enable-WdsBootImage](./Enable-WdsBootImage.md)

[Disable-WdsBootImage](./Disable-WdsBootImage.md)

[Import-WdsBootImage](./Import-WdsBootImage.md)

[Export-WdsBootImage](./Export-WdsBootImage.md)

