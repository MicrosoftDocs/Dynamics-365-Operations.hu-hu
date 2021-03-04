---
title: Hullámcímkék újranyomtatása és érvénytelenítése
description: Ez a témakör azt mutatja be, hogyan lehet érvényteleníteni és újranyomtatni a meglévő hullám-címkéket.
author: GarmMSFT
manager: PJacobse
ms.date: 07/09/2020
ms.topic: article
ms.service: dynamics-ax-applications
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSWaveTableListPage, WHSWorkException, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelLayout, WHSWaveLabelType, WHSWaveLabelTemplateGroup
audience: Application User
ms.reviewer: PJacobse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-07-09
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 0efa9400a3bf29e4e0dd56d9138cf8c3825556c7
ms.sourcegitcommit: a26e4963d40796da21ce6581cfb2f4d9db4f6776
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "4429961"
---
# <a name="reprint-and-void-wave-labels"></a>Hullámcímkék újranyomtatása és érvénytelenítése

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan kezelhetők a hullámfeldolgozással létrejövő címkék. (Részletes leírás és konfigurációs utasítások: [Hullámcímkék nyomtatásának konfigurálása](../warehousing/configure-wave-label-printing.md) .)

A hullámcímkéket bármikor újra lehet nyomtatni. Előfordulhat például, hogy ki kell nyomtatnia egy címkét, ha a meglévő címke elveszett vagy sérült. Másik lehetőségként előfordulhat, hogy a raktár dolgozójának vagy felettesének újra kell nyomtatnia egy teljes címketekercset, ha a hullámcímkék egy teljes sorozatának száma és/vagy összetétele megváltozott (például a készlethiány vagy más okok miatt). Előfordul, hogy a teljes tekercset akkor is újra kell nyomtatni, ha csak a dobozok száma módosult, hogy az egyes címkék „X/Y doboz” szakaszában a teljes szám pontos maradjon.

A hullámcímkék újranyomtatása funkció a következő funkciókat támogatja:

- A címkék újranyomtatása mind a raktározási alkalmazásból, mind a funkciógazdag kliensből.
- Címkék érvénytelenítése és egyidejű újranyomtatása. (Például a címkék érvénytelenítésének képessége be van ágyazva a rövid kitárolási forgatókönyvekbe.)
- Hullámcímke-előzmények törlése.

Ez a témakör olyan forgatókönyvek gyűjteményét mutatja be, amelyek példákon keresztül mutatják be a munkát a címkék újranyomtatása funkcióval.

> [!IMPORTANT]
> Az ebben a témakörben ismertetett eseteket végigkövetéséhez, először be kell kapcsolnia, és konfigurálnia kell a szükséges hullámnyomtatási funkciókat a [Hullámcímkék nyomtatásának konfigurálása](../warehousing/configure-wave-label-printing.md) témakörben leírtak szerint. Az ebben a témakörben szereplő forgatókönyvek közül több is megköveteli, elvégezze az abban a témakörben található forgatókönyveket az előfeltételt jelentő mintaadatok létrehozásához.

## <a name="scenario-1-reprint-labels-from-the-web-client"></a>1. eset: Címkék újranyomtatása a webes ügyfélprogramból

A következő lapokon megtekintheti és újranyomtathatja a hullámcímkéket. A Művelet ablaktábla **Szállítmányok** lapjának **Kapcsolódó információk** csoportjában válassza a **Hullámcímkék** elemet.

- Minden szállítmány \> Szállítmány adatai
- Minden rakomány \> Rakomány adatai
- Minden hullám
- Hullámcímkék
- Hullámcímke előzményei

