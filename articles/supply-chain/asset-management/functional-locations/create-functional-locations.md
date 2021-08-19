---
title: Munkavégzési helyszínek létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet munkavégzési helyszínt létrehozni az Eszközkezelés modulban.
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationCopyStructure, EntAssetFunctionalLocationCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e5dd5ea59b27c594752ff82428723f3afe555b5f2426a812c70e10b968c920a5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767532"
---
# <a name="create-functional-locations"></a>Munkavégzési helyszínek létrehozása

[!include [banner](../../includes/banner.md)]

 

Ez a témakör azt mutatja be, hogyan lehet munkavégzési helyszínt létrehozni az Eszközkezelés modulban.

Ha munkavégzési helyszínt hoz létre, vegye figyelembe, miután létrehozta a munkavégzési helyszín, nem helyezheti át azt az eredeti helyéről. Ez azt jelenti, hogy alaposan át kell gondolnia kell a munkavégzési helyszínek szerkezetét, mielőtt megkezdheti azok létrehozását az Eszközkezelés modulban. Ha egy munkavégzési helyszínnel kapcsolatosan meggondola magát, törölheti azt, feltéve, hogy még nem használta.

A munkavégzési helyszínekkel való munkához a munkavégzési helyszínek két „kategóriáját” kell létrehozni:

- Hozzon létre *egy* alapértelmezett munkavégzési helyszínt alhelyszínek nélkül. Ez a munkavégzési helyszín csak az eszközök alapértelmezett helyeként használatos az új eszközök létrehozásakor.  
- Hozza létre a vállalatnál a karbantartási feladatok kezeléséhez szükséges munkavégzési helyszínstruktúrákat.

## <a name="create-a-default-functional-location"></a>Alapértelmezett munkavégzési helyszín létrehozása

Ha munkavégzési helyszíneket használ, kezdje azzal, hogy létrehoz egy alapértelmezett helyszínt, amelyet az új eszközök létrehozásakor fog használni. Ez az a munkavégzési helyszín amelyet az **Eszközkezelés** > **Beállítás** > **Eszközkezelés paraméterei** > **Eszközök** hivatkozás > **Alapértelmezett munkavégzési helyszín** mezőjében választ ki. Az alapértelmezett munkavégzési helyszín akkor használható, amikor új eszközöket hoz létre, és még nem állított be munkavégzési helyszínstruktúrát ezekhez az eszközökhöz.

1. Válassza ki az **Eszközkezelés** > **Általános** > **Munkavégzési helyszínek** > **Összes munkavégzési helyszín** lehetőséget.  
2. Az **Összes munkavégzési helyszín** helyen válassza az **Új** lehetőséget.
3. Szúrjon be egy azonosítót a **Munkavégzési helyszín** hely mezőbe, például „0000” vagy „Default”, jelezve, hogy ez egy különleges munkavégzési helyszín.
4. Az alapértelmezett munkavégzési helyszín nevének beszúrása a **Név** mezőbe.
5. *Ne* jelöljön ki szülőt a **Szülő** mezőben – hagyja üresen ezt a mezőt.
6. A **Munkavégzési helyszín típusa** mezőben válassza ki az alapértelmezett munkavégzési helyszínhez használandó munkavégzési helyszíntípust. Lásd: [Munkavégzési helyszínek típusai](../setup-for-functional-locations/functional-location-types.md) a munkavégzési helyszínek beállításával kapcsolatosan.
7. Válassza ki az **OK** lehetőséget. Ne adjon hozzá további adatokat ehhez a munkavégzési helyszínhez, mert az csak az új eszközök ideiglenes helyeként használatos, amíg nem telepíti az eszközöket a vállalata által használt munkavégzési helyszínekre.

## <a name="create-functional-locations"></a>Munkavégzési helyszínek létrehozása

Az alábbi eljárás bemutatja, hogyan hozhatók létre a vállalat karbantartásához szükséges munkavégzési helyszínek.

1. Válassza ki az **Eszközkezelés** > **Általános** > **Munkavégzési helyszínek** > **Összes munkavégzési helyszín** lehetőséget. A munkavégzési helyszínt rácsnézetben vagy a részletek nézetben hozhatja létre.
2. Kattintson a **Új** gombra.
3. Azonosító beszúrása a **Munkavégzési helyszín** mezőbe.
4. Az alapértelmezett munkavégzési helyszín nevének beszúrása a **Név** mezőbe.
5. Ha a munkavégzési helyszín egy szerkezet egyik alhelye, jelölje ki a szülőhelyet a **Szülő** mezőben.
6. Válassza ki a típust a **Munkavégzési helyszín típusa** mezőben.
7. Válassza ki az **OK** lehetőséget.
8. Válassza ki a munkavégzési helyszínt és további információ hozzáadásához kattintson a **Szerkesztés** gombra.

