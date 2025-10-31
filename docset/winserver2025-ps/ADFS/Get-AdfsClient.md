---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsClient
---

# Get-AdfsClient

## SYNOPSIS
Retrieves registration information for an OAuth 2.0 client.

## SYNTAX

### Name (Default)
```
Get-AdfsClient [[-Name] <String[]>] [<CommonParameters>]
```

### ClientId
```
Get-AdfsClient [-ClientId] <String[]> [<CommonParameters>]
```

### InputObject
```
Get-AdfsClient [-InputObject] <AdfsClient> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsClient** cmdlet retrieves registration information for an OAuth 2.0 client that was previously registered with Active Directory Federation Services (AD FS).

## EXAMPLES

### Example 1: Retrieve registration information for all clients
```
PS C:\> Get-AdfsClient



RedirectUri : {ms-app://windows.immersivecontrolpanel/}
Name        : Device Registration Client
Description : Client for the Device Registration Service
ClientId    : dd762716-544d-4aeb-a526-687b73838a22
BuiltIn     : True
Enabled     : True
ClientType  : Public

RedirectUri : {https://168f3ee4-63fc-4723-a61a-6473f6cb515c/redir}
Name        : Windows Server Work Folders Client
Description : Client for syncing user files to a Work Folders sync share
ClientId    : 168f3ee4-63fc-4723-a61a-6473f6cb515c
BuiltIn     : True
Enabled     : True
ClientType  : Public
```

This command retrieves registration information for all OAuth 2.0 clients currently registered withAD FS.

### Example 2: Retrieve registration information by client name
```
PS C:\> Get-AdfsClient -Name "Device Registration Client"



RedirectUri : {ms-app://windows.immersivecontrolpanel/}
Name        : Device Registration Client
Description : Client for the Device Registration Service
ClientId    : dd762716-544d-4aeb-a526-687b73838a22
BuiltIn     : True
Enabled     : True
ClientType  : Public
```

This command retrieves registration information for the OAuth 2.0 client named Device Registration Client.

### Example 3: Retrieve registration information by client ID
```
PS C:\> Get-AdfsClient -ClientId "dd762716-544d-4aeb-a526-687b73838a22"



RedirectUri : {ms-app://windows.immersivecontrolpanel/}
Name        : Device Registration Client
Description : Client for the Device Registration Service
ClientId    : dd762716-544d-4aeb-a526-687b73838a22
BuiltIn     : True
Enabled     : True
ClientType  : Public
```

This command retrieves registration information for the OAuth 2.0 client specified by the client identifier dd762716-544d-4aeb-a526-687b73838a22.

## PARAMETERS

### -ClientId
Specifies an array of client identifiers for the OAuth 2.0 client for which to retrieve registration information.

```yaml
Type: String[]
Parameter Sets: ClientId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies an object of type **AdfsClient** that represents an OAuth 2.0 client for which to retrieve registration information.

```yaml
Type: AdfsClient
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the OAuth 2.0 client for which to retrieve registration information.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

String objects are received by the *ClientId* and *Name* parameters.

### Microsoft.IdentityServer.Management.Resources.AdfsClient

AdfsClient objects are received by the *InputObject* parameter.

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.AdfsClient

Returns one or more AdfsClient objects that represent the Adfs Clients for the Federation Service.

## NOTES

## RELATED LINKS

[Add-AdfsClient](./Add-AdfsClient.md)

[Disable-AdfsClient](./Disable-AdfsClient.md)

[Enable-AdfsClient](./Enable-AdfsClient.md)

[Remove-AdfsClient](./Remove-AdfsClient.md)

[Set-AdfsClient](./Set-AdfsClient.md)

