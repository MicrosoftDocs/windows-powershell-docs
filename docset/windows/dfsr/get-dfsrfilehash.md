---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-DfsrFileHash
ms.reviewer:
ms.assetid: 6F7A9B63-557E-456B-95EE-30F1E03716F9
---

# Get-DfsrFileHash

## SYNOPSIS
Gets a file hash.

## SYNTAX

```
Get-DfsrFileHash [-Path] <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsrFileHash** cmdlet gets a hash value identical to the one computed by the Distributed File System (DFS) Replication service for the specified file or folder during normal replication.
Use this cmdlet to determine if you correctly populated a content set, or if a file is in sync between replication partners.

## EXAMPLES

### Example 1: Get a file hash
```
PS C:\> Get-DfsrFileHash -Path "C:\Rf01\Drawing2.vsd"

Path                                                        FileHash
----                                                        --------
C:\Rf01\Drawing2.vsd                                        6EA20E2D-EAA03FE3-22004718-F1D0FCE2
```

This command uses the **Get-DfsrFileHash** cmdlet to retrieve the simulated marshaled hash of the file C:\Rf01\Drawing2.vsd.

### Example 2: Retrieve the hash of a folder and its contents
```
PS C:\> Get-DfsrFileHash -Path "C:\Rf01\*"

Path                                                        FileHash
----                                                        --------
C:\Rf01\archive                                             13B7D499-1D5B4DBF-8800A20D-52CA5845
C:\Rf01\Drawing2.png                                        EA22F7CF-AD58721C-29CB086B-CDE228BC
C:\Rf01\Drawing2.vsd                                        6EA20E2D-EAA03FE3-22004718-F1D0FCE2
```

This command uses the **Get-DfsrFileHash** cmdlet to retrieve the hash of a folder and the hashes for the individual files in the folder.

### Example 3: Retrieve the hash of a folder and its contents using recursion
```
PS C:\> Get-DfsrFileHash -Path (Get-ChildItem -Path "C:\Rf01" -Recurse).fullname

Path                                                        FileHash
----                                                        --------
C:\Rf01\archive                                             13B7D499-1D5B4DBF-8800A20D-52CA5845
C:\Rf01\Drawing2.png                                        EA22F7CF-AD58721C-29CB086B-CDE228BC
C:\Rf01\Drawing2.vsd                                        6EA20E2D-EAA03FE3-22004718-F1D0FCE2
C:\Rf01\archive\Drawing1.png                                A32E700D-E541F7B7-241CD9B3-D1EA9D6C
C:\Rf01\archive\Drawing1.vsd                                DA61DD74-52BDCB8E-2A793467-EB4BCED0
```

This command uses the **Get-DfsrFileHash** cmdlet to retrieve the hash of a folder and the hashes for the individual files in the folder.
The command also uses the **Get-ChildItem** cmdlet to recursively find all files and folders in the path.

### Example 4: Retrieve the hash of files with the *.png extension
```
PS C:\> Get-DfsrFileHash -Path (Get-ChildItem -Path "C:\Rf01" -Recurse -Filter *.png ).fullname

Path                                                        FileHash
----                                                        --------
C:\Rf01\Drawing2.png                                        EA22F7CF-AD58721C-29CB086B-CDE228BC
C:\Rf01\archive\Drawing1.png                                A32E700D-E541F7B7-241CD9B3-D1EA9D6C
```

This command uses the **Get-DfsrFileHash** cmdlet to retrieve the hash of all files with a *.png extension.
The command searches the folder path recursively.

### Example 5: Retrieve and compare file hashes between two replicated folders
```
PS C:\> net use x: \\Srv01\c$\Rf01
PS C:\> Get-DfsrFileHash x:\* | Out-File C:\Srv01.txt
PS C:\> net use x: /d
PS C:\> net use x: \\Srv02\e$\data
PS C:\> Get-DfsrFileHash x:\* | Out-File C:\Srv02.txt
PS C:\> net use x: /d
PS C:\> Compare-Object -ReferenceObject (Get-Content C:\Srv01.txt) -DifferenceObject (Get-Content C:\Srv02.txt) -IncludeEqual
InputObject                                                 SideIndicator
-----------                                                 -------------
                                                            ==
Path                                                    ... ==
----                                                    ... ==
x:\archive                                              ... ==
x:\Drawing2.vsd                                         ... ==
                                                            ==
                                                            ==
x:\Drawing2.png                                         ... =>
x:\Drawing2.png                                         ... <=
```

This example retrieves and compares simulated file hashes for two replicated folders on different computers.

The first command maps a drive to the replicated folder on the first computer.

The second command uses the **Get-DfsrFileHash** cmdlet to retrieve the simulated file hashes for the contents of the folder.
The command saves the output to a text file.

The third command deletes the mapped drive for the first computer.

The fourth command maps the same drive letter to the replicated folder on the second computer.

The fifth command uses the **Get-DfsrFileHash** cmdlet to retrieve the simulated file hashes for the contents of the folder.
The command saves the output to a text file.

The sixth command deletes the mapped drive for the second computer.

The seventh command uses the **Compare-Object** cmdlet to compare the two output files and display the results.
In this example, the Drawing2.png files differ.

## PARAMETERS

### -Path
Specifies an array of paths to files or folders.
You can use local paths, mapped drives, or UNC paths.

If you specify a file or folder with a wildcard character, this cmdlet calculates any matching files or folders individually.
If you specify a folder path that ends with a wildcard descriptor, such as C:\Rf01\*, the cmdlet calculates hashes for all immediate contents of that folder.
This parameter does not support recursion of subfolders and their contents.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### DfsrFileHash

## NOTES

## RELATED LINKS

