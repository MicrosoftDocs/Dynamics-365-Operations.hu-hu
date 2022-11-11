---
title: Alaptervezés ellátási előrejelzésekkel
description: Ez a témakör azt ismerteti, hogyan kell figyelembe venni az ellátási előrejelzéseket az alaptervezés során.
author: t-benebo
ms.date: 09/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-21
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 2bac9355bb1ac00f697ec459f494a64553e0eacc
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740141"
---
# <a name="master-planning-with-supply-forecasts"></a>Alaptervezés ellátási előrejelzésekkel

[!include [banner](../../includes/banner.md)]

Az ellátási előrejelzések segítségével megadhatja, hogy egy jövőbeli időszakban várhatóan mire lesz szüksége. A becslést általában az előző év értékesítési előzményeire alapként használja, majd az előrejelzést költségvetési célokra használja. Az alapterveket beállíthatja úgy is, hogy a tervezés során figyelembe vegye az előrejelzéseket.

## <a name="set-up-a-master-plan-to-consider-supply-forecasts"></a>Alapterv beállítása az ellátás-előrejelzések figyelembe vennie

Megadhatja, hogy minden alapterv figyelembe vegye-e az előrejelzéseket a futtatásakor. A következő eljárás szerint állíthatja be az egyes tervek előrejelzési beállításait.

1. Válassz az **Alaptervezés \> Beállítás \> Tervek \> Alaptervezések** lehetőséget.
1. Válasszon ki egy meglévő alaptervet a listaablakban, **vagy** az Új gombra kattintva hozzon létre egy újat a munkaablakban.
1. Az **Általános** gyorslapon állítsa be a következő mezőket:

    - **Előrejelzési** modell – válassza ki azt a modellt, amely az alapterv által figyelembe kívánt ellátás- és/vagy igény-előrejelzéseket tartalmazza.
    - **Ellátási előrejelzéssel** – Akkor állítsa *Igen* beállításra ezt a beállítást, ha az alaptervnek figyelembe kell vennie az ellátási előrejelzéseket.
    - **Igény-előrejelzéssel** – akkor állítsa *Igen* beállításra ezt a beállítást, ha az alaptervnek figyelembe kell vennie az igény-előrejelzéseket. Bár ez a beállítás független az **Ellátás**-előrejelzéssel együtt beállítástól, az oldal néhány más beállítása az ellátási és az igény-előrejelzésekre is vonatkozik. Az igény-előrejelzéseket figyelembeó tervezéssel kapcsolatos további tudnivalókat lásd [az igény-előrejelzéssel kapcsolatos alaptervezésnél](demand-forecast.md).
    - **Az előrejelzési követelmények csökkentésére használt** módszer – válassza ki az előrejelzési követelmények csökkentésére használt módszert az alaptervezés során:

        - *Nincs* – az előrejelzési követelmények nem csökkennek az alaptervezés során.
        - *Százalék - csökkentési kulcs* – az előrejelzési követelmények csökkentése a csökkentési kulcsban meghatározott százalékok és időszakok alapján fog csökkenni.
        - *Tranzakciók – csökkentési kulcs* – az előrejelzési követelményeket csökkenteni fogják a csökkentési kulcsban meghatározott időszakok tranzakciói.
        - *Tranzakciók – dinamikus időszak* – az előrejelzési követelményeket csökkenteni fogják a dinamikus időszakban előforduló rendelési tranzakciók. A dinamikus időszak az aktuális előrejelzési dátumokat fedi le, és akkor ér véget, amikor a következő előrejelzés elkezdődik. A *Tranzakciók – a dinamikus* időszak metódusa nem használ vagy nem igényel csökkentési kulcsot, és használata esetén a következő feltételek érvényesek:

            - Ha az előrejelzés teljes mértékben lecsökken, az előrejelzési követelmények az aktuális előrejelzéshez 0-ra (nulla) váltanak.
            - Nincs jövőbeli előrejelzés esetén beírt utolsó előrejelzésből az előrejelzési követelmények csökkentése.
            - Időkorlátok az előrejelzés-csökkentés-számításban szerepel.
            - Időkorlátok az előrejelzés-csökkentés-számításban szerepel.
            - Tényleges rendelési tranzakciók túllépik az előre jelzett követelményeit, ha a fennmaradó tranzakciók nem továbbítja a következő előrejelzési időszak.

        > [!NOTE]
        > Az **előrejelzési követelmények beállításának** csökkentésére használt módszer az igény-előrejelzésekre is vonatkozik, ha engedélyezte azokat az alaptervben, és hasonló módon befolyásolja azokat. A további tudnivalókat lásd [az igény-előrejelzéssel kapcsolatos alaptervezésnél](demand-forecast.md).

