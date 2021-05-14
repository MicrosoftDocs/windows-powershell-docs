---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/hcs/enable-hcsremotemanagement?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-HcsRemoteManagement
---

# Enable-HcsRemoteManagement

## SYNOPSIS
Enables remote Windows PowerShell management.

## SYNTAX

```
Enable-HcsRemoteManagement [-AllowHttp] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-HcsRemoteManagement** cmdlet enables remote Windows PowerShell® management for this device.
You can manage remotely by using the SSAdmin console session configuration and the Support session configuration.
By default, the cmdlet enables remote management over HTTPS only.
Specify the **AllowHttp** parameter to enable remote management over HTTP as well.

To obtain the required certificate for connecting by using HTTPS, use the Get-HcsRemoteManagementCert cmdlet.

For more information about how to run remote commands in Windows PowerShell, type Get-Help about_Remotehttp://technet.microsoft.com/en-us/library/hh847900.aspx.

## EXAMPLES

### Example 1: Enable remote management
```
PS C:\>Enable-HcsRemoteManagement -AllowHttp
```

This command enables remote management for this device.
You can manage the device by using HTTP or HTTPS.

## PARAMETERS

### -AllowHttp
Indicates that the cmdlet enables remote management over HTTP as well as HTTPS.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[about_Remote](https://technet.microsoft.com/en-us/library/hh847900.aspx)

[Disable-HcsRemoteManagement](./Disable-HcsRemoteManagement.md)

[Get-HcsRemoteManagementCert](./Get-HcsRemoteManagementCert.md)

