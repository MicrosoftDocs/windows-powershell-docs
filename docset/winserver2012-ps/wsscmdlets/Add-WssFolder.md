---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/add-wssfolder?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-WssFolder

## SYNOPSIS
Creates a new server folder.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-WssFolder [-Name] <String> [-Path] <String> [[-Description] <String>]
 [[-HideFolderFromRemoteAccess] <Boolean>] [-KeepPermissions]
```

### UNNAMED_PARAMETER_SET_2
```
Add-WssFolder [-Id] <Guid> [-Path] <String> [[-Description] <String>] [[-HideFolderFromRemoteAccess] <Boolean>]
 [-KeepPermissions]
```

## DESCRIPTION
The **Add-WssFolder** cmdlet creates a server folder.

## EXAMPLES

### Example 1: Create a server folder
```
PS C:\> Add-WssFolder -Name "ProjectsEast" -Path "D:\Contoso\Main"
```

This command creates the folder named ProjectsEast in D:\Contoso\Main.

## PARAMETERS

### -Description
Specifies a description for the server folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the GUID for a built-in server folder.
Specify this parameter to re-create a default shared folder, such as the Music folder or the Pictures folder.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeepPermissions
Indicates that the cmdlet applies the permissions of the parent folder to the new folder.

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

### -Name
Specifies a name for the folder.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path of the folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.Folder

## NOTES

## RELATED LINKS

[Get-WssFolder](./Get-WssFolder.md)

[Set-WssFolder](./Set-WssFolder.md)

[Move-WssFolder](./Move-WssFolder.md)

[Remove-WssFolder](./Remove-WssFolder.md)

[Measure-WssFolder](./Measure-WssFolder.md)

