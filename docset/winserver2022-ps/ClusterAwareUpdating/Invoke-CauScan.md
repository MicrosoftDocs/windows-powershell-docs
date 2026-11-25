---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 09/27/2022
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/invoke-causcan?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CauScan
---

# Invoke-CauScan

## SYNOPSIS
Performs a scan of cluster nodes for applicable updates and gets a list of the initial set of
updates that are applied to each node in a specified cluster.

## SYNTAX

```
Invoke-CauScan [[-ClusterName] <String>] [[-CauPluginName] <String[]>]
 [[-Credential] <PSCredential>] [-CauPluginArguments <Hashtable[]>] [-RunPluginsSerially]
 [-StopOnPluginFailure] [-OsRollingUpgrade] [-AttemptSoftReboot] [-RebootMode <RebootType>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Invoke-CauScan` cmdlet performs a scan of cluster nodes for applicable updates and gets a
list of the initial set of updates that are applied to each node in a specified cluster. Generation
of the list can take a few minutes to complete.

The preview list includes only an initial set of updates. The list doesn't include updates that
might become applicable after the initial updates are installed.

If the **Microsoft.HotfixPlugin** plug-in is specified, the scan gets only the list of hotfix files
that are discovered on the hotfix file share.

## EXAMPLES

### Example 1: Get a detailed list of the initial set of updates on the specified cluster

```powershell
Invoke-CauScan -ClusterName "CONTOSO-FC1" -CauPluginName "Microsoft.WindowsUpdatePlugin" -Verbose
```

This command gets a detailed list of the initial set of updates that would currently be applied to
each node in the cluster named **CONTOSO-FC1**. The list is based on the updates that would be
applied by the **Microsoft.WindowsUpdatePlugin** plug-in, which is the default plug-in. The preview
list includes only an initial set of updates, and doesn't include updates that might become
applicable only after the initial updates are installed.

### Example 2: Get a detailed list of the initial set of updates on the specified cluster using a query string

```powershell
$SecPasswd = ConvertTo-SecureString "PlainTextPassword" -AsPlainText -Force 
$Cred = New-Object System.Management.Automation.PSCredential ("username", $SecPasswd) 
$parameters = @{
    ClusterName = 'CONTOSO-FC1'
    CauPluginName = 'Microsoft.WindowsUpdatePlugin',
                    'Microsoft.HotfixPlugin'
    CauPluginArguments = @{'QueryString'="IsInstalled=0 and Type='Software' and IsHidden=0"},
                         @{'HotfixRootFolderPath' = '\\CauHotfixSrv\shareName'}
    StopOnPluginFailure = $true
    EnableFirewallRules = $true
    Force = $true
}
Invoke-CauScan $parameters -Credential $Cred
```

This example gets a detailed list of the initial set of updates that would currently be applied to
each node in the cluster named **CONTOSO-FC1**. The list is based on the updates that would be applied
by the **Microsoft.WindowsUpdatePlugin** plug-in, using a specified query string, and the
**Microsoft.HotfixPlugin**, after the necessary hotfixes and the hotfix configuration file have been
downloaded to `\\CauHotfixSrv\shareName`. This example also shows how to pass the administrative
credentials for cluster `CONTOSO-FC1` to the cmdlet.

