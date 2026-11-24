---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/new-website?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-Website
---

# New-Website

## SYNOPSIS
Creates an IIS website.

## SYNTAX

```
New-Website [-Name] <String> [-Id <UInt32>] [-Port <UInt32>] [-IPAddress <String>] [-SslFlags <Int32>]
 [-HostHeader <String>] [-PhysicalPath <String>] [-ApplicationPool <String>] [-Ssl] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-Website** cmdlet creates an Internet Information Services (IIS) website with the settings specified in parameter values.

## EXAMPLES

### Example 1: Create a website
```
IIS:\> New-WebSite -Name "TestSite" -Port 80 -HostHeader "TestSite" -PhysicalPath "$Env:systemdrive\inetpub\testsite"
```

This command creates a website named TestSite.

## PARAMETERS

### -ApplicationPool
Specifies the application pool in which the new site runs.

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

### -HostHeader
Specifies the host header of the new site.

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

### -IPAddress
Specifies the IP address of the new site.

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

### -Id
Specifies the ID of the new site.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the new site.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PhysicalPath
Specifies the physical path of the new site.
The specified folder must already exist.

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

### -Port
Specifies the port of the new site.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ssl
Indicates that this cmdlet enables HTTPS binding on the site.

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

### -SslFlags
Indicates what type of certificate and certificate storage the new website supports.
The acceptable values for this parameter are:

- 0: Regular certificate in Windows certificate storage.
- 1: SNI certificate.

- 2: Central certificate store.
- 3: SNI certificate in central certificate store.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Website](./Get-Website.md)

[Remove-Website](./Remove-Website.md)

[Start-Website](./Start-Website.md)

[Stop-Website](./Stop-Website.md)

