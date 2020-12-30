---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 8DE21BE5-0DFD-485D-B001-AB483A80DB8C
manager: dansimp
---

# Remove-WssFolder

## SYNOPSIS
Removes a server folder.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-WssFolder [-DeleteContents] [-Force] -Name <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-WssFolder [-DeleteContents] [-Force] -Folder <Folder> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-WssFolder [-DeleteContents] [-Force] -ID <Guid> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-WssFolder** cmdlet removes a server folder.
If you specify the **DeleteContents** parameter, the cmdlet deletes the contents of the server folder that you specify.
If you do not specify the **DeleteContents** parameter, the cmdlet stops sharing the contents of the server folder.

## EXAMPLES

### Example 1: Remove a server folder
```
PS C:\> Remove-WssFolder -Name "ProjectsNorth" -DeleteContents
```

This command removes the server folder named ProjectsNorth and deletes all the contents of the folder.

## PARAMETERS

### -DeleteContents
Indicates that the cmdlet deletes the contents of the server folder.

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

### -Folder
Specifies the name of a folder.

```yaml
Type: Folder
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
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

### -ID
Specifies the GUID for a folder.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a folder.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
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

### Microsoft.WindowsServerSolutions.Storage.Folder

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.Folder

## NOTES

## RELATED LINKS

[Add-WssFolder](./Add-WssFolder.md)

[Get-WssFolder](./Get-WssFolder.md)

[Set-WssFolder](./Set-WssFolder.md)

[Move-WssFolder](./Move-WssFolder.md)

[Measure-WssFolder](./Measure-WssFolder.md)

