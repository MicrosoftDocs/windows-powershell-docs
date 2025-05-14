---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmMgmtProperty.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/remove-fsrmmgmtproperty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-FsrmMgmtProperty
---

# Remove-FsrmMgmtProperty

## SYNOPSIS
Removes a management property.

## SYNTAX

```
Remove-FsrmMgmtProperty [-Namespace <String>] [-Name] <String> [-Recurse] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-FsrmMgmtProperty** cmdlet removes a management property from a namespace.
A management property is a classification property that includes Folder in its AppliesTo property and whose Flags property does not include the Secure value.
You can use the **Get-FsrmClassificationPropertyDefinition** cmdlet to get definitions of classification properties.

## EXAMPLES

### Example 1: Remove all management properties
```
PS C:\> Remove-FsrmMgmtProperty -Name "FolderUsage_MS"
```

This command removes all management properties from the server that have the value FolderUsage_MS.

### Example 2: Remove a management property by using a namespace
```
PS C:\> Remove-FsrmMgmtProperty -Name "FolderUsage_MS" -Namespace "C:\Shares"
```

This command removes all management properties from the namespace C:\Shares that have the value FolderUsage_MS.

### Example 3: Remove all management property in a namespace hierarchy
```
PS C:\> Remove-FsrmMgmtProperty -Name "FolderUsage_MS" -Namespace "C:\Shares" -Recurse
```

This command removes all management properties that have the value FolderUsage_MS from the namespace C:\Shares and any namespaces below it in the hierarchy.

### Example 4: Remove all management properties in a namespace hierarchy
```
The first command gets all management properties on the server and stores the results in the $props variable.
PS C:\> $props = Get-FsrmMgmtProperty

The second command is a script that identifies management properties where the property applied on folders dos not exist anymore. The script uses the **Remove-FsrmMgmtProperty** cmdlet to remove the management properties for which there is no corresponding property definition on the server.
PS C:\> $nonExistingProperties = $props | where { $_.Exists -ne $true}
foreach ($candidate in $nonExistingProperties)
{foreach ($prop in $_.Properties) {Remove-FsrmMgmtProperty -Name $prop.Name -Namespace $candidate.Namespace}}
```

This example removes all management properties from namespaces that do not exist on the server.
Property definitions are removed from a server by an administrator or as a result of group policy updates.
When you remove a property definition, the management property values that the server sets on folders by using the property definition are obsolete.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a management property.
Specify the value of the Name property in a **FsrmClassificationPropertyDefinition** object.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace
Specifies a local path to a folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Recurse
Indicates that this cmdlet removes management properties for all folders that contain management properties in the namespace.
If you specify this parameter, you must specify the *Namespace* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-FsrmClassificationPropertyDefinition](./Get-FsrmClassificationPropertyDefinition.md)

[Get-FsrmMgmtProperty](./Get-FsrmMgmtProperty.md)

[Set-FsrmMgmtProperty](./Set-FsrmMgmtProperty.md)