This example uses splatting to pass parameter values from the `$parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

## PARAMETERS

### -AttemptSoftReboot

Indicates that command assumes a Kernel Soft Reboot (KSR) for the failover cluster.

KSR bypasses BIOS/firmware initialization.
You can only use KSR for updates that do not require a BIOS/firmware initialization.

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

### -CauPluginArguments

Specifies a set of name=value pairs, as arguments, for each updating plug-in to use.

For instance, to specify a Domain argument for one plug-in:

- `@{Domain=Domain.local}`

You can specify multiple pairs in a set separated with semicolons. For instance:

- `@{name1=value1;name2=value2;name3=value3}`

These name=value pairs must be meaningful to the **CauPluginName** parameter that you specify. If
you specify arguments for more than one plug-in, provide the sets of name=value pairs in the order
that you pass values in **CauPluginName**, separated by commas. For instance:

- `@{name1=value1;name2=value2;name3=value3},@{name4=value4;name5=value5}`

For the default **Microsoft.WindowsUpdatePlugin** plug-in, no arguments are needed. The following
arguments are optional:

- **'IncludeRecommendedUpdates'='\<Value\>'**: Boolean value to indicate that recommended updates
  will be applied in addition to important updates on each node. If not specified, the default value
  is False.
- A standard Windows Update Agent query string that specifies criteria used by the Windows Update
  Agent to filter the updates that will be applied to each node. For a name, use **QueryString** and
  for a value, enclose the full query in quotation marks. If not specified, then the
  **Microsoft.WindowsUpdatePlugin** plug-in by default uses the following argument:
- `QueryString="IsInstalled=0 and Type='Software' and IsHidden=0 and IsAssigned=1"`

For more information about query strings for the default **Microsoft.WindowsUpdatePlugin** plug-in
and the criteria such as IsInstalled that can be included in the query strings, see
[IUpdateSearcher::Search method](/windows/win32/api/wuapi/nf-wuapi-iupdatesearcher-search).

For the **Microsoft.HotfixPlugin** plug-in, the following argument is required:

- **HotfixRootFolderPath=\<Path\>**: The UNC path to a hotfix root folder in an SMB share with a
  structure that contains the updates to apply and that contains the hotfix configuration file.

The following arguments are optional for the **Microsoft.HotfixPlugin** plug-in:

- **RequireSmbEncryption=\<Value\>**: Boolean value to indicate that SMB Encryption will be enforced
  for accessing data from the SMB share. If not specified, the default value is False. To ensure the
  integrity of the data accessed from the SMB share, the plug-in requires that the share is enabled
  for either SMB signing or SMB Encryption.
- **DisableAclChecks=\<Value\>**: Boolean value to indicate that the plug-in will check for
  sufficient permissions on the hotfix root folder and the hotfix configuration file. If not
  specified, the default value is False.
- **HotfixInstallerTimeoutMinutes=\<Integer\>**: The length of time in minutes that the plug-in
  allows the hotfix installer process to return. If not specified, the default value is 30 minutes.
- **HotfixConfigFileName=\<name\>**: Name for the hotfix configuration file. If not specified, the
  default name `DefaultHotfixConfig.xml` is used. For more information about required and optional
  arguments for the **Microsoft.HotfixPlugin** plug-in, see
  [How Cluster-Aware Updating plug-ins work](/windows-server/failover-clustering/cluster-aware-updating-plug-ins).

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CauPluginName

Specifies one or more plug-ins to use when performing scans. You can specify multiple values
separated with commas. The default is the **Microsoft.WindowsUpdatePlugin** plug-in. This plug-in
coordinates the Windows Update Agent software resident on each cluster node, the same software that
is used when updates are downloaded from Windows Update or Microsoft Update, or from a Windows
Server Update Services (WSUS) server.

For more information about how plug-ins work with
Cluster-Aware Updating (CAU), see
[Cluster-Aware Updating plug-ins](/windows-server/failover-clustering/cluster-aware-updating-plug-ins).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName

Specifies the name of the cluster which should be scanned for applicable updates. This parameter is
only required when this cmdlet isn't run on a failover cluster node, or this cmdlet is used to
reference a failover cluster different from where the cmdlet is run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OsRollingUpgrade

Indicates that the CAU cluster role scans for upgrades to the operating system of the cluster nodes
without stopping the Hyper-V or the Scale-Out File Server workloads.

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

### -RebootMode

Specifies the type of reboot to use for each node in the cluster during the update. The available
values are:

- `ClusProp`
- `FullReboot`
- `SoftReboot`
- `PluginCustomReboot`
- `OrchestratorDefault`

```yaml
Type: RebootType
Parameter Sets: DefaultParamSet
Aliases:
Accepted values: ClusProp, FullReboot, SoftReboot, PluginCustomReboot, OrchestratorDefault

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunPluginsSerially

Indicates that CAU scans each cluster node for applicable updates and stages the updates for each
plug-in in the plug-in order passed into the **CauPluginName** parameter then multiple plug-ins are
used during a scan for updates

By default, CAU scans and stages the applicable updates for all plug-ins in parallel. This
parameter is valid only when multiple plug-ins are specified in the **CauPluginName** parameter. If
a single plug-in is specified, a warning appears.

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

### -StopOnPluginFailure

Indicates that if a failure occurs during a scan on a node by any plug-in, subsequent scans on the
node that are coordinated by the remaining plug-ins are stopped when multiple plug-ins are used
during a scan for updates.

The parameter is valid only when multiple plug-ins are specified in the **CauPluginName** parameter.
If a single plug-in is specified, a warning appears.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### None

## OUTPUTS

### Microsoft.ClusterAwareUpdating.UpdateInfo

### Microsoft.ClusterAwareUpdating.ActivityIdMap

### Microsoft.ClusterAwareUpdating.UpgradeSetupInfo

## NOTES

## RELATED LINKS

[Add-CauClusterRole](add-cauclusterrole.md)

[Get-CauRun](get-caurun.md)

[Invoke-CauRun](invoke-caurun.md)

[Stop-CauRun](stop-caurun.md)
