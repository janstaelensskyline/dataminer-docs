---
uid: KI_Upgrade_fails_VerifyNoObsoleteApiDeployed_prerequisite
---

# Upgrade fails because of VerifyNoObsoleteApiDeployed.dll prerequisite

## Affected versions

DataMiner 10.4.0 or newer.

## Cause

From DataMiner 10.4.0 onwards, the obsolete *API Deployment* feature will be completely removed from DataMiner and replaced by [User-Defined APIs](xref:UD_APIs). The *VerifyNoObsoleteApiDeployed* upgrade prerequisite verifies that no obsolete APIs are deployed before upgrading, as these will no longer work after the upgrade.

## Fix

If you do not want to lose your APIs, you will have to migrate them to the *User-Defined APIs* feature. For more information, see [Defining a new API](xref:UD_APIs_Define_New_API) and [Using existing scripts](xref:UD_APIs_Using_existing_scripts).

If you want to remove obsolete APIs from your system, follow the steps below. Note that you will also have to follow these steps after you have migrated your APIs to the *User-Defined APIs* feature.

1. Open DataMiner Cube, and log into your DataMiner System.

1. Go to *System Center* > *API deployment (Deprecated)*.

   Your APIs will be displayed in a tree view.

   ![Obsolete APIs in System Center in Cube on a 10.3.9 DataMiner](~/user-guide/images/UDAPIS_Migration_1.jpg)

1. To undeploy the API, click the button in the *Undeploy* column, and then click *Yes*.

When finished, you should only have *Unused Tokens* left in your tree view. This process only needs to be done on one DataMiner Agent in the cluster. The changes will be be synchronized to the rest of the cluster.

![No more Obsolete APIs in System Center in Cube on a 10.3.9 DataMiner](~/user-guide/images/UDAPIS_Migration_2.jpg)

## Issue description

Upgrading to 10.4.0 or newer will remove *API Deployment* and all configuration/data related to it. If you still have APIs deployed with this feature, they would be removed by the upgrade. This prerequisite prevents this by forcing you to remove the deployments.
