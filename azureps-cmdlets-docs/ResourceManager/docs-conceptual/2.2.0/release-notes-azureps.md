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
ms.openlocfilehash: 143d92384fd270711378f6741ba59e88c12833d1
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="1ae82-103">Kibocsátási megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1ae82-103">Release notes</span></span>
<a id="release-notes" class="xliff"></a>

<span data-ttu-id="1ae82-104">Az alábbiakban az Azure PowerShell jelen kiadásában végrehajtott módosítások listája olvasható.</span><span class="sxs-lookup"><span data-stu-id="1ae82-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <span data-ttu-id="1ae82-105">2.2.0-ás verzió</span><span class="sxs-lookup"><span data-stu-id="1ae82-105">Version 2.2.0</span></span>
<a id="version-220" class="xliff"></a>
* <span data-ttu-id="1ae82-106">Számítás</span><span class="sxs-lookup"><span data-stu-id="1ae82-106">Compute</span></span>
  - <span data-ttu-id="1ae82-107">A titkosítás állapotának az AzureDiskEncryptionForLinux bővítményből történő lekérésének támogatása</span><span class="sxs-lookup"><span data-stu-id="1ae82-107">Add support for querying encryption status from the AzureDiskEncryptionForLinux extension</span></span>
* <span data-ttu-id="1ae82-108">DataFactory</span><span class="sxs-lookup"><span data-stu-id="1ae82-108">DataFactory</span></span>
  - <span data-ttu-id="1ae82-109">Új parancsmag hozzáadása a tevékenységablakok felsorolásához</span><span class="sxs-lookup"><span data-stu-id="1ae82-109">Added new cmdlet for listing activity windows</span></span>
    + <span data-ttu-id="1ae82-110">Get-AzureRmDataFactoryActivityWindow</span><span class="sxs-lookup"><span data-stu-id="1ae82-110">Get-AzureRmDataFactoryActivityWindow</span></span>
* <span data-ttu-id="1ae82-111">DataLake</span><span class="sxs-lookup"><span data-stu-id="1ae82-111">DataLake</span></span>
  - <span data-ttu-id="1ae82-112">A `Host` paraméter lecserélése a `DatabaseHost` paraméterre, valamint alias hozzáadása a `Host` paraméterhez.</span><span class="sxs-lookup"><span data-stu-id="1ae82-112">Changed parameter `Host` to `DatabaseHost` and added alias to `Host`</span></span>
    + <span data-ttu-id="1ae82-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="1ae82-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
    + <span data-ttu-id="1ae82-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="1ae82-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
  - <span data-ttu-id="1ae82-115">Az ACL és alapértelmezett ACL eltávolításának támogatása</span><span class="sxs-lookup"><span data-stu-id="1ae82-115">Add support for ACL and Default ACL removal</span></span>
  - <span data-ttu-id="1ae82-116">Névtelen engedélyek beszerzésének és beállításának támogatása fájlok és mappák esetében</span><span class="sxs-lookup"><span data-stu-id="1ae82-116">Add support for getting and setting unnamed permissions on files and folders</span></span>
* <span data-ttu-id="1ae82-117">KeyVault</span><span class="sxs-lookup"><span data-stu-id="1ae82-117">KeyVault</span></span>
  - <span data-ttu-id="1ae82-118">Tanúsítványok támogatása</span><span class="sxs-lookup"><span data-stu-id="1ae82-118">Add support for certificates</span></span>
    + <span data-ttu-id="1ae82-119">Add-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="1ae82-119">Add-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="1ae82-120">Add-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="1ae82-120">Add-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="1ae82-121">Get-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="1ae82-121">Get-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="1ae82-122">Get-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="1ae82-122">Get-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="1ae82-123">Get-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="1ae82-123">Get-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="1ae82-124">Get-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="1ae82-124">Get-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="1ae82-125">Get-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="1ae82-125">Get-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="1ae82-126">Import-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="1ae82-126">Import-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="1ae82-127">New-AzureKeyVaultCertificateAdministratorDetails</span><span class="sxs-lookup"><span data-stu-id="1ae82-127">New-AzureKeyVaultCertificateAdministratorDetails</span></span>
    + <span data-ttu-id="1ae82-128">New-AzureKeyVaultCertificateOrganizationDetails</span><span class="sxs-lookup"><span data-stu-id="1ae82-128">New-AzureKeyVaultCertificateOrganizationDetails</span></span>
    + <span data-ttu-id="1ae82-129">New-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="1ae82-129">New-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="1ae82-130">Remove-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="1ae82-130">Remove-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="1ae82-131">Remove-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="1ae82-131">Remove-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="1ae82-132">Remove-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="1ae82-132">Remove-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="1ae82-133">Remove-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="1ae82-133">Remove-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="1ae82-134">Set-AzureKeyVaultCertificateAttribute</span><span class="sxs-lookup"><span data-stu-id="1ae82-134">Set-AzureKeyVaultCertificateAttribute</span></span>
    + <span data-ttu-id="1ae82-135">Set-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="1ae82-135">Set-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="1ae82-136">Set-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="1ae82-136">Set-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="1ae82-137">Stop-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="1ae82-137">Stop-AzureKeyVaultCertificateOperation</span></span>
