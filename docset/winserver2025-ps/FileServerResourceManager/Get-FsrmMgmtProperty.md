---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmMgmtProperty.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/get-fsrmmgmtproperty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FsrmMgmtProperty
---

# Get-FsrmMgmtProperty

## SYNOPSIS
Gets management properties.

## SYNTAX

```
Get-FsrmMgmtProperty [-Namespace <String>] [-Name <String>] [-Recurse] [-Effective]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-FsrmMgmtProperty** cmdlet gets File Server Resource Manager (FSRM) management properties for a namespace.
A management property is a classification property that includes Folder in its AppliesTo property and whose Flags property does not include the Secure value.
You can use the **Get-FsrmClassificationPropertyDefinition** cmdlet to get definitions of classification properties.

## EXAMPLES

### Example 1: Get all management properties
```
PS C:\> Get-FsrmMgmtProperty
```

This command gets all management properties for the server.

### Example 2: Get management properties by using a namespace
```
PS C:\> Get-FsrmMgmtProperty -Namespace "C:\Shares"
```

This command gets the Folder Usage property for the folder C:\Shares.

### Example 3: Get management properties by using a name
```
PS C:\> Get-FsrmMgmtProperty -Namespace "C:\Shares" -Name "FolderUsage_MS"
```

This command gets the Folder Usage property for the management property named FolderUsage_MS in the folder C:\Shares.

### Example 4: Get management properties for all folders in a path
```
PS C:\> Get-FsrmMgmtProperty -Namespace "C:\Shares" -Recurse
```

This command gets management properties for C:\Shares and for all folders within the path.

### Example 5: Get the nearest management properties by using a name
```
PS C:\> Get-FsrmMgmtProperty -Namespace "C:\Shares\CtrShares03" -Name "FolderUsage_MS" -Effective
```

This command gets the FolderUsage property value on C:\Shares\CtrShares03.
If the folder usage management property named FolderUsage_MS is not set on C:\Shares\CtrShares03, the cmdlet searches up through the namespace (C:\shares, C:\\) and finds the first occurrence of the management property.

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

### -Effective
Indicates that the cmdlet gets the management property for the nearest folder that has the name that you specify.
The cmdlet finds the nearest management property based on the namespace that you specify or the parent hierarchy.
If you specify this parameter, you must specify the *Name* parameter.

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

### -Name
Specifies the name of a management property.
Specify the value of the Name property in a **FsrmClassificationPropertyDefinition** object.
If you do not specify this parameter, the cmdlet gets all management properties on the server.

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
Indicates that this cmdlet gets management properties for all folders that contain management properties in the namespace.
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

### Microsoft.Management.Infrastructure.CimInstance[]

## NOTES

## RELATED LINKS

[Get-FsrmClassificationPropertyDefinition](./Get-FsrmClassificationPropertyDefinition.md)

[Remove-FsrmMgmtProperty](./Remove-FsrmMgmtProperty.md)

[Set-FsrmMgmtProperty](./Set-FsrmMgmtProperty.md)

