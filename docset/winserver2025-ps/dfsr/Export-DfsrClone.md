---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/export-dfsrclone?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-DfsrClone
---

# Export-DfsrClone

## SYNOPSIS
Exports the cloned DFS Replication database and volume configuration settings.

## SYNTAX

```
Export-DfsrClone [-Volume] <String> [[-Path] <String>] [[-Validation] <ValidationLevel>] [-AllowClobber]
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-DfrsClone** cmdlet exports the Distributed File System (DFS) Replication database and volume configuration XML file settings for a given volume from the local computer, in order to clone that database on another computer.
DFS Replication databases exist on every volume that contains replicated folder content and a single database contains references for all replicated folders on that volume.
Once you run the cmdlet, it triggers the export in the DFS Replication service and waits for the service to complete the operation.
Use Get-DfsrCloneState to monitor the export process.

DFSR does not support cloning SYSVOL or read-only replicas in Windows Server 2012 R2.
These replicated folders are automatically skipped by the export process.
You can only export or import one database at a time for a computer.

Follow the recommended and supported steps to perform DFS Replication database cloning, as described in [Export a Clone of the DFS Replication Database](https://go.microsoft.com/fwlink/?LinkId=302005) in the TechNet Library.
The term upstream refers to the server that is the authoritative source of both replicated file data and the DFS Replication database.
The term downstream refers to the non-authoritative server that is a clone of the authoritative server.

## EXAMPLES

### Example 1: Export a database to a folder
```
PS C:\> Export-DfsrClone -Volume "C:" -Path "C:\DfsRClone" | Format-List
This operation will export the database and create a clone. It can take a long time to complete and any replication
will stop on the volume. Use Get-DfsrCloneState or DFSR event 2402 to determine when the export has succeeded. Volume:
C:\ Path: "C:\Dfsrclone"
Are you sure you want to continue to export the database clone?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):y

CloneFolderPath : C:\Dfsrclone
CopyHint : Robocopy.exe "c:\dfsrclone" "<DestinationPath>" /B

RootFolderPath : c:\Rf01
PreseedingHint : Robocopy.exe "c:\Rf01" "<DestinationPath>" /E /B /COPYALL /R:6 /W:5 /MT:64 /XD DfsrPrivate /TEE /LOG+:preseed.log

