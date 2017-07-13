---
title: "<span data-ttu-id=\"0c868-101\">Bejelentkezés az Azure PowerShell-lel</span><span class=\"sxs-lookup\"><span data-stu-id=\"0c868-101\">Log in with Azure PowerShell</span></span>"
description: "<span data-ttu-id=\"0c868-102\">Bejelentkezés az Azure PowerShell-lel</span><span class=\"sxs-lookup\"><span data-stu-id=\"0c868-102\">Log in with Azure PowerShell</span></span>"
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
ms.openlocfilehash: f6d249ca5bb09c4fe8445ba5b339ffa6012815ed
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="0c868-103">Bejelentkezés az Azure PowerShell-lel</span><span class="sxs-lookup"><span data-stu-id="0c868-103">Log in with Azure PowerShell</span></span>
<a id="log-in-with-azure-powershell" class="xliff"></a>

<span data-ttu-id="0c868-104">Az Azure PowerShell többféle bejelentkezési módszert támogat.</span><span class="sxs-lookup"><span data-stu-id="0c868-104">Azure PowerShell supports multiple login methods.</span></span> <span data-ttu-id="0c868-105">Első lépésként a legegyszerűbb módszer, ha interaktívan bejelentkezik a parancssoron.</span><span class="sxs-lookup"><span data-stu-id="0c868-105">The simplest way to get started is to log in interactively at the command line.</span></span>

## <span data-ttu-id="0c868-106">Interaktív bejelentkezés</span><span class="sxs-lookup"><span data-stu-id="0c868-106">Interactive log in</span></span>
<a id="interactive-log-in" class="xliff"></a>

1. <span data-ttu-id="0c868-107">Gépelje be: `Login-AzureRmAccount`.</span><span class="sxs-lookup"><span data-stu-id="0c868-107">Type `Login-AzureRmAccount`.</span></span> <span data-ttu-id="0c868-108">Egy párbeszédpanel jelenik meg, amelyen meg kell adnia Azure-beli hitelesítő adatait.</span><span class="sxs-lookup"><span data-stu-id="0c868-108">You will get dialog box asking for your Azure credentials.</span></span>

2. <span data-ttu-id="0c868-109">Írja be a fiókjához tartozó e-mail-címet és jelszót.</span><span class="sxs-lookup"><span data-stu-id="0c868-109">Type the email address and password associated with your account.</span></span> <span data-ttu-id="0c868-110">Az Azure hitelesíti és menti a hitelesítő adatokat, majd bezárja az ablakot.</span><span class="sxs-lookup"><span data-stu-id="0c868-110">Azure authenticates and saves the credential information, and then closes the window.</span></span>

## <span data-ttu-id="0c868-111">Bejelentkezés szolgáltatásnévvel</span><span class="sxs-lookup"><span data-stu-id="0c868-111">Log in with a service principal</span></span>
<a id="log-in-with-a-service-principal" class="xliff"></a>

<span data-ttu-id="0c868-112">A szolgáltatásnevek használatával nem interaktív fiókokat hozhat létre az erőforrások kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="0c868-112">Service principals provide a way for you to create non-interactive accounts that you can use to manipulate resources.</span></span> <span data-ttu-id="0c868-113">A szolgáltatásnevek szolgáltatások olyan felhasználói fiókokhoz hasonlóak, amelyekre szabályokat alkalmazhat az Azure Active Directory használatával.</span><span class="sxs-lookup"><span data-stu-id="0c868-113">Service principals are like user accounts to which you can apply rules using Azure Active Directory.</span></span> <span data-ttu-id="0c868-114">Az automatizálási szkriptek biztonságának növelése érdekében csak a minimálisan szükséges engedélyeket adja meg a szolgáltatásneveknek.</span><span class="sxs-lookup"><span data-stu-id="0c868-114">By granting the minimum permissions needed to a service principal, you can ensure your automation scripts are even more secure.</span></span>

