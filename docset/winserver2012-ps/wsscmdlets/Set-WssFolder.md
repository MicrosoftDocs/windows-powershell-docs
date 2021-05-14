---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssfolder?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WssFolder

## SYNOPSIS
Changes the settings of a server folder.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-WssFolder [-Folder] <Folder> [-Description <String>] [-Force] [-HideFolderFromRemoteAccess <Boolean>]
 [-NewName <String>] [-Permission] [-UserName <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-WssFolder [-Folder] <Folder> [-Description <String>] [-Force] [-HideFolderFromRemoteAccess <Boolean>]
 [-NewName <String>] [-Permission] [-UserSid <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-WssFolder** cmdlet changes the settings of a server folder.

## EXAMPLES

### Example 1: Change the settings of a server folder
```
PS C:\>$Folder = Get-WssFolder -Name "ProjectsWest" PS C:\> Set-WssFolder -Folder $Folder -NewName "ProjectsSouthwest01" -UserName "SarahJones" -Permission Full
```

The first command gets the folder named ProjectsWest and stores it in the **$Folder** variable.

The second command changes the name of the folder stored in the **$Folder** variable to ProjectsSouthwest01, and grants the user named SarahJones full access to ProjectsSouthwest01.

## PARAMETERS

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
Position: 1
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: None, ReadOnly, Full, Other

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.Folder

## NOTES

## RELATED LINKS

[Add-WssFolder](./Add-WssFolder.md)

[Get-WssFolder](./Get-WssFolder.md)

[Move-WssFolder](./Move-WssFolder.md)

[Remove-WssFolder](./Remove-WssFolder.md)

[Measure-WssFolder](./Measure-WssFolder.md)

