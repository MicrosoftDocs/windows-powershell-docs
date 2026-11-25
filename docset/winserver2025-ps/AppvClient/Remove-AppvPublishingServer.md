---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/remove-appvpublishingserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AppvPublishingServer
---

# Remove-AppvPublishingServer

## SYNOPSIS
Removes an App-V publishing server.

## SYNTAX

### ByServerId (Default)
```
Remove-AppvPublishingServer [-ServerId] <UInt32> [<CommonParameters>]
```

### ByObject
```
Remove-AppvPublishingServer [-Server] <AppvPublishingServer> [<CommonParameters>]
```

### ByNameUrl
```
Remove-AppvPublishingServer [[-Name] <String>] [[-URL] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AppvPublishingServer** cmdlet removes the Microsoft Application Virtualization (App-V) publishing server from the App-V client list.

## EXAMPLES

### Example 1: Remove a publishing server
```
PS C:\> Remove-AppvPublishingServer -Name "Server01"
```

This command removes the publishing server named Server01.

### Example 2: Remove multiple publishing servers
```
PS C:\> Remove-AppvPublishingServer -Name "Server*"
```

This command removes all publishing servers that have names that start with the string Server.

## PARAMETERS

### -Name
Specifies the name of the composition.

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

### -Server
Specifies an **AppvPublishingServer** object.
To obtain an **AppvPublishingServer** object, use the **Get-AppvPublishingServer** cmdlet.

```yaml
Type: AppvPublishingServer
Parameter Sets: ByObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServerId
Specifies the ID for the publishing server.

```yaml
Type: UInt32
Parameter Sets: ByServerId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -URL
Specifies the URL path of the publishing server.

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

### Microsoft.AppvAgent.AppvMgmtServer

## OUTPUTS

## NOTES
* If an operation is being done between the server and targeted App-V agent, the cmdlet deletes the App-V server object, but any operation that had already been initiated finishes. Subsequent actions that may have been queued up fail.
* The cmdlet checks that you have permissions to perform the specific action. If not, the cmdlet returns the following error: The action could not be performed due to current App-V permissions. Please modify the permissions and try the operation again.

## RELATED LINKS

[Add-AppvPublishingServer](./Add-AppvPublishingServer.md)

[Get-AppvPublishingServer](./Get-AppvPublishingServer.md)

[Set-AppvPublishingServer](./Set-AppvPublishingServer.md)

[Sync-AppvPublishingServer](./Sync-AppvPublishingServer.md)

