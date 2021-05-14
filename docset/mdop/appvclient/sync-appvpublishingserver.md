---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
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
The **Sync-AppvPublishingServer** cmdlet Initiates the Microsoft Application Virtualization (App-V) publishing refresh operation in the context of the current user.
The publishing refresh connects to all added servers on the client and expose new App-V packages and their respective extension points to the user.

## EXAMPLES

### Example 1
```
PS C:\> Sync-AppvPublishingServer -Name "MyServer"
```

## PARAMETERS

### -Force
Indicates that the cmdlet forces all publishes and unpublishes of packages.

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
Not Specified.

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
Specifies the URL path to the server.

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

[Sync-AppvPublishingServer](./Sync-AppvPublishingServer.md)


