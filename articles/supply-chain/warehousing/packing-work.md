---
title: Csomagolási munka kimenő tárolók csomagolásához és szállítmányok feldolgozásához
description: Ez a témakör leírja a "Csomagolás" munkarendelési típust, amely a csomagoló tárolókhoz kapcsolódó munkát kezeli, és támogatja a csomagolt tárolók részleges szállítását, amelyek olyan rakományokkal kapcsolatosak, ahol a készletcikkek kicsomagolása még nem sikerült.
author: perlynne
ms.date: 7/13/2022
ms.topic: article
ms.search.form: WHSPackingWorkLocationSetup, WHSPack, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 34a7087df7e7768d0012ea4f534aa109654af8fa
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220746"
---
# <a name="packing-work-for-packing-outbound-containers-and-processing-shipments"></a>Csomagolási munka kimenő tárolók csomagolásához és szállítmányok feldolgozásához

[!include [banner](../../includes/banner.md)]

Ez a témakör leírja *a* Csomagolási munka rendeléstípust, amely a csomagoló tárolókhoz kapcsolódó munkát kezeli, és támogatja a csomagolt tárolók részleges szállítmányát, amelyek olyan rakományokkal kapcsolatosak, ahol a készletcikkek kicsomagolása még nem sikerült. A csomagolási munka lehetővé teszi a [megerősítési](confirm-and-transfer.md) és átviteli funkciókat a tárolókhoz kapcsolódó kimenő szállítmányok megerősítésére.

A csomagolási munka automatikusan létrejön, amikor a forrásdokumentumok munkához kapcsolódó készletet a Csomagolás hely *típusú helyekre kerülnek*. A munka két sorból áll, egyből *kitárolóból* *·*, és egy bezárásból, és a rendszer automatikusan karbantartja egy tárolózárási/újranyitási folyamat részeként.

A tároló csomagolási folyamatának [beállításával és használatával kapcsolatos további tudnivalókat lásd: Szállítmány tárolók csomagolása](packing-containers.md).

## <a name="turn-on-the-feature"></a>A funkció bekapcsolása

Ha a rendszer még nem tartalmazza az ebben a cikkben ismertetett funkciókat, [használja a Funkciókezelést](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), és a következő sorrendben kapcsolja be a következő funkciókat. Mindkét funkció a Raktárkezelési **modul része**.

1. *Megerősítés és áthelyezés*
1. *Csomagolási munka a csomagolási állomásokhoz*

## <a name="set-up-a-location-for-packing-work"></a>Csomagolási munka helyének beállítása

A következő eljárás szerint állíthatja be a csomagolási helyeket. Minden egyes helyhez megadhatja, hogy a rendszer automatikusan létrehozza-e a csomagolási munkát.

1. Ugrás a Raktárkezelés **beállítása \> csomagolóállomás \>\> beállításához**
1. A munkaablak új **beállításának** kiválasztásával adjon hozzá egy csomagolóállomás-beállítási rekordot.
1. Az új rekordban állítsa be a következő mezőket:

    - **Raktár** – válassza ki vagy adja meg azt a raktárt, ahol a csomagolási hely található.
    - **Hely** – válassza ki vagy adja meg a csomagolási helyet. Ezt a helyet olyan helyprofilhoz kell hozzárendelni, amely a **vállalat csomagolásihely-típusaként beállított helytípust használja a Raktárkezelési paraméterek** lapon. További tájékoztatás: Szállítmány [tárolók csomagolása](packing-containers.md).
    - **Csomagolási munka létrehozása** – akkor jelölje be ezt a jelölőnégyzetet, ha minden alkalommal csomagolási munkát kell létrehozni, amikor a cikkeket a csomagolási helyre szállítják. A munka a kapcsolódó rakománysorra mutató hivatkozásokat tartalmaz, így a részleges rakományok csomagolható és szállíthatóak.

## <a name="example-scenario"></a>Példaforgatókönyv

A példa azt mutatja be, hogyan kell feldolgozni a kimenő értékesítési rendelési folyamatot egy tároló csomagolásával és részleges rakomány szállításával.

### <a name="make-sample-data-available"></a>A mintaadatok elérhetővé tétele

Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/fin-ops/get-started/demo-data.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

