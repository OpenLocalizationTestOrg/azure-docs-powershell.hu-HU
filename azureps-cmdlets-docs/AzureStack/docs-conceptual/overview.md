---
title: "Az Azure Stack PowerShell áttekintése | Microsoft Docs"
description: "Az Azure Stack PowerShell telepítésének és konfigurálásának áttekintése."
author: SnehaGunda
manager: Byronr
ms.product: azure-stack
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.author: sngun
ms.manager: byronr
ms.openlocfilehash: 2a03697e0f3e80d63c48f2dc5615f6c99b9ef716
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2017
---
# <a name="azure-stack-powershell"></a><span data-ttu-id="bc8d5-103">Azure Stack PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc8d5-103">Azure Stack PowerShell</span></span> 

<span data-ttu-id="bc8d5-104">Az Azure Stack a következő két PowerShell-modult igényli:</span><span class="sxs-lookup"><span data-stu-id="bc8d5-104">Azure Stack requires the following two PowerShell modules:</span></span>  

1. <span data-ttu-id="bc8d5-105">Az Azure Stack szolgáltatással kompatibilis **AzureRM**-modul, amely a **2017-03-09-profile** API-verzióprofil telepítésével érhető el.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-105">The Azure Stack compatible **AzureRM** module which is available by installing the **2017-03-09-profile** API Version Profile.</span></span> <span data-ttu-id="bc8d5-106">A profil használatával telepített parancsmagokat az Azure Stack-felhő rendszergazdái és bérlői egyaránt használhatják.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-106">The cmdlets installed by using this profile can be used by the Azure Stack cloud administrators and the tenants.</span></span> <span data-ttu-id="bc8d5-107">A profilban elérhető PowerShell-parancsmagokkal kapcsolatos további információkért tekintse meg a PowerShell-referenciatartalom az [AzureRM-modul 1.2.9-es verziójára](https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-1.2.9) vonatkozó részét.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-107">To learn about the PowerShell cmdlets that are available in this profile, see the PowerShell reference content for the [1.2.9 version of AzureRM](https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-1.2.9) module.</span></span>  

2. <span data-ttu-id="bc8d5-108">Az **AzureStack**-modul **1.2.9-es** verziója.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-108">The **1.2.9** version of the **AzureStack** module.</span></span> <span data-ttu-id="bc8d5-109">A modul használatával telepített parancsmagokat csak az Azure Stack-felhő rendszergazdái használhatják.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-109">The cmdlets installed by using this module can be used by Azure Stack cloud administrators only.</span></span> <span data-ttu-id="bc8d5-110">A rendszergazdák a modul által biztosított PowerShell-parancsmagok segítségével olyan műveleteket hajthatnak végre, mint az ajánlatok, tervek, szolgáltatások, kvóták stb. kezelése.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-110">Administrator can perform operations such as manage offers, plans, services, quotas, etc. by using the PowerShell cmdlets provided by this module.</span></span> <span data-ttu-id="bc8d5-111">A modulban elérhető PowerShell-parancsmagokkal kapcsolatos további információkért tekintse meg az [AzureStack](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.9#azurerm.azurestackadmin) és [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.9#azurerm.azurestackstorage) referenciatartalmakat.</span><span class="sxs-lookup"><span data-stu-id="bc8d5-111">To learn about the PowerShell cmdlets available in this module, see the [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.9#azurerm.azurestackadmin) and [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.9#azurerm.azurestackstorage) Reference content.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc8d5-112">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="bc8d5-112">Next Steps</span></span>

* [<span data-ttu-id="bc8d5-113">A PowerShell telepítése az Azure Stack szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="bc8d5-113">Install PowerShell for Azure Stack</span></span>](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
* [<span data-ttu-id="bc8d5-114">A PowerShell konfigurálása az Azure Stack szolgáltatással való használathoz</span><span class="sxs-lookup"><span data-stu-id="bc8d5-114">Configure PowerShell for use with Azure Stack</span></span>](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)