RootFolderPath : c:\RF02
PreseedingHint Robocopy.exe "c:\RF02" "<DestinationPath>" /E /B /COPYALL /R:6 /W:5 /MT:64 /XD DfsrPrivate /TEE /LOG+:preseed.log
```

This command exports the DFS Replication database clone for the C: volume into the C:\DfsRClone destination folder and displays the associated replicated folders.
The suggested Robocopy syntax appears in the output.

### Example 2: Export a database and monitor progress
```
PS C:\> Export-DfsrClone -Volume "C:" -Path "C:\DfsRClone" -Force
PS C:\> Get-DfsrCloneState
PS C:\> Get-DfsrCloneState
```

This example demonstrates exporting the DFS Replication database clone and then uses Get-DfsrCloneState to periodically retrieve state until the replication completes.

The first command uses the **Export-DfsrClone** cmdlet to start the export process.
You must open another Windows PowerShell console or hit CTRL+C to exit the **Export-DfsrClone** cmdlet.
The cloning continues on the server even if the cmdlet stops running.

The second command uses the **Get-DfsrCloneState** cmdlet to check the state of the export process.
The output appears after the command.

The third command uses the **Get-DfsrCloneState** cmdlet to check the state of the export process.
The output indicates that the export completed successfully.

### Example 3: Export and import a database
```
PS C:\> New-DfsReplicationGroup "RG05" | New-DfsReplicatedFolder -FolderName "RF 5" | Add-DfsrMember -ComputerName "SRV01"
PS C:\> Set-DfsrMembership -ComputerName "SRV01" -ContentPath C:\Rf05 -PrimaryMember $True -FolderName "RF05"
PS C:\> Update-DfsrConfigurationFromAD
PS C:\> New-Item -Path "C:\DfsRClone" -Type Directory
PS C:\> Export-DfsrClone -Volume C: -Path "C:\DfsRClone"
PS C:\> Robocopy.exe C:\Rf05 \\srv02\c$\Rf05 /E /B /COPYALL /R:6 /W:5 /MT:64 /XD DfsrPrivate /TEE /LOG+:preseed.log
PS C:\> Robocopy.exe C:\DfsRClone \\srv02\c$\DfsRClone /B
PS C:\> RD "C:\system volume information\dfsr" -Force -Recurse
PS C:\> Import-DfsrClone -Volume C: -Path "C:\DfsRClone"
PS C:\> Get-DfsrCloneState
PS C:\> Add-DfsrMember -GroupName "RG05" -ComputerName "SRV02" | Set-DfsrMembership -FolderName "RF05" -ContentPath "C:\Rf05"
PS C:\> Add-DfsrConnection -GroupName "RG05" -SourceComputerName "SRV01" -DestinationComputerName "SRV02"
PS C:\> Update-DfsrConfigurationFromAD
```

This example demonstrates the end-to-end process of cloning SRV01 and its RF05 replicated folder on C:\ to server SRV02.
The first seven commands run on the upstream server, and the remaining commands run on the downstream server.

The first command, on the upstream server, uses the **New-DfsReplicationGroup** cmdlet to create a replication group named RG05.
The output of that command is piped to the **New-DfsReplicatedFolder** cmdlet to create a folder named RF05, and the output of that command is piped to the **Add-DfsrMember** cmdlet to add the computer named SRV01 as a member.

The second command, on the upstream server, uses the **Set-DfsrMembership** cmdlet to modify the membership for the computer named SRV01.

The third command, on the upstream server, uses the **Update-DfsrConfigurationFromAD** cmdlet to update the DFS Replication configuration on the source server.

The fourth command, on the upstream server, uses the **New-Item** cmdlet to create a new directory in the path C:\DfsRClone.

The fifth command, on the upstream server, uses the **Export-DfsrClone** cmdlet to export a volume.

The sixth command, on the upstream server, uses Robocopy to copy the replicated folder directory structure to the destination server.

The seventh command, on the upstream server, uses Robocopy to copy the C:\DfsRClone directory to the destination server.

The eighth command, on the downstream server, uses RD to remove the replication directory, if it exists.

The ninth command, on the downstream server, uses the **Import-DfsrClone** cmdlet to import the database and volume configuration on the destination server.

The tenth command, on the downstream server, uses the **Get-DfsrCloneState** cmdlet to verify the completion of the import process.

The eleventh command, on the downstream server, uses the **Add-DfsrMember** cmdlet to add a new group on the destination server.
The command pipes the output of this cmdlet to the **Set-DfsrMembership** cmdlet to add membership for the replicated folder group.

The twelfth command, on the downstream server, uses the **Add-DfsrConnection** cmdlet to add a connection for the destination server.

The final command, on the downstream server, uses the **Update-DfsrConfigurationFromAD** cmdlet to update the DFS Replication configuration on the destination server.

## PARAMETERS

### -AllowClobber
Indicates that the cmdlet overwrites an existing exported database and XML configuration file.
By default, if a file exists in the specified path, the operation halts.
After you export the DFS Replication database, but before you perform the import clone operation, you must populate the downstream server with the contents of the replicated folder.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Overwrite

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

### -Force
Forces the command to run without asking for user confirmation.
Use this parameter for scripted cloning.

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

### -Path
Specifies a folder path to which to write the exported DFS Replication files dfsr.db.clone and config.xml.
The folder path must exist.
The path must be a local volume and not a mapped drive or a UNC path.
If you do not specify this parameter, the cmdlet uses the current working directory.
After you export the DFS Replication files, but before you perform the import clone operation, you must populate the downstream server with the contents of the replicated folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DestinationFolderPath

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Validation
Specifies the verbosity level of checks performed by the DFS Replication service against the replicated content set files and folders for comparison to the populated data on the destination clone during import.
Acceptable values for this parameter are:

- None (0) No validation is performed on the files, all files and folders are assumed to exist, and the administrator must have populated the files and folders without errors, or allowing any changes to the file structures on upstream and downstream servers. This is the fastest but most optimistic mode.
- Basic (1) Simple comparisons are performed for every file and folder using the size, modified time-date stamp, and hash of the ACL. Any added, missing or differing files or folders are replicated inbound and any inconsistent local copies on the downstream are moved to the \<replicated-folder\>\Dfsrprivate\ConflictAndDeleted folder or to the \<replicated-folder\>\DfsrPrivate\PreExisting folder. This mode is a good balance of performance and optimism.
- Full (2) DFS Replication hash computation is performed for every file and folder. Any missing or differing files or folders are replicated inbound and any inconsistent local copies on the downstream are moved to the \<replicated-folder\>\Dfsrprivate\ConflictAndDeleted folder or to the \<replicated-folder\>\DfsrPrivate\PreExisting folder. This is the slowest but most accurate mode.

```yaml
Type: ValidationLevel
Parameter Sets: (All)
Aliases:
Accepted values: None, Basic, Full

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume
Specifies a drive letter or mount point path that contains the database to export for that volume's replicated content folders, in order to perform cloning.
If there are multiple replicated folders hosted on that volume, they all use the same DFS Replication database and they all clone.
After you export the DFS Replication database, but before you perform the import clone operation, you must populate the downstream server with the contents of the replicated folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### String

## OUTPUTS

### DfsrFolderToSync

## NOTES

## RELATED LINKS

[Get-DfsrCloneState](./Get-DfsrCloneState.md)

[Import-DfsrClone](./Import-DfsrClone.md)

[Reset-DfsrCloneState](./Reset-DfsrCloneState.md)