Ha újra szeretne nyomtatni egy hullámcímkét a webes ügyfélből, hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.
1. Válassza ki azt a hullámot, amelyből a címkéket újra szeretné nyomtatni.
1. A Műveleti ablaktáblán a **Hullám** lapon a **Nyomtatás** csoportban válassza a **Hullámcímkék** lehetőséget.
1. Hajtsa végre a következő lépések valamelyikét vagy mindkettőt:

    - A címke újranyomtatásához a **Nyomtató neve** mezőben válassza ki a nyomtatót. (Hagyja üresen ezt a mezőt, ha a címke újranyomtatása nélkül szeretné frissíteni a hullámcímkék adatait.)
    - A címke frissítéséhez jelölje be a **Hullámcímke adatainak frissítése** jelölőnégyzetet. (Akkor hagyja üresen ezt a jelölőnégyzetet, ha csak az előző címkét szeretné újranyomtatni.)

    > [!NOTE]
    > Minden alkalommal, amikor kinyomtat vagy újranyomtat egy hullámcímkét, az adatok a megfelelő hullámcímke-elrendezés alapján lesznek átalakítva, és a program minden helyőrzőt felülír a tényleges értékekkel. A létrejövő karakterlánc tárolása rekordként történik a hullámcímkék előzményeiben. Ha törli a jelölést a **Hullámcímkék adatainak frissítése** jelölőnégyzetből, akkor a rendszer a tárolt Zebra Programming Language (ZPL) adatokat használja a címke újranyomtatásakor. Ha be van jelölve a **Hullám-címke adatainak frissítése** jelölőnégyzet, új karakterlánc jön létre. A program újraszámítja a meglévő hullám-címkéket, valamint a felesleges címkéket (például a kapcsolódó munkasorok érvénytelenítve vagy módosítva lettek) **Érvénytelenítve** értékkel jeleníti meg, és nem nyomtatja újra.

1. A kiválasztás jóváhagyásához kattintson az **OK** gombra.

## <a name="scenario-2-reprint-labels-from-the-warehousing-app"></a>2. eset: Címkék újranyomtatása a raktározási alkalmazásból

Ezt a forgatókönyvet általában akkor kell alkalmazni, ha egy címketekercse elveszett vagy sérült. Egy példa bemutatja, hogy hogyan lehet beállítani a mobileszköz menüelemeit, amelyek lehetővé teszik a dolgozók számára egy vagy több címke újranyomtatását. Ezt követően bemutatja, hogy hogyan kell használni ezeket az új menüelemeket, miközben egy mobileszközön dolgozik.

### <a name="set-up-the-required-menu-items-and-menu-for-the-mobile-device"></a>A szükséges menüelemek és menük beállítása a mobileszközhöz

Mielőtt a dolgozók egy mobileszközről újranyomtathatják a címkéket, be kell állítani a menüelemeket a funkció biztosításához, majd ezeket az elemeket hozzá kell adni a raktározási alkalmazás menüjéhez.

#### <a name="create-new-mobile-device-menu-items"></a>Új mobileszköz-menüelemek létrehozása

Hajtsa végre a következő lépéseket, ha új menüelemeket szeretne létrehozni a címkék újranyomtatásához a raktári alkalmazásból.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. Hozzon létre egy menüelemet, és állítsa be hozzá a következő értékeket:

    - **Menüelem neve:** *Egy hullámcímke újranyomtatása*
    - **Cím:** *Egy hullámcímke újranyomtatása*
    - **Mód:** *Közvetett*
    - **Tevékenységkód:** *Egy hullámcímke újranyomtatása*

1. Hozzon létre egy második menüelemet, és állítsa be hozzá a következő értékeket:

    - **Menüelem neve:** *Címkék újranyomtatása (Cikk)*
    - **Cím:** *Hullámcímkék újranyomtatása (cikk)*
    - **Mód:** *Közvetett*
    - **Tevékenységkód:** *Több hullámcímke újranyomtatása*
    - **Munkalista-csoportosítási szűrő megjelenítése:** *Igen*
    - **Csoportosító rendszermező:** *ShipmentID*
    - **Csoportosító rendszercímke:** *Szállítmányazonosító*
    - **Nyomtatási mód:** *Termék*