Ez az eset a termelési rendszeren használt funkció használatának útmutatásaként is használható. Ebben az esetben azonban az itt leírt mindegyik beállítás esetében be kell helyettesítenie a saját értékeit.

### <a name="configure-packing-work-for-warehouse-packing-location"></a>Csomagolási munka konfigurálása raktári csomagolási helyhez

Első lépésekhez konfigurálnia kell *a* Csomagolási munka folyamatot egy adott raktárhoz és helyhez.

1. Ugrás a Raktárkezelés **beállítása \> csomagolóállomás \>\> beállításához**
1. A műveletpanel új **beállítási rekord** hozzáadásához válassza az Új lehetőséget.
1. Az új rekordban állítsa be a következő értékeket:

    - **Raktár:** *62*
    - **Hely:** *Csomag*
    - **Csomagolási munka létrehozása:** *Igen*

1. Zárja be **a Csomagolóállomás beállítási lapját**.

### <a name="create-a-load-template-that-allows-partial-shipping"></a>Részleges szállítást lehetővé tő rakománysablon létrehozása

Ahhoz, hogy egy rakomány több szállítmányon keresztül szállítható legyen, olyan rakománysablonnal kell társítva lennie, amely lehetővé teszi a részleges szállítást. A következő lépések szerint hozza létre a szükséges sablont.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Rakomány \> Rakománysablonok** elemre.
1. A műveletpanel új **beállítási rekord** hozzáadásához válassza az Új lehetőséget.
1. Az új rekordban állítsa be a következő értékeket:

    - **Rakománysablon azonosítója:** *részleges*
    - **Rakományok felosztásának engedélyezése szállításkor - megerősítés:** *Igen*

1. Zárja be a Rakománysablonok **lapot**.

További információ a Megerősítés és [átvitel oldalon található](Confirm-and-transfer.md).

### <a name="process-a-sales-order"></a>Értékesítési rendelés feldolgozása

Kövesse az alábbi lépéseket egy értékesítési rendelés feldolgozásához és részleges szállításához.

1. A szállítmányhoz [csomagtárolókban](packing-containers.md#scenario)[található példa eset befejezése](packing-containers.md). Ebben az esetben egy cikk két darabja számára hoz létre értékesítési rendelést. Ezt követően csak az egyik darabot fogja egy tárolóba csomagolni, és a tárolót bezárja. Az eset utasítása szerint megjegyzést kell tenni a létrehozott szállítmányazonosítóról.
1. Ugorjon a **Raktárkezelés \> Munka \> Minden munka** pontra.
1. A szűrőterületen jelölje be **a Lezárt munka megjelenítése** jelölőnégyzetet. Ezután adja meg a szállítmány azonosítóját a Szűrő **mezőben**, és válassza ki, hogy a szállítmányazonosító **érték alapján szűr-e**. Most három munkafejlécet kell látnia. Az egyik az értékesítési rendelés kitárolási munkához, állapota *Lezárva*. A kettő a csomagolási folyamat: *az* egyik a lezárt tárolóhoz kapcsolódik, az állapota Lezárt, *a másik a ki nem csomagolt cikkhez kapcsolódik, állapota Nyitott*.
1. Válassza ki **bármelyik munkafejléc** rakományazonosító értékét a **rakomány rakomány részletezési** oldalának megnyitásához.
1. Váltson a **Fejléc** nézetre.
1. Az Általános **gyorssablonban** válassza a **Rakománysablon** azonosítója mező Szerkesztés **gombját**. Ezután válassza ki az esethez létrehozott részleges szállítási terhelési sablont (*részleges*).
1. A Munkaablak Szállítás és fogadás **lap** Megerősítés **csoportjában** válassza a **Kimenő szállítmány lehetőséget**.
1. A Szállítás megerősítése **párbeszédpanelen** válassza a **Mennyiség felosztása új rakományhoz beállítást**.
1. Válassza ki az **OK** lehetőséget.

Ezzel már leszállított egy tárolót, amely az eredeti rakományhoz kapcsolódik, és a rendszer új rakományt hozott létre a fennmaradó cikkekhez, még mindig tárolókba kell csomagolni.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
