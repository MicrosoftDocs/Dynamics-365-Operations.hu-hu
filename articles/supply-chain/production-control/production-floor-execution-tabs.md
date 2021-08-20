---
title: A termelési üzem végrehajtási felületének tervezése
description: Ez a témakör azt mutatja be, hogyan lehet megtervezni az egyes konfigurációk felhasználói felületének tartalmát.
author: johanhoffmann
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration, JmgProductionFloorExecutionConfigurationTab
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 6332b4b15b277faca506da4ea67fcc3ddb9799153a6fe73a711050ab93bdf565
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782467"
---
# <a name="design-the-production-floor-execution-interface"></a>A termelési üzem végrehajtási felületének tervezése

[!include [banner](../includes/banner.md)]

A felhasználói felület tartalmát a termelési üzem végrehajtási felülete által használt minden konfigurációhoz megtervezheti. Előfordulhat például, hogy egy munkacellában dolgozóknak meg kell tudniuk nyitni a termelési üzemben a feladatra vonatkozó utasításokat, míg egy másik munkacellában nem szükségesek az utasítások. Ebben az esetben két konfigurációt kell létrehozni, egyet egy gombbal a dokumentumok mellékleteinek megnyitásához és egyet a gomb nélkül.

## <a name="design-a-tab"></a>Lap tervezése

A **Termelési üzem végrehajtásának konfigurálása** lapon létrehozhatja és konfigurálhatja a lapokat a műveleti ablak **Lapok tervezése** elemének kiválasztásával.

Mindegyik lap négy részre van osztva, ahogy az a következő ábrán látható.

![Lap elrendezése.](media/pfe-tab-layout.png "Lap elrendezése")

A következő elemek jelennek meg az ábrán:

1. Elsődleges eszköztár
1. Másodlagos eszköztár
1. Fő nézet
1. Részletes nézet

Új lap létrehozásához és konfigurálásához kövesse ezeket a lépéseket:

1. Lépjen a **Gyártásvezérlés \> Beállítás \> Gyártásvégrehajtás \> termelési üzem végrehajtásának konfigurálása** részre.

1. Válassza a **Lapok tervezése** elemet a műveleti panelen a **Lapok tervezése** oldal megnyitásához.

    ![A Lapok tervezése oldal.](media/pfe-design-tabs.png "A Lapok tervezése oldal")

1. A Művelet panelen válassza az **Új** lehetőséget.

1. Végezze el a következő beállításokat a lap fejlécében:

    - **Lap neve** – adja meg a lap nevét.
    - **Fő nézet** – Válasszon a két előre meghatározott munkalista (*Aktív feladatok*, *Összes feladat* vagy *Saját gép*) között.
    - **Részletes nézet** – válassza ki az üres értéket vagy a **feladat adatait**. Ha az üres értéket választja, akkor a lapon nem jelenik meg részletes nézet. Ha a **Feladat adatait** választja, akkor a részletes nézet a főnézetben a feladatlistában kiválasztott feladat részletes leírását tartalmazza.

1. Az **Elsődleges eszköztár** szakaszban válassza ki, hogy mely gombokat kell elérhetővé tenni az elsődleges eszköztáron. A **Választható műveletek** oszlop felsorolja az összes olyan gombot, amelyet fel lehet venni. A **Kiválasztott műveletek** oszlopai az aktuális konfigurációban szereplő összes gomb listáját jelenítik meg. Az oszlopok között látható gombokkal lehet áthelyezni a kiválasztott elemeket a szükséges oszlopok között. A **Kiválasztott műveletek** oszlop melletti fel és le gombbal lehet szabályozni, hogy milyen sorrendben jelenjenek meg a gombok a felhasználói felületen.

1. A **Másodlagos** **eszköztár** szakaszban válassza ki, hogy mely gombokat kell elérhetővé tenni a másodlagos eszköztáron. A **Választható műveletek** oszlop felsorolja az összes olyan gombot, amelyet fel lehet venni. A **Kiválasztott műveletek** oszlopai az aktuális konfigurációban szereplő összes gomb listáját jelenítik meg. Az oszlopok között látható gombokkal lehet áthelyezni a kiválasztott elemeket a szükséges oszlopok között. A **Kiválasztott műveletek** oszlop melletti fel és le gombbal lehet szabályozni, hogy milyen sorrendben jelenjenek meg a gombok a felhasználói felületen.

## <a name="associate-a-tab-with-a-configuration"></a>Lap társítása konfigurációval

Miután megtervezte az összes szükséges lapot, hozzárendelheti őket egy konfigurációhoz.

1. Lépjen a **Gyártásvezérlés \> Beállítás \> Gyártásvégrehajtás \> termelési üzem végrehajtásának konfigurálása** részre.

    ![Termelési üzem végrehajtásának konfigurálása.](media/pfe-config-prod-floor-execution.png "Termelési üzem végrehajtásának konfigurálása")

1. A **Lapválasztás** gyorslapon válassza a **Hozzáadás** lehetőséget.

1. A program új sort ad hozzá a rácshoz. Ehhez az új sorhoz válassza ki a konfigurációhoz hozzáadni kívánt lap nevét.

1. Szükség esetén folytassa a további lapok hozzáadását.

1. Az eszköztáron található **Mozgatás felfelé** és **Mozgatás lefelé** gombokkal igény szerint átrendezheti a lapokat. A lapok balról jobbra haladva jelennek meg a fenti képernyőképen látható sorrendben (a felső lap a bal oldalon látható).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]