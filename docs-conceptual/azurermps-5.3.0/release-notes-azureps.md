---
title: "Az Azure PowerShell változásnaplója | Microsoft Docs"
description: "Az alábbiakban az Azure PowerShell legutóbbi kiadásában végrehajtott módosítások előzményei olvashatók."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.service: azure-powershell
ms.product: azure
ms.devlang: powershell
ms.topic: conceptual
ms.workload: 
ms.date: 2/20/2018
ms.openlocfilehash: 40d5a9199e000d0e2d605527c27409ac65d48dd1
ms.sourcegitcommit: 48461455bc8b70576a75eaa62318bcf66d9ddbb9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/20/2018
---
# <a name="release-notes"></a>Kibocsátási megjegyzések

Az alábbiakban az Azure PowerShell jelen kiadásában végrehajtott módosítások listája olvasható.

---

## <a name="530---february-2018"></a>5.3.0 – 2018. február
### <a name="azurermprofile"></a>AzureRM.Profile
* Elavulással kapcsolatos figyelmeztetés hozzáadva a PowerShell 3-hoz és 4-hez
* Az `Add-AzureRmAccount` új neve `Connect-AzureRmAccount`; a régi parancsmag nevéhez egy új alias lett hozzáadva, és más aliasok (a `Login-AzAccount` és a `Login-AzureRmAccount`) át lettek irányítva az új parancsmag nevéhez.
* Az `Remove-AzureRmAccount` új neve `Disconnect-AzureRmAccount`; a régi parancsmag nevéhez egy új alias lett hozzáadva, és más aliasok (a `Logout-AzAccount` és a `Logout-AzureRmAccount`) át lettek irányítva az új parancsmag nevéhez.
* Az erőforrás-karakterláncok mostantól a `Login-AzureRmAccount` helyett a `Connect-AzureRmAccount` aliast használják
* `Add-AzureRmEnvironment` és `Set-AzureRmEnvironment`
  - `-AzureOperationalInsightsEndpoint` és `-AzureOperationalInsightsEndpointResourceId` paraméterek hozzáadva, amelyek az OperationalInsights adatsík RP-vel használhatók.

### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* A `Login-AzureRmAccount` javítva a `Connect-AzureRmAccount` használatára

### <a name="azurermcompute"></a>AzureRM.Compute
* `-AvailabilitySetName` paraméter hozzáadva a `New-AzureRmVM` egyszerűsített paraméterkészletéhez.
* A `Login-AzureRmAccount` javítva a `Connect-AzureRmAccount` használatára
* Felhasználó által hozzárendelt identitások támogatása virtuális gépekhez és virtuális gépek méretezési csoportjaihoz
    - `-IdentityType` és `-IdentityId` paraméterek hozzáadva a következőkhöz: `New-AzureRmVMConfig`, `New-AzureRmVmssConfig`, `Update-AzureRmVM` és `Update-AzureRmVmss`
* `-EnableIPForwarding` paraméter hozzáadva a `Add-AzureRmVmssNetworkInterfaceConfig` parancshoz
* `-Priority` paraméter hozzáadva a `New-AzureRmVmssConfig` parancshoz

### <a name="azurermdatalakeanalytics"></a>AzureRM.DataLakeAnalytics
* A `Login-AzureRmAccount` javítva a `Connect-AzureRmAccount` használatára

### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* A `Login-AzureRmAccount` javítva a `Connect-AzureRmAccount` használatára
* A `Test-AzureRmDataLakeStoreAccount` hibaüzenete javítva, ha ezt a parancsmagot anélkül futtatja, hogy a `Login-AzureRmAccount` parancsmaggal bejelentkezett volna

### <a name="azurermeventgrid"></a>AzureRM.EventGrid
* Frissítve a 2018-01-01-es API-verzió használatára.

### <a name="azurermeventhub"></a>AzureRM.EventHub
* Az alábbi új parancsok hozzáadva a földrajzi vészhelyreállítási műveletekhez.
    – Új Alias(Vészhelyreállítási konfiguráció) létrehozása: – `New-AzureRmEventHubGeoDRConfiguration` – Alias(Vészhelyreállítási konfiguráció) lekérése: – `Get-AzureRmEventHubGeoDRConfiguration` – Vészhelyreállítás letiltása, módosítások replikálásának leállítása az elsődleges névterekből a másodlagos névterekbe – `Set-AzureRmEventHubGeoDRConfigurationBreakPair` – Vészhelyreállítási feladatátvétel meghívása és az alias átkonfigurálása, hogy a másodlagos névtérre mutasson – `Set-AzureRmEventHubGeoDRConfigurationFailOver` – Alias(Vészhelyreállítási konfiguráció) törlése – `Remove-AzureRmEventHubGeoDRConfiguration`
* Az alábbi új parancsok hozzáadva, amelyekkel a Névtér és a GeoDr-konfiguráció (Alias) nevének rendelkezésre állása ellenőrizhető.
    – A Névtérhez vagy az Alias(Vészhelyreállítási konfigurációhoz) tartozó név rendelkezésre állásának ellenőrzése: – `Test-AzureRmEventHubName`

### <a name="azurerminsights"></a>AzureRM.Insights
* A `Login-AzureRmAccount` javítva a `Connect-AzureRmAccount` használatára

### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* A `Login-AzureRmAccount` javítva a `Connect-AzureRmAccount` használatára

### <a name="azurermnetwork"></a>AzureRM.Network
* Az „Are you sure you want to overwriteresource” (Biztosan felülírja a forrást?) üzenet javítva

