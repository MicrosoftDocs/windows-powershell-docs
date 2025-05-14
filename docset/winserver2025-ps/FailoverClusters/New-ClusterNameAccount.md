---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/new-clusternameaccount?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ClusterNameAccount
---

# New-ClusterNameAccount

## SYNOPSIS
Creates a cluster name account in Active Directory Domain Services.

## SYNTAX

### InputObject (Default)

```
New-ClusterNameAccount -Name <String> [-Credentials <PSCredential>] [-Domain <String>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

### Credentials

```
New-ClusterNameAccount -Name <String> -Credentials <PSCredential> -Domain <String>
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `New-ClusterNameAccount` cmdlet creates a cluster name account in Active Directory Domain
Services. A cluster name account is also referred to as a cluster name object (CNO). This cmdlet
changes the existing cluster name to match the cluster name account that it creates. If a cluster
name account already exists for a cluster, this cmdlet has no effect.

## EXAMPLES

### Example 1: Create a cluster name account for the current cluster

```powershell
New-ClusterNameAccount -Name "cluster_17" -Domain "production.contoso.com"
```

This command creates a cluster name account for the current cluster in the specified domain.
The current cluster is the default value for the cluster on which this cmdlet operates.

### Example 2: Create a cluster name account by using credentials

```powershell
$Credential = Get-Credential
New-ClusterNameAccount -Name "cluster27" -Domain "production.contoso.com" -Credentials $Credential
```

The first command prompts you for credentials, and then stores them in the `$Credential` variable.

The second command creates a cluster name account for the current cluster in the specified domain.
The command supplies the credentials stored in `$Credential` to access Active Directory Domain
Services.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credentials

Specifies the credentials that this cmdlet uses when it connects to Active Directory Domain
Services. To obtain credentials, use the `Get-Credential` cmdlet. For more information, type
`Get-Help Get-Credential`.

```yaml
Type: PSCredential
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: PSCredential
Parameter Sets: Credentials
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain

Specifies the Active Directory Domain Services domain in which this cmdlet creates a cluster name
account.

```yaml
Type: String
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Credentials
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Specifies the cluster for which this cmdlet adds a cluster name account.

```yaml
Type: PSObject
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Specifies the name of the cluster name account that this cmdlet creates.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

This cmdlet accepts a **Cluster** object for which it creates a cluster name account.

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)
