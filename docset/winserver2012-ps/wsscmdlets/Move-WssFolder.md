---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/move-wssfolder?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Move-WssFolder

## SYNOPSIS
Moves a server folder to a different drive.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Move-WssFolder [-Folder] <Folder> [-NewDrive] <String> [-Force] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Move-WssFolder [-Folder] <Folder> [-Cancel] [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Move-WssFolder** cmdlet moves a server folder to a different drive.

## EXAMPLES

### Example 1: Move a folder to a different drive
```
PS C:\>$Folder = Get-WssFolder -Name "ProjectsWest" PS C:\> Move-WssFolder -Folder $Folder -NewDrive "E:\"
```

The first command gets the folder named ProjectsWest and stores it in the **$Folder** variable.

The second command moves the folder stored it in the **$Folder** variable from the current drive to the root directory on the drive E.

## PARAMETERS

### -Cancel
Indicates that the cmdlet attempts to cancel a move that is in progress.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewDrive
Specifies the destination path for the folder on the new drive.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
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

### Folder

## NOTES

## RELATED LINKS

[Add-WssFolder](./Add-WssFolder.md)

[Get-WssFolder](./Get-WssFolder.md)

[Set-WssFolder](./Set-WssFolder.md)

[Remove-WssFolder](./Remove-WssFolder.md)

[Measure-WssFolder](./Measure-WssFolder.md)