## <a name="set-reduction-options-for-coverage-groups"></a>Csökkentési beállítások megadása fedezetcsoportokhoz

A következő lépésekkel olyan beállításokat állíthat be, amelyek a fedezeti csoportoknak a tranzakción alapuló csökkentést követő alaptervek előrejelzési követelményeit csökkentik.

1. Manjen az **Alaptervezés \> Beállítás \> Tervek \> Fedezeti csoportok** menübe.
1. Válasszon ki egy meglévő fedezeti csoportot a listaablakban, **vagy** az Új gombra kattintva hozzon létre egy újat a munkaablakban.
1. Az Előrejelzés csökkentése mező másik gyorsoldalán állítsa be, hogyan kell csökkenteni az ellátás-előrejelzési követelményeket a fedezeti csoport cikkeinél **az** **olyan alaptervek esetében, amelyeknél az előrejelzési követelmények csökkentésére használt módszer a Tranzakciók -** **csökkentési kulcs vagy a Tranzakciók - dinamikus** időszak.*·* *·* Válasszon a következő értékek közül:

    - *Minden tranzakció* – Minden tranzakciónak csökkentenie kell az előrejelzést.
    - *Rendelések* – csak az azonos típusú rendelések csökkentik az előrejelzést.

    Egy cikk alapértelmezett rendelési beállításai például azt jelzik, hogy termelni kell. 50 mennyiségű ellátás-előrejelzési sor van, és 20 mennyiségű beszerzési rendelés létezik. Ha az **Előrejelzés csökkentése mezőben** a Rendelések *beállítás* van beállítva, akkor egy tervezett termelési rendelés jön létre 50 mennyiségre. Ha az Összes tranzakcióra *van állítva*, a tervezett termelési rendelés 30 mennyiségre csökken.

    Ez a beállítás az igény-előrejelzés csökkentésére is vonatkozik. A további tudnivalókat lásd [az igény-előrejelzéssel kapcsolatos alaptervezésnél](demand-forecast.md).

## <a name="enter-a-supply-forecast-for-a-product"></a>Adja meg egy termék ellátási előrejelzését.

A következő lépések szerint adja meg egy termék ellátási előrejelzését.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válassza ki azt a terméket, amelyről előrejelzést szeretne megadni.
1. A Művelet ablaktábla Terv lapján **válassza** az Ellátás **előrejelzést**.
1. Az Ellátás előrejelzése **lap** munkaablakában az Új **gombra** kattintva adjon hozzá előrejelzést a rácshoz.
1. Írja be az új sor adatait az előrejelzés megadásához szükséges adatokat.

## <a name="plan-for-an-item-with-supply-forecast-lines"></a>Terv egy cikkhez ellátás-előrejelzési sorokkal

Amikor olyan alaptervet futtat, amely olyan cikket tartalmaz, amelyhez ellátási előrejelzés tartozik, a rendszer beszerzési rendelést hoz létre a megadott ellátási sorokhoz. A cikkre vonatkozó alapértelmezett rendelési beállításokat be kell tartani. Ha az alapértelmezett rendelési beállítások alapértelmezett rendeléstípus-értéket határoznak meg **a** *Beszerzési* rendelés mezőben, és nincs megadva szállítói számla a készlet-előrejelzési sorban, akkor a rendszer a cikk alapértelmezett szállítóját használja.