>[!NOTE]
>A munkavégzési helyszín életciklus-állapotának beállításától függően előfordulhat, hogy minden alhelyet létre kell hoznia egy munkavégzési helyszínhez, majd meg kell változtatnia a munkavégzési helyszín életciklusának állapotát, mielőtt megkezdheti az eszközök telepítését. Tekintse meg az [Eszközök telepítése munkavégzési helyszínekre](../functional-locations/install-objects-on-functional-locations.md) további információért az eszközök telepítésével kapcsolatban. A [Munkavégzési helyszín életciklus-állapotai](../setup-for-functional-locations/functional-location-stages.md) című témakörben további információt talál a funkcionális életciklus-állapotok beállításáról.

A Részletek nézetben Gyorslapokat fog látni, amelyeken a munkavégzési helyszínre vonatkozó információkat adhatja hozzá és szerkesztheti.

## <a name="general-information"></a>Általános információ

Ez a szakasz amunkavégzési helyszín szerkezetében lévő szülő-és gyermekinformációk áttekintését tartalmazza. A **Részletek** szakaszban megtekintheti a munkavégzési helyszínhez kapcsolódó eszközattribútumok, karbantartási tervek és eszközök számát. A **Készlet** szakaszban kiválaszthatja azt a helyet és raktárat, amelyhez a munkavégzési helyszín kapcsolódik. A hely és a raktár a munkarendelések cikk-előrejelzéseivel kapcsolatosan használatos. Egy cikkelőrejelzés létrehozásakor a program automatikusan felhasználja a hely-és a raktáradatokat az eszköz munkavégzési helyszínéről. Az **Életciklus-állapot** szakaszban a munkavégzési helyszín életciklus-állapotáról látható információ.

## <a name="installed-assets"></a>Telepített eszközök

Tekintse meg az [Eszközök telepítése munkavégzési helyszínekre](../functional-locations/install-objects-on-functional-locations.md) további információért az eszközök telepítésével kapcsolatban. A gyorslapon található **Nézet** gomb használatával több mezőt is megjelenítheti a gyorslapon. Az **Érvényesség kezdete** és az **Aleszköz** mezők jeleníthetők meg a rácsban.

## <a name="asset-attribute-requirements"></a>Eszközattribútum követelményei

Ezen a gyorslapon a munkavégzési helyszínen telepített eszközök egyedi attribútumkövetelményeit adhatja meg. Ezek a követelmények csak tájékoztatási célokat szolgálnak. Nem akadályozzák meg az eszközök más attribútumkövetelményekkel való telepítését. Jelölje be a **Sor hozzáadása** lehetőséget, és jelölje ki az attribútumtípust. Ezután szúrja be a megfelelő **Értéket**, jelöljön ki egy küszöbértéket a **Küszöbérték feltételek** mezőben, majd mentse a rekordot.

## <a name="maintenance-plans-and-maintenance-rounds"></a>Karbantartási tervek és karbantartási körök

Itt adhat hozzá karbantartási terveket és karbantartási köröket a munkavégzési helyszínhez, beleértve egy kezdési dátumot is. A munkavégzési helyszínre telepített eszközökhöz más karbantartási terveket is be lehetnek állítva. A karbantartási tervek és a karbantartási körök a munkavégzési helyszín tárgyieszköznaptár-bejegyzéseinek illetve a jelenleg telepített eszközök ütemezésére használhatók.

>[!NOTE]
>Ha frissíti a karbantartási tervek eszköztípusainak, eszközmárkáinak és eszközmodelljeinek a beállítását az **Összes munkavégzési helyszín** részletek nézet> **Karbantartási tervek** gyorslapján, az ütemezett karbantartási tervek, és meglévő az karbantartási ütemezés bejegyzések a munkavégzési helyszínre vonatkozóan automatikusan törölve lesznek. Ha új ütemezési bejegyzéseket szeretne létrehozni, amelyek megfelelnek a frissített karbantartási terv beállításának a munkavégzési helyszínen, akkor az adott munkavégzési helyszínhez új karbantartásiterv-ütemezést kell futtatnia. 

## <a name="address"></a>Cím

Szúrja be a munkavégzési helyszín címét a **Cím** gyorslapra. A munkavégzési helyszíneken lévő címek öröklődnek, tehát ha az alhelyen nincs cím definiálva, a szülőhely címe kerül felhasználásra.

## <a name="workers"></a>Dolgozók

Ezen a gyorslapon a munkavégzési helyszínhez kapcsolódó dolgozókat adhat hozzá, és a dolgozó számára kijelölhet egy munkavégzési helyszínt elsődlegesként. 

## <a name="attributes"></a>Attribútumok

