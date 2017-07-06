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
ms.date: 05/18/2017
ms.openlocfilehash: 97a23180a1fc65d96fdc9dbdffcbe3501a4c4c2a
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2017
---
# <a name="release-notes"></a>Kibocsátási megjegyzések

Az alábbiakban az Azure PowerShell jelen kiadásában végrehajtott módosítások listája olvasható.

## <a name="version-400"></a>4.0.0-s verzió

* Ez a kiadás jelentős változásokat tartalmaz. A változás részleteit és a meglévő szkriptekre gyakorolt hatást [a migrálási útmutatóban](https://aka.ms/azps-migration-guide) találja.
* ApiManagement
  - Külső csoportok konfigurálásának támogatása a New-AzureRmApiManagementGroup parancsmagban.
* Számlázás
  - Új Get-AzureRmBillingPeriod parancsmag
    + az Azure-előfizetés elszámolási időszakainak beolvasásához.
  - Módosult a Get-AzureRmBillingInvoice parancsmag
  - Új BillingPeriodNames tulajdonság
  - Kimenet listanézetben
* Számítás
  - A módosult Set-AzureRmVMAEMExtension és Test-AzureRmVMAEMExtension parancsmagok támogatják a prémium szintű Managed Disks szolgáltatást
  - Az IaaS VM-ek titkosítási beállításainak biztonsági mentése; hiba esetén visszaállítása
  - A ChefServiceInterval beállítás új neve mostantól ChefDaemonInterval, de a régi név is használható.
  - A duplikált DataDiskNames és NetworkInterfaceIDs tulajdonságok el lettek távolítva a PS VM-objektumából.
  - A DataDiskNames és a NetworkInterfaceIDs paraméterek mostantól nem kötelezőek a Remove-AzureRmVMDataDisk és a Remove-AzureRmVMNetworkInterface parancsmagban.
  - Kijavítottuk a Get parancsmagok átirányítását listaobjektum visszaadásakor.
  - Az RDFE-parancsmagokkal ütköző parancsmagok új nevet kaptak. További részletek: https://github.com/Azure/azure-powershell/issues/2917
    + A `New-AzureVMSqlServerAutoBackupConfig` új nevet kapott: `New-AzureRmVMSqlServerAutoBackupConfig`
    + A `New-AzureVMSqlServerAutoPatchingConfig` új nevet kapott: `New-AzureRmVMSqlServerAutoPatchingConfig`
    + A `New-AzureVMSqlServerKeyVaultCredentialConfig` új nevet kapott: `New-AzureRmVMSqlServerKeyVaultCredentialConfig`
* Használat
  - Új Get-AzureRmConsumptionUsageDetail parancsmag
    + az előfizetés használati adatainak beolvasásához.
* ContainerRegistry
  - Új PowerShell-parancsmagok az Azure Container Registry szolgáltatásban
    + New-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistry
    + Update-AzureRmContainerRegistry
    + Remove-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistryCredential
    + Update-AzureRmContainerRegistryCredential
    + Test-AzureRmContainerRegistryNameAvailability
* DataLakeAnalytics
  - A katalóguscsomag beolvasásának és listázásának támogatása
  - Az alábbi katalóguselemek mélyebb szintű elődökből való listázásának támogatása:
    + Tábla
    + TVF
    + Nézet
    + Statisztika
* DataLakeStore
  - Az `Import-AzureRMDataLakeStoreItem` és az `Export-AzureRMDataLakeStoreItem` nyomkövetési naplózása alapértelmezés szerint le lett tiltva a teljesítmény javítása céljából. Ha nyomkövetési naplózásra van szükség, használja a `-DiagnosticLogLevel` és a `-DiagnosticLogPath` paramétereket
  - Kijavítottunk egy, nagy mennyiségű kis fájl ADLS-be való feltöltésekor a PowerShell összeomlását okozó hibát.
* EventHub
  - Hibajavítás:
    + Kijavítottunk egy hibát a Set-AzureRmEventHubNamespace parancsmagban (a Tier értéke SkuName helyett nem lehet null)
    + Set-AzureRmEventHub – kijavítottuk az EventHub frissítésekor jelentkező „Az objektumhivatkozás nincs beállítva az objektum egyik példányára” hibát
* Insights
  - Add-AzureRm*AlertRule
    + Egyetlen objektumot ad vissza: newResource, statusCode, requestId
  - Get-AzureRmAlertRule
    + A kimenet mostantól enumerált, és nem egyetlen objektumnak számít. A típus nem változott, továbbra is listának minősül.
  - Remove-AzureRmAlertRule
    + A statusCode a kérelem által visszaadott állapotkódot követi – korábban mindig OK értékű volt.
  - Add-AzureRmAutoscaleSetting
    + Egyetlen objektumot ad vissza (nem pedig egy listát, mint korábban), amelyben szerepel az állapotkód, a kérés azonosítója és az újonnan létrehozott vagy módosított erőforrás.
    + A statusCode a kérelem által visszaadott állapotot követi – korábban mindig OK értékű volt.
  - New-AzureRmAutoscaleRule
    + A ScaleActionType paraméter ki lett bővítve, mostantól megkapja a következő értékeket: ChangeCount, PercentChangeCount, ExactCount.
  - Remove-AzureRmAutoscaleSetting
    + A kimenetben szereplő statusCode a kérelem által visszaadott statusCode értéket követi. Korábban mindig OK értékű volt.
  - Get-AzureRMLogProfile
    + A kimenet mostantól enumerált, míg korábban egyetlen objektumnak számított. A kimenet típusa nem változott, továbbra is listának minősül.
  - Remove-AzureRmLogProfile
    + Implementáltuk a PassThru paramétert.
  - Metrikák API
    + Az SDK mostantól az MDM-től kéri le a metrikákat.
  - Get-AzureRmMetricDefinition
    + A kimenet továbbra is listának minősül, de a lista szerkezete megváltozott.
  - Get-AzureRmMetric
    + A hívás megváltozott. Az új szintaxis: Get-AzureRmMetric ResourceId [MetricNames [TimeGrain] [AggregationType] [StartTime] [EndTime]] [DetailedOutput]
    + A kimenet listának minősül, és az elemek szerkezete megváltozott.
* KeyVault
  - A KeyVault titkos kódjai támogatják a biztonsági mentést/visszaállítást
    + Biztonsági másolat készíthető a titkos kódokról, és vissza lehet állítani azokat – ugyanúgy, ahogy eddig a kulcsokat

  - A kulcsok és a titkos kódok biztonsági mentési parancsmagjai mostantól bemeneti paraméterként fogadják a megfelelő objektumokat
    + A hívó elvégezheti a lekérési és a biztonsági mentési műveletek láncolását: Get-AzureKeyVaultKey -VaultName myVault -Name myKey | Backup-AzureKeyVaultKey

  - A biztonsági mentési parancsmagok mostantól támogatják a -Force kapcsolót, amellyel elvégezhető egy korábbi fájl felülírása
    + Ne feledje, hogy a korábbi fájlok felülírási kísérletére a rendszer mostantól nem dob hibát, ehelyett arra fogja kérni a felhasználót, hogy válasszon egy folytatási lehetőséget.
* LogicApp
  - Az adatcsere ellenőrzőszámához tartozó vészhelyreállítási parancsmagok új paraméterei:
    + A nem kötelező -AgreementType paraméterrel (X12 vagy Edifact) lehet megadni a megfelelő ellenőrzőszámokat
* Machine Learning
  - A szolgáltatás az Azure Machine Learning .Net SDK új verzióját használja, és egy új parancsmag is elérhető benne
    + Add-AzureRmMlWebServiceRegionalProperty
  - Kisebb fogalmazási hibákat javítottunk a súgószövegben.
* Network (Hálózat)
  - Új parancsmag: Test-AzureRmNetworkWatcherConnectivity
    + A forrásként és célként megadott virtuális gép összekapcsolhatósági adatait adja vissza
    + Ha a forrás és a cél közötti kapcsolatot nem lehet létrehozni, a parancsmag a probléma részleteit adja vissza
* Profil
  - Az új Send-Feedback parancsmaggal a felhasználók az Azure PowerShell csapatának visszajelzést küldő rendszerüzeneteket kezdeményezhetnek.
  - Az alábbi aliasokat eltávolítottuk, mert az Azure modulban meglévő parancsmagok neveivel ütköztek:
    + `Enable-AzureDataCollection` (az `Enable-AzureRmDataCollection` támogatta)
    + `Disable-AzureDataCollection` (a `Disable-AzureRmDataCollection` támogatta)
* Továbbító
  - Az új Azure Relay-parancsmagokkal a felhasználók az összes Azure Relay-erőforrás létrehozását és kezelését elvégezhetik.
    + `New-AzureRmRelayNamespace`
    + `Get-AzureRmRelayNamespace`
    + `Set-AzureRmRelayNamespace`
    + `Remove-AzureRmRelayNamespace`
    + `New-AzureRmWcfRelay`
    + `Get-AzureRmWcfRelay`
    + `Set-AzureRmWcfRelay`
    + `Remove-AzureRmWcfRelay`
    + `New-AzureRmRelayHybridConnection`
    + `Get-AzureRmRelayHybridConnection`
    + `Set-AzureRmRelayHybridConnection`
    + `Remove-AzureRmRelayHybridConnection`
    + `Test-AzureRmRelayName`
    + `Get-AzureRmRelayOperation`
    + `New-AzureRmRelayKey`
    + `Get-AzureRmRelayKey`
    + `New-AzureRmRelayAuthorizationRule`
    + `Get-AzureRmRelayAuthorizationRule`
    + `Set-AzureRmRelayAuthorizationRule`
    + `Remove-AzureRmRelayAuthorizationRule`
* Erőforrások
  - Több erőforráscsoportra kiterjedő üzembe helyezés támogatása a New-AzureRmResourceGroupDeployment parancsmaghoz
    + A felhasználók mostantól beágyazott üzembe helyezések révén különböző erőforráscsoportokba helyezhetnek üzembe erőforrásokat.
* ServiceBus

  - Hibajavítás: A ServiceBus Queue objektumának tulajdonságai null értékre lettek állítva, és az objektum bemeneti paraméterként szolgál a Set-AzureRmServiceBusQueue parancsmagban az üzenetsor frissítésekor.
   - Az érintett tulajdonságok a következők: LockDuration, EntityAvailabilityStatus, DuplicateDetectionHistoryTimeWindow, MaxDeliveryCount és MessageCount
* ServiceFabric

  - Új Service Fabric-parancsmagok
    + Add-AzureRmServiceFabricApplicationCertificate       Alkalmazás-tanúsítványként szolgáló tanúsítvány felvétele
    + Add-AzureRmServiceFabricClientCertificate       Köznapi név vagy ujjlenyomat hozzáadása a fürtbeállításokhoz az ügyfél hitelesítése céljából
    + Add-AzureRmServiceFabricClusterCertificate       Másodlagos fürttanúsítvány hozzáadása a fürthöz a meglévő tanúsítvány kiegészítése céljából
    + Add-AzureRmServiceFabricNodes       Adott csomóponttípusú csomópontok vagy virtuális gépek hozzáadása a fürthöz
    + Add-AzureRmServiceFabricNodeType       Csomóponttípus vagy virtuális gépek hozzáadása meglévő fürthöz
    + Get-AzureRmServiceFabricCluster       A fürterőforrás részleteinek beolvasása
    + New-AzureRmServiceFabricCluster Új ServiceFabric-fürt létrehozása. A parancsnak többféle változata létezik az eltérő helyzetek kezelésére
    + Remove-AzureRmServiceFabricClientCertificate       Fürtök elérésére használható ügyféltanúsítvány eltávolítása
    + Remove-AzureRmServiceFabricClusterCertificate       Fürtbiztonsági célra használható fürttanúsítvány eltávolítása
    + Remove-AzureRmServiceFabricNodes       Csomópontok eltávolítása a fürt adott csomóponttípusából
    + Remove-AzureRmServiceFabricNodeType       Csomóponttípus eltávolítása a fürtből
    + Remove-AzureRmServiceFabricSettings       Legalább egy ServiceFabric-beállítás eltávolítása a fürtből
    + Set-AzureRmServiceFabricSettings       A fürt legalább egy ServiceFabric-beállításának megadása vagy módosítása
    + Set-AzureRmServiceFabricUpgradeType       A fürt ServiceFabric-frissítéstípusának módosítása
    + Update-AzureRmServiceFabricDurability       A fürt tartóssági szintjének módosítása
    + Update-AzureRmServiceFabricReliability       A fürt megbízhatósági szintjének módosítása
* SQL
  - Új paraméter (-SampleName) a New-AzureRmSqlDatabase parancsmaghoz
  - Megváltoztak a feladatátvételi csoport parancsmagjai
  - A Tag paraméterek el lettek távolítva
  - A Remove-AzureRmSqlDatabaseFailoverGroup parancsmagnál megszűnt a PartnerResourceGroupName és a PartnerServerName paraméter
  - A GracePeriodWithDataLossHour paramétert majdan leváltó GracePeriodWithDataLossHours paraméter jelent meg a New- és a Set- parancsmagokhoz
  - Bővült és frissült a dokumentáció
  - Módosítottuk a visszaadott objektumok formázását, és kijavítottunk néhány hibát, amelyek miatt bizonyos mezők feltöltése nem mindig történt meg
  - Új tulajdonságok a feladatátvételi csoport objektumához: DatabaseNames és PartnerLocation
  - Kijavítottunk egy hibát, amely miatt a Switch- parancsmag azonnal visszatért ahelyett, hogy megvárta volna a művelet befejezését
  - Kijavítottunk a türelmi időszakhoz tartozó magas értékek használatakor jelentkező egészszám-túlcsordulási hibát
  - A türelmi időszak értéke legalább 1 óra lesz, ha ennél alacsonyabb értéket adnak meg
  - A Usage_Anomaly el lett távolítva a Set-AzureRmSqlDatabaseThreatDetectionPolicy és a Set-AzureRmSqlServerThreatDetectionPolicy parancsmag ExcludedDetectionType paraméterének elfogadható értékei közül.
* Tárolás
  - Az SRP SDK a 6.3.0-s verzióra frissült
  - New/Set-AzureRmStorageAccount: az EnableHttpsTrafficOnly attribútumot támogató új paraméter
  - New/Set/Get-AzureRmStorageAccount: A visszaadott tárfióknak új attribútuma van (EnableHttpsTrafficOnly)
* Azure.Storage
  - Frissítés az Azure Storage ügyféloldali kódtárának 8.1.1-es és az Azure Storage adatátviteli kódtárának 0.5.1-es verziójára
  - Új, a blob növekményes másolati szolgáltatását támogató parancsmag
