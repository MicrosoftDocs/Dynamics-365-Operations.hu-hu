---
title: Eszköz beállítása a termelési üzem végrehajtási felületének futtatására
description: A termelési üzem végrehajtási felülete a termelési üzemben található összes eszközhöz be van állítva. A vállalatok általában minden eszközt különbözően állítanak be, attól függően, hogy az eszköz milyen célra szolgál. Előfordulhat például, hogy egy vállalatnak van egy eszköze a recepción, ahol a dolgozók érkezéskori és távozáskori ki- és beblokkolást végeznek, és egy másik az üzemszinten, ahol a dolgozók jezelik a feladataikat.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution, HcmWorker, JmgProductionFloorExecutionDeviceConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 3ee7f0af9f390e1dceac9dc49ae2b7f5fa7fbea8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814706"
---
# <a name="set-up-a-device-to-run-the-production-floor-execution-interface"></a>Eszköz beállítása a termelési üzem végrehajtási felületének futtatására

[!include [banner](../includes/banner.md)]

A termelési üzem végrehajtási felülete a termelési üzemben található összes eszközhöz be van állítva. A vállalatok általában minden eszközt különbözően állítanak be, attól függően, hogy az eszköz milyen célra szolgál. Előfordulhat például, hogy egy vállalatnak van egy eszköze a recepción, ahol a dolgozók érkezéskori és távozáskori ki- és beblokkolást végeznek, és egy másik az üzemszinten, ahol a dolgozók jezelik a feladataikat.

## <a name="set-the-configuration-and-filters-for-a-specific-device"></a>Egy adott eszköz konfigurációjának és szűrőinek beállítása

Egy eszköz konfigurációs és feladattípusának beállításához jelentkezzen be a **Termelési üzem végrehajtása** lapjára olyan fiókkal, amely olyan biztonsági szerepkörrel rendelkezik, amely tartalmazza a *Felügyelői idő fenntartása* kötelességet. (A beépített biztonsági szerepkörök közül az *Üzemirányítás vezetője* rendelkezik ezzel a kötelességgel.) Hajtsa végre az alábbi lépéseket.

1. Nyissa meg a beállítani kívánt eszközt, és jelentkezzen be a Microsoft Dynamics 365 Supply Chain Management szolgáltatásba üzemfelügyelőként. (Olyan fiókot használjon, amely tartalmazza a *Felügyelői idő fenntartása* kötelességet.)
1. Győződjön meg róla, hogy a beállított eszköz számára elérhető legyen a konfiguráció. Ha még nem létezik konfiguráció, akkor a rendszer egy alapértelmezett konfigurációt ad meg. A konfiguráció beállításával kapcsolatos további tudnivalókért lásd [A termelési üzem végrehajtási felületének konfigurálása](production-floor-execution-configure.md) című témakört.
1. Lépjen a **Gyártásvezérlés \> Gyártásvégrehajtás \> Termelési üzem végrehajtásának konfigurálása** részre.

    Ha a termelés végrehajtási felületét már legalább egyszer beállították az aktuális eszközön, megjelenik egy bejelentkezési lap. Ellenkező esetben egy üdvözlőképernyő jelenik meg.

1. A bejelentkezési vagy az üdvözlő oldalon válassza a **Konfigurálás** elemet.
1. Jelöljön ki egy konfigurációt a listából.
1. Válassza ki **Következő** lehetőséget.
1. Jelöljön ki egy vagy több szűrőt az aktuális eszközre vonatkozóan. Ezek a szűrők segítenek biztosítani, hogy csak a megfelelő feladatok jelenjenek meg az eszközön. Egy szűrő beállításához válassza ki az értékek listáját tartalmazó szűrő típusát, majd válassza ki a szűrni kívánt értéket. Az alábbi szűrők állnak rendelkezésre:

    - **Termelési egység** – Ez a szűrő a legmagasabb szintű szűrő. Általában egy nagy munkaterületre vonatkozik, amelyen több erőforráscsoport és erőforrás található.
    - **Erőforráscsoport** – Ez egy közepes szintű szűrő. Általában a munkaterület korlátozott területein található kapcsolódó erőforrások gyűjteményére vonatkozik. Ha előbb kiválasztja a **Termelési egység** szűrőjét, akkor az erőforráscsoportok listája csak az adott egységből származó csoportokat jeleníti meg. Ellenkező esetben az összes elérhető erőforráscsoportot megjeleníti.
    - **Erőforrás** – Ez a legkonkrétabb szűrő. Általában egy adott gépre vagy más egyéni erőforrásra vonatkozik. Ha előbb kiválasztja az **Erőforráscsoport** és/vagy a **Termelési egység** szűrőjét, akkor az erőforrások listája csak az adott csoportból és/vagy egységből származó csoportokat jeleníti meg. Ellenkező esetben az összes elérhető erőforrást megjeleníti.

