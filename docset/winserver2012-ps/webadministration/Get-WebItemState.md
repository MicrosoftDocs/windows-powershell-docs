---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://docs.microsoft.com/powershell/module/webadministration/get-webitemstate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WebItemState

## SYNOPSIS
Gets the run-time state of a site or an application pool.

## SYNTAX

```
Get-WebItemState [-Protocol <String>] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Gets the run-time state of a site or an application pool.

## EXAMPLES

### -------------- EXAMPLE 1: Retrieve the State of all Web sites --------------
```
C:\PS>Get-WebItemState "IIS:\sites\*"
```

Returns information about the state of all the sites on the IIS server.

### -------------- EXAMPLE 2: Retrieving the State of the Default Web Site using HTTP--------------
```
IIS:\>Get-WebItemState '.\Default Web Site' -Protocol http
```

Value

-----

Started

Returns information about the HTTP binding on the Default Web Site.

## PARAMETERS

### -PSPath
The path to the application pool or site.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Protocol
Specifies the protocol binding for which information is returned, such as HTTP or FTP.
TheProtocolparameter is applicable only when the cmdlet is used for sites.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSObject

## OUTPUTS

### PSObject

## NOTES

## RELATED LINKS

