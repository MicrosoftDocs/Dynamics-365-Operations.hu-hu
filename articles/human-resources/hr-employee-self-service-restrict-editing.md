---
title: Személyes adatok szerkesztésének korlátozása
description: A kapcsolattartók részleteinek alkalmazottak általi szerkesztésének korlátozása a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c5e3eeb66d4f32b1fea1a43fff9f5b09d87d1f53
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018709"
---
# <a name="restrict-editing-of-personal-information"></a>Személyes adatok szerkesztésének korlátozása

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

Ez a témakör azt ismerteti, hogyan lehet korlátozni az alkalmazottak számára a kapcsolattartók részleteinek szerkesztését a Dynamics 365 Human Resources alkalmazásban. Előfordulhat, hogy meg szeretné akadályozni, hogy az alkalmazottak bizonyos kapcsolattartási adatokat, például az vállalati telephelyet vagy az e-mail-címet szerkeszthessenek.

> [!NOTE]
> A funkció használatához először engedélyeznie kell az **(Előzetes verzió) Alkalmazottak korlátozása a cím és kapcsolatfelvételi adatok hozzáadásánál és szerkesztésénél adott célok esetén** beállítást a Funkciókezelésben. Az előzetes funkciók aktiválásával kapcsolatos további részletekért tekintse meg a [Szolgáltatások kezelése](hr-admin-manage-features.md) oldalt.<br><br>![Előzetes funkció engedélyezése](./media/hr-employee-self-service-restrict-enable.png)

## <a name="choose-the-information-an-employee-can-add-or-edit"></a>Válassza ki az alkalmazott által hozzáadható vagy szerkeszthető információkat

1. A Human Resources szolgáltatásban válassza ki a **Személyzetkezelés** elemet , válassza ki a **hivatkozások** elemet, majd válassza ki a **emberi erőforrás paramétereit**.

   ![Lépjen a Humar Resources paramétereihez](./media/hr-employee-self-service-human-resources-parameters.png)

2. A **Human Resources paraméterei** oldalon válassza az **Alkalmazotti önkiszolgáló rendszer** lapot.

   ![Válassza az Alkalmazotti önkiszolgáló rendszer lehetőséget](./media/hr-employee-self-service-tab.png)

3. Az **Alkalmazotti önkiszolgáló rendszer** lapon törölje a jelet a **Cím- és kapcsolattartási adatok** szakaszösszes olyan információjának jelölőnégyzetéből, amelyet nem szeretne, ha az alkalmazottak hozzáadhatnának vagy szerkeszthetnének. Ebben a példában töröltük a jelet az **Üzleti** kapcsolattartói adatok jelölőnégyzetéből.

   ![Az üzleti kapcsolattartási adatok szerkesztésének korlátozása](./media/hr-employee-self-service-restrict-business.png)

4. Válassza a **Mentés** lehetőséget.

   ![Módosítások mentése](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a>Alkalmazotti felhasználói élmény

Miután korlátozta az alkalmazottak számára a kapcsolattartók részleteinek hozzáadását vagy szerkesztését, láthatják az adatokat, de nem módosíthatja őket.

Ebben a példában, ahol az alkalmazottak nem szerkeszthetik az **Üzleti** kapcsolattartási adatokat, továbbra is láthatják az adatokat az Alkalmazotti önkiszolgáló rendszerben:

![Üzleti kapcsolattartói részletek megtekintése](./media/hr-employee-self-service-restrict-view.png)

Amikor azonban kiválasztják az üzleti kapcsolattartó adatait, a **Cím szerkesztése** ablaktábla csak olvashatóként jelenik meg, és egyik mező sem módosítható.

![Az üzleti kapcsolattartó adatai csak olvashatóként jelennek meg](./media/hr-employee-self-service-restrict-read-only.png)

Emellett, ha a **Hozzáadás** gombot választják új cím hozzáadásához, akkor a **Cél** legördülő listában nem választhatják ki az **Üzleti** lehetőséget.

![Az alkalmazott nem tud Üzleti címet hozzáadni.](./media/hr-employee-self-service-restrict-add.png)

Az alkalmazottak ugyanezzel a viselkedéssel találkoznak, amikor kiválasztják a **Kapcsolattartó adatai** elemet a **Személyes adatok** lapon, és új címet adnak meg. A **Cél** legördülő lista csak azokat az információtípusokat jeleníti meg, amelyekhez hozzáadhatnak. 

![Az alkalmazott nem választhatja ki a Vállalkozás lehetőséget a Cél legördülő mezőben](./media/hr-employee-self-service-restrict-purpose.png)

A **Kapcsolattartó adatai** most a **Cél** értéket jeleníti meg a rácsban.

![A Cél jelenik meg a Kapcsolattartó adatai rácsban](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a>Lásd még

[Alkalmazotti és vezetői önkiszolgáló rendszer áttekintése](hr-employee-manager-self-service-overview.md)<br>
[A Human Resources paramétereinek konfigurálása](hr-setup-parameters.md)<br>
[Személyes információk szerkesztése](hr-employee-manager-self-service-edit-personal-information.md)