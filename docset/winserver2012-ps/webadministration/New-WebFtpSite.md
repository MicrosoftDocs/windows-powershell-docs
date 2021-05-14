---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://docs.microsoft.com/powershell/module/webadministration/new-webftpsite?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-WebFtpSite

## SYNOPSIS
Create a new FTP 7 Site.

## SYNTAX

```
New-WebFtpSite [-Name] <String> [-Id <UInt32>] [-Port <UInt32>] [-IPAddress <String>] [-HostHeader <String>]
 [-PhysicalPath <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
Creates a new FTP site.
FTP 7 or later must be installed before this cmdlet will function successfully.

## EXAMPLES

### -------------- EXAMPLE 1: Creating a new FTP site binding --------------
```
IIS:\>New-WebFtpSite -Name testFtpSite -Port 21 -PhysicalPath c:\test -HostHeader mySite -IPAddress 127.0.0.1
```

Creates a new FTP site named "testFtpSite" (works with FTP7 only).

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
The host header of the new FTP site.

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
The IP Address of the new FTP site.

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
The ID of the new FTP site.

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
The name of the new FTP site.

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
The physical path to the new FTP site.
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
The port number of the new FTP site.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

