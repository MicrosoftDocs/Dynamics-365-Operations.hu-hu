---
title: Készletütemezés
description: Ez a témakör a Készletütemezés lapról és annak képességeiről nyújt tájékoztatást.
author: crytt
ms.date: 9/3/2021
ms.topic: article
ms.search.form: ReqSupplyDemandSchedule, ReqSupplyDemandScheduleFilters, ReqSupplyDemandItemDetails, ReqTransFuturesActionsPart, ReqSupplyDemandOverviewLegendPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0760fcd5408d3960dcc55f773b4e09efc3c9f81c
ms.sourcegitcommit: 99bde425ade701ef244c6bca6d411aef94a59b3c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/20/2021
ms.locfileid: "7505575"
---
# <a name="supply-schedule"></a>Készletütemezés

[!include [banner](../includes/banner.md)]

A **Készletütemezés** lapon átfogó áttekintést kaphat egy termék vagy termékcsalád készletéről és keresletéről. A program hely, alapterv és időszakok szerint szűri az adatokat. Ez a lap használható új rendelések létrehozására, a meglévő tervezett rendelések módosítására és az alaptervezés futtatására is.

## <a name="open-the-supply-schedule-page"></a>A Készletütemezés lap megnyitása

A **Készletütemezés** lapot a következőképpen nyithatja meg:

- Ugorjon az **Alaptervezés \> Alaptervezés \> Készletütemezés** pontra. A **Szűrő módosítása** párbeszédpanelen adja meg a tervet és terméket, amelyet keres, ehhez a megadott mezőkbe írja be a szűrőértékeket. (A témakör többi részében a megadott szűrőértékek gyűjteményét "szűrőnek" vagy "aktuális szűrőnek" nevezzük.) Ha végzett, kattintson az **OK** gombra.
- Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre. Jelöljön ki vagy nyisson meg egy terméket. Ezután a műveleti ablaktáblán a **Terv** lapján a **Nézet** csoportban válassza a **Készletütemezés** lehetőséget.
- Lépjen az **Alaptervezés \> Beállítása \> Igény-előrejelzés \> Cikkhozzárendelési-kulcsok** részre. Válassza ki azt a cikkhozzárendelési kulcsot, amely termékcsaládként használatos. Majd Műveleti ablaktáblán válassza ki a **Készletütemezés** lehetőséget.
- Ugorjon az **Alaptervezés \> Alaptervezés \> Tervezett rendelések** pontra. Válasszon ki vagy nyisson meg egy tervezett rendelést. Ezután a műveleti ablaktáblán a **Nézet** lapon a **Nézet** csoportban válassza a **Készletütemezés** lehetőséget.

> [!NOTE]
> Ha egy termékből, termékcsaládból vagy tervezett rendelésből nyitja meg a **Készletütemezés** lapot, akkor nem kell szűrőértékeket megadnia. A rendszer az alapértelmezett időszaksablont fogja használni.

## <a name="use-the-supply-schedule-page"></a>A Készletütemezés lap használata

A **Készletütemezés** lap egy felső szakaszból, az **Időszak vége készlet** gyorslapból, valamint egy további gyorslapból áll, amely a felső szakaszban kiválasztott sor és az Adatterület ablak alapján láthatóvá válik. (Az Adatterület ablak megnyitásához és az Adatterület megtekintéséhez válassz a **Kapcsolódó információk** lehetőséget a lap jobb szélén.)

### <a name="upper-section"></a>Felső szakasz

A **Készletütemezés** lap felső része egy rácsot tartalmaz, amely a következő adatokat jeleníti meg egy termékhez vagy termékcsaládhoz. Ezt az adatot a szűrőből az **Időszak sablon** értéke által meghatározott időszakokra bontja a rendszer.

- **Időszaki kezdőkészlet** – Ez a sor a várható készletegyenleget mutatja az időszak elején, ha a rendszerben minden rendelésre megtörténik.
- **Időszaki befejező készlet** – Ez a sor a várható készletegyenleget mutatja az időszak végén, ha a rendszerben minden rendelésre megtörténik.
- **Időszak végi rögzített készlet** – Ez a sor a készletmennyiséget jeleníti meg az időszak végén, amely rögzítve van a jövőbeni igény szerint.
- **Időszak nettó készlete** – Ez a sor az adott időszakban a készlet és a kereslet közötti különbséget mutatja.
- **Minimális készlet** – Ez a csomópont mutatja egy termék vagy termékcsalád biztonsági készletét. A csomópont kibontásához vagy összecsukásához jelölje ki a csomópontot, majd válassza az eszköztár **Kibontás** vagy **Összecsukás** elemét. Ez a csomópont csak akkor látható, ha a termékhez vagy termékcsaládhoz van biztonsági készlet.
- **Kereslet** – Ez a csomópont egy termék vagy termékcsalád iránti keresletet jeleníti meg. A kereslet tranzakciótípus szerint van csoportosítva. A csomópont kibontásához vagy összecsukásához jelölje ki a csomópontot, majd válassza az eszköztár **Kibontás** vagy **Összecsukás** elemét. Az igénytranzakció-típusok az értékesítéseket, átvitelek és készletnaplókat is tartalmazzák. Ez a csomópont csak akkor látható, ha a termékhez vagy termékcsaládhoz van igény.
- **Készlet** – Ez a csomópont egy termék vagy termékcsalád készletét jeleníti meg. A készlet tranzakciótípus szerint van csoportosítva. A csomópont kibontásához vagy összecsukásához jelölje ki a csomópontot, majd válassza az eszköztár **Kibontás** vagy **Összecsukás** elemét. Az készlettranzakció-típusok a termelés, a beszerzés és az átvitelek. Ez a csomópont csak akkor látható, ha a termékhez vagy termékcsaládhoz van készlet.

