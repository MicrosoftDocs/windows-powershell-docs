---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfsclient?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsClient
---

# Add-AdfsClient

## SYNOPSIS
Registers an OAuth 2.0 client with AD FS.

## SYNTAX

```
Add-AdfsClient [-ClientId] <String> [-Name] <String> [[-RedirectUri] <Uri[]>] [-Description <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsClient** cmdlet registers an OAuth client with Active Directory Federation Services (AD FS).
In order to allow access from OAuth clients to resources secured by AD FS, you need to register the OAuth client with AD FS by using this cmdlet.

When you register an OAuth 2.0 client with AD FS, you must specify a client identifier  and a redirection URI, as well as a friendly name and description, for the OAuth client.
When an OAuth client requests access to a resource using the OAuth 2.0 protocol, the client must specify a client identifier and redirection URI to AD FS, in accordance with [RFC 6749](https://tools.ietf.org/html/rfc6749). 
AD FS will not allow access to a resource to clients that specify a client identifier or redirection URI that are not registered with AD FS.

## EXAMPLES

### Example 1: Add a client
```
PS C:\> Add-AdfsClient -Name "Payroll Application" -ClientId "ab762716-544d-4aeb-a526-687b73838a33" -RedirectUri "ms-app://s-1-15-2-2205112887-4282980309-3272664163-2407253042-283898840-27493891-3661245662/" -Description "OAuth 2.0 client for our Payroll application"
```

This command registers an OAuth 2.0 client with AD FS by using a client identifier, redirection URI, name and description.

### Example 2: Add a client with multiple redirection URIs
```
PS C:\> Add-AdfsClient -Name "Payroll Application" -ClientId "ab762716-544d-4aeb-a526-687b73838a33" -RedirectUri @("ms-app://s-1-15-2-2205112887-4282980309-3272664163-2407253042-283898840-27493891-3661245662/", "https://Contosopayrollapplication/oauthclient/") -Description "OAuth 2.0 client for our Payroll application"
```

This command registers an OAuth 2.0 client with a client identifier, two redirection URIs, a name and description with AD FS.
The command uses two different redirections URIs to denote multiple forms of the application that may use different redirection URIs,

## PARAMETERS

### -ClientId
Specifies a client identifier.
The cmdlet adds a client identifier for the OAuth 2.0 client to register with AD FS.
You can also use GUIDs to represent client identifiers.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description.
The cmdlet adds a description for the OAuth 2.0 client to register with AD FS.

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
Specifies a name.
The cmdlet adds a name for the OAuth 2.0 client to register with AD FS.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -RedirectUri
Specifies one or more redirection URIs.
The cmdlet adds the redirection URIs for the OAuth 2.0 client to register with AD FS.
The OAuth 2.0 client specifies the redirection URI when it requests authorization to access a resource secured byAD FS.
You can register more than one redirection URI for a single client identifier.
The redirect URI must be a valid URI.

```yaml
Type: Uri[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### string, string, uri[], string

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Disable-AdfsClient](./Disable-AdfsClient.md)

[Enable-AdfsClient](./Enable-AdfsClient.md)

[Get-AdfsClient](./Get-AdfsClient.md)

[Remove-AdfsClient](./Remove-AdfsClient.md)

[Set-AdfsClient](./Set-AdfsClient.md)

