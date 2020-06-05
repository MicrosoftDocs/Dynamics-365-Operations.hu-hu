---
title: Forgatókönyv beállítása IoT Intelligencia esetén
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy forgatókönyvet a Supply Chain Management for IoT Intelligencia alkalmazásban.
author: robinarh
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b87a9b73f49e73fe13b98fb11da939c9b30e0f6e
ms.sourcegitcommit: 261b70ea358b2c231e20f320ed8bd6adc1e7d715
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/19/2020
ms.locfileid: "3386522"
---
# <a name="scenario-setup-for-iot-intelligence"></a>Forgatókönyv beállítása IoT Intelligencia esetén

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani egy forgatókönyvet a Supply Chain Management for IoT Intelligencia alkalmazásban. A forgatókönyvek beállítása előtt [be kell állítania az LCS-t](iot-lcs-setup.md).

Ebben a témakörben konfigurálni fogja a **Berendezés üzemkimaradása** forgatókönyvet, hogy értesítést hozzon létre a Supply Chain Management alkalmazásban, amikor egy gép leáll.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>A **Berendezés üzemkimaradása** forgatókönyv konfigurálása a Supply Chain Management alkalmazásban

A **Berendezés üzemkimaradása** forgatókönyv egy darabkimenet jelet rendel a gép figyelmeztetési küszöbértékéhez. A gépet csak akkor figyeli a program, ha a forgatókönyvhöz ki van választva a gép, és a Supply Chain Management alkalmazásban való futtatására van beállítva. Ha a géptől kapott utolsó darabkimeneti jel óta eltelt idő meghaladja a figyelmeztetési küszöbértéket, akkor a **Gép leállt** értesítés aktiválódik. Ha a gép továbbra is fut, akkor a következő **PartOut** jel fogadásakor a **Gép üzemel** értesítés aktiválódik. Ha egy gép 30 percen keresztül áll, egy új **Gép leállt** értesítés aktiválódik.

A **Berendezés üzemkimaradása** forgatókönyv az alábbi függőségekkel rendelkezik:

+ Egy termelési rendelésnek futnia kell egy leképezett gépen, hogy a figyelmeztetés aktiválódjon.
+ A hozzárendelt gép darabkiadási jelét jelképező jelet kell küldeni az IoT-központnak egyedit tulajdonságnévvel.
+ A Unix ezredmásodperces időbélyegnek szerepelnie kell az IoT-központnak küldött üzenetben.

A forgatókönyv konfigurálásához tegye a következőket:

1. Jelentkezzen be a Supply Chain Management alkalmazásba.
2. Engedélyezze az IoT Intelligencia funkció jelzőjét. További tájékoztatás: [Funkciókezelés – áttekintés](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
3. Konfigurálja a mutatókat. További információ: [Mutatók konfigurálása](iot-metrics-setup.md#configure-metrics).
4. Nyissa meg a **Gyártásvezérlés** részt.
5. Keresse meg a **Beállítás \> IoT Intelligencia \> Forgatókönyvek kezelése** beállítást.
6. Kattintson a **Konfigurálás** lehetőségre a **Berendezés üzemkimaradása** csempe alatt. A konfiguráló varázsló a elindítja a **Berendezés érzékelősémájának meghatározása** oldalt. A cél a Supply Chain Management sémájának beállítása, hogy megfeleljen az IoT-üzenetek JSON-formátumának. Több üzenetséma is definiálható. További tájékoztatás: [IoT-központ üzenetséma-formátumai](iot-schema-format.md). Ebben a példában az üzenet tartalma olyan üzenetköteget tartalmaz, amelyekben ilyen formátumú üzenetek szerepelnek:

    ```json
    {
        "timestamp": 1576016821614,
        "payload": [
            {
                "id": "IoTInt.Machine1225.PartOut",
                "timestamp": 1576016821614,
                "value": True
            },
            {
                "id": "IoTInt.Machine1226.PartOut",
                "timestamp": 1576016991616,
                "value": True
            }
        ]
    }
    ```

7. Adjon hozzá egy sort a táblához.

    1. A **Séma neve** beállítást állítsa **Azonosító** értékre.
    2. A **Séma útvonala** beállítást állítsa **/payload[\*]/id** értékre.
    3. A **Leírás** számára adja meg az **Üzenet azonosítója** értéket.

8. Adjon hozzá egy sort a táblához.

    1. A **Séma neve** beállítást állítsa **Időbélyeg** értékre.
    2. A **Séma útvonala** beállítást állítsa **/payload[\*]/timestamp** értékre.
    3. A **Leírás** számára adja meg az **Üzenet időbélyege** értéket.

9. Adjon hozzá egy sort a táblához.

    1. A **Séma neve** beállítást állítsa **Érték** értékre.
    2. A **Séma útvonala** beállítást állítsa **/payload[\*]/value** értékre.
    3. A **Leírás** számára adja meg az **Üzenet értéke** értéket.

    Nem kell megadnia az üzenet összes tulajdonságát, csak a szükségeseket. Ebben a példában nem hozott létre sort a **Gyökér időbélyege** számára. A **Gyökér időbélyege** útvonala **/timestamp** lenne.
  
10. Kattintson a **Következő** gombra a **Berendezés érzékelősémájának leképezése** oldalra lépéshez.
11. A **Berendezés erőforrás-azonosítója** sorban állítsa a **Séma neve** beállítást **Azonosító** értékre. Az érvényes értékek a legördülő táblázatban láthatók.
12. Az **UTC idő** sorában állítsa a **Séma neve** beállítást **Időbélyeg** értékre. Az érvényes értékek a legördülő táblázatban láthatók.
13. A **Legyártott darab jel** sorban állítsa a **Séma neve** beállítást **Érték** értékre. Az érvényes értékek a legördülő táblázatban láthatók.
14. Kattintson a **Következő** gombra a **Berendezés erőforrás-azonosítójának konfigurációja** oldalon.
15. Ebben a lépésben az IoT-központ üzenetének értékeit képezi le a Supply Chain Management erőforrásaira.

    1. A **Jeladatok értékei** táblázatban adjon hozzá egy új sort, és adja meg az **IoTInt.Machine1225.PartOut** értéket az **Érték** oszlopban. Az **IoTInt.Machine1225.PartOut** érték az IoT-központ üzenetének JSON **azonosító** tulajdonságából származik.
    2. Kattintson a **Mentés** gombra.
    3. Az **Üzleti rekord leképezése** táblában kattintson az **Új** elemre. Az **Üzleti rekordtípus** alapértelmezett értéke automatikusan ki van töltve, és nem szükséges módosítani azt.
    4. Válassza ki az **Üzleti rekord** oszlopban azt a Supply Chain Management géperőforrást, amelyből ez a jel elküldésre került.
    5. Kattintson a **Mentés** gombra.
    6. Ismételje meg ezeket a lépéseket, és adjon hozzá egy új üzletirekord-hozzárendelést a **Machine1226** esetében. A Supply Chain Management egyetlen rekordjához több jeladatértéket rendelhet hozzá.

16. A **Kiválasztott** oszlopban kiválaszthatja, hogy melyik gépeket szeretné feldolgozni. Nem kell minden jelértéket megadni, és nem kell kijelölnie az összes gépet.
17. Kattintson a **Következő** gombra a **Legyártott darab jel konfigurációja** oldalon.
18. A **Jeladatok értékei** táblában adjon hozzá egy sort, és adja meg az **Érték** számára az **Igaz** értéket. Az **Igaz** érték az IoT-központ üzenetének JSON **érték** tulajdonságából származik. A forgatókönyvéhez annyi értéket adhat hozzá, amennyit csak szükséges.
19. Kattintson a **Mentés** gombra.
20. Kattintson a **Következő** gombra a **Berendezés üzemkimaradásának küszöbértéke** oldalra lépéshez. A felsorolt gépek a korábban a jelértékekre leképezett gépek. Ebben a lépésben meghatároz egy küszöbértéket annak meghatározására, hogy a gép áll-e. Ha például a küszöb 10 értékre van állítva, akkor a Supply Chain Management egy értesítést generál, ha a gépről 10 percig nem érkezik darabkiadási üzenet.
21. Kattintson a **Következő** lehetőségre a **Forgatókönyv engedélyezése** oldalra lépéshez. Kapcsolja át a csúszkát a forgatókönyv engedélyezéséhez.
22. Kattintson a **Befejezés** gombra.

A forgatókönyv beállítása befejeződött. Az IoT Intelligencia automatikusan elindítja a IoT-központ üzeneteinek feldolgozását.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>A **Termékminőség** forgatókönyv konfigurálása a Supply Chain Management alkalmazásban

A **Termékminőség** forgatókönyv értesítést generál, ha egy cikk egyik attribútuma kívül esik a megadott tartományon. Egy érzékelő például elküldheti az egyes cikkek súlyát az IoT-központhoz. A Supply Chain Management alkalmazásban egy értesítés jön létre, ha a cikk túl nehéz vagy túl könnyű.

A forgatókönyv a következő függőségekkel rendelkezik:

+ A termelési rendelésnek egy leképezett gépen kell futnia, és egy olyan terméket kell előállítania, amely leképezett kötegattribútummal rendelkezik egy értesítés aktiválásához.
+ A kötegattribútumot jelképező jelet kell küldeni az IoT-központnak egyedit tulajdonságnévvel.
+ A Unix ezredmásodperces időbélyegnek szerepelnie kell az IoT-központnak küldött üzenetben.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>A **Termelési késések** forgatókönyv konfigurálása a Supply Chain Management alkalmazásban

A **Termelési késések** forgatókönyv értesítést generál, ha a termelési teljesítmény egy küszöbérték alá esik. Ebben a forgatókönyvben a **PartOut** jelet a rendszer elküldi az IoT-központhoz minden egyes legyártott tételnél. A Supply Chain Management alkalmazásban a rendelési késés a termelési rendelés ütemezett futási idejének hossza, a termelni kívánt darabszám, a feladat eltelt futásideje és a fogadott **PartOut** jelek száma alapján kerül kiszámításra. Ha a feladathoz tartozó **PartOut** jelek száma nem éri el a várt érték küszöbértékét, akkor egy késési értesítés jön létre.

A forgatókönyv a következő függőségekkel rendelkezik:

+ Egy termelési rendelésnek futnia kell egy leképezett gépen, hogy a figyelmeztetés aktiválódjon.
+ A hozzárendelt gép darabkiadási jelét jelképező jelet kell küldeni az IoT-központnak egyedit tulajdonságnévvel.
+ A Unix ezredmásodperces időbélyegnek szerepelnie kell az IoT-központnak küldött üzenetben.

## <a name="how-to-disable-a-scenario"></a>Forgatókönyv letiltása

Kövesse az alábbi lépéseket a forgatókönyv letiltásához:

1. A Supply Chain Management alkalmazásban lépjen a **Gyártásvezérlés \> Beállítás \> IoT Intelligencia \> Forgatókönyvek kezelése** lehetőségre.
2. Kattintson a forgatókönyv **Konfigurálás** lehetőségére.
3. Kattintson a **Következő** gombra a varázsló utolsó lapjára lépéshez.
4. Kapcsolja át a csúszkát a forgatókönyv letiltásához.
