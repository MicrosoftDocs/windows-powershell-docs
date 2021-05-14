---
external help file: ClusterAware_Cmdlets.xml
Module Name: ClusterAwareUpdating
online version: https://docs.microsoft.com/powershell/module/clusterawareupdating/get-cauclusterrole?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-CauClusterRole

## SYNOPSIS
Retrieves configuration properties of the Cluster-Aware Updating (CAU) clustered role on the specified cluster.

## SYNTAX

```
Get-CauClusterRole [[-ClusterName] <String>] [-Credential <PSCredential>]
```

## DESCRIPTION
The **Get-CauClusterRole** cmdlet retrieves configuration properties of the Cluster-Aware Updating (CAU) clustered role on the specified cluster.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-CauClusterRole -ClusterName CONTOSO-FC1
Name                                                        Value 
----                                                        ----- 
ResourceGroupName                                           CAUCAUCldy8 
Status                                                      Online 
StartDate                                                   10/14/2011 3:00:00 AM 
MaxFailedNodes                                              2 
MaxRetriesPerNode                                           2 
PostUpdateScript                                            G:\verifyupdatesinstalled.ps1 
RequireAllNodesOnline                                       On 
DaysOfWeek                                                  Tuesday, Saturday 
WeeksOfMonth                                                {2, 4}
```

This example gets information about the CAU clustered role on the cluster called CONTOSO-FC1.

## PARAMETERS

### -ClusterName
Specifies the name of the cluster for which the CAU clustered role information should be retrieved.
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

## INPUTS

### None

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauParameter

## NOTES

## RELATED LINKS

[Add-CauClusterRole](./Add-CauClusterRole.md)

[Disable-CauClusterRole](./Disable-CauClusterRole.md)

[Enable-CauClusterRole](./Enable-CauClusterRole.md)

[Remove-CauClusterRole](./Remove-CauClusterRole.md)

[Set-CauClusterRole](./Set-CauClusterRole.md)

