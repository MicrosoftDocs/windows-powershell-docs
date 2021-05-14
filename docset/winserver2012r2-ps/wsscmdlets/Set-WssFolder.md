---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssfolder?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssFolder
---

# Set-WssFolder

## SYNOPSIS
Changes the settings of a server folder.

## SYNTAX

### ByNameParamSet (Default)
```
Set-WssFolder [-Force] [-Folder] <Folder> [-NewName <String>] [-Description <String>] [-UserName <String>]
 [-GroupName <String>] [-Permission <Permission>] [-HideFolderFromRemoteAccess <Boolean>] [-Quota <UInt64>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BySidParamSet
```
Set-WssFolder [-Force] [-Folder] <Folder> [-NewName <String>] [-Description <String>] [-UserSid <String>]
 [-GroupSid <String>] [-Permission <Permission>] [-HideFolderFromRemoteAccess <Boolean>] [-Quota <UInt64>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssFolder** cmdlet changes the settings of a server folder.

## EXAMPLES

### Example 1: Change the settings of a server folder
```
PS C:\>$Folder = Get-WssFolder -Name "ProjectsWest"PS C:\> Set-WssFolder -Folder $Folder -NewName "ProjectsSouthwest01" -UserName "SarahJones" -Permission Full
```

The first command gets the folder named ProjectsWest and stores it in the **$Folder** variable.

The second command changes the name of the folder stored in the **$Folder** variable to ProjectsSouthwest01, and grants the user named SarahJones full access to ProjectsSouthwest01.

## PARAMETERS

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
Specifies a description for the server folder.

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

### -Folder
Specifies the name of a folder.

```yaml
Type: Folder
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupName
Specifies the name of a group.

```yaml
Type: String
Parameter Sets: ByNameParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupSid
Specifies a security ID of a group.

```yaml
Type: String
Parameter Sets: BySidParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HideFolderFromRemoteAccess
Specifies whether to hide the folder in Remote Desktop Web Access or Web service applications.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName
Specifies a new name for the folder.

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

### -Permission
Specifies the access to the shared folder that the server grants to the user that you specify in the **UserName** parameter.
The acceptable values for this parameter are:
- None
- Readonly
- Full

```yaml
Type: Permission
Parameter Sets: (All)
Aliases: 
Accepted values: None, ReadOnly, Full, Other, ReadPermissions

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Quota
Specifies a quota, in bytes, for the folder.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies the user name of an account.
The server grants the user the permission to the shared folder that you specify the **Permission** parameter.

```yaml
Type: String
Parameter Sets: ByNameParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserSid
Specifies the security identifier (SID) of the user that you specify in the **UserName** parameter.

```yaml
Type: String
Parameter Sets: BySidParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsServerSolutions.Storage.Folder

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.Folder
This cmdlet generates an object that represents the modified folder.

## NOTES

## RELATED LINKS

[Add-WssFolder](./Add-WssFolder.md)

[Get-WssFolder](./Get-WssFolder.md)

[Move-WssFolder](./Move-WssFolder.md)

[Remove-WssFolder](./Remove-WssFolder.md)

[Measure-WssFolder](./Measure-WssFolder.md)