A rendelkezésre álló eszköztárgombok, adatterület-kijelzők és gyorslap-kijelzések megjelenítése a felső részben kiválasztott beállításoktól függnek. A tranzakciótípust jellemzően az **Ellátás** vagy **Igény** csomópont alatti sorok egyikének kiválasztásával lehet kiválasztani. Ezt követően úgy választhatja ki az időszakot, hogy kiválaszt egy adott oszlopot a kiválasztott sorhoz.

Az **Készletütemezés** lap felső szakaszában található rács fölötti eszköztár a következő gombokat kínálja:

- **Kibontás/összecsukás** – A kijelölt csomópont kibontása vagy összecsukása, például az **Igény** csomópont, a **Ellátás** csomópont és az alcsomópontjaik. (A csomópontok egy **\[+\]** vagy **\[-\]** több előtaggal jelzik, hogy éppen összecsukva vagy kibontva vannak.)
- **Új** – egy menü megnyitása, ahol minden parancs egy párbeszédpanelt vagy lapot nyit meg, lehetővé teszi meghatározott típusú elem hozzáadását a kiválasztáshoz. A rendelkezésre álló parancsok közé tartozik az **Előrejelzett ellátás**, a **Tervezett rendelés**, az **Ütemezett kanban**, az **Új termelési rendelés**, a **Beszerzési rendelés** és az **Átmozgatási rendelés**.
- **Alaptervezés** – Alaptervezés futtatása. Megjelenik egy párbeszédpanel, ahol megadhatja a futtatás tervét. Alapértelmezett módon az **Alaptervezés** mező értéke megfelel az aktuális szűrőnek.
- **Max. készként jelentés** – Az aktuális szűrőben meghatározott termék **Max. készként jelentés** oldalának megnyitása.
- **Tervezett rendelések frissítése** – megnyitja a **Tervezett rendelések** lapot, amely az aktuális szűrőben meghatározott termék vagy termékcsalád tervezett rendeléseit jeleníti meg.
- **Szint** – a tervezett rendelések terjesztése a megjelenő párbeszédpanel beállításainak megfelelően.
- **Anyagterv-irányelv hely szerint** – megnyitja az aktuális szűrőben definiált termék **cikkfedezet** lapját.
- **Kanban szabály** – Megnyitja az aktuális szűrőben meghatározott termék **Kanban szabályok** lapját.

### <a name="fasttabs"></a>Gyorslapok

A **Készletütemezés** lap a következő gyorslapokat tartalmazhatja:

- **Időszak végi készlet** – Ez a gyorslap grafikus formában jeleníti meg az időszak végi készletadatokat.
- **Készletprofil** – Ez a Gyorslap grafikus formátumban jeleníti meg a készletadatokat. Akkor válik láthatóvá, ha a felső szakaszban kiválaszt egy **Ellátás** csomópontot vagy az alatta lévő sort.
- **Összegzés** – Ez a gyorslap a felső szakaszban kiválasztott tranzakciótípussal kapcsolatos összesítő részleteket jeleníti meg. Ha például az **Igény** csomópont alatt az **Értékesítés** lehetőséget választja, ez a gyorslap az értékesítési rendelésekhez kapcsolódó mezőket jeleníti meg, például **Kért értékesítésirendelés-sorok** vagy **Teljes összeg**. Ha a **Termelési rendelések** lehetőséget választja a **Termelés** csomópont **Ellátás** alcsomópontja alatt, ez a gyorslap a termelési rendelésekhez kapcsolódó mezőket jeleníti meg, például az **Ütemezett termelési rendeléseket** vagy az **Összesen ütemezett** mezőt. A mezőértékek a felső szakaszban kiválasztott időszaktól függenek. 
- **\[Tranzakciótípus\] - \[Időszak\]** – Ez a gyorslap a felső szakaszban kiválasztott tranzakciótípushoz és időszakhoz kapcsolódó rendeléseket jeleníti meg. A gyorslap neve tükrözi ezeket a beállításokat. Lehet például, hogy **Értékesítési rendelések - Tartalék** vagy a **Termelési rendelések – 37. hét**.

### <a name="action-pane"></a>Műveleti panel

Az alábbi gombok érhetők el a Műveleti panelen:

- **Szűrő módosítása** – megnyitja a **Szűrő módosítása** párbeszédpanelt, ahol frissítheti a szűrőértékeket, majd újra megnyithatja a **Készletütemezés** lapot, amely a frissített szűrőbeállításokat tükrözi.
- **Késések megjelenítése** – Jelölje ki a megfelelő sorokat a felső szakaszban, ha az adott tranzakciótípushoz késleltetett rendelés tartozik.

### <a name="factbox-pane"></a>Adatterület panel

Az Adatterület ablak megnyitásához és az Adatterület megtekintéséhez válassz a **Kapcsolódó információk** lehetőséget a lap jobb szélén. A **Készletütemezés** lapon a következő adatterületek érhetők el:

- **Cikk részletei** – Ez az adatterület az aktuális szűrőben meghatározott termék alapvető adatait jeleníti meg. Üres, ha a szűrőben termékcsalád van meghatározva.
- **Műveletek** – Ez az adatterület a felső szakaszban kiválasztott tranzakciótípushoz kapcsolódó rendelések műveleteit jeleníti meg.
- **Késedelmek** – Ez az adatterület a felső szakaszban kiválasztott tranzakciótípushoz kapcsolódó rendelések késedelmeit jeleníti meg.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
