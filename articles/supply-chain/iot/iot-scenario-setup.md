---
title: Forgatókönyv beállítása IoT Intelligencia esetén
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a IoT-intelligencia forgatókönyveit a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.
author: robinarh
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 36be4a85dbbd28839afd45b6ed167b4c8181ae72
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909501"
---
# <a name="scenario-setup-for-iot-intelligence"></a>Forgatókönyv beállítása IoT Intelligencia esetén

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani a IoT-intelligencia forgatókönyveit a Microsoft Dynamics 365 Supply Chain Management alkalmazásban. A forgatókönyvek helyek beállítása előtt [be kell állítania a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatást](iot-lcs-setup.md).

Ebben a témakörben konfigurálni fogja a **Berendezés üzemkimaradása** forgatókönyvet, hogy értesítést hozzon létre a Supply Chain Management alkalmazásban, amikor egy gép leáll. A témakör bemutatja, hogy hogyan lehet beállítani a **Termékminőség** esetet, hogy az értesítés jöjjön létre, ha a cikk egy attribútuma egy megadott tartományon kívülre esik, és hogyan kell beállítani a **Termelési késések** esetet, ha a termelési teljesítmény egy küszöbérték alá esik.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>A Berendezés üzemkimaradása forgatókönyv konfigurálása a Supply Chain Management alkalmazásban

A **Berendezés üzemkimaradása** forgatókönyv egy **PartOut** jelet rendel a gép figyelmeztetési küszöbértékéhez. A gépet csak akkor figyeli a program, ha a forgatókönyvhöz ki van választva, és a beállítása **Fut** a Supply Chain Management alkalmazásban. Ha a géptől kapott utolsó **PartOut** jel óta eltelt idő meghaladja a figyelmeztetési küszöbértéket, akkor a **Gép leállt** értesítés aktiválódik. Ha a gép továbbra is fut, akkor a következő **PartOut** jel fogadásakor a **Gép üzemel** értesítés aktiválódik. Ha egy gép 30 percen keresztül áll, egy új **Gép leállt** értesítés aktiválódik.

A **Berendezés üzemkimaradása** forgatókönyv a következő függőségekkel rendelkezik:

+ Egy termelési rendelésnek futnia kell egy leképezett gépen, hogy a figyelmeztetés aktiválva legyen.
+ A hozzárendelt gép **PartOut** jelét jelképező jelet kell küldeni az IoT-központnak egyedi tulajdonságnévvel.
+ Egy UNIX **időbélyegző** tulajdonságnak, ahol az érték ezredmásodpercben (ms) van kifejezve, jelen kell lennie az Azure IoT Hub üzenetben.

A forgatókönyv konfigurálásához tegye a következőket.

