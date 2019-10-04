---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: 
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-RDPersonalVirtualDesktopAssignment
ms.reviewer:
ms.assetid: 9E44FA3F-AD00-43B5-B5CE-D10F4DD4C9B6
---

# Get-RDPersonalVirtualDesktopAssignment

## SYNOPSIS
Retrieves a list of personal virtual desktops and associated user accounts.

## SYNTAX

### GetByCollection (Default)
```
Get-RDPersonalVirtualDesktopAssignment [-CollectionName] <String> [-ConnectionBroker <String>]
 [<CommonParameters>]
```

### GetByDesktop
```
Get-RDPersonalVirtualDesktopAssignment [-CollectionName] <String> -VirtualDesktopName <String>
 [-ConnectionBroker <String>] [<CommonParameters>]
```

### GetByUser
```
Get-RDPersonalVirtualDesktopAssignment [-CollectionName] <String> -User <String> [-ConnectionBroker <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDPersonalVirtualDesktopAssignment** cmdlet retrieves a list of personal virtual desktops and associated user accounts.
Specify one or more user accounts to retrieve the associated personal virtual desktops, or specify one or more personal virtual desktop names to retrieve the associated user accounts.

## EXAMPLES

### Example1: Retrieve a list of the current associations between personal virtual desktops and users
```
PS C:\>Get-RDPersonalVirtualDesktopAssignment -CollectionName "Virtual Desktop Collection"
```

This command lists current associations between personal virtual desktops and users from the virtual desktop collection named Virtual Desktop Collection.

## PARAMETERS

### -CollectionName
Specifies the name of a personal virtual desktop collection.

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

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not supply a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

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

### -User
Specifies one or more user accounts, in DOMAIN\User format.

```yaml
Type: String
Parameter Sets: GetByUser
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopName
Specifies the name of the virtual desktop.
This parameter is required.
The virtual desktop identified here must be a member of the collection that the **CollectionName** parameter specifies.

```yaml
Type: String
Parameter Sets: GetByDesktop
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Export-RDPersonalVirtualDesktopAssignment](./Export-RDPersonalVirtualDesktopAssignment.md)

[Import-RDPersonalVirtualDesktopAssignment](./Import-RDPersonalVirtualDesktopAssignment.md)

[Remove-RDPersonalVirtualDesktopAssignment](./Remove-RDPersonalVirtualDesktopAssignment.md)

[Set-RDPersonalVirtualDesktopAssignment](./Set-RDPersonalVirtualDesktopAssignment.md)

