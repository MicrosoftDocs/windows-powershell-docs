---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 3FE2F1F8-0CFC-4D74-B465-E7DA2B20E0E4
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-FsrmMgmtProperty

## SYNOPSIS
Gets management properties.

## SYNTAX

```
Get-FsrmMgmtProperty [-AsJob] [-CimSession <CimSession[]>] [-Effective] [-Name <String>] [-Namespace <String>]
 [-Recurse] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Get-FsrmMgmtProperty** cmdlet gets File Server Resource Manager (FSRM) management properties for a namespace.
A management property is a classification property that includes Folder in its AppliesTo property and whose Flags property does not include the Secure value.
You can use the Get-FsrmClassificationPropertyDefinition cmdlet to get definitions of classification properties.

## EXAMPLES

### Example 1: Get all management properties
```
PS C:\>Get-FsrmMgmtProperty
```

This command gets all management properties for the server.

### Example 2: Get management properties by using a namespace
```
PS C:\>Get-FsrmMgmtProperty -Namespace "C:\Shares"
```

This command gets the Folder Usage property for the folder C:\Shares.

### Example 3: Get management properties by using a name
```
PS C:\>Get-FsrmMgmtProperty -Namespace "C:\Shares" -Name "FolderUsage_MS"
```

This command gets the Folder Usage property for the management property named "FolderUsage_MS" in the folder C:\Shares.

### Example 4: Get management properties for all folders in a path
```
PS C:\>Get-FsrmMgmtProperty -Namespace "C:\Shares" -Recurse
```

This command gets management properties for C:\Shares and for all folders within the path.

### Example 5: Get the nearest management properties by using a name
```
PS C:\>Get-FsrmMgmtProperty -Namespace "C:\Shares\CtrShares03" -Name "FolderUsage_MS" -Effective
```

This command gets the FolderUsage property value on C:\Shares\CtrShares03.
If the folder usage management property named "FolderUsage_MS" is not set on C:\Shares\CtrShares03, the cmdlet searches up through the namespace (C:\shares, C:\\) and finds the first occurrence of the management property.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -Effective
Indicates that the cmdlet gets the management property for the nearest folder that has the name that you specify.
The cmdlet finds the nearest management property based on the namespace that you specify or the parent hierarchy.
If you specify this parameter, you must specify the **Name** parameter.

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
Accept wildcard characters: True
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
If you specify this parameter, you must specify the **Namespace** parameter.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMMgmtProperty

## NOTES

## RELATED LINKS

[Set-FsrmMgmtProperty](./Set-FsrmMgmtProperty.md)

[Remove-FsrmMgmtProperty](./Remove-FsrmMgmtProperty.md)

[Get-FsrmClassificationPropertyDefinition](./Get-FsrmClassificationPropertyDefinition.md)