#### <a name="azurermoperationalinsights"></a>AzureRM.OperationalInsights
* A V2 API-lekérdezések támogatása az `Invoke-AzureRmOperationalInsightsQuery` parancsmaggal. Az új API-val kapcsolatos további információért lásd: [https://dev.loganalytics.io/](https://dev.loganalytics.io/).

### <a name="azurermresources"></a>AzureRM.Resources
* `Get-AzureRmADServicePrincipal`: `-ServicePrincipalName` eltávolítva az alapértelmezett üres paraméterkészletből, mert redundáns volt az SPN paraméterkészlettel

### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Funkciójavítás hozzáadva a következőkhöz: `Remove-AzureRmServiceBusRule` és `Get-AzureRmServiceBusKey`
* Az alábbi új parancsmagok hozzáadva a földrajzi vészhelyreállítási műveletekhez.
    – Új Alias(Vészhelyreállítási konfiguráció) létrehozása: – `New-AzureRmServiceBusDRConfigurations` – Alias(Vészhelyreállítási konfiguráció) lekérése: – `Get-AzureRmServiceBusDRConfigurations` – Vészhelyreállítás letiltása, módosítások replikálásának leállítása az elsődleges névterekből a másodlagos névterekbe – `Set-AzureRmServiceBusDRConfigurationsBreakPairing` – Vészhelyreállítási feladatátvétel meghívása és az alias átkonfigurálása, hogy a másodlagos névtérre mutasson – `Set-AzureRmServiceBusDRConfigurationsFailOver` – Alias(Vészhelyreállítási konfiguráció) törlése – `Remove-AzureRmServiceBusDRConfigurations`
* `Test-AzureRmServiceBusName` parancsmagok frissítve, hogy támogassák azokat a műveleteket, amelyek a földrajzi vészhelyreállítási alias nevének rendelkezésre állását ellenőrzik.
    – A Névtérhez vagy az Alias(Vészhelyreállítási konfigurációhoz) tartozó név rendelkezésre állásának ellenőrzése: – `Test-AzureRmServiceBusName`

### <a name="azurermusageaggregates"></a>AzureRM.UsageAggregates
* A `Login-AzureRmAccount` javítva a `Connect-AzureRmAccount` használatára

## <a name="520---january-2018"></a>5.2.0 – 2018. január
#### <a name="azurermprofile"></a>AzureRM.Profile
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* Add-AzureRmAccount
  * Hitelesítési célból hozzáadott -MSI-bejelentkezés, amely az aktuális virtuális gép vagy szolgáltatás felügyeltszolgáltatás-identitásának hitelesítő adatait használja
  * Kijavított KeyVault-hitelesítés a felhasználó által megadott hozzáférési jogkivonatokkal történő bejelentkezéskor

#### <a name="azurestorage"></a>Azure.Storage
* Parancsmagok hozzáadása a Storage-szolgáltatás tulajdonságainak lekéréséhez és beállításához
    - Get-AzureStorageServiceProperty
    - Update-AzureStorageServiceProperty

#### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermapimanagement"></a>AzureRM.ApiManagement
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A -Tags paraméter elavulttá tétele a -Tag paraméter használata érdekében a New-AzureRmApiManagementProperty, Set-AzureRmApiManagementProperty és New-AzureRmApiManagement parancsmagok esetében

#### <a name="azurermapplicationinsights"></a>AzureRM.ApplicationInsights
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermautomation"></a>AzureRM.Automation
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A -Tags paraméter elavulttá tétele a -Tag paraméter használata érdekében a Set-AzureRmAutomationRunbook parancsmag esetében

#### <a name="azurermbackup"></a>AzureRM.Backup
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermbatch"></a>AzureRM.Batch
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermcdn"></a>AzureRM.Cdn
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A -Tags paraméter elavulttá tétele a -Tag paraméter használata érdekében a New-AzureRmCdnEndpoint és a New-AzureRmCdnProfile parancsmagok esetében

#### <a name="azurermcognitiveservices"></a>AzureRM.CognitiveServices
* Integráció a Cognitive Services Management SDK 3.0.0-s verziójával.

#### <a name="azurermcompute"></a>AzureRM.Compute
* Egyszerűsített paraméterkészlet hozzáadva a New-AzureRmVmss parancsmaghoz, amely az intelligens alapértelmezett beállítások használatával létrehoz egy virtuálisgép-méretezési csoportot és az összes szükséges erőforrást
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A -Tags paraméter elavulttá tétele a -Tag paraméter használata érdekében a New-AzureRmVm és az Update-AzureRmVm parancsmagok esetében
* A Get-AzureRmComputeResourceSku parancsmag kijavítása azokra az esetekre, amikor korlátozásba a zóna is bele van foglalva.
* Frissített diagnosztikaiügynök-konfigurációs séma az Azure Monitor-fogadó támogatásához.

#### <a name="azurermcontainerinstance"></a>AzureRM.ContainerInstance
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermcontainerregistry"></a>AzureRM.ContainerRegistry
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermdatafactories"></a>AzureRM.DataFactories
* Az Azure Key Vault támogatásának engedélyezése minden adattárhoz társított szolgáltatás esetében
* Hozzáadott licenctípus-tulajdonság az Azure SSIS integrációs modul esetében
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A -Tags paraméter elavulttá tétele a -Tag paraméter használata érdekében a New-AzureRmDataFactory parancsmag esetében

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Az Azure Key Vault támogatásának engedélyezése minden adattárhoz társított szolgáltatás esetében
* Hozzáadott licenctípus-tulajdonság az Azure SSIS integrációs modul esetében
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A „LicenseType” paraméter hozzáadva a „Set-AzureRmDataFactoryV2IntegrationRuntime” parancssorhoz az AHUB működésének lehetővé tétele érdekében

#### <a name="azurermdatalakeanalytics"></a>AzureRM.DataLakeAnalytics
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A -Tags paraméter elavulttá tétele a -Tag paraméter használata érdekében a New-AzureRmDataLakeAnalyticsAccount és a Set-AzureRmDataLakeAnalyticsAccount parancsmagok esetében

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A -Tags paraméter elavulttá tétele a -Tag paraméter használata érdekében a New-AzureRmDataLakeStoreAccount és a Set-AzureRmDataLakeStoreAccount parancsmagok esetében

#### <a name="azurermdevtestlabs"></a>AzureRM.DevTestLabs
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermdns"></a>AzureRM.Dns
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermeventgrid"></a>AzureRM.EventGrid
* A következő új parancsmag lett hozzáadva:
    - Update-AzureRmEventGridSubscription
        - Frissítve lettek az Event Grid-eseményelőfizetések tulajdonságai.
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermhdinsight"></a>AzureRM.HDInsight
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurerminsights"></a>AzureRM.Insights
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermiothub"></a>AzureRM.IotHub
* Tanúsítvány használatának támogatása az IoTHub-parancsmagokhoz
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* -AsJob támogatás hozzáadva a sokáig futó KeyVault-parancsmagok számára. Lehetővé teszi, hogy a kiválasztott parancsmagok a háttérben fussanak, és visszaad egy feladatot, amely nyomon követi és szabályozza az előrehaladást.
    * Érintett parancsmag: Remove-AzureRmKeyVault
* Kijavított hiba a Set-AzureRmKeyVaultAccessPolicy parancsmagban, amely akkor jelentkezett, amikor az AAD szűrő az UPN beállítása helyett az SPN számára adja meg az UPN értékét
   - További információkért tekintse meg a következő problémaleírást: https://github.com/Azure/azure-powershell/issues/5201

#### <a name="azurermlogicapp"></a>AzureRM.LogicApp
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermmachinelearning"></a>AzureRM.MachineLearning
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A -Tags paraméter elavulttá tétele a -Tag paraméter használata érdekében az Update-AzureRmMlCommitmentPlan parancsmag esetében

#### <a name="azurermmachinelearningcompute"></a>AzureRM.MachineLearningCompute
* Az IncludeAllResources paraméter hozzáadása a Remove-AzureRmMlOpCluster parancsmaghoz
    - E kapcsolóparaméter használatával eltávolítható az összes, eredetileg a fürttel együtt létrehozott erőforrás
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermmedia"></a>AzureRM.Media
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A -Tags paraméter elavulttá tétele a -Tag paraméter használata érdekében a Set-AzureRmMediaService és a New-AzureRmMediaService parancsmagok esetében

#### <a name="azurermnetwork"></a>AzureRM.Network
* -AsJob támogatás hozzáadva a sokáig futó Network-parancsmagok számára. Lehetővé teszi, hogy a kiválasztott parancsmagok a háttérben fussanak, és visszaad egy feladatot, amely nyomon követi és szabályozza az előrehaladást.
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermnotificationhubs"></a>AzureRM.NotificationHubs
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A -Tags paraméter elavulttá tétele a -Tag paraméter használata érdekében a New-AzureRmNotificationHubsNamespace és a Set-AzureRmNotificationHubsNamespace parancsmagok esetében

#### <a name="azurermoperationalinsights"></a>AzureRM.OperationalInsights
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A -Tags paraméter elavulttá tétele a -Tag paraméter használata érdekében a New-AzureRmOperationalInsightsSavedSearch, Set-AzureRmOperationalInsightsSavedSearch, New-AzureRmOperationalInsightsWorkspace és Set-AzureRmOperationalInsightsWorkspace parancsmagok esetében

#### <a name="azurermpowerbiembedded"></a>AzureRM.PowerBIEmbedded
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermrecoveryservices"></a>AzureRM.RecoveryServices
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermrecoveryservicesbackup"></a>AzureRM.RecoveryServices.Backup
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A -UseOriginalStorageAccount beállítás hozzáadva a Restore-AzureRmRecoveryServicesBackupItem parancsmaghoz.
    - Ezen jelző engedélyezésekor a rendszer visszaállítja a lemezeket az eredeti tárfiókokban, így a felhasználók a visszaállított virtuális gép konfigurálásakor a lehető legnagyobb mértékben megtarthatják az eredeti virtuális gép konfigurációját.
    - Ezzel hozzájárul továbbá a visszaállítási művelet teljesítményének javításához is.

#### <a name="azurermrediscache"></a>AzureRM.RedisCache
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* 3 új parancsmag hozzáadva a tűzfalszabályok esetében
* 3 új parancsmag hozzáadva a georeplikáció esetében
* További támogatás a zónák és a címkék esetében
* A ResourceGroup opcionálissá tétele, amikor csak lehetséges.

#### <a name="azurermrelay"></a>AzureRM.Relay
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermresources"></a>AzureRM.Resources
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* -AsJob támogatás hozzáadva a sokáig futó Resources-parancsmagok számára. Lehetővé teszi, hogy a kiválasztott parancsmagok a háttérben fussanak, és visszaad egy feladatot, amely nyomon követi és szabályozza az előrehaladást.
* Alias hozzáadva a Get-AzureRmProviderOperation parancsmagból a Get-AzureRmResourceProviderAction parancsmaghoz az elnevezési konvenciók teljesülése érdekében

#### <a name="azurermscheduler"></a>AzureRM.Scheduler
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermservermanagement"></a>AzureRM.ServerManagement
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A -Tags paraméter elavulttá tétele a -Tag paraméter használata érdekében a New-AzureRmServerManagementNode és a New-AzureRmServerManagementGateway parancsmagok esetében

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermsiterecovery"></a>AzureRM.SiteRecovery
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermsql"></a>AzureRM.Sql
* A naplózási parancsok paraméter-leírásának frissítése
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* -AsJob paraméter hozzáadva a sokáig futó parancsmagokhoz
* A -DatabaseName paraméter elavulttá tétele a Get-AzureRmSqlServiceObjective parancsmagban

#### <a name="azurermstorage"></a>AzureRM.Storage
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* A New-AzureRMStorageAccount parancsmag -EnableEncryptionService None paraméterrel történő futtatásakor jelentkező „null értékű hivatkozás” hiba kijavítása
* -AsJob támogatás hozzáadva a sokáig futó Storage-parancsmagok számára. Lehetővé teszi, hogy a kiválasztott parancsmagok a háttérben fussanak, és visszaad egy feladatot, amely nyomon követi és szabályozza az előrehaladást.
    - Érintett parancsmagok: A Storage-fiók és a Storage-fiók hálózati szabályainak New-, Remove-, Add- és Update-parancsmagjai.

#### <a name="azurermstreamanalytics"></a>AzureRM.StreamAnalytics
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermtrafficmanager"></a>AzureRM.TrafficManager
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben

#### <a name="azurermwebsites"></a>AzureRM.Websites
* A -Location paraméterekhez hozzáadott Location Completer lehetővé teszi a parancssori kiegészítési funkció érvényes helyeken keresztül történő használatát
* A -ResourceGroup paraméterekhez hozzáadott ResourceGroup Completer lehetővé teszi a parancssori kiegészítési funkció erőforráscsoportokon keresztül történő használatát az aktuális előfizetésben
* -AsJob támogatás hozzáadva a sokáig futó Websites-parancsmagok számára. Lehetővé teszi, hogy a kiválasztott parancsmagok a háttérben fussanak, és visszaad egy feladatot, amely nyomon követi és szabályozza az előrehaladást.
     - Érintett parancsmagok: A WebApps, az AppServicePlan és a Slots New-, Remove-, Add- és Set-parancsmagjai

## <a name="2017128-version-511"></a>2017.12.8. – 5.1.1-es verzió
* AnalysisServices
    - Az érvényesítés helykészletének dinamikus keresésre való módosítása, hogy az összes felhőt támogassa.
* Automatizálás
    - Frissítés a következőre: Import-AzureRMAutomationRunbook
        - Mostantól támogatás érhető el a Python2-runbookokhoz
* Batch
    - Ki lett javítva az a hiba, amely miatt az erőforráscsoport nélküli fiókműveletek nem tudták automatikusan észlelni az erőforráscsoportot
* Számítás
    - A Get-AzureRmComputeResourceSku parancsmag megjeleníti az időzónával kapcsolatos információkat.
    - A Disable-AzureRmVmssDiskEncryption parancsmag frissült az alábbi hiba javítása érdekében: https://github.com/Azure/azure-powershell/issues/5038
    - -AsJob támogatás hozzáadva a sokáig futó Compute parancsmagok számára. Lehetővé teszi, hogy a kiválasztott parancsmagok a háttérben fussanak, és visszaad egy feladatot, amely nyomon követi és szabályozza az előrehaladást.
        - Érintett parancsmagok: A virtuális gépek és virtuálisgép-méretezési csoportok New-, Update-, Set-, Remove-, Start-, Restart-, és Stop- parancsmagjai
    - Egyszerűsített paraméterkészlet hozzáadva a New-AzureRmVM parancsmaghoz, amely az intelligens alapértelmezett beállítások használatával létrehoz egy virtuális gépet és az összes szükséges erőforrást
* ContainerInstance
    - Az Azure Container Instance SDK 2017-10-01 alkalmazása
        - A tárolók befejezésig való futtatásának támogatása
        - Azure File kötetcsatlakoztatás támogatása
        - Több port megnyitásának támogatása a nyilvános IP-címek számára
* ContainerRegistry
    - Új parancsmagok a georeplikáció és a webhookok számára
        - Get/New/Remove-AzureRmContainerRegistryReplication
        - Get/New/Remove/Test/Update-AzureRmContainerRegistryWebhook
* DataFactories
    - A hitelesítő adatok titkosítása funkció mostantól engedélyezett „Távoli hozzáférés” (hálózaton keresztül) és letiltott „Távoli hozzáférés” (helyi számítógép) esetén is működik.
* DataFactoryV2
    - Két új parancsmag hozzáadva: Update-AzureRmDataFactoryV2 és Stop-AzureRmDataFactoryV2PipelineRun
* DataLakeAnalytics
    - A ScriptParameter nevű paraméter hozzá lett adva a Submit-AzureRmDataLakeAnalyticsJob parancsmaghoz
        - A ScriptParameter paraméterről részletes információkat a Get-Help Submit-AzureRmDataLakeAnalyticsJob parancsmagon való használatával találhat
    - A New-AzureRmDataLakeAnalyticsAccount parancsmag esetében a MaxDegreeOfParallelism paraméter a MaxAnalyticsUnits paraméterre módosult
        - Alias hozzáadva a MaxAnalyticsUnits paraméterhez: MaxDegreeOfParallelism
    - A New-AzureRmDataLakeAnalyticsComputePolicyt parancsmag esetében a MaxDegreeOfParallelismPerJob paraméter a MaxAnalyticsUnitsPerJob paraméterre módosult
        - Alias hozzáadva a MaxAnalyticsUnitsPerJob paraméterhez: MaxDegreeOfParallelismPerJob
    - A Set-AzureRmDataLakeAnalyticsAccount parancsmag esetében a MaxDegreeOfParallelism paraméter a MaxAnalyticsUnits paraméterre módosult
        - Alias hozzáadva a MaxAnalyticsUnits paraméterhez: MaxDegreeOfParallelism
    - A Submit-AzureRmDataLakeAnalyticsJob parancsmag esetében a DegreeOfParallelism paraméter az AnalyticsUnits paraméterre módosult
        - Alias hozzáadva az AnalyticsUnits paraméterhez: DegreeOfParallelism
    - Az Update-AzureRmDataLakeAnalyticsComputePolicy parancsmag esetében a MaxDegreeOfParallelismPerJob paraméter a MaxAnalyticsUnitsPerJob paraméterre módosult
        - Alias hozzáadva a MaxAnalyticsUnitsPerJob paraméterhez: MaxDegreeOfParallelismPerJob
* MachineLearningCompute
    - Set-AzureRmMlOpCluster parancsmag hozzáadása
        - Frissíti egy fürt ügynökeinek számát vagy az SSL-konfigurációt
    - A vezénylőtulajdonságok nem kötelezőek
        - Ha nincs megadva, a szolgáltatás létre fog hozni egy egyszerű szolgáltatást, így a vezénylőtulajdonságok mostantól nem kötelezőek
* PowerBIEmbedded
    - Támogatás hozzáadása a Power BI Embedded-kapacitások parancsmagjaihoz
    - Új Get-AzureRmPowerBIEmbeddedCapacity parancsmag – Lekéri a Power BI Embedded-kapacitás részleteit.
    - Új New-AzureRmPowerBIEmbeddedCapacity parancsmag – Létrehoz egy új Power BI Embedded-kapacitást
    - Új Remove-AzureRmPowerBIEmbeddedCapacity parancsmag – Töröl egy Power BI Embedded-kapacitáspéldányt
    - Új Resume-AzureRmPowerBIEmbeddedCapacity parancsmag – Folytatja egy Power BI Embedded-kapacitáspéldány használatát
    - Új Suspend-AzureRmPowerBIEmbeddedCapacity parancsmag – Felfüggeszt egy Power BI Embedded-kapacitáspéldányt
    - Új Test-AzureRmPowerBIEmbeddedCapacity parancsmag – Teszteli, hogy létezik-e Power BI Embedded-kapacitáspéldány
    - Új Update-AzureRmPowerBIEmbeddedCapacity parancsmag – Módosít egy Power BI Embedded-kapacitáspéldányt
* Profil
    - USGovernmentActiveDirectoryEndpoint frissítve a következőre: https://login.microsoftonline.us/
        - Az Azure Government végpontleképezéseivel kapcsolatos további információkért tekintse meg az alábbi hivatkozást: https://docs.microsoft.com/en-us/azure/azure-government/documentation-government-developer-guide#endpoint-mapping
    - -AsJob támogatás hozzáadva a parancsmagokhoz, amely lehetővé teszi, hogy a kiválasztott parancsmagok a háttérben fussanak, és visszaad egy feladatot, amely nyomon követi és szabályozza az előrehaladást
    - -AsJob paraméter hozzáadva a Get-AzureRmSubscription parancsmaghoz
* RecoveryServices.Backup
    - Hiba kijavítva – A Get-AzureRmRecoveryServicesBackupItem mostantól a kis- és nagybetűket megkülönböztető összehasonlítást végez a tárolónévszűrőnél.
    - Hiba kijavítva – Az AzureVmItem mostantól rendelkezik egy olyan tulajdonsággal, amely megjeleníti, mikor történt a legutóbbi biztonsági mentési művelet – LastBackupTime.
* További források
    - Ki lett javítva az a hiba, amely miatt a Get-AzureRMRoleAssignment parancsmag olyan hozzárendeléseket eredményezett, amelyekben nem tartozott szerepkördefiníció-név az egyéni szerepkörökhöz
        - A felhasználók mostantól a szerepkörtípustól függetlenül használhatják a Get-AzureRMRoleAssignment parancsmagot a szerepkördefiníció-névvel rendelkező hozzárendelésekkel
    - Ki lett javítva az a hiba, amely miatt a Set-AzureRMRoleRoleDefinition parancsmag „RD nem található” hibát jelzett, amikor az „assignablescopes” új hatókört tartalmazott
        - A felhasználók mostantól a hatókör pozíciójától függetlenül használhatják a Set-AzureRMRoleRoleDefinition parancsmagot a hozzárendelhető hatókörökkel, az új hatóköröket is beleértve
    - A „/” végződés engedélyezése a hatóköröknél
        - A felhasználók mostantól az API-val és a parancssori felülettel összhangban a „/” végződéssel rendelkező hatókörökkel is használhatják a RoleDefinition és a RoleAssignment parancsmagokat
    - RoleAssignment delegálási jelző használata nélküli létrehozásának engedélyezése a felhasználók számára
        - A felhasználók mostantól egy delegálási jelző hozzáadásának lehetőségével használhatják a New-AzureRMRoleAssignment parancsmagot
    - Javítás: A RoleAssignment mostantól figyelembe veszi a hatókör-paramétert
    - Alias hozzáadása a New-AzureRmRoleAssignment parancsmag ServicePrincipalName paraméteréhez
        - A felhasználók mostantól a New-AzureRmRoleAssignment parancsmag használatakor a ServicePrincipalName helyett használhatják az ApplicationId paramétert
* SiteRecovery
    - Elavulással kapcsolatos figyelmeztetések hozzáadása a modul összes parancsmagjához a következő használhatatlanná tévő változást tartalmazó kiadás előkészítéséhez.
        - A parancsmagok AzureRM-ből való migrálásával kapcsolatos további információkért tekintse meg a soron következő használhatatlanná tévő változások útmutatóját.
* SQL
    - Mostantól át lehet nevezni az adatbázisokat a Set-AzureRmSqlDatabase parancsmag használatával
    - Hiba kijavítva: https://github.com/Azure/azure-powershell/issues/4974
        - A naplózási parancsmagoknál az érvénytelen AUDIT_CHANGED_GROUP érték megadása többé nem eredményez hibát, és egy soron következő kiadásban el lesz távolítva.
    - Hiba kijavítva: https://github.com/Azure/azure-powershell/issues/5046
        - A rendszer többé nem hagyja figyelmen kívül a naplózási parancsmagok AuditAction paraméterét
    - Ki lett javítva a hiba a naplózási parancsmagok „Másodlagos” StorageKeyType paraméterének megadásánál
        - A blobnaplózás beállításakor a StorageKeyType paraméter „Másodlagos” értékének megadásánál a rendszer az elsődleges tárfiókkulcsot használta a másodlagos kulcs helyett.
    - A Set-AzureRmSqlServerTransparentDataEncryptionProtector parancsmagtól érkező megerősítő üzenet szövegének megváltoztatása
* Azure (RDFE)
    - RemoteApp parancsmagok eltávolítva
* Azure.Storage
    - Frissítés az Azure Storage ügyféloldali kódtárának 8.6.0-s és az Azure Storage adatátviteli kódtárának 0.6.5-ös verziójára

## <a name="20171110-version-501"></a>2017.11.10. – 5.0.1-es verzió
* Kijavítottuk a szerelvénybetöltési hibát, amely egyes parancsmagok sikertelen futtatását okozta az alábbi modulokban történő végrehajtás során:
    - AzureRM.ApiManagement
    - AzureRM.Backup
    - AzureRM.Batch
    - AzureRM.Compute
    - AzureRM.DataFactories
    - AzureRM.HDInsight
    - AzureRM.KeyVault
    - AzureRM.RecoveryServices
    - AzureRM.RecoveryServices.Backup
    - AzureRM.RecoveryServices.SiteRecovery
    - AzureRM.RedisCache
    - AzureRM.SiteRecovery
    - AzureRM.Sql
    - AzureRM.Storage
    - AzureRM.StreamAnalytics

## <a name="2017118---version-500"></a>2017.11.8. – 5.0.0-s verzió
* Megjegyzés: Ez egy használhatatlanná tévő változást tartalmazó kiadás. A bevezetett használhatatlanná tévő változások teljes listájához tekintse meg a migrálási útmutatót (https://aka.ms/azps-migration-guide).
* Mostantól az AzureRM összes parancsmagja támogatja az online súgó használatát
    - Futtassa a Get-Help parancsmagot -Online paraméterrel az online súgónak az alapértelmezett böngészőben történő megnyitásához
* AnalysisServices
    * A Synchronize-AzureAsInstance mostantól működik az új AsAzure szinkronizálási REST API-val
* ApiManagement
    * A jelen kiadás keretében az ApiManagement parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
    * A Get-AzureRmApiManagementUser parancsmag frissítve az alábbi hiba javítása érdekében: https://github.com/Azure/azure-powershell/issues/4510
    * A New-AzureRmApiManagementApi parancsmag frissítve üres elérési útvonallal rendelkező API létrehozásához: https://github.com/Azure/azure-powershell/issues/4069
* ApplicationInsights
    * Parancsok hozzáadása Application Insights-erőforrások lekérdezéséhez/létrehozásához/eltávolításához
        - Get-AzureRmApplicationInsights
        - New-AzureRmApplicationInsights
        - Remove-AzureRmApplicationInsights
    * Parancsok hozzáadása az Application Insights-erőforrások díjszabásának és napi maximális értékének lekérdezéséhez/frissítéséhez
        - Get-AzureRmApplicationInsights -IncludeDailyCap
        - Set-AzureRmApplicationInsightsPricingPlan
        - Set-AzureRmApplicationInsightsDailyCap
    * Parancsok hozzáadása az Application Insights-erőforrások folyamatos exportálásának lekérdezéséhez/létrehozásához/frissítéséhez/eltávolításához
        - Get-AzureRmApplicationInsightsContinuousExport
        - Set-AzureRmApplicationInsightsContinuousExport
        - New-AzureRmApplicationInsightsContinuousExport
        - Remove-AzureRmApplicationInsightsContinuousExport
    * Parancsok hozzáadása az Application Insights-erőforrások API-kulcsainak lekérdezéséhez/létrehozásához/eltávolításához
        - Get-AzureRmApplicationInsightsApiKey
        - New-AzureRmApplicationInsightsApiKey
        - Remove-AzureRmApplicationInsightsApiKey
* AzureBatch
    * Új paraméterek hozzáadva a következőhöz: `New-AzureRmBatchAccount`.
        - `PoolAllocationMode`: Készletek a Batch-fiókban történő létrehozásához használandó lefoglalási mód. Ha olyan Batch-fiókot szeretne létrehozni, amely lefoglalja a készletcsomópontokat a felhasználó előfizetésében, állítsa `UserSubscription` értékre.
        - `KeyVaultId`: A Batch-fiókhoz társított Azure Key Vault erőforrás-azonosítója.
        - `KeyVaultUrl`: A Batch-fiókhoz társított Azure Key Vault URL-címe.
    * Paraméterek frissítve a következő esetében: `New-AzureBatchTask`.
        - A `RunElevated` kapcsoló eltávolítva. A `UserIdentity` paraméter hozzáadva a `RunElevated` helyett, az egyenértékű viselkedés pedig egy `PSUserIdentity` felépítésével érhető el, az alábbi módon:
            - $autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
            - $userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
        - A következő paraméter hozzáadva: `AuthenticationTokenSettings`. Ez a paraméter lehetővé teszi a Batch szolgáltatás felkérését arra, hogy biztosítson egy hitelesítési tokent a feladat számára annak futtatásakor. Így nincs szükség a Batch-fiók kulcsainak átadására a feladat számára, hogy az kéréseket küldhessen a Batch szolgáltatásnak.
        - A következő paraméter hozzáadva: `ContainerSettings`.
            - Ez a paraméter lehetővé teszi, hogy felkérje a Batch szolgáltatást a feladat tárolóban történő futtatására.
        - A következő paraméter hozzáadva: `OutputFiles`.
            - Ez a paraméter lehetővé teszi, hogy úgy konfigurálja a feladatot, hogy az fájlokat töltsön fel az Azure Storage-ba, miután befejeződött.
    * Paraméterek frissítve a következő esetében: `New-AzureBatchPool`.
        - A következő paraméter hozzáadva: `UserAccounts`.
            - Ez a paraméter a készlet egyes csomópontjain létrehozott felhasználói fiókokat definiálja.
        - `TargetLowPriorityComputeNodes` hozzáadva, `TargetDedicated` átnevezve a következőre: `TargetDedicatedComputeNodes`.
            - Egy `TargetDedicated` alias létrehozva a következő paraméterhez: `TargetDedicatedComputeNodes`.
        - A következő paraméter hozzáadva: `NetworkConfiguration`.
            - Ez a paraméter lehetővé teszi a készletek hálózati beállításainak konfigurálását.
    * Paraméterek frissítve a következő esetében: `New-AzureBatchCertificate`.
        - A `Password` paraméter mostantól `SecureString`.
    * Paraméterek frissítve a következő esetében: `New-AzureBatchComputeNodeUser`.
        - A `Password` paraméter mostantól `SecureString`.
    * Paraméterek frissítve a következő esetében: `Set-AzureBatchComputeNodeUser`.
        - A `Password` paraméter mostantól `SecureString`.
    * A `Name` paraméter átnevezve erre: `Path` a `Get-AzureBatchNodeFile`, `Get-AzureBatchNodeFileContent` és `Remove-AzureBatchNodeFile` esetében.
        - Egy `Name` alias létrehozva a következő paraméterhez: `Path`.
    * Objektumokat érintő változások
        - A teljes listáért tekintse meg a Batch változásnaplóját
    * Támogatás hozzáadva az Azure Active Directory-alapú hitelesítéshez.
        - Az Azure Active Directory-hitelesítés használatához kérjen le egy `BatchAccountContext` objektumot a `Get-AzureRmBatchAccount` parancsmag használatával, majd adja meg a `BatchAccountContext` paramétert egy Batch szolgáltatás parancsmagjának `-BatchContext` paraméteréhez. Az Azure Active Directory-hitelesítés kötelező a `PoolAllocationMode = UserSubscription` lefoglalási móddal rendelkező fiókok esetében.
        - A meglévő vagy a `PoolAllocationMode = BatchService` használatával létrehozott új fiókok esetében továbbra is használhat megosztott kulcsos hitelesítést, ha lekér egy `BatchAccountContext` objektumot a `Get-AzureRmBatchAccoutKeys` parancsmag segítségével.
* Számítás
    * Az Azure Disk Encryption bővítmény parancsai
        - A 'Set-AzureRmVmDiskEncryptionExtension’ parancs új paramétere, az '-EncryptFormatAll’ titkosított módon formázza az adatlemezeket
        - A 'Set-AzureRmVmDiskEncryptionExtension' parancs új paraméterei, az '-ExtensionPublisherName' és '-ExtensionType’ lehetővé teszik a bővítmény másik verziójára történő váltást
        - A 'Disable-AzureRmVmDiskEncryption' parancs új paraméterei, az '-ExtensionPublisherName' és '-ExtensionType’ lehetővé teszik a bővítmény másik verziójára történő váltást
        - A 'Get-AzureRmVmDiskEncryptionStatus' parancs új paraméterei, az '-ExtensionPublisherName' és '-ExtensionType’ lehetővé teszik a bővítmény másik verziójára történő váltást
* DataLakeAnalytics
    * A jelen kiadás keretében a DataLakeAnalytics parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
    * A Get-AzureRmDataLakeAnalyticsAccount egyik OutputType paramétere módosítva
        - Erről: List\<DataLakeAnalyticsAccount>, erre: List\<PSDataLakeAnalyticsAccountBasic>
        - A PSDataLakeAnalyticsAccountBasic tulajdonságai a DataLakeAnalyticsAccount tulajdonságainak egy szigorú alkészletéből állnak
        - A DataLakeAnalyticsAccount paraméterben található további tulajdonságokat nem adja vissza a szolgáltatás.  A változtatás célja tehát ennek pontos megjelenítése. Ezek a további tulajdonságok továbbra is megtalálhatók a PSDataLakeAnalyticsAccountBasic paraméterben, de Obsolete (Elavult) címkével vannak ellátva.
    * A Get-AzureRmDataLakeAnalyticsJob egyik OutputType paramétere módosítva
        - Erről: List\<JobInformation>, erre List\<PSJobInformationBasic>
        - A PSJobInformationBasic tulajdonságai a JobInformation tulajdonságainak egy szigorú alkészletéből állnak
        - A JobInformation paraméterben található további tulajdonságokat nem adja vissza a szolgáltatás.  A változtatás célja tehát ennek pontos megjelenítése. Ezek a további tulajdonságok továbbra is megtalálhatók a PSJobInformationBasic paraméterben, de Obsolete (Elavult) címkével vannak ellátva.
* DataLakeStore
    * A jelen kiadás keretében a DataLakeStore parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
    * A Get-AzureRmDataLakeStoreAccount egyik OutputType paramétere módosítva
        - Erről: List\<PSDataLakeStoreAccount>, erre: List\<PSDataLakeStoreAccountBasic>
        - A PSDataLakeStoreAccountBasic tulajdonságai a PSDataLakeStoreAccount tulajdonságainak egy szigorú alkészletéből állnak
        - A PSDataLakeStoreAccount paraméterben található további tulajdonságokat nem adja vissza a szolgáltatás.  A változtatás célja tehát ennek pontos megjelenítése. Ezek a további tulajdonságok továbbra is megtalálhatók a PSDataLakeStoreAccountBasic paraméterben, de Obsolete (Elavult) címkével vannak ellátva.
* DNS
    * A CAA-rekordtípusok támogatása az Azure DNS szolgáltatásban
       - A CAA-rekordtípuson elvégzett összes műveletet támogatja
* EventHub
    * A jelen kiadás keretében az EventHub parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
* Insights
    * A jelen kiadás keretében az Insights parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
* Network (Hálózat)
    * A jelen kiadás keretében a Network parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
    * Parancsmag hozzáadva az egyes Azure-régiókban elérhető internetszolgáltatók felsorolásához
        - Get-AzureRmNetworkWatcherReachabilityProvidersList
    * Parancsmag hozzáadva az internetszolgáltatók egy adott hely és az Azure-régiók közötti relatív késési pontszámának lekéréséhez
        - Get-AzureRmNetworkWatcherReachabilityReport
* Profil
    - Set-AzureRmDefault
        - A parancsmag használatával alapértelmezett erőforráscsoportot adhat meg.  Ennek következtében a -ResourceGroup nem lesz kötelező egyes parancsmagok esetében, és ha nincs erőforráscsoport megadva, a parancs az alapértelmezést használja majd
        - ```Set-AzureRmDefault -ResourceGroupName "ExampleResourceGroup"```
        - Ha van megadott erőforráscsoport az előfizetésben, az lesz alapértelmezettként beállítva.  Ellenkező esetben a rendszer létrehozza az erőforráscsoportot, majd beállítja alapértelmezettként.
    - Get-AzureRmDefault
        - A parancsmag használatával lekérdezheti az aktuális alapértelmezett erőforráscsoportot (és egyéb alapértelmezéseket is a jövőben).
        - ```Get-AzureRmDefault -ResourceGroup```
    - Clear-AzureRmDefault
        - A parancsmag használatával eltávolíthatja az aktuális alapértelmezett erőforráscsoportot
        - ```Clear-AzureRmDefault -ResourceGroup```
    - Add-AzureRmEnvironment és Set-AzureRmEnvironment
        - A BatchAudience paraméter hozzáadása lehetővé teszi az Azure Batch Active Directory célközönségének megadását, amelyet a hitelesítési tokeneknek a Batch szolgáltatás számára történő beszerzésekor kíván használni.
* RecoveryServices.Backup
    * Parancsmagok hozzáadva azonnali fájlhelyreállítás végrehajtásához.
        - Get-AzureRmRecoveryServicesBackupRPMountScript
        - Disable-AzureRmRecoveryServicesBackupRPMountScript
    * A RecoveryServices.Backup SDK frissítve a legújabb verzióra
    * Az Azure virtuális gép számítási feladatainak tesztje frissítve, hogy a tesztek futtatásához szükséges beállításokat maguk a tesztek végezzék el.
    * Ez a következőt javítja ki: https://github.com/Azure/azure-powershell/issues/3164
* RecoveryServices.SiteRecovery
    * Az ASR VMware–Azure Site Recovery változásai (a parancsmagok jelenleg az Enterprise–Enterprise, Enterprise–Azure és HyperV–Azure műveleteket támogatják)
        - New-AzureRmRecoveryServicesAsrPolicy
        - New-AzureRmRecoveryServicesAsrProtectedItem
        - Update-AzureRmRecoveryServicesAsrPolicy
        - Update-AzureRmRecoveryServicesAsrProtectionDirection
    * Támogatás hozzáadva az AAD-alapú tárolóhoz
    * Parancsmagok hozzáadva a VCenter-erőforrások kezeléséhez
        - Get-AzureRmRecoveryServicesAsrVCenter
        - New-AzureRmRecoveryServicesAsrVCenter
        - Remove-AzureRmRecoveryServicesAsrVCenter
        - Update-AzureRmRecoveryServicesAsrVCenter
    * Egyéb parancsmagok hozzáadva
        - Get-AzureRmRecoveryServicesAsrAlertSetting
        - Get-AzureRmRecoveryServicesAsrEvent
        - New-AzureRmRecoveryServicesAsrProtectableItem
        - Set-AzureRmRecoveryServicesAsrAlertSetting
        - Start-AzureRmRecoveryServicesAsrResynchronizeReplicationJob
        - Start-AzureRmRecoveryServicesAsrSwitchProcessServerJob
        - Start-AzureRmRecoveryServicesAsrTestFailoverCleanupJob
        - Update-AzureRmRecoveryServicesAsrMobilityService
* ServiceBus
    - A jelen kiadás keretében a ServiceBus parancsban történt használhatatlanná tévő változásokért tekintse meg a migrálási útmutatót
* SQL
    * Támogatás hozzáadása az aszinkron updateslo művelet listázásához és megszakításához az adatbázison
        - a meglévő Get-AzureRmSqlDatabaseActivity parancsmag frissítése, hogy visszaadja az adatbázis updateslo műveletének állapotát.
        - új Stop-AzureRmSqlDatabaseActivity hozzáadása az aszinkron updateslo művelet megszakításához az adatbázison.
    * A Zone Redudancy támogatásának hozzáadása adatbázisok és rugalmas készletek esetében
        - Új kapcsolóparaméter (ZoneRedundant) hozzáadása a New-AzureRmSqlDatabase parancsmaghoz
        - Új kapcsolóparaméter (ZoneRedundant) hozzáadása a Set-AzureRmSqlDatabase parancsmaghoz
        - Új kapcsolóparaméter (ZoneRedundant) hozzáadása a New-AzureRmSqlElasticPool parancsmaghoz
        - Új kapcsolóparaméter (ZoneRedundant) hozzáadása a Set-AzureRmSqlElasticPool parancsmaghoz
    * Támogatás hozzáadása a kiszolgálói DNS-aliasok számára
        - A Get-AzureRmSqlServerDnsAlias parancsmag hozzáadása, amely lekérdezi a kiszolgálói DNS-aliasokat a kiszolgálók és aliasok neve szerint, vagy egy Azure SQL-kiszolgáló kiszolgálói DNS-aliasainak listáját.
        - A New-AzureRmSqlServerDnsAlias parancsmag hozzáadása, amely létrehoz egy új kiszolgálói DNS-aliast egy adott Azure SQL-kiszolgáló számára
        - A Set-AzurermSqlServerDnsAlias parancsmag hozzáadása, amely lehetővé teszi azon Azure SQL-kiszolgáló frissítését, amelyre a kiszolgálói DNS-alias mutat
        - A Remove-AzureRmSqlServerDnsAlias parancsmag hozzáadása, amely eltávolítja egy adott Azure SQL-kiszolgáló egy kiszolgálói DNS-aliasát
* Azure.Storage
    * Frissítés az Azure Storage ügyféloldali kódtárának 8.5.0-s és az Azure Storage adatátviteli kódtárának 0.6.3-as verziójára
    * Fájlmegosztási pillanatkép támogatásának hozzáadása
        - 'SnapshotTime’ hozzáadva a Get-AzureStorageShare parancsmaghoz
        - 'IncludeAllSnapshot’ hozzáadva a Remove-AzureStorageShare parancsmaghoz