1. <span data-ttu-id="0c868-115">Ha még nem rendelkezik szolgáltatásnévvel, akkor [hozzon létre egyet](create-azure-service-principal-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="0c868-115">If you don't already have a service principal, [create one](create-azure-service-principal-azureps.md).</span></span>

2. <span data-ttu-id="0c868-116">Jelentkezzen be a szolgáltatásnévvel.</span><span class="sxs-lookup"><span data-stu-id="0c868-116">Log in with the service principal.</span></span>

    ```powershell
    Login-AzureRmAccount -ServicePrincipal -ApplicationId  "http://my-app" -Credential $pscredential -TenantId $tenantid
    ```

    <span data-ttu-id="0c868-117">A bérlőazonosító megismeréséhez jelentkezzen be interaktívan, és kérje le az előfizetésből.</span><span class="sxs-lookup"><span data-stu-id="0c868-117">To get your TenantId, log in interactively and then get the TenantId from your subscription.</span></span>

    ```powershell
    Get-AzureRmSubscription
    ```

    ```
    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Production Subscription
    CurrentStorageAccount :
    ```

## <span data-ttu-id="0c868-118">Bejelentkezés egy másik felhőbe</span><span class="sxs-lookup"><span data-stu-id="0c868-118">Log in to another Cloud</span></span>
<a id="log-in-to-another-cloud" class="xliff"></a>

<span data-ttu-id="0c868-119">Az Azure-beli felhőszolgáltatások különböző környezeteket biztosítanak, amelyek igazodnak az egyes kormányzatok adatkezelési szabályzataihoz.</span><span class="sxs-lookup"><span data-stu-id="0c868-119">Azure cloud services provide different environments that adhere to the data-handling regulations of various governments.</span></span> <span data-ttu-id="0c868-120">Ha az Azure-fiók valamelyik kormányzati felhőben található, bejelentkezéskor meg kell adnia a környezetet.</span><span class="sxs-lookup"><span data-stu-id="0c868-120">If your Azure account is in one the government clouds, you need to specify the environment when you sign in.</span></span> <span data-ttu-id="0c868-121">Például ha a fiók a kínai felhőszolgáltatásban található, a regisztrálás az alábbi paranccsal történik:</span><span class="sxs-lookup"><span data-stu-id="0c868-121">For example, if you account is in the China cloud you sign on using the following command:</span></span>

```powershell
Login-AzureRmAccount -EnvironmentName AzureChinaCloud
```

<span data-ttu-id="0c868-122">Az alábbi paranccsal olvashatja be a rendelkezésre álló környezetek listáját:</span><span class="sxs-lookup"><span data-stu-id="0c868-122">Use the following command to get a list of available environments:</span></span>

```powershell
Get-AzureRmEnvironment | Select-Object Name
```

```
Name
----
AzureCloud
AzureChinaCloud
AzureUSGovernment
AzureGermanCloud
```

## <span data-ttu-id="0c868-123">További információ az Azure szerepkör-alapú hozzáférés kezeléséről</span><span class="sxs-lookup"><span data-stu-id="0c868-123">Learn more about managing Azure role-based access</span></span>
<a id="learn-more-about-managing-azure-role-based-access" class="xliff"></a>

<span data-ttu-id="0c868-124">Az Azure-beli hitelesítésről és előfizetés-kezelésről a [fiókok, előfizetések és rendszergazdai szerepkörök kezeléséről](/azure/active-directory/role-based-access-control-configure) szóló cikkben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="0c868-124">For more information about authentication and subscription management in Azure, see [Manage Accounts, Subscriptions, and Administrative Roles](/azure/active-directory/role-based-access-control-configure).</span></span>

<span data-ttu-id="0c868-125">Azure PowerShell-parancsmagok a szerepkörök kezeléséhez</span><span class="sxs-lookup"><span data-stu-id="0c868-125">Azure PowerShell cmdlets for role management</span></span>

* [<span data-ttu-id="0c868-126">Get-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="0c868-126">Get-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/Get-AzureRmRoleAssignment)
* [<span data-ttu-id="0c868-127">Get-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="0c868-127">Get-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/Get-AzureRmRoleDefinition)
* [<span data-ttu-id="0c868-128">New-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="0c868-128">New-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/New-AzureRmRoleAssignment)
* [<span data-ttu-id="0c868-129">New-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="0c868-129">New-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/New-AzureRmRoleDefinition)
* [<span data-ttu-id="0c868-130">Remove-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="0c868-130">Remove-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleAssignment)
* [<span data-ttu-id="0c868-131">Remove-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="0c868-131">Remove-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleDefinition)
* [<span data-ttu-id="0c868-132">Set-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="0c868-132">Set-AzureRmRoleDefinition</span></span>](/powershell/moduel/AzureRM.Resources/Set-AzureRmRoleDefinition)
