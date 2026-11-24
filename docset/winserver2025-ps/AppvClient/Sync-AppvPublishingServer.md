---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/sync-appvpublishingserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Sync-AppvPublishingServer
---

# Sync-AppvPublishingServer

## SYNOPSIS
Initiates the App-V Publishing Refresh operation.

## SYNTAX

### ByServerId (Default)
```
Sync-AppvPublishingServer [-ServerId] <UInt32> [-Global] [-Force] [-NetworkCostAware]
 [-HidePublishingRefreshUI] [<CommonParameters>]
```

### ByObject
```
Sync-AppvPublishingServer [-Server] <AppvPublishingServer> [-Global] [-Force] [-NetworkCostAware]
 [-HidePublishingRefreshUI] [<CommonParameters>]
```

### ByNameUrl
```
Sync-AppvPublishingServer [[-Name] <String>] [[-URL] <String>] [-Global] [-Force] [-NetworkCostAware]
 [-HidePublishingRefreshUI] [<CommonParameters>]
```

## DESCRIPTION
The **Sync-AppvPublishingServer** cmdlet initiates the Microsoft Application Virtualization (App-V) publishing refresh operation in the context of the current user.
The publishing refresh connects to all added servers on the client and expose new App-V packages and their respective extension points to the user.

## EXAMPLES

### Example 1: Start publishing refresh
```
PS C:\> Sync-AppvPublishingServer -Name "MyServer"
```

This command starts publishing refresh for the current user for the server named MyServer.

## PARAMETERS

### -Force
Indicates that the cmdlet forces all publishes and unpublishes of packages.

The Force switch specifies whether to suppress warning and confirmation messages. It can be useful in scripting to suppress interactive prompts. If the Force switch isn't provided in the command, you're prompted for administrative input if required.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Global
Indicates that the cmdlet synchronizes packages from the App-V publishing server that are provisioned to the computer and are published to all users on the computer.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HidePublishingRefreshUI
Indicates that the cmdlet suppresses the Publishing Refresh Progress bar.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of the server.

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

### -NetworkCostAware
Indicates that this cmdlet is network cost aware.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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
Specifies the identifier for the App-V Publishing Server.
This can be queried using the **Get-AppvPublishingServer** cmdlet.

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
Specifies the URL path of the server.

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

## NOTES

## RELATED LINKS

[Add-AppvPublishingServer](./Add-AppvPublishingServer.md)

[Get-AppvPublishingServer](./Get-AppvPublishingServer.md)

[Remove-AppvPublishingServer](./Remove-AppvPublishingServer.md)

[Set-AppvPublishingServer](./Set-AppvPublishingServer.md)

