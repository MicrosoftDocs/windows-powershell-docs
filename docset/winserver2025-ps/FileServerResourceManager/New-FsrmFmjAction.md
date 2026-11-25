---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmFmjAction.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmfmjaction?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-FsrmFmjAction
---

# New-FsrmFmjAction

## SYNOPSIS
Returns an action object for file management jobs.

## SYNTAX

```
New-FsrmFmjAction [-Type] <FmjActionTypeEnum> [-ExpirationFolder <String>] [-RmsFolderOwner]
 [-RmsFullControlUser <String[]>] [-RmsReadUser <String[]>] [-RmsWriteUser <String[]>] [-RmsTemplate <String>]
 [-Command <String>] [-WorkingDirectory <String>] [-CommandParameters <String>]
 [-SecurityLevel <FmjActionSecurityLevelEnum>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmFmjAction** cmdlet returns an object that you can use to create file management job actions.
You can use the **FsrmFmjAction** object as input for the **New-FsrmFileManagementJob** cmdlet and the **Set-FsrmFileManagementJob** cmdlet.

The **FsrmFmjAction** object defines one action of the file management job when the job acts on a file.
This cmdlet supports the following actions:

- Expiration.
Move the file to another location.
- RMS.
Encrypt the file (Rights Management Services).
- Custom.
Run a command.

## EXAMPLES

### Example 1: Create an action that expires files
```
PS C:\> New-FsrmFmjAction -Type Expiration -ExpirationFolder "C:\shares\expire01"
```

This command returns an object that expires files to the path C:\shares\expire01.

### Example 2: Create an action that encrypts files by using an RMS template
```
PS C:\> New-FsrmFmjAction -Type RMS -RmsTemplate "Contoso Confidential"
```

This command returns an action object that encrypts a file to the Contoso Confidential RMS template.
This command requires that an RMS template is configured on the RMS server named "Contoso Confidential".

### Example 3: Create an action that encrypts files and assigns RMS permissions
```
PS C:\> New-FsrmFmjAction -Type RMS -RmsFullControlUser "admin@contoso.com" -RmsReadUser "AllStaff@contoso.com" -RmsWriteUser "AllFTE@contoso.com"
```

This command returns an action object that encrypts a file so that the administrator account in contoso.com has full control of the file, the ALLFTE security group has edit rights to the file, and the ALLStaff group has read rights to the file.

### Example 4: Create an action that runs a command
```
PS C:\> New-FsrmFmjAction -Type Custom -Command "C:\windows\system32\cmd.exe" -CommandParameters "echo [source file path] >> c:\log.txt"
```

This command returns an action object that runs Cmd.exe and specifies the parameters for the command.

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

### -Command
Specifies the command that the action runs.
If you specify a command, you must specify Custom for the *Type* parameter.

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

### -CommandParameters
Specifies the parameters that the action passes to the command when the action runs.
If you specify parameters for a command, you must specify Custom for the *Type* parameter.

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

### -ExpirationFolder
Specifies a path that the action uses to expire files.
If you specify an expiration folder, you must specify Expiration for the *Type* parameter.

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

### -RmsFolderOwner
Indicates that the action adds the RMS FolderOwner to the Full Control list.
If a FolderOwner is not available for a file, this setting has no effect.

If you specify an RMS folder owner, you must specify RMS for the *Type* parameter.
If you specify this parameter, do not specify the *RMSFullControlUser*, *RMSReadUser*, or *RMSWriteUser* parameters.

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

### -RmsFullControlUser
Specifies an array of email addresses to provide with full control to the Active Directory Rights Management Services (AD RMS) encryption.
If you specify this cmdlet, you must specify RMS for the *Type* parameter.
If you specify this parameter, do not specify the *RMSTemplate* parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RmsReadUser
Specifies an array of addresses to provide with read permission to the Active Directory Rights Management Services (AD RMS) encryption.
If you specify this cmdlet, you must specify RMS for the *Type* parameter.
If you specify this parameter, do not specify the *RMSTemplate* parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RmsTemplate
Specifies the name of the RMS template that the actions applies to files.
If you specify an RMS template, you must specify RMS for the *Type* parameter.
If you specify this parameter, do not specify the *RMSFullControlUser*, *RMSReadUser*, or *RMSWriteUser* parameters.

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

### -RmsWriteUser
Specifies an array of addresses to provide with write permission to the Active Directory Rights Management Services (AD RMS) encryption.
If you specify this cmdlet, you must specify RMS for the *Type* parameter.
If you specify this parameter, do not specify the *RMSTemplate* parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecurityLevel
Specifies the system account that the action uses to run the command that you specify in the *Command* parameter.
If you specify this parameter, you must specify Custom for the *Type* parameter.

```yaml
Type: FmjActionSecurityLevelEnum
Parameter Sets: (All)
Aliases:
Accepted values: None, NetworkService, LocalService, LocalSystem

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

### -Type
Specifies the type of action that the file management job performs.
The acceptable values for this parameter are:

- Expiration
- RMS
- Custom

```yaml
Type: FmjActionTypeEnum
Parameter Sets: (All)
Aliases:
Accepted values: Expiration, Custom, Rms

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -WorkingDirectory
Specifies the working directory in which the program or script runs.
You must specify a valid path to a folder.
File Server Resource Manager (FSRM) does not support paths to remote computers.
If you specify this parameter, you must specify Custom for the *Type* parameter.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.FmjActionTypeEnum

### System.String

### System.Management.Automation.SwitchParameter

### System.String[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.FmjActionSecurityLevelEnum

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[New-FsrmFileManagementJob](./New-FsrmFileManagementJob.md)

[Set-FsrmFileManagementJob](./Set-FsrmFileManagementJob.md)

