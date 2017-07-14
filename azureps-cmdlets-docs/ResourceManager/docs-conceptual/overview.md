---
title: "Az Azure PowerShell áttekintése | Microsoft Docs"
description: "Az Azure PowerShell áttekintése telepítési és konfigurációs hivatkozásokkal."
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.manager: carmonm
ms.date: 05/15/2017
ms.openlocfilehash: dbcc818ecc06d3206b8ccd6f8743c670c86cead0
ms.sourcegitcommit: 5f2c794bfa44ec4ffacdd73f548288874210a498
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2017
---
# <span data-ttu-id="7e6ef-103">Az Azure PowerShell áttekintése</span><span class="sxs-lookup"><span data-stu-id="7e6ef-103">Overview of Azure PowerShell</span></span>
<a id="overview-of-azure-powershell" class="xliff"></a>

<span data-ttu-id="7e6ef-104">Az Azure PowerShell olyan parancsmagok készletét kínálja, amelyek az [Azure Resource Manager](/azure/azure-resource-manager/resource-group-overview) modellt használják az Azure-erőforrások kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="7e6ef-104">Azure PowerShell provides a set of cmdlets that use the [Azure Resource Manager](/azure/azure-resource-manager/resource-group-overview) model for managing your Azure resources.</span></span>

<span data-ttu-id="7e6ef-105">Az Azure PowerShell beüzemeléséhez tekintse át a [Telepítés](install-azurerm-ps.md) című cikket.</span><span class="sxs-lookup"><span data-stu-id="7e6ef-105">Review the [Install](install-azurerm-ps.md) article to get Azure PowerShell up and running on your system.</span></span> <span data-ttu-id="7e6ef-106">Ezután olvassa el az [Első lépések](get-started-azureps.md) című cikket, mielőtt használatba venné.</span><span class="sxs-lookup"><span data-stu-id="7e6ef-106">Then read the [Get Started](get-started-azureps.md) article to begin using it.</span></span> <span data-ttu-id="7e6ef-107">A legújabb kiadással kapcsolatos információkért lásd a [kibocsátási megjegyzéseket](release-notes-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="7e6ef-107">For information about the latest release, see the [release notes](release-notes-azureps.md).</span></span>

<span data-ttu-id="7e6ef-108">A következő példák segítenek megismerkedni az Azure PowerShell általános forgatókönyveinek végrehajtásával:</span><span class="sxs-lookup"><span data-stu-id="7e6ef-108">The following samples can help you learn how to perform common scenarios with Azure PowerShell:</span></span>

* [<span data-ttu-id="7e6ef-109">Linux rendszerű virtuális gépek</span><span class="sxs-lookup"><span data-stu-id="7e6ef-109">Linux Virtual Machines</span></span>](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=/powershell/azure/toc.json)
* [<span data-ttu-id="7e6ef-110">Windows rendszerű virtuális gépek</span><span class="sxs-lookup"><span data-stu-id="7e6ef-110">Windows Virtual Machines</span></span>](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=/powershell/azure/toc.json)
* [<span data-ttu-id="7e6ef-111">Web Apps</span><span class="sxs-lookup"><span data-stu-id="7e6ef-111">Web Apps</span></span>](/azure/app-service-web/app-service-powershell-samples?toc=/powershell/azure/toc.json)
* [<span data-ttu-id="7e6ef-112">SQL Database-adatbázisok</span><span class="sxs-lookup"><span data-stu-id="7e6ef-112">SQL Databases</span></span>](/azure/sql-database/sql-database-powershell-samples?toc=/powershell/azure/toc.json)


> [!NOTE]<span data-ttu-id="7e6ef-113"> > Ha van olyan üzemelő példánya, amely a klasszikus telepítési modellt használja, és nem alakítható át, akkor az Azure PowerShell Service Management verzióját telepítheti.</span><span class="sxs-lookup"><span data-stu-id="7e6ef-113"> > If you have deployments that use the classic deployment model that cannot be converted, you can install the Service Management version of Azure PowerShell.</span></span> <span data-ttu-id="7e6ef-114">További információ: [Az Azure PowerShell Service Management moduljának telepítése](/powershell/azure/servicemanagement/install-azure-ps).</span><span class="sxs-lookup"><span data-stu-id="7e6ef-114">For more information, see [Install the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps).</span></span>


### <span data-ttu-id="7e6ef-115">Segítségre van szüksége a PowerShell-lel kapcsolatban?</span><span class="sxs-lookup"><span data-stu-id="7e6ef-115">Need help with PowerShell?</span></span>
<a id="need-help-with-powershell" class="xliff"></a>

<span data-ttu-id="7e6ef-116">Ha nem ismeri a PowerShellt, érdemes lehet elolvasni a PowerShellt bemutató anyagot.</span><span class="sxs-lookup"><span data-stu-id="7e6ef-116">If you are unfamiliar with PowerShell, you may find an introduction to PowerShell helpful.</span></span> <span data-ttu-id="7e6ef-117">A PowerShell használatának első lépéseivel kapcsolatban lásd: [Szkriptek használata a PowerShellben](https://technet.microsoft.com/library/bb978526.aspx).</span><span class="sxs-lookup"><span data-stu-id="7e6ef-117">To get started with PowerShell, see [Scripting with PowerShell](https://technet.microsoft.com/library/bb978526.aspx).</span></span>

<span data-ttu-id="7e6ef-118">Megtekintheti a következő videót is: [A PowerShell alapjai: (1. rész) Ismerkedés a PowerShell-lel](https://channel9.msdn.com/Blogs/Taste-of-Premier/PowerShellBasicsPart1).</span><span class="sxs-lookup"><span data-stu-id="7e6ef-118">You can also watch this video: [PowerShell Basics: (Part 1) Getting Started with PowerShell](https://channel9.msdn.com/Blogs/Taste-of-Premier/PowerShellBasicsPart1).</span></span>

## <span data-ttu-id="7e6ef-119">Egyéb Azure PowerShell-modulok</span><span class="sxs-lookup"><span data-stu-id="7e6ef-119">Other Azure PowerShell modules</span></span>
<a id="other-azure-powershell-modules" class="xliff"></a>

* [<span data-ttu-id="7e6ef-120">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7e6ef-120">Azure Active Directory</span></span>](/powershell/azure/active-directory/)
* [<span data-ttu-id="7e6ef-121">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="7e6ef-121">Azure Information Protection</span></span>](/powershell/azure/aip/)
* [<span data-ttu-id="7e6ef-122">Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="7e6ef-122">Azure Service Fabric</span></span>](/powershell/azure/oservice-fabric/)
* [<span data-ttu-id="7e6ef-123">Azure ElasticDB</span><span class="sxs-lookup"><span data-stu-id="7e6ef-123">Azure ElasticDB</span></span>](/powershell/azure/elasticdbjobs/)