1. Válassza ki az **OK** lehetőséget.
1. Megjelenik a bejelentkezési lap, és az eszköz készen áll a használatra.

## <a name="allow-a-worker-to-override-the-default-filters"></a>Az alapértelmezett szűrők felülbírálásának engedélyezése dolgozók számára

Meghatározott dolgozóknak engedélyt adhat a szűrő beállításainak módosítására minden általuk használt eszközön. Azoknak a dolgozóknak, akik rendelkeznek ezzel az engedéllyel, a termelési üzem végrehajtási felülete tartalamaz egy **Szűrő** gombot a **Minden feladat** és az **Aktív feladat** munkalapokon.

> [!NOTE]
> Ha egy dolgozó megváltoztatja a szűrőt, akkor az új szűrő ettől a ponttól kezdve az eszközbe bejelentkező összes felhasználóra vonatkozik.

Ha engedélyezni szeretné, hogy egy dolgozó felülbírálhassa az eszközhöz beállított alapértelmezett feladatokhoz tartozó szűrőket, hajtsa végre az alábbi lépéseket.

1. Lépjen az **Idő és jelenlét \> Beállítás \> Munkaidő-nyilvántartási dolgozók** részhez.
1. Válasszon ki a listáról egy dolgozót, hogy megnyíljon annak **Munkaidő-nyilvántartási dolgozói** lapja.
1. A **Munkaidő-nyilvántartás** lapon a **Szűrők beállítása** lehetőség értéke legyen *Igen*.

## <a name="run-the-interface-in-full-screen-mode"></a>A kezelőfelület teljes képernyős módban való futtatása

Gyakran egy kizárólag erre a célra használt eszközön futtatja a termelési üzem végrehajtási felületét. Ennek megfelelően előfordulhat, hogy a kezelőfelületet teljes képernyős módban futtatja, a nevigáció és a Chrome böngésző megjelenítése nélkül.

- A Supply Chain Management alkalmazásbam megjelenő navigációs ablak elrejtéséhez adja hozzá az alábbi szöveget a böngésző címsorába a URL-cím végéhez: `\&limitednav=true`.
- A böngésző címsorának elrejtéséhez használja a böngésző beépített teljes képernyős üzemmódját is. (Utasításokért lásd a böngésző dokumentációját.)

Az alábbi ábra felső részén látható a kezelőfelület alapértelmezett megjelenése. Az alsó részen látható, hogy hogyan néz ki teljes képernyős módban, amikor a navigációs ablak el van rejtve.

![Normál, ill. teljes képernyős kezelőfelület](media/pfei-full-screen.png "Normál, ill. teljes képernyős kezelőfelület")

## <a name="extend-the-session-past-12-hours"></a>A munkamenet kiterjesztése 12 óránál hosszabbra

Alapértelmezetten a termelési üzem végrehajtási felület automatikusan kijelentkezik, ha azt nem használják 12 órán keresztül. Ezután a Supply Chain Management egy felhasználójának ismét be kell jelentkeznie. Az időtúllépési korlát azonban akár 90 nap hosszúságra is kiterjeszthető.

Az időtúllépési korlát meghosszabbításához jelentkezzen be a Supply Chain Management alkalamzásba, majd nyissa meg a **Rendszerfelügyelet \> Felhasználók \> Munkamenet meghosszabbítása** lehetőséget. Adja meg azt az Supply Chain Management felhasználói fiókot, amely az eszközbe történő bejelentkezéshez használatos, valamint azt, hogy hány órán át maradjon a munkamenet aktív.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]