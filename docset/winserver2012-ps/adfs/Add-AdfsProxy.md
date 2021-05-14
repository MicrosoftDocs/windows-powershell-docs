---
external help file: Microsoft.FederationServices.Deployment.dll-Help.xml
Module Name: ADFS
online version: https://docs.microsoft.com/powershell/module/adfs/add-adfsproxy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-AdfsProxy

## SYNOPSIS
Configures this computer as a federation server proxy.

## SYNTAX

```
Add-AdfsProxy [-FederationServiceName] <String> -FederationServiceTrustCredential <PSCredential>
 [-ForwardProxy <String>] [<CommonParameters>]
```

## DESCRIPTION
The Add-Adfsproxy cmdlet configures this computer as a federation server proxy.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>$fsCredential = Get-Credential
C:\PS>Add-AdfsProxy -FederationServiceName fs.corp.contoso.com -FederationServiceTrustCredential $fscredential
```

Description

-----------

Adds a federation service proxy to an existing AD FS installation with federation service name fs.corp.contoso.com.
Credentials entered as FederationServiceTrustCredential can be the AD FS service account or another account that has administrative permissions on the federation server(s) on which the federation service is installed.

## PARAMETERS

### -FederationServiceName
Specifies the name of the federation service for which this computer will proxy requests.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FederationServiceTrustCredential
Specifies the credentials of the Active Directory identity that is authorized to register new federation server proxies.
By default, this is the account under which the federation service runs or an account that is a member of the administrators group on the federation server.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForwardProxy
Specifies the DNS name and port of an HTTP proxy that this federation server proxy will use to obtain access to the federation service.
For example, the syntax to use to specify a forward proxy with a host name of "proxy01" that is located within the corp.contoso.com domain and that can be reached using the HTTP port of 8080 would be "proxy-01.corp.contoso.com:8080".

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### none

## OUTPUTS

### Result object

## NOTES

## RELATED LINKS