1. A művelet ablaktáblán válassza ki a **Mezőlista** elemet a lap megnyitásához, ahol kiválaszthatja azokat a mezőket, amelyeket meg szeretne jeleníteni, hogy a dolgozók azonosíthassák a megfelelő címketekercset.
1. Legfeljebb hét mezőt lehet megjeleníteni. A legördülő listák segítségével kiválaszthatja az egyes rendelkezésre álló pozíciókban megjelenő mezőket. A mezőket, amelyeket nem szükségesek, hagyja üresen. 

    Egy példa:

    - **Megjelenített mező:** *LabelItemId*
    - **Megjelenített mező 2:** *LabelItemName*
    - **Megjelenített mező 3:** *InventQty*
    - **Megjelenített mező 4:** *LabelUnitId*

1. Zárja be a lapot.
1. Hozzon létre egy harmadik menüelemet, és állítsa be hozzá a következő értékeket:

    - **Menüelem neve:** *Címkék újranyomtatása (Enum)*
    - **Cím:** *Hullámcímkék újranyomtatása (Enum)*
    - **Mód:** *Közvetett**
    - **Tevékenységkód:** *Több hullámcímke újranyomtatása*
    - **Munkalista-csoportosítási szűrő megjelenítése:** *Igen*
    - **Csoportosító rendszermező:** *ShipmentID*
    - **Csoportosító rendszercímke:** *Szállítmányazonosító*
    - **Nyomtatási mód:** *Számbavétel*

1. A műveleti ablaktáblán válassza ki a **Mezőlista** elemet , majd a legördülő lista segítségével válassza ki azokat a mezőket, amelyeket meg szeretne jeleníteni, hogy a dolgozók azonosíthassák a megfelelő címketekercset (például *LabelItemId*, *LabelItemName*, *InventQty*, *LabelUnitId* és *NumberOfLabels*).
1. Zárja be a lapot.
1. Hozzon létre egy negyedik menüelemet, és állítsa be hozzá a következő értékeket:

    - **Menüelem neve:** *Címkék újranyomtatása (utolsó szerint)*
    - **Cím:** *Hullámcímkék újranyomtatása (utolsó szerint)*
    - **Mód:** *Közvetett*
    - **Tevékenységkód:** *Több hullámcímke újranyomtatása*
    - **Munkalista-csoportosítási szűrő megjelenítése:** *Igen*
    - **Csoportosító rendszermező:** *ShipmentID*
    - **Csoportosító rendszercímke:** *Szállítmányazonosító*
    - **Nyomtatási mód:** *Utolsó helyes hullámcímke-azonosító*

1. A műveleti ablaktáblán válassza ki a **Mezőlista** elemet , majd a legördülő lista segítségével válassza ki azokat a mezőket, amelyeket meg szeretne jeleníteni, hogy a dolgozók azonosíthassák a megfelelő címketekercset (például *LabelItemId*, *LabelItemName*, *InventQty*, *LabelUnitId* és *NumberOfLabels*).
1. Zárja be a lapot.

#### <a name="set-up-the-mobile-device-menu"></a>A Mobileszköz-menü beállítása

Kövesse az alábbi lépéseket, és adja hozzá az új menüelemeket a raktározási alkalmazás menüjéhez.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.
1. Válasszon ki egy meglévő **Kimenő** menüt.
1. A bal oldali listában keresse meg az imént létrehozott újranyomtatás menüelemeket, majd a jobbra nyíllal adja azokat a jobb oldali listához.
1. Zárja be a lapot.

### <a name="use-cases"></a>Használati esetek

Az itt megadott használati esetek példákat mutatnak be, amelyek megmutatják, hogyan lehet használni a különböző mobileszköz-menüelemeket, amelyek segítségével a dolgozók újranyomtathatják a címkéket.

