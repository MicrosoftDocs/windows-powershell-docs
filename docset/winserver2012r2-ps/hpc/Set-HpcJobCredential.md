---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/set-hpcjobcredential?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HpcJobCredential
---

# Set-HpcJobCredential

## SYNOPSIS
Sets the credentials for submitting jobs.

## SYNTAX

### password (Default)
```
Set-HpcJobCredential -Credential <PSCredential> [-ExtendedData <String>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

### softcard
```
Set-HpcJobCredential [-SoftCard] [-Thumbprint <String>] [-ExtendedData <String>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

### AAD
```
Set-HpcJobCredential [-ExtendedData <String>] [-AadUser]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HpcJobCredential** cmdlet sets the credentials for submitting jobs.
The cmdlet stores these credentials in the credential cache of the user who ran the cmdlet.

## EXAMPLES

### Example 1: Set credentials to submit jobs
```
PS C:\>Set-HpcJobCredential
```

This command sets the credentials for submitting jobs on the cluster.
When the **Set-HpcJobCredential** cmdlet runs, a dialog box appears requesting a user name and password.
After you enter this information, the **Set-HpcJobCredential** cmdlet sets the credentials for submitting jobs on the cluster to the credentials you supplied.

### Example 2: Get credentials and set them to submit jobs
```
PS C:\>$Credential = Get-Credential
PS C:\> Set-HpcJobCredential -Credential $Credential
```

This command gets a **PSCredential** object, and then sets the credentials for submitting jobs on the cluster to the credentials that the **PSCredential** object represents.
When the Get-Credential cmdlet runs, a dialog box appears requesting a user name and password.
After you enter this information, the **Get-Credential** cmdlet creates the **PSCredential** object and passes it to the **Set-HpcJobCredential** cmdlet.

## PARAMETERS

### -Credential
Specifies a **PSCredential** object that represents the credentials that you want to set for submitting the jobs on the cluster that the *Scheduler* parameter specifies.
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
Specifies the host name or IP address of the head node for the cluster that contains jobs for which you want to set the credentials.
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
Indicates that this operation caches the HPC soft card on the cluster.
If an HPC soft card for that user is already cached, it is replaced.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2).
It is not supported in previous versions.

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
Specifies the certificate thumbprint toused to identify the proper certificate if multiple HPC soft card certificates are present.
If multiple HPC certificates are present and the thumbprint is not present, or if the thumbprint does not match a certificate in the user's personal store, then an error is returned.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2).
It is not supported in previous versions.

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

### -AadUser
{{Fill AadUser Description}}

```yaml
Type: SwitchParameter
Parameter Sets: AAD
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedData
{{Fill ExtendedData Description}}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSCredential

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-HpcJobCredential](./Get-HpcJobCredential.md)

[Remove-HpcJobCredential](./Remove-HpcJobCredential.md)
