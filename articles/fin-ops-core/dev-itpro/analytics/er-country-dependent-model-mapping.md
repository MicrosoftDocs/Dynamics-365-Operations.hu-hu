---
title: Az országkörnyezet-függő modell-leképezések konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani az ER modell-hozzárendeléseket, hogy azok a használatukat szabályozó jogi személy ország-/régióbeli környezetétől függjenek.
author: NickSelin
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.2
ms.openlocfilehash: 5b26c605bd64b8d8e5a90f4389261e8e56825111
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605371"
---
# <a name="configure-country-context-dependent-er-model-mappings"></a>Az országkörnyezet-függő modell-leképezések konfigurálása

[!include[banner](../includes/banner.md)]

Az elektronikus jelentéskészítési (ER) modell-hozzárendeléseket úgy konfigurálhatja, hogy az általános ER adatmodellt hajtsák végre, de legyen jellemző a Dynamics 365 Finance szolgáltatásra. Ez a témakör azt mutatja be, hogyan lehet több ER modell-hozzárendelést tervezni egy ER-adatmodellre vonatkozóan annak szabályozására, hogy hogyan használják azokat a megfelelő ER formátumok, amelyek a különböző ország/régió környezetekben működő vállalatoktól származnak.

## <a name="prerequisites"></a>Előfeltételek

A jelen témakörben szereplő példák elvégzéséhez a következő hozzáférésekkel kell rendelkeznie:

- Hozzáférés a Finance alkalmazáshoz a következő szerepkörök egyikével:
    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

- Hozzáférés a Regulatory Configuration Service (RCS) példányához, amelyet ugyanarra a bérlőre telepítettek, mint a Finance alkalmazást, a következő szerepkörök egyikéhez:
    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

Az ebben a témakörben leírt lépések végrehajtásához kötelező az ER formátum. Bizonyos esetekben az ER-formátum végrehajtását érinti annak a vállalatnak az ország-/régióbeli környezete, amelybe jelenleg be van jelentkezve. A jelenlegi RCS példányban is futtathat egy ER formátumot, ha a szükséges ország-/régió környezettel rendelkező vállalat elérhető az RCS-ben. Ellenkező esetben fel kell töltenie az ER-modell hozzárendelésének és ER formátumkonfigurációk teljes verzióját, amelyek a Finance példány számára az ER-adatmodellt használják, majd a Finance példányban futtassa az ER formátumot. A RCS egy Finance példányban található konfigurációk importálásával kapcsolatos tudnivalókat lásd: [Konfigurációk importálása a RCS-ből](rcs-download-configurations.md).

## <a name="single-model-mapping-case"></a>Egy modell-hozzárendelési eset