1. Jelentkezzen be a Supply Chain Management alkalmazásba.
2. Engedélyezze az IoT Intelligencia funkció jelzőjét. További tájékoztatás: [Funkciókezelés – áttekintés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
3. Konfigurálja a mutatókat. További információ: [Mutatók konfigurálása](iot-metrics-setup.md#configure-metrics).
4. Nyissa meg a **Gyártásvezérlés \> Beállítások \> IoT-intelligencia \> Forgatókönyvek kezelése** lehetőséget.
6. A beállítási varázsló megnyitásához Kattintson a **Konfigurálás** lehetőségre a **Berendezés üzemkimaradása** csempe alatt.

   A konfiguráló varázsló a első lapja a **Berendezés érzékelősémájának meghatározása** lap. Ezen a lapon a célja a séma beállítása a Supply Chain Management alkalmazásban, hogy az megfeleljen az IoT Hub-üzenetek JavaScript Object Notation (JSON) formátumának. Több üzenetséma is definiálható. További tájékoztatás: [IoT Hub-üzenetek sémaformátumai](iot-schema-format.md). Ebben a példában az üzenet tartalma olyan üzenetköteget tartalmaz, amelyek formátuma a következő.

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

7. Adjon hozzá egy sort a táblához, és állítsa be a következő értékeket:

    1. A **Séma neve** mezőt állítsa **Azonosító** értékre.
    2. A **Séma útvonala** mezőt állítsa **/payload\[\*\]/id** értékre.
    3. A **Leírás** mezőben adja meg az **Üzenet azonosítója** értéket.

8. Adjon hozzá még egy sort a táblához, és állítsa be a következő értékeket:

    1. A **Séma neve** mezőt állítsa **Időbélyeg** értékre.
    2. A **Séma útvonala** mezőt állítsa **/payload\[\*\]/timestamp** értékre.
    3. A **Leírás** mezőben adja meg az **Üzenet időbélyege** értéket.

9. Adjon hozzá még egy sort a táblához, és állítsa be a következő értékeket:

    1. A **Séma neve** mezőt állítsa **Érték** beállításra.
    2. A **Séma útvonala** mezőt állítsa **/payload\[\*\]/value** értékre.
    3. A **Leírás** mezőben adja meg az **Üzenet értéke** értéket.

    > [!NOTE]
    > Nem kell megadnia az üzenet összes tulajdonságát. Csak a szükséges tulajdonságokat határozza meg. Az előző lépésben nem hozott létre sort a **Gyökér időbélyege** számára. A **Gyökér időbélyege** útvonala **/timestamp** lenne.

10. Válassza a **Következő** lehetőséget a **Berendezés érzékelősémájának leképezése** oldalra lépéshez.
11. A **Berendezés erőforrás-azonosítója** sorban a **Séma neve** mezőt állítsa **Azonosító** értékre.
12. Az **UTC idő** sorában a **Séma neve** mezőben válassza az **Időbélyeg** értéket.
13. A **Legyártott darab jel** sorban a **Séma neve** mezőben válassza az **Érték** értéket.
14. Válassza a **Következő** lehetőséget a **Berendezés erőforrás-azonosítójának konfigurációja** oldalon.
15. Kövesse ezeket a lépéseket az IoT-központ üzenete értékeinek leképezéséhez a Supply Chain Management erőforrásaira:

    1. Adjon hozzá egy új sort a **Jeladatok értékei** táblában. Írja be az **Érték** mezőbe a következőt: **IoTInt.Machine1225.PartOut**. Ez az érték az IoT-központ üzenetének JSON **azonosító** tulajdonságából származik.
    2. Válassza a **Mentés** lehetőséget.
    3. Az **Üzleti rekord leképezése** táblában válassza az **Új** elemet. Az **Üzleti rekordtípus** mező alapértelmezett értéke automatikusan ki van töltve, és nem szükséges módosítani azt.
    4. Válassza ki az **Üzleti rekord** mezőben azt a Supply Chain Management géperőforrást, amelyből ez a jel elküldésre került.
    5. Válassza a **Mentés** lehetőséget.
    6. Ismételje meg ezeket a lépéseket, és adjon hozzá egy új üzletirekord-hozzárendelést a **Machine1226** esetében. A Supply Chain Management egyetlen rekordjához több jeladatértéket rendelhet hozzá.

16. A **Kiválasztott** oszlopban kiválaszthatja, hogy melyik gépeket szeretné feldolgozni. Nem kell minden jelértéket megadni, és nem kell kijelölnie az összes gépet.
17. Válassza a **Következő** lehetőséget a **Legyártott darab jelkonfigurációja** oldalon.
18. A **Jeladatok értékei** táblában adjon hozzá egy sort, és adja meg az **Érték** mezőben az **Igaz** értéket. Ez az érték az IoT-központ üzenetének JSON **érték** tulajdonságából származik. A forgatókönyvéhez annyi értéket adhat hozzá, amennyit csak szükséges.
19. Válassza a **Mentés** lehetőséget.
20. Válassza a **Következő** lehetőséget a **Berendezés üzemkimaradásának küszöbértéke** oldalra lépéshez. A felsorolt gépek a korábban a jelértékekre leképezett gépek. Ezen az oldalon meghatároz egy küszöbértéket annak meghatározására, hogy a gép áll-e. Ha például a küszöb **10** értékre van állítva, akkor a Supply Chain Management egy értesítést generál, ha a gépről 10 percig nem érkezik **PartOut** üzenet.
21. Válassza a **Következő** lehetőséget a **Forgatókönyv engedélyezése** oldalra lépéshez. Állítsa be a lehetőséget a forgatókönyv engedélyezéséhez.
22. Válassza a **Befejezés** lehetőséget.

A forgatókönyv beállítása immár befejeződött. Az IoT Intelligencia automatikusan elindítja a IoT-központ üzeneteinek feldolgozását.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>A Termékminőség forgatókönyv konfigurálása a Supply Chain Management alkalmazásban

A **Termékminőség** forgatókönyv értesítést generál, ha egy cikk egyik attribútuma kívül esik a megadott tartományon. Egy érzékelő például elküldi az egyes cikkek súlyát az IoT-központhoz. A Supply Chain Management alkalmazásban egy értesítés jön létre, ha a cikk túl nehéz vagy túl könnyű.

A **Termékminőség** forgatókönyv a következő függőségekkel rendelkezik:

+ A termelési rendelésnek egy leképezett gépen kell futnia, és egy olyan terméket kell előállítania, amely leképezett kötegattribútummal rendelkezik egy értesítés aktiválásához.
+ A kötegattribútumot jelképező jelet kell küldeni az IoT-központnak egy kötelező egyedi tulajdonságnévvel.
+ Egy UNIX **időbélyegző** tulajdonságnak, ahol az érték ezredmásodpercben (ms) van kifejezve, jelen kell lennie az Azure IoT Hub üzenetben.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>A Termelési késések forgatókönyv konfigurálása a Supply Chain Management alkalmazásban

A **Termelési késések** forgatókönyv értesítést generál, ha a termelési teljesítmény egy küszöbérték alá esik. Ebben a forgatókönyvben a **PartOut** jelet a rendszer elküldi az IoT-központhoz minden egyes legyártott tételnél. A Supply Chain Managementben a rendelés késleltetése a termelési rendelés ütemezés szerinti időpontja, az előállítandó cikkek száma, a feladat futásának ideje, valamint a fogadott **PartOut**-jelek számának alapján történik. Ha a feladathoz tartozó **PartOut** jelek száma nem éri el a küszöbértékét, akkor egy késési értesítés jön létre.

A **Termelési késések** forgatókönyv a következő függőségekkel rendelkezik:

+ Egy termelési rendelésnek futnia kell egy leképezett gépen, hogy a figyelmeztetés aktiválva legyen.
+ A hozzárendelt gép **PartOut** jelét jelképező jelet kell küldeni az Azure IoT Hubnak egyedi tulajdonságnévvel.
+ Egy UNIX **időbélyegző** tulajdonságnak, ahol az érték ezredmásodpercben (ms) van kifejezve, jelen kell lennie az Azure IoT Hub üzenetben.

## <a name="disable-a-scenario"></a>Forgatókönyv letiltása

Kövesse az alábbi lépéseket a forgatókönyv letiltásához.

1. A Supply Chain Management alkalmazásban lépjen a **Gyártásvezérlés \> Beállítás \> IoT Intelligencia \> Forgatókönyvek kezelése** lehetőségre.
2. A eset mozaikján válassza a **Konfigurálás** elemet.
3. Válassza a **Következő** lehetőséget a varázsló utolsó oldalára lépéshez.
4. Állítsa be a lehetőséget a forgatókönyv letiltásához.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]