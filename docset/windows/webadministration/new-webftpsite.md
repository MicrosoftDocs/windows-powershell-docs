---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: New-WebFtpSite
ms.reviewer:
ms.assetid: 39D2484E-0D39-40CB-B348-94BE0088156B
---

# New-WebFtpSite

## SYNOPSIS
Creates an FTP 7 Site.

## SYNTAX

```
New-WebFtpSite [-Name] <String> [-Id <UInt32>] [-Port <UInt32>] [-IPAddress <String>] [-HostHeader <String>]
 [-PhysicalPath <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **New-WebFtpSite** cmdlet creates an FTP site.
This cmdlet requires FTP 7 or later.

## EXAMPLES

### Example 1: Create an FTP site binding
```
IIS:\> New-WebFtpSite -Name "testFtpSite" -Port 21 -PhysicalPath "c:\test" -HostHeader "mySite" -IPAddress "127.0.0.1"
```

This command creates an FTP site named testFtpSite.
This command works with FTP7 only.

## PARAMETERS

### -Force
Forces the new FTP site to be created.

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
Specifies the host header of the new FTP site.

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
Specifies the IP Address of the new FTP site.

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
Specifies the ID of the new FTP site.

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
Specifies the name of the new FTP site.

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
Specifies the physical path to the new FTP site.
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
Specifies the port number of the new FTP site.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

