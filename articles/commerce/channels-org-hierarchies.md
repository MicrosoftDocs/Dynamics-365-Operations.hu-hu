---
title: Szervezeti hierarchiák létrehozása
description: Ez a témakör azt ismerteti, hogyan lehet beállítani a szervezeti hierarchiákat a Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 2555378c119e4c096c4bf0c0adc11e3a50cbfe38
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280447"
---
# <a name="set-up-organization-hierarchies"></a>Szervezeti hierarchiák létrehozása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet beállítani a szervezeti hierarchiákat a Microsoft Dynamics 365 Commerce.

A csatornák létrehozása előtt győződjön meg arról, hogy be van állítva a szervezeti hierarchiák.

A szervezeti hierarchiák segítségével több nézőpontból is megtekintheti vállalatát, és jelentést is készíthet róla. Például beállíthat egy hierarchiát adózási, jogi, illetve kötelezően előírt jelentésekhez. Utána beállíthat egy másik hierarchiát olyan pénzügyi információkat tartalmazó jelentéshez, mely jogilag nem kötelező, de a belső jelentésekhez használható.

A szervezeti hierarchia létrehozása előtt létre kell hoznia a szervezeteket. További tudnivalókért lásd a [Jogi személyek létrehozása](channels-legal-entities.md) vagy [Üzemi egységek létrehozása](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json) feladatokat.


A további tudnivalókat lásd a következő cikkekben.
- [Szervezetek és szervezeti hierarchiák áttekintése](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [Szervezeti hierarchia megtervezése](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [Szervezeti hierarchia létrehozása](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a>Szervezeti hierarchia létrehozása

A szervezeti hierarchia létrehozásához kövesse az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Szervezeti hierarchiák** részhez.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Név** mezőben adjon meg egy értéket.
1. A **Cél** területen kattintson a **Cél hozzárendelése** elemre.
1. Keresse meg és jelölje ki a kívánt rekordot a listán. Cél kiválasztása a szervezeti hierarchia hozzárendeléséhez.
1. A **Hozzárendelt hierarchiák** szakaszban kattintson a **Hozzáadás** gombra.
1. A listában jelölje meg a kiválasztott sort. A most létrehozott hierarchia keresése.
1. Válassza ki az **OK** lehetőséget.

A következő kép egy fiktív "Adventure Works" üzletcsoport számára létrehozott példa szervezeti hierarchiát mutat be.

![Szervezeti hierarchia – példa.](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a>Szervezetek felvétele a hierarchiába

A szervezetek hierarchiához való hozzáadásához kövesse az alábbi lépéseket.

1. Keresse meg és jelölje ki a kívánt rekordot a listán. A hierarchia kiválasztása.
1. A műveleti ablaktáblán válassza a **Megtekintés** lehetőséget.
1. Szükség szerint adjon hozzá szervezeteket.
1. Szervezet hozzáadásához válassza a **Szerkesztés** parancsot, majd válassza a **Beszúrás** parancsot. Amikor befejezte a módosításokat elmentheti a vázlatot és közzé teheti a módosításokat.

A következő kép azt jeleníti meg, hogy milyen jogi személy van hozzáadva a hierarchia gyökerében, négy költséghely hozzáadásával a "Áruház", "Kifutó", "online" és a "Hívásközpont" csatornákhoz. Ezután a különböző kiskereskedelmi, hívásközponti és online csatornák mindegyikhez hozzáadhatók.

![Hierarchiatervező – példa.](media/hierarchy-designer.png)

## <a name="additional-resources"></a>További erőforrások

[Szervezetek és szervezeti hierarchiák áttekintése](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Szervezeti hierarchia megtervezése](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Jogi személyek létrehozása](channels-legal-entities.md)

[Üzemi egységek létrehozása](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[Csatornák áttekintése](channels-overview.md)

[Csatornák beállításának előfeltételei](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
