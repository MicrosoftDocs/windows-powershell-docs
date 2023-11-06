---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
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

### Example 1
```
PS C:\> Get-AppvPublishingServer -Name "Server*"
```

### Example 2
```
PS C:\> Get-AppvPublishingServer -ServerId 1
```

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
Specifies the URL path to the App-V Publishing server

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

[Add-AppvPublishingServer](./add-appvpublishingserver.md)

[Remove-AppvPublishingServer](./remove-appvpublishingserver.md)

[Set-AppvPublishingServer](./set-appvpublishingserver.md)

[Sync-AppvPublishingServer](./sync-appvpublishingserver.md)
