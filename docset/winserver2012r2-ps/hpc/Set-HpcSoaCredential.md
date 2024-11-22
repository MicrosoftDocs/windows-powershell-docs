---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/set-hpcsoacredential?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HpcSoaCredential
---

# Set-HpcSoaCredential

## SYNOPSIS
Sets the credentials for creating SOA sessions.

## SYNTAX

```
Set-HpcSoaCredential -Credential <PSCredential> [-Azure]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HpcSoaCredential** cmdlet sets the credentials for creating service-oriented architecture (SOA) sessions.
The cmdlet stores these credentials in the credential cache of the user who ran the cmdlet.

## EXAMPLES

### Example 1: Set SOA session credentials
```
PS C:\>Set-HpcSoaCredential
```

This command sets the credentials for creating SOA sessions on the cluster.
When the **Set-HpcSoaCredential** cmdlet runs, a dialog box appears that requests a user name and password.
After you enter this information, the **Set-HpcSoaCredential** cmdlet sets the credentials for creating SOA sessions on the cluster to the credentials that you supplied.

### Example 2: Get a credential and use it to update SOA credentials
```
PS C:\>$Credential = Get-Credential
Set-HpcSoaCredential -Credential $Credential
```

This command gets a **PSCredential** object, and then sets the credentials for creating SOA sessions on the cluster to the credentials that the **PSCredential** object represents.
When the Get-Credential cmdlet runs, a dialog box appears that requests a user name and password.
After you enter this information, the **Get-Credential** cmdlet creates the **PSCredential** object and passes it to the **Set-HpcSoaCredential** cmdlet.

## PARAMETERS

### -Azure
Indicates that the *Scheduler* parameter is the URL of a Windows Azure cloud service that is running the Windows Azure HPC Scheduler.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 3 (SP3).
It is not available in previous versions.

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

### -Credential
Specifies a **PSCredential** object that represents the credentials that you want to set for creating SOA sessions on the cluster that the *Scheduler* parameters specifies.
This cmdlet sets these credentials in the credential cache of the user who ran the cmdlet.

You can use the Get-Credential cmdlet to get a **PsCredential** object.
Save that object in a variable, and then use that variable with this parameter.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or the IP address of the head node for the cluster for which you want to set the credentials that are used to create the SOA sessions.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PsCredential

## OUTPUTS

### None

## NOTES
* The cached credentials are used to create SOA sessions when the SOA client application does not specify a user name and password in the **SessionStartInfo** object that the application specifies when creating the session.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Remove-HpcSoaCredential](/powershell/module/hpcpack2016/remove-hpcsoacredential?view=hpc16-ps)

[Set-HpcJobCredential](/powershell/module/hpcpack2016/set-hpcjobcredential?view=hpc16-ps)

[Set-HpcTestCredential](./Set-HpcTestCredential.md)
