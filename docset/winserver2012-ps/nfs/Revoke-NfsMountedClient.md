---
external help file: NFS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 034AE8BF-2EAC-498F-8B82-785F494573C5
manager: dansimp
---

# Revoke-NfsMountedClient

## SYNOPSIS
Revokes a mounted client from an NFS server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Revoke-NfsMountedClient [-ClientId] <UInt64[]> [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Revoke-NfsMountedClient [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Revoke-Nfs-MountedClient** cmdlet revokes a mounted client from a Network File System (NFS) server.
When a mounted client is revoked, the NFS server removes all open states such as open files, locked files, and all the sessions that belong to that client.
To revoke a mounted client, you must specify a client ID.
You can use the **Get-NfsMountedClient** cmdlet to get all mounted clients and their IDs from an NFS server.

## EXAMPLES

### Example 1: Revoke a mounted client from a local NFS server
```
PS C:\> Revoke-NfsMountedClient -ClientId 101
```

This command revokes a mounted client that has the ID 101 from a local NFS server.

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

### -ClientId
Specifies the ID of a client that is mounted to an NFS server.

```yaml
Type: UInt64[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies a mounted client object.
To obtain a mounted client object, including its ID, use the **Get-NfsMountedClient** cmdlet.

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

[Get-NfsMountedClient](./Get-NfsMountedClient.md)