* <span data-ttu-id="1ae82-138">Network (Hálózat)</span><span class="sxs-lookup"><span data-stu-id="1ae82-138">Network</span></span>

  - <span data-ttu-id="1ae82-139">Új kapcsolóparaméter hozzáadása a hálózati adapter számára a gyorsított hálózatkezelés engedélyezéséhez/letiltásához – +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span><span class="sxs-lookup"><span data-stu-id="1ae82-139">New switch parameter added for network interface to enable/disable accelerated networking +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span></span>
  - <span data-ttu-id="1ae82-140">Aktív-aktív átjárószolgáltatás PowerShell-parancsmagjainak engedélyezése</span><span class="sxs-lookup"><span data-stu-id="1ae82-140">Enable Active-Active gateway feature PowerShell cmdlets</span></span>
    + <span data-ttu-id="1ae82-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="1ae82-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span></span>
    + <span data-ttu-id="1ae82-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="1ae82-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span></span>
  - <span data-ttu-id="1ae82-143">Új parancsmag hozzáadása</span><span class="sxs-lookup"><span data-stu-id="1ae82-143">Added new cmdlet</span></span>
    + <span data-ttu-id="1ae82-144">Test-AzureRmPrivateIpAddressAvailability</span><span class="sxs-lookup"><span data-stu-id="1ae82-144">Test-AzureRmPrivateIpAddressAvailability</span></span>
* <span data-ttu-id="1ae82-145">Erőforrások</span><span class="sxs-lookup"><span data-stu-id="1ae82-145">Resources</span></span>
  - <span data-ttu-id="1ae82-146">Zónák támogatása szolgáltatói és erőforrás-parancsmagok esetében</span><span class="sxs-lookup"><span data-stu-id="1ae82-146">Support zones in provider and resource cmdlets</span></span>
    + <span data-ttu-id="1ae82-147">Get-AzureRmProvider</span><span class="sxs-lookup"><span data-stu-id="1ae82-147">Get-AzureRmProvider</span></span>
    + <span data-ttu-id="1ae82-148">New-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="1ae82-148">New-AzureRmResource</span></span>
    + <span data-ttu-id="1ae82-149">Set-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="1ae82-149">Set-AzureRmResource</span></span>
* <span data-ttu-id="1ae82-150">SQL</span><span class="sxs-lookup"><span data-stu-id="1ae82-150">Sql</span></span>
  - <span data-ttu-id="1ae82-151">Új parancsmagok hozzáadása az Azure SQL fenyegetésészlelési házirendkezelése számára a kiszolgálók szintjén</span><span class="sxs-lookup"><span data-stu-id="1ae82-151">Added new cmdlets for Azure SQL threat detection policy management at server level</span></span>
    + <span data-ttu-id="1ae82-152">Get-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="1ae82-152">Get-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="1ae82-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="1ae82-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="1ae82-154">Set-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="1ae82-154">Set-AzureRmSqlServerThreatDetectionPolicy</span></span>
  - <span data-ttu-id="1ae82-155">Új parancsmagok hozzáadása a GeoBackupPolicy paraméter engedélyezésének/letiltásának támogatása érdekében az SQL Azure-adattárházak esetében</span><span class="sxs-lookup"><span data-stu-id="1ae82-155">Added new cmdlets to support enabling/disabling GeoBackupPolicy for Sql Azure DataWarehouses</span></span>
    + <span data-ttu-id="1ae82-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="1ae82-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
    + <span data-ttu-id="1ae82-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="1ae82-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
  - <span data-ttu-id="1ae82-158">Új parancsmagok hozzáadása az Azure SQL-tanácsadók és Javasolt műveletek API-k számára</span><span class="sxs-lookup"><span data-stu-id="1ae82-158">Added new cmdlets for Azure Sql Advisors and Recommended Actions APIs</span></span>
    + <span data-ttu-id="1ae82-159">Get-AzureRmSqlDatabaseAdvisor</span><span class="sxs-lookup"><span data-stu-id="1ae82-159">Get-AzureRmSqlDatabaseAdvisor</span></span>
    + <span data-ttu-id="1ae82-160">Get-AzureRmSqlElasticPoolAdvisor</span><span class="sxs-lookup"><span data-stu-id="1ae82-160">Get-AzureRmSqlElasticPoolAdvisor</span></span>
    + <span data-ttu-id="1ae82-161">Get-AzureRmSqlServerAdvisor</span><span class="sxs-lookup"><span data-stu-id="1ae82-161">Get-AzureRmSqlServerAdvisor</span></span>
    + <span data-ttu-id="1ae82-162">Get-AzureRmSqlDatabaseRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="1ae82-162">Get-AzureRmSqlDatabaseRecommendedActions</span></span>
    + <span data-ttu-id="1ae82-163">Get-AzureRmSqlElasticPoolRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="1ae82-163">Get-AzureRmSqlElasticPoolRecommendedActions</span></span>
    + <span data-ttu-id="1ae82-164">Get-AzureRmSqlServerRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="1ae82-164">Get-AzureRmSqlServerRecommendedActions</span></span>
    + <span data-ttu-id="1ae82-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="1ae82-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="1ae82-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="1ae82-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="1ae82-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="1ae82-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="1ae82-168">Set-AzureRmSqlDatabaseRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="1ae82-168">Set-AzureRmSqlDatabaseRecommendedActionState</span></span>
    + <span data-ttu-id="1ae82-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="1ae82-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span></span>
    + <span data-ttu-id="1ae82-170">Set-AzureRmSqlServerRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="1ae82-170">Set-AzureRmSqlServerRecommendedActionState</span></span>