## <a name="check-whether-a-planned-order-is-a-supply-forecast-order"></a>Annak ellenőrzése, hogy a tervezett rendelés ellátás-előrejelzési rendelés-e.

A következő eljárás szerint lehet tudni, hogy egy tervezett rendelés ellátási előrejelzés eredményeként jött-e létre.

1. Ugorjon az **Alaptervezés \> Alaptervezés \> Tervezett rendelések** pontra.
1. Nyissa meg a vizsgálni kívánt tervezett rendelést.
1. Az Általános **gyorsjelentés** oldalon nézze meg az Ellátási előrejelzés **mező** értékét. Ha a rendelés ellátási előrejelzés fedezésére jött létre, a *mező Beállítása Igen*.

## <a name="examples-of-master-planning-with-supply-forecasts"></a>Néhány példa az ellátás-előrejelzéseket is megszabadó alaptervezésre

Ez a szakasz néhány példát mutat be arról, hogyan befolyásolja az ellátás-előrejelzés az alaptervezést.

### <a name="example-1-supply-forecast-for-an-item"></a>1. példa: cikk ellátási előrejelzése

Van egy cikk, ahol az alapértelmezett rendeléstípus a Beszerzési *rendelés, az* alapértelmezett szállító pedig az US-002 *·*. A következő ellátási előrejelzési sorból áll.

| Modell    | Dátum     | Szállítói számla | Szállítócsoport | Mennyiség | Egység | Webhely | Raktár |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 22/10/10 |                |              | 35       | darab   | 1    | 11        |

Az alaptervezés futtatásakor egy *tervezett beszerzési rendelés jön létre 35 ea* számára az *US-002 szállítótól*.

### <a name="example-2-several-supply-forecast-lines-with-and-without-a-vendor"></a>2. példa: Több ellátás-előrejelzési sor szállítóval és szállító nélkül

Van egy cikk, ahol az alapértelmezett rendeléstípus a Beszerzési *rendelés, az* alapértelmezett szállító pedig az US-002 *·*. A következő ellátási előrejelzési sorokat tartalmazza.

| Modell    | Dátum     | Szállítói számla | Szállítócsoport | Mennyiség | Egység | Webhely | Raktár |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 22/10/10 |                |              | 35       | darab   | 1    | 11        |
| CurrentF | 22/10/10 | US-101         |              | 25       | darab   | 1    | 11        |

Ebben az esetben a rendszer azt a sort kezeli általános előrejelzésként, amely nem határoz meg szállítót, és feltételezi, hogy a szállítót meg nem határozó sort ki kell vonni az általános előrejelzésből. Ennek megfelelően az alaptervezés a következő tervezett beszerzési rendeléseket hozza létre a cikkhez:

- Tervezett beszerzési rendelés, 25 ea *mennyiséggel* az *US-101* szállítótól (a rendszer az előrejelzési sorban megadott szállítót és mennyiséget használja.)
- Tervezett beszerzési rendelés, 10 ea *mennyiséggel* az US-002 *szállítótól (mivel a másik előrejelzési sorban nincs megadva szállító, az alapértelmezett szállítót használja a program, és ennek az előrejelzési sornak a mennyiségét csökkenti a* szállítóspecifikus előrejelzési sor mennyiségére.)

### <a name="example-3-plans-that-use-the-transactions---dynamic-period-reduction-method-in-a-single-forecast-period"></a>3. példa: A Tranzakciók - dinamikus időszak-csökkentési módszer egyetlen előrejelzési időszakban

A Tranzakciók – *dinamikus* időszak előrejelzés-csökkentési módszert használjon alaptervek esetén az alaptervezés csökkenti az előrejelzési mennyiségeket, ha vannak olyan tranzakciók, amelyek megfelelnek ezeknek a készletjellemzőknek.

