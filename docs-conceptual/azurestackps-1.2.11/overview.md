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
# <a name="azure-stack-powershell"></a>Azure Stack PowerShell

Az Azure Stack a következő két PowerShell-modult igényli:  

1. Az Azure Stack szolgáltatással kompatibilis **AzureRM**-modul, amely a **2017-03-09-profile** API-verzióprofil telepítésével érhető el. A profil használatával telepített parancsmagokat az Azure Stack operátorai és felhasználói használhatják.

2. Az **AzureStack**-modul legújabb telepíthető verziója az **1.2.11**-es. A modul használatával telepített parancsmagokat csak az Azure Stack operátorai használhatják. Az operátorok a modul által biztosított PowerShell-parancsmagokkal olyan műveleteket hajthatnak végre, mint az ajánlatok, csomagok, szolgáltatások, kvóták stb. kezelése. A modulban elérhető PowerShell-parancsmagokkal kapcsolatos további információkért tekintse meg az [AzureStack](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.11#azurerm.azurestackadmin) és [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.11#azurerm.azurestackstorage) referenciatartalmakat.

## <a name="next-steps"></a>Következő lépések

* [A PowerShell telepítése az Azure Stack szolgáltatáshoz](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
* [A PowerShell konfigurálása az Azure Stack szolgáltatással való használathoz](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
