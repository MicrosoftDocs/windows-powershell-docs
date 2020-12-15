---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-VHD

## SYNOPSIS
Gets the virtual hard disk object associated with a virtual hard disk.

## SYNTAX

### Path (default)
```
Get-VHD [-Path] <String[]> [-ComputerName <String[]>]
```

### Disk
```
Get-VHD [-DiskNumber] <UInt32> [-ComputerName <String[]>]
```

### VMId
```
Get-VHD [-VMId] <Guid[]> [-ComputerName <String[]>]
```

## DESCRIPTION
The **Get-VHD** cmdlet gets the virtual hard disk object associated with a virtual hard disk.

> [!Note]
> When the VHD is in use (for example by a VM or mounted in the OS) and it is on shared storage, the **Get-VHD** cmdlet can only access it from the host that is using it. Any other server trying to run the **Get-VHD** cmdlet will get an error that it is in use. 

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-VHD -Path C:\test\testvhdx.vhdx
```

Gets the virtual hard disk where the path to the virtual hard disk file is `C:\test\testvhdx.vhdx`.

### Example 2
```powershell
PS C:\> Get-VHD -DiskNumber 6
```

Gets the virtual hard disk attached to the system with disk number 6.

### Example 3
```powershell
PS C:\> Get-VM -VMName TestVM | Select-Object -Property VMId | Get-VHD
```

Gets the virtual hard disk objects associated with virtual machine TestVM, using the pipeline feature for the VMId parameter.

### Example 4
```powershell
PS C:\> Get-VM -VMName TestVM | Select-Object -Property VMId | Get-VHD
```

Gets the virtual hard disk objects associated with virtual machine TestVM using the pipeline feature for the path parameter.

### Example 5
```powershell
PS C:\> Get-ChildItem -Path C:\test -Recurse -Include *.vhd, *.vhdx, *.vhds, *.avhd, *.avhdx | Get-VHD
```

Gets the virtual hard disk object for all the virtual hard disk files that are contained in the specified directory and its subdirectories.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a virtual hard disk is to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskNumber
Specifies the disk number associated with the virtual hard disk to be retrieved.

```yaml
Type: UInt32
Parameter Sets: Disk
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path to the virtual hard disk file of the virtual hard disk to be retrieved.
If a filename or relative path is specified, the path is calculated relative to the current working directory.

```yaml
Type: String[]
Parameter Sets: Path
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: True
```

### -VMId
Specifies the virtual machine identifier of the virtual machine whose virtual hard disks are to be retrieved.

```yaml
Type: Guid[]
Parameter Sets: VMId
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### VHDObject[]

## NOTES

## RELATED LINKS