Például van egy olyan cikk, ahol az alapértelmezett rendeléstípus a Beszerzési *rendelés*. A következő ellátási előrejelzési sorból áll.

| Modell    | Dátum     | Szállítói számla | Szállítócsoport | Mennyiség | Egység | Webhely | Raktár |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 22/10/10 | US-101         |              | 25       | darab   | 1    | 11        |

Mivel csak egy ellátás-előrejelzési sor van, csak egy előrejelzési időszak van.

Ha olyan alaptervet futtat, amely a *Tranzakciók – dinamikus* időszak csökkentési módszer használatára van beállítva, a következő eredmények fordulhatnak elő:

- *Ha létezik beszerzési rendelés az* US-101 *szállítóhoz* és 10 ea **mennyiség,** *és* az Ellátási előrejelzés mező beállítása Igen *, az alaptervezés új tervezett beszerzési rendelést hoz létre a fennmaradó 10 ea mennyiségre.* Az előrejelzési sor csökken, mert a szállító megfelel a meglévő beszerzési rendelésnek.
- *Ha létezik beszerzési rendelés az US-102* szállítóhoz, *az 1*. helyhez, *a 11-es* *raktárhoz és 10 ea* mennyiséghez, **·** *és az Ellátási előrejelzés mező beállítása Igen*, *az alaptervezés új tervezett beszerzési rendelést hoz létre 25 ea teljes mennyiséggel.* Az előrejelzési sor nem csökkenthető, mert más szállítója van, mint a meglévő beszerzési rendelésnek.

> [!NOTE]
> Ez a helyzet a tervezett beszerzési rendeléseknél fordulhat elő, mivel van hozzájuk szállító társítva. Az átátviteli és termelési rendelések esetén azonban a beszerzési előrejelzés összegei mindig csökkennek a meglévő rendeléseknél, mivel az ilyen típusú rendelésekhez nincs megadva szállító.

### <a name="example-4-plans-that-use-the-transactions---dynamic-period-reduction-method-over-several-forecast-periods"></a>4. példa: Tranzakciók - dinamikus időszak-csökkentési módszer több előrejelzési időszakra vonatkozó tervek

Olyan cikke van, ahol az alapértelmezett rendeléstípus a Beszerzési *rendelés*. A következő ellátási előrejelzési sorokat tartalmazza.

| Modell    | Dátum     | Szállítói számla | Szállítócsoport | Mennyiség | Egység | Webhely | Raktár |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 22/10/10 | US-101         |              | 25       | darab   | 1    | 11        |
| CurrentF | 22/15/10 | US-101         |              | 25       | darab   | 1    | 11        |

Ebben a példában két előrejelzési sor van, amelyek mindegyikének más a dátuma. A dátumok következésképpen meghatározzák az előrejelzési időszakok határait. Az első időszak október 10-től 2022. október 14-ig (20/10/22–10/14/22). A második: 2022. október 15-e (10/15/22) van.

Létezik egy *beszerzési rendelés az US-101* szállítóhoz, *10 ea* mennyiséggel és *10/12/22* dátummal (2022. október 12. ). Ha olyan alaptervet futtat, amely a *Tranzakciók – dinamikus* időszak csökkentési módszer használatára van beállítva, a következő rendeléseket hozza létre:

- Tervezett rendelés 15 ea *mennyiséggel* és 10/10/22 *dátummal (a mennyiséget csökkenti a* meglévő beszerzési rendelés, amely ugyanannak az előrejelzési időszaknak a dátuma.)
- *25* *ea mennyiséggel és 10/15/22* dátummal tervezett rendelés (a mennyiség az előrejelzés teljes mennyisége.)

### <a name="example-5-plans-that-use-no-reduction"></a>5. példa: Csökkentési nélkül használható tervek

Ha olyan tervet futtat *, amelyben az előrejelzés-csökkentési módszer Nincs*, az alaptervezés mindig tervezett ellátásokat hoz létre az összes ellátás-előrejelzési sorhoz. A tervezett készlet jóváhagyása után csökkenti a jövőbeli tervezett rendeléseket. A beszerzési rendelések azonban nem csökkentik az ellátás-előrejelzési sorokat.