Ezen a gyorslapon beállíthatja a munkavégzési helyszín attribútumértékeit. Ezek az attribútumok leírják a munkavégzési helyszínhez tartozó tulajdonságokat vagy jellemzőket, például a szerkezeti tulajdonságokat, az épület típusát, a területleírásokat, hogy a helyszín a föld felett vagy alatt van.

Jelölje be a **Sor hozzáadása** lehetőséget, és jelölje ki az attribútumtípust. Ezután szúrja be az attribútumtípushoz kapcsolódó **Értéket**, és mentse a rekordot.

## <a name="financial-dimensions"></a>Pénzügyi dimenziók

Kiválaszthat pénzügyi dimenziókat is a munkavégzési helyszínhez. [Munkavégzési helyszínek típusai](../setup-for-functional-locations/functional-location-types.md) beállítása lehetővé teszi a pénzügyi dimenziók automatikus frissítését egy munkavégzési helyszínről. Ez azt jelenti, hogy a pénzügyi dimenzióra telepített eszközök automatikusan megkapják a munkavégzési helyszín pénzügyi dimenzióit. Ez akkor hasznos, ha különböző költséghelyeket szeretne a helyszínektől függően.

Ha a **Hely**, **Raktár**, **Cím** és **Pénzügyi dimenziók** adatokat a szülő munkavégzési helyszínén frissíti, a kapcsolódó al munkavégzési helyszíneket is frissíteni lehet ennek megfelelően, ha frissítés során ezt választja. Megnyílik egy párbeszédablak, amely a frissítési lehetőségeket kínálja.

## <a name="copy-a-functional-location-structure"></a>Munkavégzési helyszín szerkezetének másolása

Ha a vállalatnál több, hasonló helystruktúrával rendelkező munkavégzési helyszín van, akkor az Eszközkezelés másolás funkciójával gyorsan létrehozhat több hasonló helyszínhierarchiát. Egy adott munkavégzési helyszín vagy egy teljes struktúra másolásakor az új helyszín vagy struktúra neve megegyezik a másolt elemével. A másolási folyamat után egyszerűen módosíthatja az új munkavégzési helyszín nevét vagy egyéb beállításait, feltéve, hogy az új munkavégzési helyszín életciklus-állapota lehetővé teszi ezt.

1. Az **Összes munkavégzési helyszín** helyen válassza ki a másolni kívánt munkavégzési helyszínt. Ha például egy legfelső helyszínt (szülőt) jelöljön ki, ha egy teljes munkavégzési helyszín szerkezetét, beleértve az alhelyeket is át kívánja másolni.
2. Válassza a **Munkavégzési helyszín szerkezetének másolása** gombot. A listaoldalon kijelölt hely megjelenik a **Másolás forrása** mezőben.
3. Szúrja be az új hely nevét az **Új funkcionális hely** mezőbe.
4. A **Szülő, amely alá beszúrandó** mezőbe csak akkor szúrjon be szülőazonosítót, ha a létrehozandó hely egy meglévő, munkavégzési helyszín struktúrájának részét képezi.
5. Kattintson az **OK** gombra. Az új munkavégzési helyszín struktúra megjelenik a **Minden munkavégzési helyszín** helyen.

>[!NOTE]
>A munkavégzési helyszín struktúrájának másolásakor az új struktúrában a munkavégzési helyszín életciklus-állapotok értéke az „első állapot” lesz, amelyet a munkavégzési helyszínekhez hozott létre. Az, hogy a funkcionális hely átnevezhető vagy törölhető- e az **Átnevezés** és **Törlés** gombokkal az **Összes munkavégzési helyszín** menüben az a munkavégzési helyszín aktuális életciklus-állapotától függ.

## <a name="delete-a-functional-location"></a>Munkavégzési helyszín törlése

A kapcsolódó alhelyekkel rendelkező munkavégzési helyszín törölhető, ha nem telepített eszközöket a törölni próbált munkavégzési helyszínek egyikére sem, és aktuális munkavégzési helyszín életciklus-állapot lehetővé teszi ezt.

1. Az **Összes munkavégzési helyszín** helyen válassza ki a törölni kívánt munkavégzési helyszínt.
2. Ha szükséges, frissítse a munkavégzési helyszínt egy olyan munkavégzési helyszín életciklus állapotra amely lehetővé teszi a munkavégzési helyszín törlését.
3. Válassza a **Törlés** lehetőséget.

>[!NOTE]
>Ha nem tud törölni egy munkavégzési helyszínt, akkor a törlés elvégezheti úgy, hogy létrehoz egy munkavégzési helyszín életciklus-állapotot erre a célra. Beállíthat például egy „Selejtezett” vagy „Törölt” állapotot amely nem lehet aktív állapot **Munkavégzési helyszín életciklus-állapotai** képernyőn.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]