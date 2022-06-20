---
title: Aszinkron vevők átalakítása szinkron vevőkké
description: Ez a témakör bemutatja, hogyan lehet az aszinkron vevőket a következőben szinkronizált vevőként átalakítani:Microsoft Dynamics 365 Commerce
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 0ce4906816deab8824b1079a34489e55651c0e03
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884391"
---
# <a name="convert-asynchronous-customers-to-synchronous-customers"></a>Aszinkron vevők átalakítása szinkron vevőkké

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet az aszinkron vevőket a következőben szinkronizált vevőként átalakítani:Microsoft Dynamics 365 Commerce

Az aszinkron vevők szinkronizálása érdekében kövesse ezeket a lépéseket.

1. A Commerce Headquartersben futtassa **a P-feladatot**, és küldje el az aszinkron vevőket a Commerce Headquarters számára.
1. A vevők és **üzleti partnerek szinkronizálása aszinkron módú feladat** futtatásával hozza létre a vevői számlaszámokat. (Ezt a feladatot korábban elnevezték. **Vevők és üzleti partnerek szinkronizálása async módból**.)
1. Futtassa **a 1010-es** feladatot, hogy szinkronizálja az új vevői számlaszámokat a csatornákkal.

Ha egy rendelés olyan aszinkron vevőre vagy címre hivatkozik, amely még nincs szinkronizálva a Commerce Headquarters alkalmazással, **akkor** a rendszer a vevőt vagy a címet a Rendelések szinkronizálása kötegelt feladat részeként szinkronizálja. Ha a készpénz-/áthozott tranzakció aszinkron vevőre vagy címre hivatkozik, akkor a rendszer szinkronizálja a vevőt vagy a címet a napvégi feladás előtt.

## <a name="additional-resources"></a>További erőforrások

[Vevők kezelése az üzletekben](customer-mgmt-stores.md)

[Aszinkron vevőlétrehozási mód](async-customer-mode.md)

[Vevőattribútumok](dev-itpro/customer-attributes.md)

[Offline adatok kizárása](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