A szükséges ER-összetevők megtervezéséhez kövesse a témakör [1. függelékének](#appendix1) lépéseit. Most megvan a **Leképezés (Általános)** modell-leképezési konfiguráció, amely tartalmazza az **1. belépési pont** meghatározásához tartozó modell-leképezést.

![ER konfigurációs lap, formátumok a megfeleltetések konfigurációjának elsajátításához.](./media/RCS-Context-specific-mapping-Tree.PNG)

### <a name="run-the-configured-format"></a>A konfigurált formátum futtatása

1.  Válassza a **Konfigurációk** lap **Verziók** gyorslapján a **Futtatás** elemet.
2.  Válassza ki az **OK** lehetőséget.

Figyelje meg, hogy a webböngésző felajánlja a végrehajtható ER formátummal létrehozott szövegfájl letöltését. Mivel ez a formátum úgy van beállítva, hogy az **1. belépési pont** definícióját használja, és csak egy modell-hozzárendelés jelenleg elérhető a definíció leképezését tartalmazó alapmodellhez, a végrehajtott ER formátum, amelyet a **Leképezés (általános)** konfiguráció adatforrásként történő **Leképezési (általános)** leképezését használja. Ezért a letöltött fájlok tartalmazzák az **1. általános funkció** szöveget.

## <a name="multiple-shared-model-mappings-case"></a>Több megosztott modell-hozzárendelési eset

A szükséges ER-összetevők megtervezéséhez kövesse a témakör [2. függelékének](#appendix2) lépéseit. Most megvan a **Leképezés (Általános)** és **Leképezés (Általános) egyéni** modell-leképezési konfiguráció, amelyek tartalmazzák az **1. belépési pont** meghatározásához tartozó modell-leképezést.

![ER konfigurációs lap, Leképezés általános egyéni konfiguráció.](./media/RCS-Context-specific-mapping-TreeCustom.PNG)

### <a name="run-the-configured-format"></a>A konfigurált formátum futtatása

1.  A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Leképezések megismerési formátuma** elemet.
2.  A **Verziók** gyorslapon kattintson a **Futtatás** lehetőségre.
3.  Válassza ki az **OK** lehetőséget.

Figyelje meg, hogy a kijelölt ER formátum végrehajtása sikertelen. Egy hibaüzenet arról tájékoztat, hogy a **Leképezések megismerése modellhez** és az **1. belépési pont** definícióhoz egynél több modell-leképezés létezik a **Leképezés (általános)** és **Leképezés (általános) egyéni** modell-leképezés konfigurációjában. Az üzenet azt is javasolja, hogy az egyik konfigurációt az alapértelmezett konfigurációként válassza ki.

![ER konfigurációs lap hibaüzenettel.](./media/RCS-Context-specific-mapping-FormatRunCustomFailed.PNG)

### <a name="define-a-default-mapping-configuration"></a>Alapértelmezett leképezési konfiguráció definiálása

Kövesse ezeket a lépéseket a **Leképezés (általános) egyéni** modell-leképezési konfiguráció alapértelmezett konfigurációként való meghatározásához, hogy ennek leképezéseit a rendszer adatforrásként használhassa a **Leképezések megismerési formátuma** ER-formátumban.

1.  A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Leképezések (általános) egyéni** elemet.
2.  Ha szükséges, a **szerkesztés** gombbal az aktuális lapot szerkesztésre készre állíthatja.
3.  Állítsa az **Alapértelmezett a modell-hozzárendeléshez** beállítást **Igen** értékre.
4.  Válassza a **Mentés** lehetőséget.

![ER konfigurációs lap, Az alapértelmezett modell-leképezés csúszka Igen értékre állítva.](./media/RCS-Context-specific-mapping-MappingsCustomDefault.PNG)

### <a name="run-the-configured-format"></a>A konfigurált formátum futtatása

1.  A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Leképezések megismerési formátuma** elemet.
2.  A **Verziók** gyorslapon kattintson a **Futtatás** lehetőségre.
3.  Válassza ki az **OK** lehetőséget.

Figyelje meg, hogy a kijelölt ER formátum végrehajtása sikeres. A webböngésző felajánlja a végrehajtható ER formátummal létrehozott szövegfájl letöltését. Mivel ez a formátum úgy van beállítva, hogy az **1. belépési pont** definícióját használja, és a **Leképezés (általános) egyéni** modell-leképezési konfigurációt választották ki alapértelmezett konfigurációként, a végrehajtott ER formátum a **Leképezés (általános) egyéni** konfiguráció adatforrásként a **Leképezési (általános) másolat** leképezését használja. Ezért a letöltött fájlok tartalmazzák az **1. általános funkció egyéni** szöveget.

> [!NOTE]
> Ha megváltoztatja azt a vállalatot, amelybe éppen bejelentkezett, és újra futtatja ezt az ER formátumot, ugyanaz a tartalom jelenik meg a létrehozott fájlban, mert az alapértelmezett ER modell-hozzárendelési konfiguráció nem tartalmaz vállalattól függő korlátozásokat.

## <a name="multiple-mixed-model-mappings-case"></a>Több vegyes modell-hozzárendelési eset

A szükséges ER-összetevők megtervezéséhez kövesse a témakör [3. függelékének](#appendix3) lépéseit. Most megvan a **Leképezés (Általános)**, **Leképezés (Általános) egyéni** és **Leképezés (FR) modell-leképezési** konfiguráció, amelyek tartalmazzák az **1. belépési pont** meghatározásához tartozó modell-leképezést.

Figyelje meg, hogy a **Leképezés (FR)** modell-hozzárendelési konfiguráció 1. verziója úgy van beállítva, hogy csak a **Leképezések megismerési modellje** modell ER formátumaira érvényes, amelyek a francia ország/régió környezettel rendelkező Finance vállalatokon futnak.

![ER konfigurációs lap, Modell-leképezés (ER) konfiguráció.](./media/RCS-Context-specific-mapping-TreeFR.PNG)

### <a name="run-the-configured-format"></a>A konfigurált formátum futtatása

1.  Módosítsa a vállalatot **FRSI** értékre.
2.  A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Leképezések megismerési formátuma** elemet.
3.  A **Verziók** gyorslapon kattintson a **Futtatás** lehetőségre.
4.  Válassza ki az **OK** lehetőséget.

Figyelje meg, hogy a kijelölt ER formátum végrehajtása sikeres. A webböngésző felajánlja a végrehajtható ER formátummal létrehozott szövegfájl letöltését. Mivel ez a formátum úgy van beállítva, hogy az **1. belépési pont** definícióját használja, és a **Leképezés (általános) egyéni** modell-leképezési konfigurációt választották ki alapértelmezett konfigurációként, a végrehajtott ER formátum a **Leképezés (általános) egyéni** konfiguráció adatforrásként a **Leképezési (általános) másolat** leképezését használja. Ezért a letöltött fájlok tartalmazzák az **1. általános funkció egyéni** szöveget.

### <a name="define-the-france-specific-mapping-configuration-as-the-default-configuration"></a>A Franciaországra jellemző leképezési konfiguráció meghatározása alapértelmezett konfigurációként

Hajtsa végre az alábbi lépéseket, ha alapértelmezett konfigurációként meg szeretné határozni a **Leképezés (FR)** modell hozzárendelésének konfigurációját. Ne feledje, hogy mivel ez a megfeleltetés Franciaországra vonatkozik, a program alapértelmezett leképezésként kezeli az összes olyan modell-hozzárendelési konfiguráció közötti, amelynél a **FR** országkód szerepel az **ISO ország/régiókódok** mezőben.

1.  A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Leképezések (FR)** elemet.
2.  Ha szükséges, a **szerkesztés** gombbal az aktuális lapot szerkesztésre készre állíthatja.
3.  Állítsa az **Alapértelmezett a modell-hozzárendeléshez** beállítást **Igen** értékre.
4.  Válassza a **Mentés** lehetőséget.

![ER konfigurációs lap, Leképezés (FR) konfiguráció, Alapértelmezett modell-leképezés csúszka Igen értékre állítva.](./media/RCS-Context-specific-mapping-TreeFRDefault.PNG)

### <a name="run-the-configured-format"></a>A konfigurált formátum futtatása

1.  A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Leképezések megismerési formátuma** elemet.
2.  A **Verziók** gyorslapon kattintson a **Futtatás** lehetőségre.
3.  Válassza ki az **OK** lehetőséget.

Figyelje meg, hogy a kijelölt ER formátum végrehajtása sikeres. A webböngésző felajánlja a végrehajtható ER formátummal létrehozott szövegfájl letöltését. Mivel ez a formátum úgy van beállítva, hogy az **1. belépési pont** definícióját használja, és a **Leképezés (FR)** modell-leképezési konfigurációt választották ki alapértelmezett konfigurációként, a végrehajtott ER formátum a **Leképezés (FR)** konfiguráció adatforrásként a **Leképezés (FR)** leképezését használja. Ezért a letöltött fájlok tartalmazzák az **1. FR funkció** szöveget.

> [!NOTE]
> Ha módosítja azt a vállalatot, amelybe jelenleg be van jelentkezve, és újra szeretné futtatni ezt az ER formátumot, akkor a kimenet a kiválasztott vállalat ország-/régióbeli környezetén múlik.

## <a name="other-model-mapping-cases"></a>Más modell-hozzárendelési esetek

Amint már láttuk, a következő módon lehet kiválasztani egy modell hozzárendelését az ER-formátum végrehajtásához:

- A modell-hozzárendelés definíciója, amelyet az ER formátum használ (**1. belépési pont** a jelen témakörben használt példákban).
- Minden olyan leképezési konfiguráció, amely a megadott definícióval rendelkezik, és amely megfelel a konfigurált ország-/régióbeli környezeti korlátozásoknak, használható az ER-formátum futtatására (a jelen témakörben szereplő példákban: **Leképezés (általános)**, **Leképezés (általános) egyéni** és **Leképezés (FR)**).
- Az ország-/régió környezeti korlátozásokat tartalmazó alapértelmezett modell-hozzárendelések a legmagasabb kiválasztási prioritással rendelkeznek (a jelen témakörben szereplő példákban: **Leképezés (FR)**).
- Az ország/régió környezeti korlátozásokat nem tartalmazó alapértelmezett modell-hozzárendelések a második legmagasabb kiválasztási prioritással rendelkeznek (a jelen témakörben szereplő példákban: **Leképezés (általános) egyéni**).
- Az ország/régió környezeti korlátozásokat tartalmazó modell-hozzárendelések kiválasztási prioritása magasabb, mint egy olyan modell-hozzárendelés, amely nem rendelkezik az ország-/régióbeli környezet korlátozásával.

A következő táblázat a modell-hozzárendelési kiválasztéások eredményeivel kapcsolatban tartalmaz tájékoztatást a modell hozzárendelési beállítások minden egyes esetére vonatkozóan:

- Az 1. oszlop azt jelzi, hogy melyik az első olyan modell, amelynél nincsenek megadva az ország-/régióbeli környezet korlátozásai (például a megosztott **Leképezés (általános)** hozzárendelés), és ha igen, akkor az **Alapértelmezett a modell-leképezéshez** beállítás **Igen** értékre van-e állítva.
- Az 2. oszlop azt jelzi, hogy melyik a második olyan modell, amelynél nincsenek megadva az ország-/régióbeli környezet korlátozásai (például a megosztott **Leképezés (általános) egyéni** hozzárendelés), és ha igen, akkor az **Alapértelmezett a modell-leképezéshez** beállítás **Igen** értékre van-e állítva.
- Az 3. oszlop azt jelzi, hogy melyik az első olyan modell, amelynél meg vannak adva az A ország-/régióbeli környezet korlátozásai (például a Franciaország-specifikus **Leképezés (FR)** hozzárendelés), és ha igen, akkor az **Alapértelmezett a modell-leképezéshez** beállítás **Igen** értékre van-e állítva.
- Az 4. oszlop azt jelzi, hogy melyik a második olyan modell, amelynél meg vannak adva az A ország-/régióbeli környezet korlátozásai, és ha igen, akkor az **Alapértelmezett a modell-leképezéshez** beállítás **Igen** értékre van-e állítva.
- Az 5. oszlop bemutatja az ER-formátum végrehajtására vonatkozó modell-leképezési kiválasztás eredményét egy olyan vállalat irányítása alatt, amely A ország/régiós környezettel rendelkezik.
- Az 6. oszlop bemutatja az ER-formátum végrehajtására vonatkozó modell-leképezési kiválasztás eredményét egy olyan vállalat irányítása alatt, amely B ország/régiós környezettel rendelkezik.

A táblában egy pluszjel (+) jelzi a modell-hozzárendelés konfigurációjának jelenlétét a Microsoft Azure szolgáltatás jelenlegi példányán, amely az ER formátum (Finance vagy RCS) futtatására szolgál.

| Láda | 1. modell-leképezés ország/régiós környezet nélkül (MM1) | 2. modell-leképezés ország/régiós környezet nélkül (MM2) | 1. modell-leképezés A ország/régiós környezettel (MM1A) | 2. modell-leképezés A ország/régiós környezettel (MM2A) | Futtatás egy olyan vállalat ellenőrzése alatt, amelynek A ország-/régióbeli környezettel rendelkezik. | Futtatás egy olyan vállalat ellenőrzése alatt, amelynek B ország-/régióbeli környezettel rendelkezik. |
|---------|---------|---------|---------|---------|---------------------------|----------------------------|
|         |     1   |     2   |    3    |    4    |           5               |            6               |
|     1   |         |         |         |         | Hiba (hiányzó leképezés)   | Hiba (hiányzó leképezés)    |
|     2   |     +   |         |         |         | MM1                       | MM1                        |
|     3   |     +   |     +   |         |         | Hiba (több leképezés) | Hiba (több leképezés)  |
|     4   |     +   |         |    +    |         | MM1A                      | MM1                        |
|     5   |     +   |         |    +    |    +    | Hiba (több leképezés) | MM1                        |
|     6   |     +   | alapértelmezett |    +    |    +    | MM2                       | MM2                        |
|     7   |     +   |         | alapértelmezett |         | MM1A                      | MM1                        |
|     8   |     +   |         | alapértelmezett |    +    | MM1A                      | MM1                        |
|     9   |     +   |         | alapértelmezett | alapértelmezett | Hiba (több leképezés) | MM1                        |
|    10   | alapértelmezett |         |         |         | MM1                       | MM1                        |
|    11   | alapértelmezett |    +    |         |         | MM1                       | MM1                        |
|    12   | alapértelmezett |         |    +    |         | MM1                       | MM1                        |
|    13   | alapértelmezett | alapértelmezett |         |         | Hiba (több leképezés) | Hiba (több leképezés)  |
|    14   | alapértelmezett |         | alapértelmezett |         | MM1A                      | MM1                        |
|    15   | alapértelmezett |         | alapértelmezett | alapértelmezett | MM1A                      | MM2A                       |
|    16   |         |         |    +    |    +    | MM1A                      | MM2A                       |
|    17   |         |         | alapértelmezett | alapértelmezett | MM1A                      | MM2A                       |

## <a name="learn-what-mapping-was-used-in-the-execution-of-an-er-format"></a>Útmutató egy ER-formátum végrehajtása során használt leképezés megállapításához

### <a name="configure-er-user-parameters"></a>ER felhasználói paraméterek konfigurálása

1.  A **Konfigurációk** oldal műveleti ablaktábláján, a **KONFIGURÁCIÓK** lapon, válassza a **Felhasználói paraméterek** lehetőséget.
2.  A **Futtatás hibakeresési módban** beállítása legyen **Igen**.
4.  Válassza ki az **OK** lehetőséget.

### <a name="run-the-configured-format"></a>A konfigurált formátum futtatása

1.  A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Leképezések megismerési formátuma** elemet.
2.  A **Verziók** gyorslapon kattintson a **Futtatás** lehetőségre.
3.  Válassza ki az **OK** lehetőséget.

### <a name="review-the-er-debug-log"></a>Az ER hibakeresési napló áttekintése

1.  A navigációs ablakban nyissa meg a **Modulok \> Szervezeti felügyelet \> Elektronikus jelentéskészítés \> Konfiguráció hibakeresési naplója** lehetőséget.
2.  Jelölje be a **Lap újratöltése** gombot.

![ER futtatási naplók oldala.](./media/RCS-Context-specific-mapping-DebugLog.PNG)

Figyelje meg, hogy a végrehajtott ER-formátumhoz új rekord lett hozzáadva a ER hibakeresési naplóhoz. Mivel a rekord **Szint** mezője az **információ** értékre van állítva, a rekord tájékoztató jellegű. Mivel a Formátum-összetevő mező **Leképezési konfiguráció** értékre van állítva, a rekord tájékoztatást nyújt a modell-leképezésről, amelyet a **Leképezés megismerési formátuma** ER formátum végrehajtása során használt a rendszer (amelyet a **Konfiguráció neve** mezőben kiválasztottak). A **létrejövő szöveg** mező tartalma azt jeleníti meg, hogy a jelentés futtatásához a **Leképezési (FR)** hozzárendelési összetevőt használja a rendszer, amely a **Leképezés (FR)** konfigurációban található.

## <a name="appendix-1"></a><a name="appendix1"></a>1. függelék

### <a name="configure-a-sample-data-model"></a>Mintaadatmodell konfigurálása

Jelentkezzen be a RCS-példányba.

Ebben a példában létrehozunk egy konfigurációt a Litware, Inc. mintavállalatra vonatkozóan. A lépések végrehajtásához először az RCS-ben a [Konfigurációszolgáltató létrehozása, és megjelölés aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) részben leírt lépéseket kell végrehajtani.

#### <a name="create-an-er-data-model-configuration"></a>ER adatmodell-konfiguráció létrehozása

1.  Az alapértelmezett irányítópulton válassza az **Elektronikus jelentéskészítés** elemet.
2.  Válassza a **Jelentéskészítési konfigurációk** csempét.
3.  A **Konfigurációk** oldalon válassza a **Konfiguráció létrehozása** elemet.
4.  Írja be a legördülő párbeszédpanel **Név** mezőjébe ezt: **Leképezések megismerési modellje**.
5.  Válassza a **Konfiguráció létrehozása** lehetőséget.
6.  Válassza ki a **Konfigurációs összetevők** gyorslapot.

Figyelje meg, hogy ez az ER-konfiguráció 1. tervezeti verziója készen áll a szerkesztésre. Ez a verzió tartalmazza az adatmodell összetevőt.

#### <a name="design-a-sample-data-model"></a>Mintaadatmodell tervezése

1.  A **Konfigurációk oldalon** válassza a **Tervező** elemet.
2.  Válassza az **Új** lehetőséget.
3.  A legördülő párbeszédpanel **Név** mezőjébe írja be az **1. belépési pont** kifejezést.
4.  Válassza a **Hozzáadás** lehetőséget.
5.  Válassza az **Új** lehetőséget.
6.  Írja be a legördülő párbeszédpanel **Név** mezőjébe ezt: **Funkció leírása**.
7.  Válassza a **Hozzáadás** lehetőséget.
8.  Válassza az **Új** lehetőséget.
9.  Írja be a legördülő párbeszédpanel **Új csomópont** mezőcsoportba ezt: **Modell gyökere**.
10. A **Név** mezőbe írja be a következőt: **2. belépési pont**.
11. Válassza ki a **2. belépési pont** elemet.
12. Válassza a **Hozzáadás** lehetőséget.
13. Válassza az **Új** lehetőséget.
14. Írja be a legördülő párbeszédpanel **Név** mezőjébe ezt: **Funkció leírása**.
15. Válassza a **Hozzáadás** lehetőséget.

    ![ER adatmodell-tervező oldal.](./media/RCS-Context-specific-mapping-Model.PNG)

16. Válassza a **Mentés** lehetőséget.
17. Zárja be a lapot.

#### <a name="complete-the-modified-version-of-the-model-configuration"></a>Az modellkonfiguráció módosított verziójának elvégzése

1.  Válassza a **Konfigurációk** oldal **Verziók** gyorslapján a **Állapot módosítása** elemet.

    > Módosítsa a megtervezett modellkonfiguráció állapotát **Tervezet** értékről **Befejeződött** értékre, így használható a szükséges modell-leképezések és formátumok tervezéséhez.

2.  Válassza a **Kész** lehetőséget.
3.  Válassza ki az **OK** lehetőséget.

Ne feledje, hogy a létrehozott konfiguráció befejeződött 1-es verzióként lesz mentve.

### <a name="configure-a-sample-model-mapping"></a>Mintamodell-leképezés konfigurálása

#### <a name="create-an-er-model-mapping-configuration"></a>ER-modellhozzárendelés-konfiguráció létrehozása

1.  A **Konfigurációk** oldalon válassza a **Konfiguráció létrehozása** elemet.
2.  A legördülő párbeszédpanel **Új** mezőcsoportjában válassza az **Leképezések megismerési modellje adatmodellen alapuló modell-leképezés** beállítást.
3.  A **Név** mezőbe írja be a következőt: **Leképezés (általános)**.
4.  Az **Adatmodell definíciója** mezőben válassza a **1. belépési pont** lehetőséget.
5.  Válassza a **Konfiguráció létrehozása** lehetőséget.

Figyelje meg, hogy ez az ER-konfiguráció 1. tervezeti verziója készen áll a szerkesztésre. Ez a verzió tartalmazza az modell-leképezési összetevőt.

#### <a name="design-a-sample-model-mapping"></a>Mintamodell-leképezés tervezése

1.  A **Konfigurációk** oldalon válassza a **Tervező** elemet.

    Figyelje meg, hogy a **Modellhez** iránytípus modell-leképezését a rendszer automatikusan hozzáadta ehhez az összetevőhöz az **1. belépési pont** meghatározásához.
    
2.  Válassza ki a **Tervezőt** a hozzáadott modell-hozzárendelés szerkesztésének megkezdéséhez.
3.  Válassza az **Adatmodell** szakaszban válassza a **Szerkesztés** elemét.
4.  A **Képlet** mezőbe írja be a következőt: **1. általános funkció**.
5.  Válassza a **Mentés** lehetőséget.
6.  Zárja be a **Képlettervező** lapot.

    ![ER modellleképezés tervezőlap, 1. beviteli pont definíciója.](./media/RCS-Context-specific-mapping-Mapping1.PNG)

7.  Válassza a **Mentés** lehetőséget.
8.  Zárja be a **Modell-hozzárendelési tervező** lapot.
9.  Válassza az **Új** lehetőséget.
10. A **Definíció** mezőben válassza a **2. belépési pont** lehetőséget.
11. A **Név** mezőbe írja be a következőt: **2. leképezés (általános)**.
12. Válassza a **Tervező** lehetőséget.
13. Válassza az **Adatmodell** szakaszban válassza a **Szerkesztés** elemét.
14. A **Képlet** mezőbe írja be a következőt: **2. általános funkció**.
15. Válassza a **Mentés** lehetőséget.
16. Zárja be a **Képlettervező** lapot.

    ![ER modell-leképezés tervezőlap, 2. beviteli pont definíciója.](./media/RCS-Context-specific-mapping-Mapping2.PNG)

17. Válassza a **Mentés** lehetőséget.
18. Zárja be a **Modell-hozzárendelési tervező** lapot.

    ![ER modell-leképezések oldal beviteli pont definíciókkal.](./media/RCS-Context-specific-mapping-Mappings.PNG)

19. Zárja be a **Modell-hozzárendelések** lapot.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>A modell-leképezési konfiguráció módosított verziójának elvégzése

1.  Válassza a **Konfigurációk oldal** **Verziók** gyorslapján az **Állapot módosítása** elemet.

    > Módosítsa a megtervezett modell-leképezési konfiguráció állapotát **Tervezet** értékről **Befejeződött** értékre, így használható az ER formátumok tervezéséhez.

2.  Válassza a **Kész** lehetőséget.
3.  Válassza ki az **OK** lehetőséget.

Ne feledje, hogy a létrehozott konfiguráció befejeződött 1-es verzióként lesz mentve.

### <a name="configure-a-sample-format"></a>Mintaformátum konfigurálása

#### <a name="create-an-er-format-configuration"></a>ER-formátumkonfiguráció létrehozása

1.  A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Leképezések megismerési modellje** elemet.
2.  Válassza a **Konfiguráció létrehozása** lehetőséget.
3.  A legördülő párbeszédpanel **Új** mezőcsoportjában válassza az **Leképezés megismerési modellje adatmodellen alapuló formátum** beállítást.
4.  A **Név** mezőbe írja be: **Leképezés megismerési formátuma**.
5.  Az **Adatmodell definíciója** mezőben válassza a **1. belépési pont** lehetőséget.
6.  Válassza a **Konfiguráció létrehozása** lehetőséget.

Figyelje meg, hogy ez az ER-konfiguráció 1. tervezeti verziója készen áll a szerkesztésre. Ez a verzió tartalmazza az formátum-összetevőt.

#### <a name="design-a-sample-format"></a>Mintaformátum tervezése

1.  A **Konfigurációk** oldalon válassza a **Tervező** elemet.
2.  Válassza a **Gyökér hozzáadása** elemet.
3.  A **Szöveg** mezőben válassza ki a **Karakterlánc** elemet.
4.  Válassza ki az **OK** lehetőséget.

#### <a name="bind-format-elements-to-a-data-source"></a>Formátum-összetevők összekötése az adatforráshoz

1.  A **Formátumtervező** oldal **Leképezések** lapján bontsa ki a modell adatforrását.
2.  Válassza ki a **Funkciók leírása** mezőt.
3.  Válassza a **Bind** elemet.

    ![ER-formátumtervező oldal.](./media/RCS-Context-specific-mapping-Format.PNG)

4.  Válassza a **Mentés** lehetőséget.
5.  Zárja be a lapot.

## <a name="appendix-2"></a><a name="appendix2"></a>2. függelék

### <a name="configure-a-sample-model-mapping-for-general-customization"></a>Minta modell-leképezés konfigurálása az általános testreszabáshoz

Előfordulhat, hogy testre szeretne szabni egy olyan modell-hozzárendelést, amelyet a konfigurációs szolgáltató (partner) biztosított Önnek, és aztán a testreszabott verziót használja adatforrásként az ER-formátumaihoz. Ebben az esetben létre kell hoznia egy egyéni ER modell-hozzárendelési konfigurációt a meglévő modell-hozzárendelésekben szükséges változtatások elvégzéséhez. Az ebben a függelékben ismertetett eljárások a **Leképezés (általános)** modell hozzárendelését használják példaként.

#### <a name="create-an-er-model-mapping-configuration"></a>ER-modellhozzárendelés-konfiguráció létrehozása

1.  A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Leképezések (általános)** elemet.
2.  Válassza a **Konfiguráció létrehozása** lehetőséget.
3.  A legördülő párbeszédpanel **új** mezőcsoportjában válassza a következőt: **Származtatás a következő névből: Leképezés (általános), Litware, Inc.**.
4.  A **Név** mezőbe írja be a következőt: **Leképezés (általános) egyéni**.
5.  Válassza a **Konfiguráció létrehozása** lehetőséget.

Figyelje meg, hogy ez az ER-konfiguráció 1. tervezeti verziója készen áll a szerkesztésre.

#### <a name="design-a-sample-model-mapping"></a>Mintamodell-leképezés tervezése

1.  A **Konfigurációk** oldalon válassza a **Tervező** elemet.

    > Figyelje meg, hogy az alapkonfiguráció modell-leképezéseit a program automatikusan átmásolta ebbe a konfigurációba.

2.  Válassza ki a **Leképezési (Általános) másolat** leképezést.
3.  Válassza a **Tervező** lehetőséget.
4.  Válassza az **Adatmodell** szakaszban válassza a **Szerkesztés** elemét.
5.  A **Képlet** mezőbe írja be a következőt: **1. általános funkció egyéni**.
6.  Válassza a **Mentés** lehetőséget.
7.  Zárja be a lapot.

    ![ER modell-leképezés tervezőlapja, Általános funkciók 1 – egyéni képlet.](./media/RCS-Context-specific-mapping-Mapping1Custom.PNG)

8.  Válassza a **Mentés** lehetőséget.
9.  Zárja be a lapot.
10. Válassza ki a **2. leképezés (Általános) másolat** leképezést.
11. Válassza a **Tervező** lehetőséget.
12. Válassza az **Adatmodell** szakaszban válassza a **Szerkesztés** elemét.
13. A **Képlet** mezőbe írja be a következőt: **2. általános funkció egyéni**.
14. Válassza a **Mentés** lehetőséget.
15. Zárja be a lapot.

    ![ER modell-leképezés tervezőlapja, Általános funkciók 2 – egyéni képlet.](./media/RCS-Context-specific-mapping-Mapping2Custom.PNG)

16. Válassza a **Mentés** lehetőséget.
17. Zárja be a lapot.

    ![AZ ER-modell és az adatforrás leképezési lapja a Leképezéshez (általános) a leképezés másolása.](./media/RCS-Context-specific-mapping-MappingsCustom.PNG)

18. Zárja be a lapot.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>A modell-leképezési konfiguráció módosított verziójának elvégzése

1.  Válassza a **Konfigurációk** oldal **Verziók** gyorslapján a **Állapot módosítása** elemet.

    > Módosítsa a megtervezett modell-leképezési konfiguráció állapotát **Tervezet** értékről **Befejeződött** értékre, így használható az ER formátumok tervezéséhez.

2.  Válassza a **Kész** lehetőséget.
3.  Válassza ki az **OK** lehetőséget.

Ne feledje, hogy a létrehozott konfiguráció befejeződött 1-es verzióként lesz mentve.

## <a name="appendix-3"></a><a name="appendix3"></a>3. függelék

### <a name="configure-a-sample-model-mapping-for-countryregion-specific-customization"></a>Minta modell-leképezés konfigurálása az ország/régióspecifikus testreszabáshoz

Néhány ER formátum esetében előfordulhat, hogy az adatok előkészítésére az ország-/régióspecifikus követelmények vonatkoznak. Ebben az esetben egy külön ER modell-hozzárendelési konfigurációt kezelhet, és elkülönítheti ezeknek az ország-/régióspecifikus követelményeknek a végrehajtását az általános végrehajtástól. A függelékben ismertetett eljárások a **Leképezés megismerési formátuma** ER formátum és a Franciaország-specifikus követelményeket használják példaként.

#### <a name="create-an-er-model-mapping-configuration"></a>ER-modellhozzárendelés-konfiguráció létrehozása

Először hozzon létre egy új ER modell-hozzárendelési konfigurációt az ország-/régióspecifikus követelmények végrehajtásához. Használja a saját ER modell-hozzárendelési konfigurációt alapként.

1.  A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Leképezések (általános) egyéni** elemet.
2.  Válassza a **Konfiguráció létrehozása** lehetőséget.
3.  A legördülő párbeszédpanel **Új** mezőcsoportjában válassza a következőt: **Származtatás a következő névből: Leképezés (általános) egyéni, Litware, Inc.**.
4.  A **Név** mezőbe írja be a következőt: **Leképezés (FR)**.
5.  Válassza a **Konfiguráció létrehozása** lehetőséget.

Figyelje meg, hogy ez az ER-konfiguráció 1. tervezeti verziója készen áll a szerkesztésre.

#### <a name="design-a-sample-model-mapping"></a>Mintamodell-leképezés tervezése

1.  A **Konfigurációk** oldalon válassza a **Tervező** elemet.

    > Figyelje meg, hogy az alapkonfiguráció modell-leképezéseit a program automatikusan átmásolta ebbe a konfigurációba.

2.  Válassza ki a **Leképezési (Általános) másolat másolat** leképezést.
3.  Nevezze át a következőre: **Leképezés (FR)**.
4.  Válassza a **Tervező** lehetőséget.
5.  Válassza az **Adatmodell** szakaszban válassza a **Szerkesztés** elemét.
6.  A **Képlet** mezőbe írja be a következőt: **1. FR funkció**.
7.  Válassza a **Mentés** lehetőséget.
8.  Zárja be a lapot.

    ![ER modell-leképezés tervezőlapja, FR funkciók 1 – egyéni képlet.](./media/RCS-Context-specific-mapping-Mapping1FR.PNG)

9.  Válassza a **Mentés** lehetőséget.
10. Zárja be a lapot.
11. Válassza ki a **Leképezési (Általános) 2 másolat másolat** leképezést.
12. Nevezze át a következőre: **2. leképezés (FR)**.
13. Válassza a **Tervező** lehetőséget.
14. Válassza az **Adatmodell** szakaszban válassza a **Szerkesztés** elemét.
15. A **Képlet** mezőbe írja be a következőt: **2. FR funkció**.
16. Válassza a **Mentés** lehetőséget.
17. Zárja be a lapot.

    ![ER modell-leképezés tervezőlapja, FR funkciók 2 – egyéni képlet.](./media/RCS-Context-specific-mapping-Mapping2FR.PNG)

18. Válassza a **Mentés** lehetőséget.
19. Zárja be a lapot.

    ![ER modell leképezése adatforráshoz lap.](./media/RCS-Context-specific-mapping-MappingsFR.PNG)

20. Zárja be a lapot.

#### <a name="specify-countryregion-context-restrictions-for-use"></a>Ország/terület környezeti korlátozásainak megadása a használathoz

1.  Válassza a **Konfigurációk** lap **ISO ország/régiókódok** gyorslapján az **Új** elemet.
2.  Az **ISO** mezőben válassza a **FR** elemet.
3.  Válassza a **Mentés** lehetőséget.

Ne feledje, hogy az ER formátum futtatásához be kell jelentkeznie egy adott vállalatba a Finance szolgáltatásban. Ennek megfelelően a vállalat olyan félnek tekinthető, amely mind az ER formátum végrehajtását és az alap ER adatmodell megfelelő ER modell-leképezésének kiválasztását is szabályozza. A **FR** országkód hozzáadásával megadhatja, hogy ez a modell-hozzárendelés csak akkor legyen elérhető az alapadatmodell ER formátuma általi kiválasztásra, ha a formátum francia ország/régiós környezettel rendelkező vállalat irányítása alatt fut.

Az ER modell-hozzárendelési konfiguráció egyetlen verziójához több ország-/régiókódot is hozzáadhat. Ily módon a modell-hozzárendelési konfigurációban található modell-leképezések használhatók olyan ER formátum esetében, amely más ország/régiós környezettel rendelkező vállalatok felügyelete alatt fut.

Ne felejtse el, hogy az ország-/régiókódok listája meg van adva az ER modell-hozzárendelési konfiguráció mindegyik verziójához, és a verziónként eltérhet.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>A modell-leképezési konfiguráció módosított verziójának elvégzése

1.  Válassza a **Konfigurációk** oldal **Verziók** gyorslapján a **Állapot módosítása** elemet.

    > Módosítsa a megtervezett modell-leképezési konfiguráció állapotát **Tervezet** értékről **Befejeződött** értékre, így használható az ER formátumok tervezéséhez.

2.  Válassza a **Kész** lehetőséget.
3.  Válassza ki az **OK** lehetőséget.

Ne feledje, hogy a létrehozott konfiguráció befejeződött 1-es verzióként lesz mentve.

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)

[ER modell-leképezés kezelése külön ER-konfigurációkban](./tasks/er-manage-model-mapping-configurations-july-2017.md)

[Ország/régióspecifikus tartalom alkalmazása](../lcs-solutions/apply-country-context.md)

## <a name="frequently-asked-questions"></a>Gyakori kérdések

#### <a name="i-configured-two-shared-er-model-mapping-configurations-in-rcs-and-marked-one-of-them-as-the-default-model-mapping-configuration-i-successfully-ran-an-er-format-that-was-created-for-the-same-base-er-data-model-configuration-to-test-model-mappings-i-then-imported-the-whole-er-solution-er-data-model-two-er-model-mapping-configurations-and-er-format-configuration-into-finance-why-do-i-receive-an-error-message-when-i-try-to-run-the-same-er-format-in-finance"></a>Két megosztott modell-hozzárendelési konfigurációt állítottam be a RCS-ben, és egyiket az alapértelmezett modell-hozzárendelési konfigurációként jelöltem meg. Sikeresen futtattam egy a modell-hozzárendelések tesztelésére szolgáló, ugyanarra az alapadat-modell-konfigurációra létrehozott, ER formátumot. Ezt követően a teljes ER megoldást (ER-adatmodell, a két ER modell-hozzárendelési konfiguráció és az ER formátumkonfiguráció) importáltam a Finance szolgáltatásba. Miért jelenik meg hibaüzenet, amikor ugyanezt az ER formátumot szeretném futtatni a Finance modulban?
Az alapértelmezett modell-hozzárendelési beállítás a környezetspecifikus. Ez a RCS-ben van beállítva, de nem exportálható a Finance modulba. Az ER formátum sikeres futtatásához meg kell jelölnie az egyik ER modell-leképezési konfigurációt alapértelmezett modell-leképezési konfigurációként a Finance modulban.

#### <a name="i-configured-one-model-mapping-as-a-shared-model-mapping-and-completed-the-draft-version-of-it-i-then-added-a-new-model-mapping-configuration-for-same-data-model-and-configured-it-as-french-specific-why-is-the-shared-model-mapping-selected-when-i-run-an-er-format-even-though-this-er-format-uses-the-correct-root-definition-and-execution-is-done-under-the-control-of-the-company-that-has-french-countryregion-context"></a>Egy modell-leképezést megosztott modell-leképezésként konfiguráltam, és véglegesítettem a tervezet verzióját. Ezt követően új modell-hozzárendelési konfigurációt adtam hozzá ugyanahhoz az adatmodellhez, és azt a Franciaország-specifikusnak állítottam be. Miért van kiválasztva az ER formátum futtatásakor kiválasztott megosztott modell-hozzárendelés, még akkor is, ha az adott ER formátum a megfelelő gyökérdefiníciót használja, és a végrehajtás a francia ország/régió környezettel működő vállalat ellenőrzése alatt történik?
Győződjön meg róla, hogy a megosztott modell-hozzárendelés konfiguráció nem az alapértelmezett modell-hozzárendelési konfigurációként van megjelölve. Ellenkező esetben a megfeleltetés kiválasztása során ennek magasabb lesz a prioritása. Arról is győződjön meg, hogy a Franciaország-specifikus modell-leképezési konfigurációt a rendszer figyelembe veszi, amikor az ER-formátum végrehajtása során kiválasztják a leképezést. Az ER modell-hozzárendelési konfiguráció csak akkor érhető el, ha a következő feltételek közül legalább az egyik teljesül:
- Az ER modell-leképezési konfiguráció legalább egy verzió vagy **Befejeződött** vagy **Megosztott** állapottal rendelkezik. Ebben az esetben a legnagyobb verziószámú verziót használja a rendszer az ER formátum végrehajtásához.
- A **Tervezet futtatása** lehetőség ez ER modell-leképezési konfigurációnál be van kapcsolva. Ebben az esetben a **Tervezet** állapottal rendelkező verziót használja a rendszer az ER formátum végrehajtásához.
> A **Tervezet futtatása** beállítás akkor válik elérhetővé az egyes ER modell-leképezési konfigurációk **Konfigurációk** oldalán, ha a **Futtatási beállítás** ER felhasználói paraméter be van kapcsolva.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
