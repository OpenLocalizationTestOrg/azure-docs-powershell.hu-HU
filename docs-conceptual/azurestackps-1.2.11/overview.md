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
ms.openlocfilehash: 49980b361c580a1a00f07c2002241e71f2c0b654
ms.sourcegitcommit: df44d5d9874b55455ec745f1846e06a4b3266d13
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2017
---
# <a name="azure-stack-powershell"></a><span data-ttu-id="9f406-103">Azure Stack PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f406-103">Azure Stack PowerShell</span></span>

<span data-ttu-id="9f406-104">Az Azure Stack a következő két PowerShell-modult igényli:</span><span class="sxs-lookup"><span data-stu-id="9f406-104">Azure Stack requires the following two PowerShell modules:</span></span>  

1. <span data-ttu-id="9f406-105">Az Azure Stack szolgáltatással kompatibilis **AzureRM**-modul, amely a **2017-03-09-profile** API-verzióprofil telepítésével érhető el.</span><span class="sxs-lookup"><span data-stu-id="9f406-105">The Azure Stack compatible **AzureRM** module which is available by installing the **2017-03-09-profile** API Version Profile.</span></span> <span data-ttu-id="9f406-106">A profil használatával telepített parancsmagokat az Azure Stack operátorai és felhasználói használhatják.</span><span class="sxs-lookup"><span data-stu-id="9f406-106">The cmdlets installed by using this profile can be used by Azure Stack operators and users.</span></span>

2. <span data-ttu-id="9f406-107">Az **AzureStack**-modul legújabb telepíthető verziója az **1.2.11**-es.</span><span class="sxs-lookup"><span data-stu-id="9f406-107">The most current version is the **1.2.11** install of the **AzureStack** module.</span></span> <span data-ttu-id="9f406-108">A modul használatával telepített parancsmagokat csak az Azure Stack operátorai használhatják.</span><span class="sxs-lookup"><span data-stu-id="9f406-108">The cmdlets installed by using this module can be used by Azure Stack operators only.</span></span> <span data-ttu-id="9f406-109">Az operátorok a modul által biztosított PowerShell-parancsmagokkal olyan műveleteket hajthatnak végre, mint az ajánlatok, csomagok, szolgáltatások, kvóták stb. kezelése.</span><span class="sxs-lookup"><span data-stu-id="9f406-109">Operators can perform operations such as manage offers, plans, services, quotas, etc. by using the PowerShell cmdlets provided by this module.</span></span> <span data-ttu-id="9f406-110">A modulban elérhető PowerShell-parancsmagokkal kapcsolatos további információkért tekintse meg az [AzureStack](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.11#azurerm.azurestackadmin) és [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.11#azurerm.azurestackstorage) referenciatartalmakat.</span><span class="sxs-lookup"><span data-stu-id="9f406-110">To learn about the PowerShell cmdlets available in this module, see the [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.11#azurerm.azurestackadmin) and [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.11#azurerm.azurestackstorage) Reference content.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9f406-111">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="9f406-111">Next Steps</span></span>

* [<span data-ttu-id="9f406-112">A PowerShell telepítése az Azure Stack szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="9f406-112">Install PowerShell for Azure Stack</span></span>](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
* [<span data-ttu-id="9f406-113">A PowerShell konfigurálása az Azure Stack szolgáltatással való használathoz</span><span class="sxs-lookup"><span data-stu-id="9f406-113">Configure PowerShell for use with Azure Stack</span></span>](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