Az használati esetek elvégzése előtt a következő előfeltételeknek kell teljesülniük:

- A demóadataokat telepíteni kell, és ki kell választani a **USMF** jogi személyt.
- A hullámcímke-nyomtatást be kell állítani, és néhány címkét létre kell hozni, a [Hullámcímkék nyomtatásának konfigurálása](../warehousing/configure-wave-label-printing.md) című témakörben leírtak szerint.

#### <a name="use-case-21-a-single-wave-label-is-scratched-and-must-be-reprinted"></a>2.1. használati eset: Egy hullámcímke megsérült, és újra kell nyomtatni.

1. Jelentkezzen be az *62*-es raktárt elérő felhasználóként a raktárkezelési alkalmazásba. (A normál demóadatokban *62* felhasználó azonosító és az *1* jelszó használatával jelentkezzen be.)
1. Ugrás a **Kimenő \> Egy hullámcímke újranyomtatása** helyre.
1. Adja meg vagy olvassa be a hullám-címke azonosítóját.
1. Válassza ki azt a nyomtatót, amelyen újra szeretné nyomtatni.
1. A művelet megerősítséséhez kattintson az **OK** lehetőségre.

#### <a name="use-case-22-several-labels-for-boxes-of-the-same-item-were-damaged-and-must-be-reprinted-each-label-has-a-product-bar-code-but-no-enumeration-or-sscc-number"></a>2.2. használati eset: Ugyanazon cikkhez tartozó dobozok több címkéje sérült, és újra kell nyomtatni. Minden címkéhez tartozik egy termékvonalkód, de nincs sorozatszám vagy SSCC-szám.

1. Jelentkezzen be az *62*-es raktárt elérő felhasználóként a raktárkezelési alkalmazásba. (A normál demóadatokban *62* felhasználó azonosító és az *1* jelszó használatával jelentkezzen be.)
1. Ugrás a **Kimenő \> Címkék újranyomtatása (cikk)** lehetőséget.
1. Adja meg vagy olvassa be a szállítmányazonosítót.
1. Válassza ki azt a csempét, amely a megfelelő címketekercset tartalmazza az újranyomtatáshoz.
1. A termék vonalkódját olvassa be meglévő címkéből a megfelelő sor kiválasztásának jóváhagyásához.
1. Adja meg az újranyomandó címkék számát.
1. Válassza ki azt a nyomtatót, amelyen újra szeretné nyomtatni.
1. A művelet megerősítséséhez kattintson az **OK** lehetőségre.

#### <a name="use-case-23-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-because-the-labels-have-enumeration-you-can-define-the-carton-range-to-reprint"></a>2.3 használati eset: A dobozok több címkéje nem lett kinyomtatva a nyomtató elakadása miatt. Mivel a címkék számozottak, meg lehet határozni az újranyomtatni kívánt kartondoboz-tartományt.

1. Jelentkezzen be az *62*-es raktárt elérő felhasználóként a raktárkezelési alkalmazásba. (A normál demóadatokban *62* felhasználó azonosító és az *1* jelszó használatával jelentkezzen be.)
1. Ugrás a **Kimenő \> Címkék újranyomtatása (Enum)** lehetőséget.
1. Adja meg vagy olvassa be a szállítmányazonosítót.
1. Válassza ki azt a csempét, amely a megfelelő címketekercset tartalmazza az újranyomtatáshoz.
1. Írja be az első dobozt, amelyhez újranyomtatja a címkét.
1. Írja be az utolsó dobozt, amelyhez újranyomtatja a címkét. Másik lehetőségként hagyja üresen ezt a mezőt, ha a megadott első doboz után újra szeretné nyomtatni az összes dobozhoz tartozó címkét.
1. Válassza ki azt a nyomtatót, amelyen újra szeretné nyomtatni.
1. A művelet megerősítséséhez kattintson az **OK** lehetőségre.