Például van egy olyan cikk, ahol az alapértelmezett rendeléstípus a Beszerzési *rendelés*. A következő ellátási előrejelzési sorból áll.

| Modell    | Dátum     | Szállítói számla | Szállítócsoport | Mennyiség | Egység | Webhely | Raktár |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 22/10/10 | US-101         |              | 25       | darab   | 1    | 11        |

Létezik egy beszerzési *rendelés az US-101* szállítóhoz, *az 1*. helyhez, *a 11-es* raktárhoz, a *mennyiség 25 ea*, *és a dátum 10/10/22*. 

Ha olyan alaptervet futtat, amely a Nincs csökkentési mód használatára van beállítva, tervezett beszerzési rendelést hoz létre az *US-101* szállítóhoz, *az 1* *. helyhez, a 11-es* raktárhoz, *25 ea* mennyiséghez, *és a dátum: 10/10/22*.*·* Más szóval a meglévő beszerzési rendelés nem csökken, mert az előrejelzés-csökkentési mód *Nincs*.

Most a legutóbbi tervezési futtatás után létrehozott tervezett beszerzési rendelést szerkeszti, *és a mennyiséget 15 ea-re módosítja*. Ezt követően jóváhagyja a rendelést. Az alapterv következő futtatásakor tervezett beszerzési rendelést hoz létre az US-101 szállítóhoz, *az 1* *., a 11*. raktárhoz, *a mennyiség 10 ea*, *valamint a* dátum: 10/10/22 *.* Ez az idő a korábbi tervezési futtatásból származó, már jóváhagyott rendelés mennyiségének megfelelően csökken.

## <a name="differences-between-planning-optimization-and-the-deprecated-master-planning-engine"></a>A tervezési optimalizálás és az elavult alaptervezési motor közötti különbségek

Az ellátási előrejelzések a használt tervezőmotortól (tervezési optimalizálás vagy elavult alaptervezési motor) függően egy kissé másképp működnek. Ez a szakasz a különbségeket írja le.

### <a name="vendor-groups"></a>Szállítói csoportok

Előrejelzési sor hozzáadásakor megadhatja a szállítót és a szállítói csoportot. Az elavult alaptervezési motorban a létrehozott tervezett rendelések a szállítói és szállítói csoport értékeinek kombinációja szerint vannak csoportosítva. A tervezési optimalizálásban a tervezett rendelések szállító szerint vannak csoportosítva.

Az alábbi táblázat néhány példát mutat be a cikkek ellátási előrejelzési soraira.

| Modell    | Dátum     | Szállítói számla | Szállítócsoport | Mennyiség | Egység | Webhely | Raktár |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 22/10/10 |                | VendorGroupA | 5        | darab   | 1    | 11        |
| CurrentF | 22/10/10 |                | VendorGroupA | 6        | darab   | 1    | 11        |
| CurrentF | 22/10/10 |                |              | 7        | darab   | 1    | 11        |

A *Szállító – A* szállító az alapértelmezett szállító a *VendorGroupA szállítócsoportban*. Egyben a cikk alapértelmezett szállítója is.

Az elavult alaptervezési motor a következő rendeléseket hozza létre:

- A szállítóra, *a VendorGroupA* *szállítócsoportra* és a *11 mennyiségre vonatkozó tervezett beszerzési rendelés*
- Az A szállító tervezett beszerzési *rendelése* *, mennyisége 7*

A tervezési optimalizálás csak egy rendelést hoz létre:

- Tervezett beszerzési rendelés a szállítóhoz *(VendorA*, VendorGroupA *)* és *18 mennyiségű*

### <a name="reduction-of-general-forecasts-by-more-specific-forecasts"></a>Az általános előrejelzések csökkentése konkrétabb előrejelzések alapján

