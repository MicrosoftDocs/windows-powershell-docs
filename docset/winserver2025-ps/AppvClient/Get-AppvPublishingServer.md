---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/get-appvpublishingserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AppvPublishingServer
---

# Get-AppvPublishingServer

## SYNOPSIS
Returns App-V Server objects.

## SYNTAX

### ByServerId (Default)
```
Get-AppvPublishingServer [[-ServerId] <UInt32>] [<CommonParameters>]
```

### ByNameUrl
```
Get-AppvPublishingServer [[-Name] <String>] [[-URL] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvPublishingServer** cmdlet returns a Microsoft Application Virtualization (App-V) Server object or set of App-V Server objects based on the criteria provided.

## EXAMPLES

### Example 1: Get servers by friendly name
```
PS C:\> Get-AppvPublishingServer -Name "Server*"
```

This command gets all publishing servers that have friendly names that start with the string Server.

### Example 2: Get servers by server ID name
```
PS C:\> Get-AppvPublishingServer -ServerId 1
```

This command gets the publishing server that has the specified ID.

## PARAMETERS

### -Name
Specifies the name of the App-V publishing server.

```yaml
Type: String
Parameter Sets: ByNameUrl
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerId
Specifies the unique identifier of the App-V Publishing Server.

```yaml
Type: UInt32
Parameter Sets: ByServerId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -URL
Specifies the URL path of the App-V Publishing server.

```yaml
Type: String
Parameter Sets: ByNameUrl
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AppV.AppvClientPowerShell.AppvPublishingServer

## NOTES
* The cmdlet checks that you have permissions to perform the specific action. If not, the cmdlet returns the following error:  The action could not be performed due to current App-V permissions. Please modify the permissions and try the operation again.
* If the get operation fails, the cmdlet returns the following error: The get operation could not be completed. An error code is returned.
* If the cmdlet cannot find the servers, the cmdlet returns the following error: The specified App-V publishing server(s) could not be found. An error code is returned.

## RELATED LINKS

[Add-AppvPublishingServer](./Add-AppvPublishingServer.md)

[Remove-AppvPublishingServer](./Remove-AppvPublishingServer.md)

[Set-AppvPublishingServer](./Set-AppvPublishingServer.md)

[Sync-AppvPublishingServer](./Sync-AppvPublishingServer.md)