#### <a name="use-case-24-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-the-last-good-label-has-a-wave-label-id-that-is-printed-as-a-bar-code"></a>2.4 használati eset: A dobozok több címkéje nem lett kinyomtatva a nyomtató elakadása miatt. Az utolsó jó címke egy olyan hullámazonosítóval rendelkezik, amelyet vonalkódként nyomtat a program.

1. Jelentkezzen be az *62*-es raktárt elérő felhasználóként a raktárkezelési alkalmazásba. (A normál demóadatokban *62* felhasználó azonosító és az *1* jelszó használatával jelentkezzen be.)
1. Ugrás a **Kimenő \> Címkék újranyomtatása (utolsó szerint)** lehetőséget.
1. Adja meg vagy olvassa be a szállítmányazonosítót.
1. Válassza ki azt a csempét, amely a megfelelő címketekercset tartalmazza az újranyomtatáshoz.
1. Adja meg vagy olvassa be az utolsó jó hullámcímke hullámazonosítóját. Az alkalmazás azonosítja a következő címkét a sorozatban, mint az első dobozt, amelyhez a címke újranyomtatása történik.
1. Írja be az utolsó dobozt, amelyhez újranyomtatja a címkét. Másik lehetőségként hagyja üresen ezt a mezőt, ha a megadott első doboz után újra szeretné nyomtatni az összes dobozhoz tartozó címkét.
1. Válassza ki azt a nyomtatót, amelyen újra szeretné nyomtatni.
1. A művelet megerősítséséhez kattintson az **OK** lehetőségre.

## <a name="scenario-3-short-pick-and-reprint"></a>3. eset: Rövid kitárolás és újranyomtatás

A forgatókönyv elvégzése előtt a következő előfeltételeknek kell teljesülniük:

- A demóadataokat telepíteni kell, és ki kell választani a **USMF** jogi személyt.
- A hullámcímke-nyomtatást be kell állítani, és néhány címkét létre kell hozni, a [Hullámcímkék nyomtatásának konfigurálása](../warehousing/configure-wave-label-printing.md) című témakörben leírtak szerint.

### <a name="set-up-work-exceptions"></a>Munkakivételek beállítása

Munkakivételek vezérlik a rövid kitárolás viselkedését. Munkakivétel beállításához kövesse az alábbi lépéseket:

1. Ugrás a **Raktárkezelés \> Beállítás \> Munka \> Munkakivételek** elemre.
1. Hozzon létre egy második rekordot, amelynek beállításai a következők:

    - **Munka-kivétel kódja:** *Rövid kitárolás és nyomtatás*
    - **Kivétel típusa:** *Rövid kitárolás*
    - **Hullámcímkék újranyomtatásának javaslása:** *Igen*

### <a name="void-and-reprint-after-a-short-pick"></a>Érvénytelenítés és újranyomtatás rövid kitárolás után

1. Jelentkezzen be az *62*-es raktárt elérő felhasználóként a raktárkezelési alkalmazásba. (A normál demóadatokban *62* felhasználó azonosító és az *1* jelszó használatával jelentkezzen be.)
1. Nyisson meg egy munkafolyamatot az értékesítési rendelés munkájához, amelyet eredetileg a hullámcímkék nyomtatásakor lett létrehozva.
1. Válassza ki a **Rövid kitárolás** lehetőséget.
1. Válassza ki az ehhez a forgatókönyvhöz létrehozott munkakivételi kódot.
1. Ha bejelölte a megfelelő kivételt, elérhetővé válik az **Érvénytelenítés és az újranyomtatás** jelölőnégyzet. Jelölje be ezt a jelölőnégyzetet, és hagyja jóvá. A megerősítést követően a program újraszámítja a **Címke-összeállítás azonosító** mező által meghatározott címketekercs-sorozatot a módosult munkasormennyiség alapján. Majd újranyomtatja a megadott nyomtatón.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]