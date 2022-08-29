---
title: Cikkek regisztrálása raktármenedzsment folyamatok engedélyezésére, cikkérkeztetési napló használatával
description: Ez a cikk egy olyan helyzetet mutat be, amely bemutatja, hogyan regisztrálhatja a cikkeket a cikkérkezési napló segítségével a raktárkezelési folyamatok (WMS) használata esetén.
author: Mirzaab
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66fc9e21b79d70ec14750440c74d354bb8ec0695
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219598"
---
# <a name="register-items-enabled-for-warehouse-management-processes-using-an-item-arrival-journal"></a>Cikkek regisztrálása raktármenedzsment folyamatok engedélyezésére, cikkérkeztetési napló használatával

[!include [banner](../../includes/banner.md)]

Ez a cikk egy olyan helyzetet mutat be, amely bemutatja, hogyan regisztrálhatja a cikkeket a cikkérkezési napló segítségével a raktárkezelési folyamatok (WMS) használata esetén. Ezt általában egy bevételezési adminisztrátor végzi.

## <a name="enable-sample-data"></a>Mintaadatok engedélyezése

Ha ezt az esetet az ebben a cikkben megadott mintarekordokkal és értékekkel kell dolgozni, olyan rendszert kell használnia, ahol telepítve vannak a [szabványos](../../../fin-ops-core/fin-ops/get-started/demo-data.md) bemutatóadatok, *és mielőtt nekikezd, ki kell választania az USMF* jogi személyt.

Ehelyett a saját adatokból származó értékeket behelyettesítésével is dolgozhat, feltéve, hogy rendelkezésre állnak a következő adatok:

- Rendelkeznie kell egy visszaigazolt beszerzési rendeléssel, amelyhez nyitott beszerzésirendelés-sor tartozik.
- A sorban szereplő cikket raktárazni kell. Nem használhat termékváltozatokat, és nem használhat nyomon követési dimenziókat.
- A cikket olyan tárolásidimenzió-csoporthoz kell társítani, amelynél engedélyezve van a raktárkezelési folyamat.
- A wmS számára engedélyezni kell a raktárt, és a bevételhez használt helynek táblavezéreltnek kell lennie.

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a>Raktárkezelést használó cikkérkezési naplófejléc létrehozása

A következő helyzet bemutatja, hogyan lehet létrehozni a raktárkezelést használó cikkérkezési naplófejléceket:

1. Győződjön meg róla, hogy a rendszer olyan visszaigazolt beszerzési rendelést tartalmaz, amely megfelel az előző szakaszban meghatározott követelményeknek. Ez az eset az *USMF* vállalatra, az *1001*-es szállítói számlára és az *51*-es raktárra vonatkozó beszerzési rendelést használ, amelyben szerepel egy rendelési sor a *M9200* cikkszámhoz *10 PL* (10 raklap) mennyiség.
1. Jegyezze fel a beszerzési rendelés számát, amit használni fog.
1. Lépjen a **Készletgazdálkodás \> Naplóbejegyzések \> Cikkérkeztetés \> Cikkérkeztetés** menüpontra.
1. A Művelet panelen válassza az **Új** lehetőséget.
1. Megjelenik a **Raktárkezelési napló létrehozása** párbeszédpanel. A **Név** mezőben válassza ki a napló nevét.
    - Az *USMF* mintaadatok használata esetén válassza az *WHS* lehetőséget.
    - Ha saját adatait használja, akkor a választott naplóban a **Kitárolási hely ellenőrzése** beállítás értéke legyen *Nem*, a **Karanténkezelés** beállítása pedig *Nem* lehet.
1. A **Hivatkozás** beállítása legyen *Beszerzési rendelés*.
1. A **Számlaszám** értéke legyen *1001*.
1. Állítsa be a **Szám** értékét azon beszerzési rendelés számára, amelyet meghatározott ehhez a gyakorlathoz.

    ![Cikkbeérkezési napló.](../media/item-arrival-journal-header.png "Cikkbeérkezési napló")

1. A naplófejléc létrehozásához kattintson az **OK** gombra.
1. A **Naplósorok** szakaszban válassza a **Sor hozzáadása** lehetőséget, és írja be a következő adatokat:
    - **Cikkszám** – értéke legyen *M9200*. A **Telephely**, a **Raktár** és a **Mennyiség** beállítása a 10 raklap (1000 ea.) készlettranzakció-adatai alapján történik.
    - **Hely** – értéke *001*. Ez a hely nem követi az azonosítótáblákat.

    ![Cikkérkeztetési naplósor.](../media/item-arrival-journal-line.png "Cikkérkeztetési naplósor")

    > [!NOTE]
    > A **Dátum** mező határozza meg, hogy mikor lesz a cikk elérhető mennyisége regisztrálva a készletbe.  
    >
    > Az **Adagazonosítót** kitölti a rendszer, ha egyedileg azonosítható a megadott adatok alapján. Ellenkező esetben manuálisan kell megadni. Ez a mező kötelező, egy adott forrásbizonylatsorhoz kapcsolja a regisztrációt.  

1. A Művelet panelen válassza ki az **Ellenőrzés** lehetőséget. Ez ellenőrzi, hogy a napló feladásra kész. Ha az ellenőrzés sikertelen, a hibákat helyre kell állítani a napló feladása előtt.  
1. Megjelenik a **Napló ellenőrzése** párbeszédpanel. Válassza ki az **OK** lehetőséget.
1. Tekintse meg az üzenetsávot. Egy üzenet látható, amely arról tájékoztat, hogy a művelet befejeződött.  
1. A műveleti ablaktáblán válassza ki a **Feladás** elemet.
1. Megjelenik a **Napló feladása** párbeszédpanel. Válassza ki az **OK** lehetőséget.
1. Tekintse meg az üzenetsávot. Itt üzenetek láthatók, amely arról tájékoztat, hogy a művelet befejeződött.
1. Válassza a **Funkciók > Termékbevételezés** lehetőséget a műveleti ablaktáblán a beszerzésirendelés-sor frissítéséhez és a termékbevételezés feladásához.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
