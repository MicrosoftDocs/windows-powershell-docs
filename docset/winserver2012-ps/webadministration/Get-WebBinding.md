---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webbinding?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WebBinding

## SYNOPSIS
Gets the bindings on the specified IIS site.

## SYNTAX

```
Get-WebBinding [[-Name] <String>] [-Protocol <String>] [-Port <String>] [-IPAddress <String>]
 [-HostHeader <String>] [<CommonParameters>]
```

## DESCRIPTION
Gets information about the bindings configured on the site specified, such as protocol and port number.

## EXAMPLES

### -------------- EXAMPLE 1: Get the site bindings of the Default Web Site --------------
```
IIS:\>Get-WebBinding -Name "Default Web Site"
```

Gets the bindings configured on the Default Web Site.

## PARAMETERS

### -HostHeader
The host name for which the binding is configured.

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
The IP address for which the binding is configured.

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

### -Name
The name of the site for which binding information is returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port
The port for which the binding is configured.

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

### -Protocol
The protocol for which the binding is configured, usually http, https or ftp.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.IIs.PowerShell.Framework.ConfigurationElement#bindings#binding

## NOTES

## RELATED LINKS
