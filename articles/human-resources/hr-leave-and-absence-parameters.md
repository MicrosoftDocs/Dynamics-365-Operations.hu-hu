---
title: Szabadság- és távollétparaméterek konfigurálása
description: Ez a témakör azt írja le, hogyan lehet definiálni a szabadságra és távollétre vonatkozó emberi erőforrások paramétereit Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3a39c74eef3865c03ccb9dd5aa2fece7f25e639a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891379"
---
# <a name="configure-leave-and-absence-parameters"></a>Szabadság- és távollétparaméterek konfigurálása

>[!Important]
>Az ebben a cikkben említett funkciók jelenleg önálló vevők számára érhetők el Dynamics 365 Human Resources. A funkciók egy része vagy egésze a Finance infrastruktúra jövőbeni kiadásának részeként lesz elérhető a Finance 10.0.26-ös kiadása után.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Mielőtt beállít szabadság Dynamics 365 Human Resources- és távolléti terveket, **jó** lenne ellenőrizni az összes kapcsolódó emberierőforrás-paraméter beállításait, például a következőket:

- A szabadságkérelmek számsorozata
- Családi okból történő és a betegszabadságról szóló amerikai törvény (FMLA) beállításai
- Alkalmazotti önkiszolgáló rendszer beállításai a szabadság- és a távollétkérelmek esetében
- Szabadság- és távollétparaméterek

## <a name="view-and-change-human-resources-parameters"></a>Emberierőforrás-paraméterek megtekintése és módosítása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Beállítás** alatt válassza az **Emberierőforrás-paraméterek** lehetőséget.

3. A **Számsorozatok** lapon ellenőrizze, a **Számsorozat kódja** beálítást a **Szabadságkérelem azonosítója** esetében, és szükség szerint módosítsa. Ez a beállítás határozza meg a szabadságkérelmekhez automatikusan hozzárendelt azonosítókhoz használt sorrendet.

4. Az **FMLA** lapon ellenőrizze az FMLA beállításait, és szükség esetén módosítsa azokat.

5. Az **Alkalmazotti önkiszolgáló rendszer** lapon jelezze, hogy a vezetők az alkalmazottak nevében beírhatják-e a szabadság- és a távolléti kérelmeket .

7. Válassza a **Mentés** lehetőséget.

>[!IMPORTANT]
>A szabadság és a távollét megtekintése a vállalatok között jelenleg előzetes verzióban érhető el. Engedélyeznie kell azt a **Tesztkörnyezetben** a szabadság és távollét lehetőségének megjelenítéséhez. Az előzetes funkciók engedélyezésével kapcsolatos további részletekért tekintse meg a [Kezelési funkciók](hr-admin-manage-features.md) cikket.

## <a name="view-and-change-human-resources-shared-parameters"></a>A Human Resources megosztott paraméterek megtekintése és módosítása

1. A **Személyzetkezelés** oldalon válassza a **Hivatkozások** lapot.

2. A **Beállítás** alatt válassza a **Humán erőforrás megosztott paraméterek** lehetőséget.

3. Az **Előzetes hozzáférés** lapon válassza az **Igen** lehetőséget a **Vállalatközi szabadságnézet engedélyezése** elemnél, hogy a szabadság megtekinthető legyen a vállalatok között.

4. Válassza a **Mentés** lehetőséget.

## <a name="view-and-change-leave-and-absence-parameters"></a>Szabadság és távollét paramétereinek megtekintése és módosítása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Beállítás** területen válassza a **Szabadság- és távollétparaméterek** lehetőséget.

3. Az **Általános** lapon állítsa be a következő paramétereket:
 
    - A **Szabadság és távollét mértékegysége** elemet állítsa órára vagy napra. Ha a nap lehetőséget választja , akkor a **Félnapos meghatározás** engedélyezése beállítással lehetővé teheti az alkalmazottak számára, hogy a nap első vagy második felét válasszák ki távollét-kérelmeikben. 

    - Válassza a **Szolgálti hónapok az érvényeség dátumáig** kiválasztásával beállíthatja, hogy az elhatárolási mérték a szolgálati hónapok alapján befolyásolja a szabadságterveket.

    - Válassza az **Egyenleg számítása** lehetőséget, ha az egyenlegeket a mai napig vagy az elhatárolási időszakig szeretné megjeleníteni. Ha az **Egyenleg a mai napig** lehetőséget választja, akkor az egyenleg az összes elhatárolást, kiigazítást és kérelmet megjeleníti a mai napig. Ha az **Egyenleg az elhatárolási időszakig** lehetőséget választja, akkor az egyenleg az elszámolási időszak gyakorisága által meghatározott elhatárolási időszak összes elhatárolását, helyesbítését és kérését jeleníti meg. 

    - Az Áthozott **lejárati** kötegelt **feladat kezdési ideje**.  
    
    - Válassza az **Igen** lehetőséget a **Szabadság vásárlásnak engedélyezése az alkalmazottaknak** és **Szabadság eladásánek engedélyezése az alkalmazottaknak** lehetőségekhez. Ha ezekhez a lehetőségekhez az **Igen** értéket választja, akkor létrehozhat szabadságvásárlási és -eladási irányelveket, és lehetővé teszi az alkalmazottak számára, hogy vásároljanak és eladjanak a szabadságot.

## <a name="configure-calendar-parameters"></a>Naptárparaméterek karbantartása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Beállítás** területen válassza a **Szabadság- és távollétparaméterek** lehetőséget.

3. A **Naptár** lapon szükség szerint módosítsa a naptár beállításait.

4. Válassza a **Mentés** lehetőséget.

## <a name="see-also"></a>Lásd még

- [Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
