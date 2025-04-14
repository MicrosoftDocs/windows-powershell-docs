---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/get-dfsrpreservedfiles?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsrPreservedFiles
---

# Get-DfsrPreservedFiles

## SYNOPSIS
Gets a list of files and folders that DFS Replication previously preserved.

## SYNTAX

```
Get-DfsrPreservedFiles [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsrPreservedFiles** cmdlet gets a list of preserved files and folders.
The Distributed File System (DFS) Replication service preserves the following kinds of files and folders:

- Conflicted.
If users make changes to the same file on multiple servers before replication converges, a file might conflict with the current version.
DFS Replication preserves previous conflicting versions of the file.
- Deleted.
When a member computer deletes a replicated file, other members also remove that file.
Depending on membership settings, computers can preserve deleted files.
To modify whether a member computer preserves deleted files, use the **Set-DfsrMembership** cmdlet.
- Preexisting.
If DFS Replication overwrites files during its initial synchronization, DFS Replication preserves those files.

For all three types, DFS Replication moves the files and folders to \<replicated folder\>\DfsrPrivate\ConflictsAndDeleted or \<replicated folder\>\DfsrPrivate\Preexisting.
DFS Replication records these files in a manifest, either ConflictAndDeletedManifest.xml or PreexistingManifest.xml, as appropriate.
Specify the ConflictAndDeletedManifest.xml manifest to view conflicted and deleted files and folders.
Specify the PreexistingManifest.xml manifest to view preexisting files and folders.
You can use the **Restore-DfsrPreservedFiles** cmdlet to restore files and folders.

## EXAMPLES

### Example 1: Get conflicted and deleted files and folders for a replicated folder
```
PS C:\> Get-DfsrPreservedFiles -Path "C:\RF01\DfsrPrivate\ConflictAndDeletedManifest.xml"
Path            : \\.\C:\ RF01\Sales 2013.pptx
Uid             : {9F159608-2199-4D8B-B9F5-51D83A778089}-v22
Gvsn            : {9F159608-2199-4D8B-B9F5-51D83A778089}-v27
MemberGuid      : e4b69303-5f51-4aec-80b1-89f21323e2b7
Attributes      : System, Directory
PreservedName   : Sales 2013-{9F159608-2199-4D8B-B9F5-51D83A778089}-v27.pptx
PreservedTime   : 4/5/2013 4:03:57 PM
PreservedReason : ConflictAndDelete
FileCount       : 1
FileSize        : 7435676

Path            : \\.\C:\RF01\Sales 2012.pptx
Uid             : {9F159608-2199-4D8B-B9F5-51D83A778089}-v24
Gvsn            : {9F159608-2199-4D8B-B9F5-51D83A778089}-v26
MemberGuid      : e4b69303-5f51-4aec-80b1-89f21323e2b7
Attributes      : System, Directory
PreservedName   : Sales 2012-{9F159608-2199-4D8B-B9F5-51D83A778089}-v26.pptx
PreservedTime   : 4/5/2013 4:03:57 PM
PreservedReason : ConflictAndDelete
FileCount       : 1
FileSize        : 7727683
```

This command gets a list of conflicted and deleted files and folders for the replicated folder C:\RF01.
The command specifies the manifest for that replicated folder.
The console displays the file name and other data.

### Example 2: Get preexisting files for a replicated folder
```
PS C:\> Get-DfsrPreservedFiles -Path "C:\RF01\DfsrPrivate\PreExistingManifest.xml"
Path            : \\.\C:\RF01\Marketing
Uid             : {9F159608-2199-4D8B-B9F5-51D83A778089}-v30
Gvsn            : {9F159608-2199-4D8B-B9F5-51D83A778089}-v30
MemberGuid      : 00000000-0000-0000-0000-000000000000
Attributes      : 10
PreservedName   : Marketing-{9F159608-2199-4D8B-B9F5-51D83A778089}-v30
PreservedTime   : 4/5/2013 4:21:16 PM
PreservedReason : Preexisting
FileCount       : 4
FileSize        : 2548978

Path            : \\.\C:\RF01\Sales
Uid             : {9F159608-2199-4D8B-B9F5-51D83A778089}-v32
Gvsn            : {9F159608-2199-4D8B-B9F5-51D83A778089}-v32
MemberGuid      : 00000000-0000-0000-0000-000000000000
Attributes      : 10
PreservedName   : Sales-{9F159608-2199-4D8B-B9F5-51D83A778089}-v32
PreservedTime   : 4/5/2013 4:21:16 PM
PreservedReason : Preexisting
FileCount       : 4
FileSize        : 4096
```

This command gets a list of preexisting files and folders for the replicated folder C:\RF01.
The console displays the file name and other data.

### Example 3: Look for conflicting or deleted files by using a name
```
PS C:\> Get-DfsrPreservedFiles -Path "C:\RF01\DfsrPrivate\ConflictAndDeletedManifest.xml" | Where-Object Path -like "*canary*"
Path            : \\.\C:\RF01\canary.bmp
Uid             : {031C15B7-397D-4F99-A340-B1C7931EEE01}-v3451
Gvsn            : {9F159608-2199-4D8B-B9F5-51D83A778089}-v54
MemberGuid      : 11d2449a-d25f-4272-bac8-fe10f2299cdd
Attributes      : System, Directory
PreservedName   : canary-{9F159608-2199-4D8B-B9F5-51D83A778089}-v54.bmp
PreservedTime   : 4/5/2013 5:00:00 PM
PreservedReason : ConflictAndDelete
FileCount       : 1
FileSize        : 848294
```

This command looks for conflicting or deleted files that have a name that contains the string canary.
The command gets the preserved files recorded in the specified manifest.
The command then passes those files to the **Where-Object** cmdlet by using the pipeline operator.
That cmdlet passes files that match the criteria back to the console.
For more information, type `Get-Help Where-Object`.

In this example, the command finds a file, named canary.bmp.
You could use the Restore-DfsrPreservedFiles to restore this file.

## PARAMETERS

### -Path
Specifies the path of a manifest.
By default, the manifest files exist in the \<Replicated Folder\>\DfsrPrivate folder.
Specify ConflictAndDeletedManifest.xml to view conflicted and deleted files.
Specify PreexistingManifest.xml to view preexisting files.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrPreservedEntry

## NOTES

## RELATED LINKS

[Restore-DfsrPreservedFiles](./Restore-DfsrPreservedFiles.md)

