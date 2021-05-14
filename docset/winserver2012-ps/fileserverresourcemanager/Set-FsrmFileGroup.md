---
external help file: FSRM_Cmdlets.xml
Module Name: FileServerResourceManager
online version: https://docs.microsoft.com/powershell/module/fileserverresourcemanager/set-fsrmfilegroup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-FsrmFileGroup

## SYNOPSIS
Changes configuration settings for file groups.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-FsrmFileGroup [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-Description <String>]
 [-ExcludePattern <String[]>] [-IncludePattern <String[]>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-FsrmFileGroup [-AsJob] [-CimSession <CimSession[]>] [-Description <String>] [-ExcludePattern <String[]>]
 [-IncludePattern <String[]>] [-PassThru] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Set-FsrmFileGroup** cmdlet changes configuration settings for one or more file groups on the server.
The file group consists of two collections of wildcard patterns for file names.
One collection indicates file names that the server includes for file screens, and the other collection indicates file names that the server does not include for file screens.

## EXAMPLES

### Example 1: Change the include pattern of a file group
```
PS C:\>Set-FsrmFileGroup -Name "Media Files" -IncludePattern @("*.mp3", "*.wmv")
```

This command changes the file group named "Media Files".
After the cmdlet runs, the file group includes only files whose name ends in mp3 or wmv.

### Example 2: Change the include pattern of a file group by using an object variable
```
The first command gets the file group named "Media Files" and stored the results in the variable **$Group**.
PS C:\>$Group = Get-FsrmFileGroup "Media Files"

The second command specifies an include pattern that includes .wma files for the file group stored in the variable **$Group**. The command stores the result in the **$list** variable.
PS C:\>$list = $Group.IncludePattern + "*.wma"

The third command sets the include pattern for the file group named "Media Files" to the include pattern stored in the variable **$list**.
PS C:\>Set-FsrmFileGroup -Name "Media Files" -IncludePattern $list
```

This example changes the file group named "Media Files".
After the cmdlet runs, the file group also includes .wma files.

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

### -Description
Specifies a description for the file group.

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

### -ExcludePattern
Specifies an array of pattern strings that can include * and ?
as wildcard characters.
The maximum size of a string is 1 KB.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludePattern
Specifies an array of pattern strings that can include * and ?
as wildcard characters.
The maximum size of a string is 1 KB.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of file groups.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMFileGroup

## NOTES

## RELATED LINKS

[Get-FsrmFileGroup](./Get-FsrmFileGroup.md)

[New-FsrmFileGroup](./New-FsrmFileGroup.md)

[Remove-FsrmFileGroup](./Remove-FsrmFileGroup.md)

