---
external help file: MSFT_WdsBootImage_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/wds/get-wdsbootimage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WdsBootImage
---

# Get-WdsBootImage

## SYNOPSIS
Gets properties of boot images from the image store.

## SYNTAX

```
Get-WdsBootImage [-Architecture <Architecture>] [-FileName <String>] [-ImageName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WdsBootImage** cmdlet gets properties of boot images in the Windows Deployment Services image store.
Get a boot image by specifying the **Architecture**, **FileName**, and **ImageName** parameters.
If the image name and architecture do not uniquely identify the image, also specify the **Filename** parameter.
If no parameter is specified, it will get all boot images.
If the image name and architecture do not uniquely identify a single image, the command will return all images that meet the criteria.

## EXAMPLES

### Example 1: Get properties of a boot image
```
PS C:\> Get-WdsBootImage -Architecture x86 -ImageName "Fabrikam LOB setup (x86)"
```

This command gets properties of the boot image named Fabrikam LOB setup (x86) for the x86 architecture.

## PARAMETERS

### -Architecture
Specifies an architecture.
This is the architecture of the boot image.
Because you can use the same image name for boot images in different architectures, specify this parameter to ensure that you return the correct image.
The acceptable values for this parameter are:


     -- ARM

     -- ia64

     -- x64

     -- x86

```yaml
Type: Architecture
Parameter Sets: (All)
Aliases: 
Accepted values: X86, Ia64, X64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
This is the file name of the boot image.

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
This is the name of the image to get.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsBootImage

## NOTES

## RELATED LINKS

[Set-WdsBootImage](./Set-WdsBootImage.md)

[Enable-WdsBootImage](./Enable-WdsBootImage.md)

[Disable-WdsBootImage](./Disable-WdsBootImage.md)

[Remove-WdsBootImage](./Remove-WdsBootImage.md)

[Import-WdsBootImage](./Import-WdsBootImage.md)

[Export-WdsBootImage](./Export-WdsBootImage.md)

