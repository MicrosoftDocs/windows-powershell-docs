---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbShare.cdxml-help.xml
Module Name: SmbShare
ms.date: 02/22/2024
online version: https://learn.microsoft.com/powershell/module/smbshare/remove-smbshare?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-SmbShare
---

# Remove-SmbShare

## SYNOPSIS
Deletes the specified SMB shares.

## SYNTAX

### Query

```
Remove-SmbShare [-Name] <String[]> [[-ScopeName] <String[]>] [-SmbInstance <SmbInstance>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject

```
Remove-SmbShare -InputObject <CimInstance[]> [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-SmbShare` cmdlet deletes one or more Server Message Block (SMB) shares.

Removing an SMB share forcibly disconnects all of the existing connections to the share. Use this
cmdlet with caution. Clients that are forcibly disconnected from a share aren't able to flush
locally cached data before they are disconnected. This may cause data loss. Use the `Get-SmbSession`
cmdlet to determine whether users are connected to a share.

## EXAMPLES

### Example 1: Delete an SMB share

```powershell
Remove-SmbShare -Name "Data"


Confirm
Are you sure you want to perform this action?
Performing operation `Remove-Share` on Target 'Contoso-FS,Data'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

This command deletes the SMB share named `Data`.

### Example 2: Delete a Windows Server failover cluster file server resource SMB share without confirmation

```powershell
Remove-SmbShare -Name "VMFiles" -ScopeName "Contoso-SO" -Force
```

This command deletes the SMB share named `VMFiles` on the `Contoso-SO` file server resource without
user confirmation.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

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

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession)
or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
current session on the local computer.

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

### -InputObject

Specifies the input object that's used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Specifies an array of names of SMB shares.

```yaml
Type: String[]
Parameter Sets: Query
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Returns an object representing the item with which you're working. By default, this cmdlet doesn't
generate any output.

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

### -ScopeName

Specifies an array of the scopes of the SMB share to delete. For use with Windows Server failover
cluster file server resources.

```yaml
Type: String[]
Parameter Sets: Query
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SmbInstance

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this
cmdlet.

```yaml
Type: SmbInstance
Parameter Sets: Query
Aliases:
Accepted values: Default, CSV, SBL, SR

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

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
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/SMB/MSFT_SmbShare

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/SMB/MSFT_SmbShare

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-SmbShare](Get-SmbShare.md)

[New-SmbShare](New-SmbShare.md)

[Set-SmbShare](Set-SmbShare.md)
