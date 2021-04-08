---
author: Kateyanne
external help file: NFS_Cmdlets.xml
manager: dansimp
Module Name: NFS
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/nfs/remove-nfsclientgroup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-NfsClientgroup

## SYNOPSIS
Removes a client group from an NFS server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-NfsClientgroup [-ClientGroupName] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-NfsClientgroup [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-NfsClientGroup** cmdlet removes one or more client groups from a Network File System (NFS) server.

## EXAMPLES

### Example 1: Remove a client group by using a name
```
PS C:\> Remove-NfsClientGroup -ClientGroupName "Contoso-cg1"
Confirm
Are you sure you want to perform this action?
Performing operation "Delete Clientgroup" on Target "Contoso-cg1".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
```

This command removes a client group named Contoso-cg1.

### Example 2: Remove a client group by using pipeline input
```
PS C:\> Get-NfsClientGroup -ClientGroupName "clientgroupA" | Remove-NfsClientGroup
Confirm
Are you sure you want to perform this action?
Performing operation "Delete Clientgroup" on Target "clientgroupA".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
```

This command gets the client group that has the name clientgroupA.

The second command uses the pipeline operator to pass the result to **Remove-NfsClientGroup**, which removes clientgroupA.

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientGroupName
Specifies an array of client group names to remove from an NFS server.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### Nothing

## NOTES

## RELATED LINKS

[Get-NfsClientgroup](./Get-NfsClientgroup.md)

[New-NfsClientgroup](./New-NfsClientgroup.md)

[Rename-NfsClientgroup](./Rename-NfsClientgroup.md)

[Set-NfsClientgroup](./Set-NfsClientgroup.md)