Az elavult alaptervezési motorban az eredmény nem várható, ha egyes előrejelzéseknek van szállítója, de másoknak nincs.

A tervezés optimalizálása során az általános előrejelzések mindig konkrétabb előrejelzésekkel csökkennek, ahogy azt a következő példa mutatja.

Az alábbi táblázat néhány példát mutat be a cikkek ellátási előrejelzési soraira.

| Dátum       | Mennyiség | Szállító   | Szállítócsoport  |
|------------|----------|----------|---------------|
| 2022/11/02 | 5.00     | Szállító - A | VendorGroup-A |
| 2022/11/02 | 6,00     | Szállító - A | VendorGroup-A |
| 2022/11/02 | 15.00    |          |               |

Az általános előrejelzés (15,00 darabra) a konkrétabb előrejelzésekkel csökken (5,00 + 6,00 = 11,00 darab). A maradékot a rendszer az alapértelmezett szállítóhoz rendeli. A következő táblázat a tervezett rendeléseket mutatja be.

| Dátum       | Mennyiség | Szállító   | Szállítócsoport  |
|------------|----------|----------|---------------|
| 2022/11/02 | 11.00    | Szállító - A | VendorGroup-A |
| 2022/11/02 | 4.00     | Szállító - A | VendorGroup-A |

### <a name="respect-for-default-order-settings-when-planned-orders-are-generated"></a>Az alapértelmezett rendelési beállítások valóraása a tervezett rendelések létrehozása esetén

Minden cikknek lehet alapértelmezett rendelési beállítása, például egy minimális beszerzési rendelési mennyiség. Az elavult alaptervezési motor figyelmen kívül hagyja ezeket a beállításokat, ezért az előrejelzéseket ugyanolyan mennyiségű tervezett rendelésekre fordítja át. A tervezés optimalizálása ezeket a beállításokat akkor használja, amikor a tervezett rendeléseket ellátási előrejelzésekből generálják. 

### <a name="aggregation-of-planned-orders-as-a-result-of-reduction-by-approved-orders"></a>Tervezett rendelések összesítése a jóváhagyott rendelések alapján történő csökkentés eredményeként

Az elavult alaptervezési motor feltételezi, hogy csak egy rendelés fogja csökkenteni a meglévő ellátási előrejelzést. Emiatt ha egy ellátási előrejelzési sornak több rendelés is megfelel, akkor csak az első rendelés csökkenti azt. A tervezés optimalizálása során az ellátási előrejelzési sornak megfelelő összes rendelés csökkenti a rendelést.

### <a name="reduction-of-forecasts-by-matching-vendors-only"></a>Az előrejelzések csökkentése csak az egyező szállítók alapján

Ha az elavult alaptervezési motor csökkenti az előrejelzést a már létező kiadott beszerzési rendelésekkel, akkor nem gondoskodik arról, hogy a beszerzési rendelés szállítója megegyezett-e az előrejelzésben lévő szállítóval. A tervezési optimalizálás csak olyan beszerzési rendelésekkel csökkenti az előrejelzéseket, amelyeknél egyező érték található a szállító mezőben.

Az áthozott és a termelési rendelések esetében a rendszer minden esetben figyelmen kívül hagyja a szállító mezőt, mivel az ilyen rendeléstípusok esetében nem lényeges.

### <a name="reduction-of-forecasts-by-transfer-orders"></a>Előrejelzések csökkentése átátviteli rendelésekkel

Ha egy cikk alapértelmezett rendeléstípusa *Az* Átvitel, az előrejelzéseket csak a meglévő tervezett átátviteli rendelésekkel lehet csökkenteni. A termelési és beszerzési rendelések esetén azonban csak a kiadott rendelések csökkentik az ellátási előrejelzést.

Az elavult alaptervezési motor csökkenti az át rendelési állapotokat, *míg* a Tervezési optimalizálás csak a Kiadott állapotban van átadva rendelésekkel csökkenti az előrejelzéseket.
