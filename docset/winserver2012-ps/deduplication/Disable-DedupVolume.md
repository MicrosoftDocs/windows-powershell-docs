---
external help file: Dedup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 35CD5640-538A-4957-B87D-A59BB87C34B1
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Disable-DedupVolume

## SYNOPSIS
Disables data deduplication activity on one or more volumes.

## SYNTAX

```
Disable-DedupVolume [-Volume] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-DataAccess]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Disable-DedupVolume** cmdlet disables further data deduplication activity on one or more volumes.
After you disable data deduplication, the volume remains in a deduplicated state and the existing deduplicated data is accessible.
The server stops running data deduplication jobs for the volume and new data is not deduplicated.
To undo data deduplication on a volume, use the Start-DedupJob cmdlet and specify Unoptimization for the **Type** parameter.

After you disable data deduplication on a volume, you can perform all read-only deduplication cmdlet operations on the volume.
For example, you can use the Get-DedupStatus cmdlet to get deduplication status for a volume that has data deduplication metadata.
After you disable data deduplication on a volume, you cannot use the data deduplication job-related cmdlets and the Update-DedupStatus cmdlet to perform operations on the volume.
For example, you cannot use Start-DedupJob to start a data deduplication job for a volume on which you have disabled data deduplication.

## EXAMPLES

### Example 1: Disable data deduplication on volumes
```
PS C:\>Disable-DedupVolume -Volume D:,E:,F:,G:
```

This command disables data deduplication for volumes D:, E:, F:, and G:.

### Example 2: Disable data deduplication on a volume by using a GUID
```
PS C:\>Disable-DedupVolume -Volume "\\?\Volume{26a21bda-a627-11d7-9931-806e6f6e6963}\"
```

This command disables data deduplication for the volume that has the GUID 26a21bda-a627-11d7-9931-806e6f6e6963.

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

### -DataAccess
Indicates that data access to deduplicated files on the volume is disabled.

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

### -Volume
Specifies an array of system volumes for which to disable data deduplication.
Specify one or more volume IDs, drive letters (such as `D:`), or volume GUID pathnames (using the form `\\\\?\Volume{{GUID}}\\`).
Separate multiple volumes with a comma.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Path,Name,DeviceId

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Enable-DedupVolume](./Enable-DedupVolume.md)

[Get-DedupVolume](./Get-DedupVolume.md)

[Set-DedupVolume](./Set-DedupVolume.md)

[Update-DedupStatus](./Update-DedupStatus.md)
