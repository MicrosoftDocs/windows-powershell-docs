---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdpersonalsessiondesktopassignment?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDPersonalSessionDesktopAssignment
---

# Get-RDPersonalSessionDesktopAssignment

## SYNOPSIS
Gets personal session desktop assignments.

## SYNTAX

### GetByCollection (Default)
```
Get-RDPersonalSessionDesktopAssignment [-CollectionName] <String> [-ConnectionBroker <String>]
 [<CommonParameters>]
```

### GetByDesktop
```
Get-RDPersonalSessionDesktopAssignment [-CollectionName] <String> -Name <String> [-ConnectionBroker <String>]
 [<CommonParameters>]
```

### GetByUser
```
Get-RDPersonalSessionDesktopAssignment [-CollectionName] <String> -User <String> [-ConnectionBroker <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDPersonalSessionDesktopAssignment** cmdlet gets Remote Desktop personal session desktop assignments.

## EXAMPLES

### Example 1: Get assignments for a collection
```
PS C:\>Get-RDPersonalSessionDesktopAssignment -CollectionName "RDSessionHostPersonalDesktopCollection"
```

This command gets the personal session desktop assignments from the collection named RDSessionHostPersonalDesktopCollection.

### Example 2: Get assignments for a user
```
PS C:\>Get-RDPersonalSessionDesktopAssignment -CollectionName "Wrdsh_pd" -User "contoso\user"
```

This command gets the personal session desktop assignments for the specified user.

### Example 3: Get assignments for a server
```
PS C:\>Get-RDPersonalSessionDesktopAssignment -CollectionName "Rdsh_pd" -Name "RdshServer.contoso.com"
```

This command gets the personal session desktop assignments from the server named RdshServer.contoso.com.

## PARAMETERS

### -CollectionName
Specifies the name of a personal virtual desktop collection.

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

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

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

### -Name
Specifies the name of the personal session desktop assignment to get.

```yaml
Type: String
Parameter Sets: GetByDesktop
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies a user account in DOMAIN\user format.

```yaml
Type: String
Parameter Sets: GetByUser
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.RemoteDesktopServices.Management.RDPersonalSessionDesktopAssignment[]

## NOTES

## RELATED LINKS

[Export-RDPersonalSessionDesktopAssignment](./Export-RDPersonalSessionDesktopAssignment.md)

[Import-RDPersonalSessionDesktopAssignment](./Import-RDPersonalSessionDesktopAssignment.md)

[Remove-RDPersonalSessionDesktopAssignment](./Remove-RDPersonalSessionDesktopAssignment.md)

[Set-RDPersonalSessionDesktopAssignment](./Set-RDPersonalSessionDesktopAssignment.md)

