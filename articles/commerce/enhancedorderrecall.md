---
title: Rendelési művelet visszahívása a pénztárban
description: Ez a cikk bemutatja a POS továbbfejlesztett rendelés-visszahívási lapjaihoz rendelkezésre álló funkciókat.
author: hhainesms
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 0624c251646110644a8a72658a6dd6f8d319c57f
ms.sourcegitcommit: e25fe4228add88dd37f4f38ece86979e1c621f6a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2022
ms.locfileid: "9734294"
---
# <a name="recall-order-operation-in-pos"></a>Rendelési művelet visszahívása a pénztárban

[!include [banner](includes/banner.md)]

A Commerce pénztárban (POS) elérhető **Rendelés-visszahívási** művelet frissített rendeléskeresési és -szűrési funkciókat, valamint rendeléshez kapcsolódó információkat nyújt. Ez a funkció a 10.0.15-ös vagy újabb verziójú Commerce modulban elérhető.

A funkció engedélyezéséhez kapcsolja be a **Továbbfejlesztett rendelés-visszahívási művelet a pénztárban** funkciót a Commerce központban található **Funkciókezelés** munkaterületen. Miután engedélyezte a funkciót, esetleg frissítse a [képernyő-elrendezéseket](pos-screen-layouts.md) a pénztárban a módosított képességek előnyeinek kihasználása érdekében.

A **Rendelés-visszahívás** művelet gombjának konfigurálásával a szervezetek előre meghatározott megjelenítéssel telepíthetik a műveletet.

![Gombrács konfigurálása.](media/recallorderbuttongrid.png)

A megjelenítés beállítási lehetőségei a következők:
- **Nincs** – Ezzel a beállítással a művelet speciális megjelenítés nélkül telepíthető. Amikor egy felhasználó ezzel a konfigurációval nyitja meg a műveletet, a program felkéri, hogy keressen megrendeléseket vagy válasszon egy előre definiált rendelésszűrőből.
- **Teljesítendő megrendelések** – Amikor a felhasználó elindítja a műveletet, a lekérdezést automatikusan futtatja a rendszer, valamint megjeleníti a felhasználó aktuális áruháza által teljesítendő megrendelések listáját. Ezeket a rendeléseket áruházon belüli felvételre vagy az áruház általi szállításra konfigurálták, és az ilyen rendelések sorai még kerültek összeszedésre vagy becsomagolásra.
- **Összeszedendő megrendelések** – Amikor a felhasználó elindítja a műveletet, a lekérdezést automatikusan futtatja a rendszer, valamint megjeleníti a felhasználó aktuális áruházában való összeszedésre konfigurált megrendelések listáját.
- **Szállítandó megrendelések** – Amikor a felhasználó elindítja a műveletet, a lekérdezést automatikusan futtatja a rendszer, valamint megjeleníti a felhasználó aktuális áruházából való szállításra konfigurált megrendelések listáját.

A **Rendelés-visszahívás** művelet pénztárból való elindításakor, ha a képernyőt **Nincs** beállításra konfigurálták, akkor a felhasználó a következő módokon keresheti meg és kérdezheti le a rendeléseket.
- Rendelésvonalkódok beolvasása. E művelet során rendelésszám, csatornahivatkozás és nyugtaazonosító mezőkben futtat keresést a rendszer.
- Válassza ki a **Rendelések keresése** vagy **Keresés és szűrése** ikont az AppBar felületen, hogy a szűrési mechanizmus segítségével megkeresse azokat a rendeléseket, amelyek megfelelnek a szűrési feltételeknek.
- Előre definiált szűrőkből választhat a **Rendelések megjelenítése** legördülő listából (teljesítendő rendelések, összeszedendő rendelések vagy szállítandó rendelések).

![RecallOrderMainMenu.](media/recallordermain.png)

A keresési feltételekkel végzett keresés után az alkalmazás megjeleníti az egyezést mutató értékesítési rendeléseket. Fontos megjegyezni, hogy a keresési/szűrési beállítások használata esetén a beolvasni kívánt rendeléseknek nem kell a felhasználó aktuális üzletéhez kapcsolt rendeléseknek lenniük. Ez a keresési folyamat beolvassa és megjeleníti a keresési feltételeknek megfelelő vevői rendeléseket, még akkor is, ha a rendelést egy másik üzlet/csatorna vagy raktár hely által teljesítendőként hozták létre vagy állították be.

![RecallOrderDetail.](media/orderrecalldetail.png)

A felhasználó kiválaszthat a listán egy rendelést, és megtekintheti a további részleteket. A képernyő jobb oldalán látható információs ablak a kiválasztott rendelés részleteit jeleníti meg, többek között a rendelési sor adatait, a szállítási adatokat és a teljesítési adatokat.

Az AppBar felületen a felhasználó kiválaszthat egy műveletet. A rendelés állapotától függően előfordulhat, hogy bizonyos műveletek nem engedélyezettek.

- **Visszáru** – kezdeményezi a visszáru létrehozását a kiválasztott vevői rendelés számlázott termékeinek bármelyikéhez.

- **Visszavonás** – A kiválasztott értékesítési rendelés teljes visszavonásának elrendelése. Ez a beállítás nem érhető el hívásközponti csatornán keresztül kezdeményezett rendelésekhez, és nem használható a rendelések részben való törlésére.

- **Teljesítés** – A felhasználót a rendelés teljesítése oldalra vezeti át, amely a kiválasztott rendelésnek megfelelő előzetesen szűrten jelenik meg. Csak azok a rendeléssorok jelennek meg, amelyek a kijelölt rendelésnek a felhasználó áruháza általi teljesítése céljából nyitottak.

- **Szerkesztés** – Lehetővé teszi a felhasználók számára a kiválasztott vevői rendelés módosítását. A rendelések csak [bizonyos helyzetekben](customer-orders-overview.md#edit-an-existing-customer-order) szerkeszthetők.

- **Felvétel** – ez a lehetőség akkor érhető el, ha a rendelés egy vagy több sorát kijelölték felvételre a felhasználó aktuális üzletében. Ez a művelet elindítja a felvételi folyamatot, amellyel a felhasználó kiválaszthatja a felvenni kívánt termékeket, és létrehozza a felvételi értékesítési tranzakciót.

## <a name="add-notifications-to-the-recall-order-operation"></a>Értesítések hozzáadása a rendelés-visszahívási művelethez

A 10.0.18-as és újabb verziókban szükség esetén konfigurálhatja a pénztárértesítéseket és az élő csempe típusú riasztásokat a **Művelet visszahívása** művelethez. További információk: [Rendelési értesítések megjelenítése a pénztárnál](notifications-pos.md) (POS).  

> [!NOTE]
> A rendeléskeresési funkció engedélyezéséhez győződjön meg arról, **·** **hogy az Ajánlatok kulcs engedélyezve van a Licenckonfiguráció konfigurációs** > **kulcsai kulcs alatt**.
>
> ![Engedélyezni kell az Árajánlatok licenckulcs-konfigurációját.](./media/Quotations_License_Key_Configuration.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
