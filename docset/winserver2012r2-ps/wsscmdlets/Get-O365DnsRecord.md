---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-o365dnsrecord?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-O365DnsRecord
---

# Get-O365DnsRecord

## SYNOPSIS
Gets all DNS records that require configuration at your domain name provider.

## SYNTAX

```
Get-O365DnsRecord [-DomainName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-O365DnsRecord** cmdlet gets all Domain Name System (DNS) records that require configuration at your domain provider so that you can complete the domain configuration for office_365_1.

## EXAMPLES

### Example 1: Get DNS records for a domain name provider
```
PS C:\> Get-O365DnsRecord -DomainName "Contoso.onmicrosoft.com"
```

This command gets all DNS records that require configuration at the domain name provider named Contoso.onmicrosoft.com.

### 1:
```
PS C:\>
```

## PARAMETERS

### -DomainName
Specifies the name of a domain name provider.
The cmdlet gets the DNS records that require configuration at the domain name provider that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
DomainName
Type: System.String
Description: name of the domain name provider

## OUTPUTS

### Microsoft.WindowsServerSolutions.RemoteAccess.Domains.DnsRecord
This cmdlet returns a class that represents the DNS record. 
When output: office_365_2 integration is enabled
Label Property System.String
Length Property System.Int32

## NOTES

## RELATED LINKS

