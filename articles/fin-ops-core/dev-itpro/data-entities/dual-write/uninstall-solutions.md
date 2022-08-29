---
title: Kettős írású alkalmazás lebonyolítási megoldások eltávolítása
description: Ez a cikk azt ismerteti, hogyan lehet eltávolítani a két írásos alkalmazáscsatornás megoldásokat.
author: RamaKrishnamoorthy
ms.date: 03/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2022-01-21
ms.openlocfilehash: fd9dc98ec1323a2ef262a330a400a6bd3833e554
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288730"
---
# <a name="uninstall-dual-write-application-orchestration-solutions"></a>Kettős írású alkalmazás lebonyolítási megoldások eltávolítása

[!include [banner](../../includes/banner.md)]

Ez a cikk azt ismerteti, hogyan lehet eltávolítani a két írásos alkalmazáscsatornás megoldásokat.

Egyes ügyfelek véletlenül telepítik a kettős írású alkalmazás-szoftvercsomagot, amely több megoldást telepít a környezetében Microsoft Dataverse. A külső megoldások csomagba telepítése váratlan és problémákat okozhat.

A két írásos alkalmazás rendelenycsomag telepítésével kapcsolatos problémák megoldásához a következő sorrendben távolítsa el a nem kívánt kétírásos megoldásokat:

1. Dynamics365FinanceAndOperationsAnchor_managed
1. msdyn_OneFSSCM_managed (ha van)
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps_managed
1. Dynamics365Notes_managed (A megoldás eltávolításához meg kell nyitnia egy támogatási jegyet a Microsoft számára.)
1. DualWriteCore_managed
1. Dynamics365AssetManagementApp_managed
1. Dynamics365AssetManagement_managed
1. Dynamics365SupplyChainExtended_managed
1. Dynamics365FinanceExtended_managed
1. HCMCommon_managed
1. Dynamics365FinanceAndOperationsCommon_managed
1. Dynamics365Company_managed
1. CurrencyExchangeRates_managed
1. msdyn_AssetCommon_managed
1. FieldServiceCommon_managed

Ha a felek és a globális címjegyzék megoldásai telepítve vannak, a következő sorrendben távolítsa el a megoldásokat:

1. Dynamics365FinanceAndOperationsAnchor
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps
1. msdyn_DualWriteCore
1. Dynamics365AssetManagementApp
1. Dynamics365AssetManagement
1. Dynamics365SupplyChainExtended
1. Dynamics365FinanceExtended
1. HCMCommon
1. Dynamics365FinanceAndOperationsCommon
1. Fél
1. Dynamics365Company_managed
1. CurrencyExchangeRates
1. msdyn_AssetCommon
1. FieldServiceCommon
