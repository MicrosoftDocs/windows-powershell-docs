---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/set-hpctestcredential?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HpcTestCredential
---

# Set-HpcTestCredential

## SYNOPSIS
Sets the credentials for running diagnostic tests.

## SYNTAX

### password (Default)
```
Set-HpcTestCredential -Credential <PSCredential>  [-Scheduler <String[]>]
 [<CommonParameters>]
```

### softcard
```
Set-HpcTestCredential [-SoftCard] [-Thumbprint <String>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HpcTestCredential** cmdlet sets the credentials for running diagnostic tests.
The cmdlet stores these credentials in the credential cache of the user who ran the cmdlet.
These credentials are used to run the clusrun commands that run each phase of the diagnostic test if the user does not specify credentials when running the test.

## EXAMPLES

### Example 1: Set test credentials for a cluster
```
PS C:\>Set-HpcTestCredential
```

This command sets the credentials for running diagnostic tests on the cluster.
When the **Set-HpcTestCredential** cmdlet runs, a dialog box appears that requests a user name and password.
After you enter this information, the **Set-HpcTestCredential** cmdlet sets the credentials for running diagnostic tests on the cluster to the credentials that you supplied.

### Example 2: Get a credential object to use for test credentials
```
PS C:\>$Credential = Get-Credential
PS C:\> Set-HpcTestCredential -Credential $Credential
```

This command gets a **PSCredential** object, and then sets the credentials for running diagnostics tests on the cluster to the credentials that the **PSCredential** object represents.
When the Get-Credential cmdlet runs, a dialog box appears that requests a user name and password.
After you enter this information, the **Get-Credential** cmdlet creates the **PSCredential** object and passes it to the **Set-HpcTestCredential** cmdlet.

## PARAMETERS

### -Credential
Specifies a **PSCredential** object that represents the credentials that you want to set for running diagnostic tests on the cluster that the *Scheduler* parameter specifies.
This cmdlet sets these credentials in the credential cache of the user who ran the cmdlet.

You can use the Get-Credential cmdlet to get a **PsCredential** object.
Save that object in a variable, and then use that variable with this parameter.

```yaml
Type: PSCredential
Parameter Sets: password
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster for which you want to set the credentials for running diagnostic tests.
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

### -SoftCard
Uploads an HPC SoftCard to the HPC Scheduler service to be used for diagnostic tests.
The certificate must be in the user's personal store on the local system and will be exported from it along with the corresponding key pair.
It will be encrypted and transmitted to the scheduler.
If an HPC SoftCard already exists on the Head Node, it is replaced with this SoftCard.

```yaml
Type: SwitchParameter
Parameter Sets: softcard
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint
Specifies a certificate thumbprint that can be used to identify the proper certificate if multiple HPC certificates are present.
If multiple HPC certificates are present and the thumbprint is not present, or if the thumbprint does not match a certificate in the user's personal store, then an error is returned.

```yaml
Type: String
Parameter Sets: softcard
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
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Invoke-HpcTest](/powershell/module/hpcpack2016/invoke-hpctest?view=hpc16-ps)

[Remove-HpcTestCredential](/powershell/module/hpcpack2016/remove-hpctestcredential?view=hpc16-ps)

[Set-HpcJobCredential](/powershell/module/hpcpack2016/set-hpcjobcredential?view=hpc16-ps)

[Set-HpcSoaCredential](./Set-HpcSoaCredential.md)
