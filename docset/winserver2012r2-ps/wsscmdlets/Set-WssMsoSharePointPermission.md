---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssmsosharepointpermission?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssMsoSharePointPermission
---

# Set-WssMsoSharePointPermission

## SYNOPSIS
Sets permission settings for a sp_online_2 securable object.

## SYNTAX

### ByLibrary
```
Set-WssMsoSharePointPermission [-Library] <SharePointLibrary> [-User] <SharePointUser>
 [-Permission] <WssMsoSharePointPermissionType> [<CommonParameters>]
```

### BySite
```
Set-WssMsoSharePointPermission [-Site] <SharePointSite> [-User] <SharePointUser>
 [-Permission] <WssMsoSharePointPermissionType> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssMsoSharePointPermission** cmdlet sets permission settings for a sp_online_1 securable object, such as a library or a site.
An office_365_1 site stores the  sp_online_2library.

## EXAMPLES

### Example 1: Set SharePoint permissions
```
PS C:\> $Library= Get-WssMSOSharePointLibrary | Select-Object -First 1
PS C:\> $Principal= Get-WssMSOSharePointPrincipal | Select-Object -First 1
PS C:\> Set-WssMSOSharePointObjectPermission -Object $Library -Principal $Principal -Permission FullControl
```

The first command uses the Get-WssMsoSharePointLibrary cmdlet to get a library, and stores the result in the $Library variable.

The second command uses the Get-WssMsoSharePointPrincipal cmdlet to get a SharePoint principal, and stores the result in the $Principal variable.

The last command sets the SharePoint permissions for the library named $Library and the principal named $Principal.

## PARAMETERS

### -Library
Specifies a sp_2013_1 library.
The cmdlet sets permissions for the library that you specify.

```yaml
Type: SharePointLibrary
Parameter Sets: ByLibrary
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Permission
Specifies the permission for a sp_2013_2 principal to modify. 
The acceptable values for this parameter are:


     -- NoAccess

     -- Read

     -- Edit

     -- FullControl

```yaml
Type: WssMsoSharePointPermissionType
Parameter Sets: (All)
Aliases: 
Accepted values: NoAccess, Read, Edit, FullControl

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Site
Specifies a sp_2013_2 site.
The cmdlet sets permissions for the site that you specify.

```yaml
Type: SharePointSite
Parameter Sets: BySite
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -User
Specifies a name for a user account.
The cmdlet sets permissions for the sp_2013_2 name that you specify.

```yaml
Type: SharePointUser
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsServerSolutions.O365Integration.SharePointLibrary,Microsoft.WindowsServerSolutions.O365Integration.SharePointSite
Library -- Type: Microsoft.WindowsServerSolutions.O365Integration.SharePointLibrary -- Description: SharePoint library

Site -- Type: Microsoft.WindowsServerSolutions.O365Integration.SharePointSite -- Description: SharePoint site

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMsoSharePointPermission](./Get-WssMsoSharePointPermission.md)

[Remove-WssMsoSharePointPermission](./Remove-WssMsoSharePointPermission.md)

