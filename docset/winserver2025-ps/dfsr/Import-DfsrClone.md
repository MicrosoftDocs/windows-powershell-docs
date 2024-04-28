---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/import-dfsrclone?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-DfsrClone
---

# Import-DfsrClone

## SYNOPSIS
Imports a cloned DFS Replication database and volume configuration settings.

## SYNTAX

```
Import-DfsrClone [-Volume] <String> [-Path] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-DfsrClone** cmdlet imports a Distributed File System (DFS) Replication database and volume configuration XML file settings for a given volume from another computer, in order to clone that database on the local computer.
DFS Replication databases exist on every volume that contains replicated folder content and a single database contains references for all replicated folders.
When you run this cmdlet, it triggers the import in the DFS Replication service and waits for the service to complete the operation.
Use Get-DfsrCloneState to monitor the import process.

Important: DFS Replication does not support cloning SYSVOL or read-only replicas in Windows Server 2012 R2.
The export process skips replicated folders automatically.
You can only export or import one database at a time for a computer.

Use the recommended and supported steps to perform DFS Replication database cloning.
For more information, see the following Microsoft web site: [http://go.microsoft.com/fwlink/?LinkId=302005](https://go.microsoft.com/fwlink/?LinkId=302005).
The term upstream refers to the server that is the authoritative source of both replicated file data and the DFS Replication database.
The term downstream refers to the non-authoritative server that is a clone of the authoritative server.

## EXAMPLES

### Example 1: Clone and import a DFS Replication database
```
PS C:\> Import-DfsrClone -Volume "C:" -Path C:\DfsRClone
This operation will import the database and clone DFSR. It can take a long time to complete. Use Get-DfsrCloneState or
DFSR event 2404 to determine when the import has succeeded. Volume:
c:\ Path: C:\Dfsrclone
Are you sure you want to continue to import the database clone? [Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):Y
```

This command clones and imports the DFS Replication database and volume configuration XML to the C: volume from the C:\ DfsRClone folder.

### Example 2: Import a DFS Replication database and periodically check status
```
PS C:\> Import-DfsrClone -Volume "C:" -Path C:\DfsRClone
PS C:\> Get-DfsrCloneState
PS C:\> Get-DfsrCloneState
PS C:\> Get-DfsrCloneState
```

This example imports a DFS Replication database clone and then uses the **Get-DfsrCloneState** cmdlet to periodically check the state until the replication operation completes.

The first command uses the **Import-DfsrClone** cmdlet to start the import process.
You must open another Windows PowerShell console or hit CTRL+C to exit the **Import-DfsrClone** cmdlet.
Even if the cmdlet stops running, the cloning continues on the server.

The second command uses the **Get-DfsrCloneState** cmdlet to check the state of the import process.
The output appears after the command.

The third command uses the **Get-DfsrCloneState** cmdlet to check the state of the import process.
The output indicates that the import succeeded.

### Example 3: Export and import a database
```
PS C:\> New-DfsReplicationGroup "RG05" | New-DfsReplicatedFolder -FolderName "RF05" | Add-DfsrMember -ComputerName "SRV01"
PS C:\> Set-DfsrMembership -ComputerName "SRV01" -ContentPath "C:\Rf05" -PrimaryMember $True -FolderName "RF05"
PS C:\> Update-DfsrConfigurationFromAD
PS C:\> New-Item -Path C:\DfsRClone -Type Directory
PS C:\> Export-DfsrClone -Volume "C:" -Path "C:\DfsRClone"
PS C:\> Robocopy.exe C:\Rf05 \\srv02\c$\Rf5 /E /B /COPYALL /R:6 /W:5 /MT:64 /XD DfsrPrivate /TEE /LOG+:preseed.log
PS C:\> Robocopy.exe C:\DfsRClone \\srv02\c$\DfsRClone /B
PS C:\> RD "C:\system volume information\dfsr" -Force -Recurse
PS C:\> Import-DfsrClone -Volume "C:" -Path C:\DfsRClone
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
Specifies a location from which to read the exported DFS Replication database and volume configuration XML file.
After you export the DFS Replication database, but before you perform the import clone operation, you must populate the downstream server with the contents of the replicated folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SourceFolderPath

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume
Specifies a drive letter or mount point that contains the populated DFS Replication file contents.
This volume contains the previously exported database once the import is complete.
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

### string

## OUTPUTS

### [none]

## NOTES

## RELATED LINKS

[Export-DfsrClone](./Export-DfsrClone.md)

