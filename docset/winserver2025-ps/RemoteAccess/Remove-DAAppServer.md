---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAAppServer_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/remove-daappserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DAAppServer
---

# Remove-DAAppServer

## SYNOPSIS
Removes the specified list of application server security groups (SGs) from the DirectAccess (DA) deployment, removes the specified application servers from the specified DA application server SG,and removes the application server Group Policy Objects (GPOs) in the specified domains.

## SYNTAX

### AppServerSGGpo (Default)
```
Remove-DAAppServer [-ComputerName <String>] [-PassThru] [-DomainName <String[]>]
 [-SecurityGroupNameList <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### AppServerFromSGGpo
```
Remove-DAAppServer [-SecurityGroupName] <String> [-Name] <String[]> [-ComputerName <String>] [-PassThru]
 [-DomainName <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DAAppServer** cmdlet removes the specified list of application server security groups (SGs) from the DirectAccess (DA) deployment, removes the specified application servers from the specified DA application server SG,and removes the application server Group Policy Objects (GPOs) in the specified domains.
This cmdlet is not applicable when DA is deployed only for the management of remote clients.

The basic paradigm is that all application server GPOs always contain all SGs even if all the corresponding domains are not represented in all the SGs.
There will never be a scenario where an SG is present only in some of the GPOs.
If this happens, then it means that the configuration is in a bad state.

The application server SG and GPO parameters are treated as independent entities.
A user can remove application server GPOs independent of the SGs and the domains where these SGs exist.
Every SG that is removed from the DA deployment is removed from all application server GPOs currently present.

The following additional capabilities of this cmdlet justify its need though AD cmdlets are already available for the deletion of SGs and GPOs.

 -- When an SG is removed it is removed in all GPOs.
Additionally, if user does not have permissions to edit a GPO the SG is not removed from any of the GPOs.
When using the AD cmdlet user would have to carefully ensure that it is run for each of the domains and it is difficult to handle the case where he does not have permissions on some domains.

 -- With the above described paradigm there is still a need to parse an SG to remove independent application servers in the SG because every application server has a unique IP address that is used in the client policy that needs to be removed.
This functionality is handled by this cmdlet.

 -- When a GPO is removed all SGs are removed from the GPO and the application server specific policies are also removed.
The cmdlet takes care of the conditions where the GPO is removed only if it was originally created at the time of adding.
If the GPO is already present at the time of adding, then it is merely edited.

App Server configuration is a global configuration and is applicable to all DA servers in the enterprise deployment even when there is multi-site enterprise deployment.

Following are additional behavioral notes for this cmdlet.

 -- If a nested SG has to be removed, then the cmdlet recursively parses the SG so that all servers are retrieved and policies can be removed accordingly.

 -- Removing a domain deletes the application server GPO only if it was created at the time of addition.
If it was already present, then only the DA related policies and settings are wiped out and the GPO is left intact.

 -- Deletion of all app server GPOs and SGs is a permitted operation.

 -- When removing SGs if the user does not have the permissions to configure even one app server GPO among the many that might be present, then this cmdlet terminates the processing of the entire list of SGs specified.
However, this cmdlet still processes any GPOs that the user might have specified to remove.

 -- When removing GPOs if the user does not have the permissions to remove or configure one of the specified GPOs, then the cmdlet still proceeds with the processing of the remaining GPOs in the list.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-DAAppServer -SecurityGroupNameList daAppServerGrp
SecurityGroupNameList:
GpoName  :
ConnectionType : E2EAuthOnlyToAppServer
TrafficProtection : Enabled
```

This example deletes the daAppServerGrp SG from all GPOs.
In current setup, daAppServerGrp was the only SG present, therefore the application server GPO (such as corp.contoso.com\DirectAccess Application Server Settings) is also removed automatically.

### EXAMPLE 2
```
PS C:\>Remove-DAAppServer -SecurityGroupName daAppServerGrp -Name "da-test-0807"
```

This example deletes the computer named da-test-0807 from SG daAppServerGrp.
The SG continues to be a part of DA Configuration.

### EXAMPLE 3
```
PS C:\>Remove-DAAppServer -DomainName "corp.contoso.com"
SecurityGroupNameList:
GpoName  :
ConnectionType : E2EAuthOnlyToAppServer
TrafficProtection : Enabled
```

This example removes the application server GPO in the DA configuration from the corp.contoso.com domain.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access server computer specific tasks should be run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies the list of domains from which application server GPOs need to be removed.
A domain is specified in the `DOMAIN` format.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the list of application servers that have to be deleted from the DA deployment.
The servers are specified by using the host names and are deleted from the SG specified by the **SecurityGroupName** parameter.
The servers cannot be specified by their IPv4 or IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: AppServerFromSGGpo
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -SecurityGroupName
Specifies the name of a SG that is already part of the DA deployment from which the specified list of app servers should be deleted.
Specified in `DOMAIN\SG_NAME` format.

```yaml
Type: String
Parameter Sets: AppServerFromSGGpo
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecurityGroupNameList
Specifies the list of application server SGs that are to be deleted from the DA deployment.
Each SG is specified in `DOMAIN\SG_NAME` format.

```yaml
Type: String[]
Parameter Sets: AppServerSGGpo
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DAAppServer

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DAAppServer object consists of the following properties:

 -- The list of application server security groups each security group is specified in the Domain\GroupName format.

 -- The list of application server GPOs: each GPO is specified in the Domain\GPOName format.

 -- The properties of the connection to the application server.

 -- Status of IPsec traffic protection: Enabled or Disabled.

## NOTES

## RELATED LINKS

[Add-DAAppServer](./Add-DAAppServer.md)

[Get-DAAppServer](./Get-DAAppServer.md)

