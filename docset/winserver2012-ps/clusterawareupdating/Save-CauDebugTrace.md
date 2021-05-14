---
external help file: ClusterAware_Cmdlets.xml
Module Name: ClusterAwareUpdating
online version: https://docs.microsoft.com/powershell/module/clusterawareupdating/save-caudebugtrace?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Save-CauDebugTrace

## SYNOPSIS
Saves Cluster-Aware Updating (CAU) debug tracing information to a local zip file.

## SYNTAX

```
Save-CauDebugTrace [[-ClusterName] <String>] [[-FilePath] <String>] [-Credential <PSCredential>] [-Force]
 [-RunId <Guid>]
```

## DESCRIPTION
The **Save-CauDebugTrace** cmdlet saves Cluster-Aware Updating (CAU) debug tracing information to a local zip file.
The tracing information is mainly intended for use by developers and support engineers.
Specify the file name with the **FilePath** parameter.

Note: To run this cmdlet, Windows PowerShell® remoting must be enabled on each node.
To do this, run the Enable-PSRemotinghttp://go.microsoft.com/fwlink/p/?LinkID=144300 cmdlet.
In addition, ensure that the Windows Remote Management - Compatibility Mode (HTTP-In) firewall exception is enabled on each node.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Save-CauDebugTrace -ClusterName CONTOSO-FC1 -FilePath C:\temp\testrun.zip
```

This example saves the debug tracing information, for the cluster called CONTOSO-FC1, to a trace file called testrun.zip in the C:\temp folder.

## PARAMETERS

### -FilePath
Specifies the name of the file to which to save the tracing information, such as `MyTrace.zip`.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Specifies that when the file specified by the **FilePath** parameter exists, it is overwritten without prompting for confirmation.
If **Force** is not specified, then when the file specified by the **FilePath** parameter exists, the cmdlet returns an error.

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

### -ClusterName
Specifies the name of the cluster for which to gather CAU debug tracing information.
This parameter is only required when this cmdlet is not run on a failover cluster node, or this cmdlet is used to reference a failover cluster different from where the cmdlet is run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the administrative credentials for the target cluster.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunId
Indicates that the cmdlet should only include debug trace files related to an Updating Run with the specified Run ID.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Invoke-CauRun](./Invoke-CauRun.md)

