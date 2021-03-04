---
title: Rendelési művelet visszahívása a pénztárban
description: Ez a témakör a pénztárban található, továbbfejlesztett rendelés-visszahívási oldalak kiemelt funkcióit ismerteti.
author: hhainesms
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 42b11ff16757d633b868dfdf248341193a44378f
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665298"
---
# <a name="recall-order-operation-in-pos"></a>Rendelési művelet visszahívása a pénztárban

[!include [banner](includes/banner.md)]

A Commerce pénztárban (POS) elérhető **Rendelés-visszahívási** művelet frissített rendeléskeresési és -szűrési funkciókat, valamint rendeléshez kapcsolódó információkat nyújt. Ez a funkció a 10.0.15-ös vagy újabb verziójú Commerce modulban elérhető.

A funkció engedélyezéséhez kapcsolja be a **Továbbfejlesztett rendelés-visszahívási művelet a pénztárban** funkciót a Commerce központban található **Funkciókezelés** munkaterületen. Miután engedélyezte a funkciót, esetleg frissítse a [képernyő-elrendezéseket](pos-screen-layouts.md) a pénztárban a módosított képességek előnyeinek kihasználása érdekében.

A **Rendelés-visszahívás** művelet gombjának konfigurálásával a szervezetek előre meghatározott megjelenítéssel telepíthetik a műveletet.

![Gombrács konfigurálása](media/recallorderbuttongrid.png)

A megjelenítés beállítási lehetőségei a következők:
- **Nincs** – Ezzel a beállítással a művelet speciális megjelenítés nélkül telepíthető. Amikor egy felhasználó ezzel a konfigurációval nyitja meg a műveletet, a program felkéri, hogy keressen megrendeléseket vagy válasszon egy előre definiált rendelésszűrőből.
- **Teljesítendő megrendelések** – Amikor a felhasználó elindítja a műveletet, a lekérdezést automatikusan futtatja a rendszer, valamint megjeleníti az áruház által teljesítendő megrendelések listáját. Ezeket a rendeléseket áruházon belüli felvételre vagy az áruház általi szállításra konfigurálták, és az ilyen rendelések sorai még kerültek összeszedésre vagy becsomagolásra.
- **Összeszedendő megrendelések** – Amikor a felhasználó elindítja a műveletet, a lekérdezést automatikusan futtatja a rendszer, valamint megjeleníti a felhasználó aktuális áruházában való összeszedésre konfigurált megrendelések listáját.
- **Szállítandó megrendelések** – Amikor a felhasználó elindítja a műveletet, a lekérdezést automatikusan futtatja a rendszer, valamint megjeleníti a felhasználó aktuális áruházából való szállításra konfigurált megrendelések listáját.

A **Rendelés-visszahívás** művelet pénztárból való elindításakor, ha a képernyőt **Nincs** beállításra konfigurálták, akkor a felhasználó a következő módokon keresheti meg és kérdezheti le a rendeléseket.
- Rendelésvonalkódok beolvasása. E művelet során rendelésszám, csatornahivatkozás és nyugtaazonosító mezőkben futtat keresést a rendszer.
- Válassza ki a **Rendelések keresése** vagy **Keresés és szűrése** ikont az AppBar felületen, hogy a szűrési mechanizmus segítségével megkeresse azokat a rendeléseket, amelyek megfelelnek a szűrési feltételeknek.
- Előre definiált szűrőkből választhat a **Rendelések megjelenítése** legördülő listából (teljesítendő rendelések, összeszedendő rendelések vagy szállítandó rendelések).

![RecallOrderMainMenu](media/recallordermain.png)

A keresési feltételekkel végzett keresés után az alkalmazás megjeleníti az egyezést mutató értékesítési rendeléseket.

![RecallOrderDetail](media/orderrecalldetail.png)

A felhasználó kiválaszthat a listán egy rendelést, és megtekintheti a további részleteket. A képernyő jobb oldalán látható információs ablak a kiválasztott rendelés részleteit jeleníti meg, többek között a rendelési sor adatait, a szállítási adatokat és a teljesítési adatokat.

Az AppBar felületen a felhasználó kiválaszthat egy műveletet. A rendelés állapotától függően előfordulhat, hogy bizonyos műveletek nem engedélyezettek.

- **Visszáru** – Visszáruzást hajt végre a kiválasztott vevői rendeléshez kapcsolódó egy vagy több számlához.

- **Visszavonás** – A kiválasztott értékesítési rendelés teljes visszavonásának elrendelése.

- **Teljesítés** – A felhasználót a rendelés teljesítése oldalra vezeti át, amely a kiválasztott rendelésnek megfelelő előzetesen szűrten jelenik meg. Csak azok a rendeléssorok jelennek meg, amelyek a kijelölt rendelésnek a felhasználó áruháza általi teljesítése céljából nyitottak.

- **Szerkesztés** – Lehetővé teszi a felhasználók számára a kiválasztott vevői rendelés módosítását.

- **Összeszedés** – Elindítja az összeszedési folyamatot, amellyel a felhasználó kiválaszthatja az összeszedendő termékeket, és létrehozza az összeszedési értékesítési tranzakciót.


[!INCLUDE[footer-include](../includes/footer-banner.md)]