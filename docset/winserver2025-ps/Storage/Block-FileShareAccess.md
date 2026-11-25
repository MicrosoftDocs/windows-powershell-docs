---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FileShare.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/block-fileshareaccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Block-FileShareAccess
---

# Block-FileShareAccess

## SYNOPSIS
Blocks access to a file share.

## SYNTAX

### ByName (Default)
```
Block-FileShareAccess -Name <String[]> [-FileServer <CimInstance>] -AccountName <String[]>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByUniqueId
```
Block-FileShareAccess -UniqueId <String[]> -AccountName <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Block-FileShareAccess -InputObject <CimInstance[]> -AccountName <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Block-FileShareAccess** cmdlet blocks access to the specified file share for the specified accounts by adding an access-denied access control entry (ACE) to the share's security descriptor.

## EXAMPLES

### Example 1: Block file share access
```
PS C:\>Block-FileShareAccess -Name "VMFiles" -AccountName "Contoso\Guest"
Confirm
Are you sure you want to perform this action?
Performing operation 'Modify' on Target 'Contoso-SO,VMFiles'.
 [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y

Name                    ScopeName               AccountName             AccessControlType       AccessRight
----                    ---------               -----------             -----------------       -----------
VMFiles                 Contoso-SO              Contoso\Guest           Deny                    Full
VMFiles                 Contoso-SO              Contoso\Administrator   Allow                   Full
VMFiles                 Contoso-SO              Contoso\Contoso-HV1$    Allow                   Full
VMFiles                 Contoso-SO              Contoso\Contoso-HV2$    Allow                   Full
VMFiles                 Contoso-SO              Contoso\Domain Admins   Allow                   Change
```

This command blocks the Guest account from accessing VMFiles.

## PARAMETERS

### -AccountName
Specifies an array of account names to block.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -FileServer
Specifies a file server on which to set permissions.

```yaml
Type: CimInstance
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the file share for which the user is being granted access.
Because the share name is not a worldwide unique name, use a different parameter set to avoid confusion.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
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

### -UniqueId
Specifies an array of unique IDs.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Grant-FileShareAccess](./Grant-FileShareAccess.md)

[Revoke-FileShareAccess](./Revoke-FileShareAccess.md)

[Unblock-FileShareAccess](./Unblock-FileShareAccess.md)

