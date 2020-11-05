---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: B942502D-1A80-4980-A8BA-5868A73F35E8
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# New-Website

## SYNOPSIS
Creates a new IIS Web site.

## SYNTAX

```
New-Website [-Name] <String> [-Id <UInt32>] [-Port <UInt32>] [-IPAddress <String>] [-SslFlags <Int32>]
 [-HostHeader <String>] [-PhysicalPath <String>] [-ApplicationPool <String>] [-Ssl] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
Creates a new IIS Web site with the settings specified in parameter values.

## EXAMPLES

### -------------- EXAMPLE 1: Add a New Web Site --------------
```
IIS:\>New-WebSite -Name TestSite -Port 80 -HostHeader TestSite -PhysicalPath "$env:systemdrive\inetpub\testsite"
```

Creates a new Web site named TestSite.

## PARAMETERS

### -ApplicationPool
The application pool in which the new site executes.

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
Specifies that the user is not prompted for confirmation.

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
The host header to use for the new site.

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
The IP address of the new site.

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
The ID to use for the new site.

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
The name of the new site to create.

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
The physical path to use for the new site.
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
The port to use for the new site.

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
Including the Ssl parameter enables HTTPS binding on the site.

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
Indicates what type of certificate and/or certificate storage the new website supports.
Only the following values are valid: 0 (Regular certificate in Windows certificate storage), 1 (SNI certificate), 2 (central certificate store), or 3 (SNI certificate in central certificate store).

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

