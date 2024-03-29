---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adreplicationqueueoperation?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADReplicationQueueOperation
---

# Get-ADReplicationQueueOperation

## SYNOPSIS
Returns the contents of the replication queue for a specified server.

## SYNTAX

```
Get-ADReplicationQueueOperation [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Server] <String>
 [-Filter <String>] [[-Partition] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADReplicationQueueOperation** cmdlet returns all of the pending operations in the replication queue.
While replication operations are pending, this cmdlet can be useful for determining the status of queued operations.

You can call the **Get-ADReplicationQueueOperation** cmdlet from script to observe when operations are moved out of the queue as they are replicated.
It also allows for filtering on any of the properties on the **ADReplicationOperation** object.

The replication queue operates in the following manner: suppose a domain controller has five inbound replication connections.
As the domain controller formulates change requests, either by a schedule being reached or from a notification, it adds a work item for each request to the end of the queue of pending synchronization requests.
Each pending synchronization request represents one \<source domain controller, directory partition\> pair, such as synchronize the schema directory partition from DC1 or delete the ApplicationX directory partition.

When a work item has been received into the queue, notification and polling intervals do not apply.
Instead, the domain controller processes the item (begins synchronizing from its source) as soon as the work item reaches the front of the replication queue.
This process continues until either the destination is fully synchronized with the source domain controller, an error occurs, or the synchronization is pre-empted by a higher-priority operation.

## EXAMPLES

### Example 1: Get the pending operations in a replication queue
```
PS C:\>Get-ADReplicationQueueOperation -Server "corp-DC01.corp.contoso.com"
```

This command gets the pending operations in the replication queue for the domain controller corp-DC01 as specified by its fully qualified domain name (FQDN).

## PARAMETERS

### -AuthType
Specifies the authentication method to use.
The acceptable values for this parameter are:

- Negotiate or 0
- Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases: 
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: Microsoft.ActiveDirectory.Management.AuthType.Negotiate
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user account that has permission to perform this action.
The default is the current user.

Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credentialhttp://go.microsoft.com/fwlink/?LinkID=293936 cmdlet.
If you type a user name, you will be prompted for a password.

This parameter is not supported by any providers installed with Windows PowerShell.

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

### -Filter
Specifies a filter in the provider's format or language.
The value of this parameter qualifies the Path parameter.
The syntax of the filter, including the use of wildcards, depends on the provider.
Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having Windows PowerShell filter the objects after they are retrieved.

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

### -Partition
Specifies the distinguished name of an Active Directory partition.
The distinguished name must be one of the naming contexts on the current directory server.
The cmdlet searches this partition to find the object defined by the **Identity** parameter.

In many cases, a default value will be used for the Partition parameter if no value is specified. 
The rules for determining the default value are given below. 
Note that rules listed first are evaluated first and once a default value can be determined, no further rules will be evaluated.

In Active Directory Domain Services (AD DS) environments, a default value for **Partition** is set in the following cases: 

- If the **Identity** parameter is set to a distinguished name, the default value of **Partition** is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of **Partition** is automatically generated from the current path in the drive. 
- If none of the previous cases apply, the default value of **Partition** is set to the default partition or naming context of the target domain.

In Active Directory Lightweight Directory Services (AD LDS) environments, a default value for **Partition** is set in the following cases:

- If the **Identity** parameter is set to a distinguished name, the default value of **Partition** is automatically generated from this distinguished name. 
- If running cmdlets from an Active Directory provider drive, the default value of **Partition** is automatically generated from the current path in the drive. 
- If the target AD LDS instance has a default naming context, the default value of **Partition** is set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent (DSA) object (**nTDSDSA**) for the AD LDS instance. 
- If none of the previous cases apply, the **Partition** parameter does not take any default value.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: NC, NamingContext

Required: False
Position: 2
Default value: DefaultNC; Provider: Default is to use the Partition that you are currently in. Else, use DefaultNC (IE: If you are in the RootDSE)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the AD DS instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: AD LDS, AD DS, or Active Directory snapshot instance.

Specify the AD DS instance in one of the following ways:  

 Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:  

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the **Server** value from objects passed through the pipeline
- By using the server information associated with the AD DS Windows PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADDirectoryServer
A class structure that represents one or more Active Directory servers.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADReplicationOperation
A class structure that represents one or more Active Directory replication operations.

## NOTES

## RELATED LINKS

