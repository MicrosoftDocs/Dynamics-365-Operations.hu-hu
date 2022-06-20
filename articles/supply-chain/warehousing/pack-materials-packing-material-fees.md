---
title: Csomagolóanyagok és díjak
description: Ez a cikk az újra feldolgozó vállalatoknak adott időközönként kifizetett csomagolóanyag-díjakkal kapcsolatban tartalmaz tájékoztatást.
author: Mirzaab
ms.date: 02/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2020-02-19
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 584bddeaedd461803bb9d62421cbb646178164a3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901734"
---
# <a name="packing-materials-and-fees"></a>Csomagolóanyagok és díjak

[!include [banner](../includes/banner.md)]

A csomagolóanyag-díjakat bizonyos időközönként kell kifizetni egy feldolgozó vállalatnak. Súlyegységenként egy bizonyos összeget kell kifizetni a csomagolási egységet alkotó minden egyes anyag után. Ugyan a program a csomagolóanyag-díjakat kiszámítja és jelentést is készít róluk, viszont – mivel nem számít a hatóságoknak fizetendő adónak – nem ad fel főkönyvi tranzakciót a díjjal kapcsolatban.

A csomagolóanyag-súlyokat és -díjakat az értékesítési rendeléssorokhoz és a beszerzési rendeléssorokhoz a program számolja ki.

Megadhat egy vagy több csomagolási egységet egy egyetlen cikkhez, egy cikkcsoporthoz (csomagolási csoport) vagy az összes cikkhez. A csomagolási egység különféle csomagolóanyagokat tartalmaz, azok súlyából és a csomagolási egységbetartozó cikkek számából áll. A Csomagolóanyag-kód a meghatározott csomagolóanyag minden egyes típusához hozzá van rendelve. A csomagolóanyag-kódon alapul, megadhatja az árat egy meghatározott időszakra. A csomagolóanyag-díj ezen információ alapján számítják ki.

> [!NOTE]
> Még akkor is, ha a vállalat nem fizeti ki a csomagolási díjakat, használhatja a funkciót a csomagolási anyagok súlyával kapcsolatos statisztikák kiszámításához.

## <a name="set-up-packing-material-allocation"></a><a name="allocations"></a>Csomagolóanyag-felosztás beállítása

A csomagolóanyag súlyának, a csomagolóanyagok díjainak vagy mindkettőnek a kiszámítása előtt be kell kapcsolni a számítást, és meg kell határozni, hogy mely anyagok és díjak tartozzanak a cikkekhez.

1. Válassz a **Készletkezelés \> Beállítás \> Készlet- és raktárkezelési paraméterek** lehetőséget.
1. Az **Általános** lap **Csomagolóanyag** szakaszában állítsa a **Csomagolóanyag-díjak számítása** beállítást **Igen** értékre.
1. Nyissa meg a **Készletkezelés \> Beállítások \> Csomagolóanyag \> Csomagolási csoportok** lehetőséget, és hozza létre az összes használt csomagolási csoportot. Egy csomagolási csoport minden cikke ugyanazt a csomagolóanyag-felosztást fogja használni. Ha nem használ csomagolási csoportokat, akkor kihagyhatja ezt a lépést.

    > [!TIP]
    > Miután létrehozta a csomagolási csoportokat, igény szerint hozzárendelheti az egyes termékekhez a szükséges csoportokat. Válassz a **Termék információ kezelése \> Termékek \> Kiadott termékek** lehetőséget, válasszon ki egy terméket, majd válassza ki a megfelelő csomagolási csoportot a **Készlet kezelése** gyorslap **Csomagolási csoport** mezőjében.

1. Nyissa meg a **Készletkezelés \> Beállítások \> Csomagolóanyag \> Csomagolóanyag-kódok** lehetőséget, adja meg az egyes használt csomagolóanyag-típusokat, és adja meg a csomagolóanyag felhasználásnak egységét szállítmányok előkészítése során.
1. Nyissa meg a **Készletkezelés \> Beállítások \> Csomagolóanyag \> Csomagolóanyag-díjak** lehetőséget és adjon meg egy díjat az imént definiált csomagolóanyagokhoz. A díjak számítása a felhasznált egységár alapján történik.
1. A csomagolóanyagok cikkekhez történő elosztáshoz nyissa meg a **Készletkezelés \> Beállítások \> Csomagolóanyag \> Csomagolóanyag-felosztás** lehetőséget, és hozza létre a felosztásokat. Annyi elosztást hozhat létre, amennyire szüksége van. Az egyes cikkekhez, cikkcsoportokhoz (csomagolási csoportokhoz) vagy az összes cikkhez lehet hozzárendelni a csomagolóanyagokat, attól függően, hogy milyen részletesnek kell lennie a felosztásoknak.

    Az alábbi lépéseket minden létrehozott felosztásra vonatkozóan el kell végezni:

    1. Az **Általános** gyorslapon állítsa be a következő mezőket:

        - **Cikk-kód** – Válassza ki a felosztás hatókörét:

            - **Tábla** – Felosztás létrehozása egyetlen meghatározott elemhez.
            - **Csoport** – Felosztás létrehozása a **Csomagolási csoport** lapon meghatározott csomagolási csoportba tartozó összes cikkhez.
            - **Összes** – Felosztás létrehozása az összes cikkhez.

            > [!NOTE]
            > Általában az összes felosztást ugyanazon a szinten kell elvégeznie (**Tábla**, **Csoport** vagy **Mind**). Ha egynél több szintet használ, akkor az egyes cikkeknél a leginkább megfelelő felosztás lesz használva. (A **Tábla** szintje elsőbbséget élvez a **Csoport** szintjéhez képest, és mindkét szint elsőbbséget élvez a **Minden** szinthez képest.)

        - **Cikk-kapcsolat** – Ha egyetlen tételhez rendeli a felosztást, válassza ki a tételt. Ha cikkek csoportjához végezi a felosztást, válassza ki a csomagolási csoportot. Ha az összes cikkre vonatkozóan végzi a felosztást, hagyja üresen ezt a mezőt.
        - **Konfiguráció**, **Méret**, **Szín** és **Stílus** – Adja meg ezen dimenziók értékeit igény szerint, hogy tovább definiálja a hozzárendelt elemet.
        - **Csomagolási egység** –Válassza ki azt az egységet, amelybe a csomagolási anyag használatakor be van csomagolva a termék. Ez az egység eltérhet a cikkek beszerzésének és tárolásának egységétől.
        - **Csomagolási egység faktora** – Adja meg azt a átváltási tényezőt, amelyet a rendszer a készletegység a csomagolási egységre történő átváltásához használ. (Az átváltás a következő képlet alapján történik *Csomagolási egység* = *Cikkegység* × *Csomagolási egység faktora*.)

    1. Adjon hozzá egy sort minden olyan **Csomagolóanyaghoz**, amely az aktuális felosztáshoz szükséges. Minden sorban adja meg az anyag típusát (a **Csomagolóanyag-kódok** lapon meghatározott módon) és mennyiséget, ami fel lesz használva az aktuális cikk minden egyes leszállított egységéhez.

## <a name="packing-units-on-sales-order-lines"></a>Az értékesítési rendelési sorokon lévő csomagolási egységek

Miután [bekapcsolta a csomagolóanyag-díjak számítását és elvégezte a felosztások beállítását](#allocations), a rendszer ellenőrzi, hogy a csomagolási egységek meg vannak-e határozva minden cikkhez, ami hozzá van adva az értékesítési rendeléshez. Ezután a program kiszámítja a szükséges díjakat. Amikor egy cikket egy értékesítési rendeléshez hozzáadnak, a következő lépések egyike történik:

- **Ha a cikkre vonatkozik csomagolási felosztás:** A rendszer frissíti a meghatározott csomagolási egységgel és csomagolási egység mennyiséggel rendelkező értékesítési rendelési sort. (A csomagolási egység mennyiségét a program automatikusan kiszámítja a következő képlettel: *Csomagolási egység mennyisége* = *Rendelt mennyiség* ÷ *A kiválasztott csomagolási egység cikkeinek száma*.)
- **Ha nem vonatkozik csomagolási egység a cikkre:** Manuálisan lehet beírni a csomagolási egységet és a csomagolási egység mennyiségét az értékesítésirendelés-sorba.

Az értékesítésirendelés-sor feladása során módosítani lehet a csomagolási egységet és a csomagolási egység mennyiségét. Ez a képesség akkor lehet fontos, ha az értékesítésirendelés-sor szállítása vagy számlázása csak részben készül el.

Az értékesítési rendelés számlázásakor, a rendszer csomagolóanyag-tranzakciókat hoz létre. A csomagolóanyag-tranzakciók tartalmazzák az értékesítés sorhoz tartozó csomagolóanyag súlyát. A tranzakciókat számlázás után módosíthatja. Ezt követően új tranzakciókat hozhat létre.

## <a name="packing-units-on-purchase-order-lines"></a>A beszerzési rendelési sorokon lévő csomagolási egységek

A rendszer nem hoz létre a beszerzési rendelés sorokhoz csomagolási anyag tranzakciókat. Ehelyett a tranzakciókat manuálisan hozza létre a számlázott beszerzési rendelési sorokhoz a **Csomagolóanyag-tranzakciók** oldalon.

## <a name="set-up-license-numbers-for-customers-that-are-charged-packing-material-fees"></a>Licencszámok beállítása azokhoz a vevőkhöz, akiknek fel vannak számítva csomagolóanyag-díjak

Ha egy adott vevő értékesítési rendeléseinek tartalmaznia kell az egyes rendelésekhez használt csomagolóanyagok költségeit, hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Kinnlevőségek \> Vevők \> Minden vevő** lehetőséget.
1. Válassza ki azt a vevőt, akinek számlázni kell a csomagolóanyagokért.
1. Az **Számla és kiszállítás** gyorslapon állítsa be a következő mezőket:

    - Az **Áfa** szakaszban, a **Csomagolási díj engedélyszáma** mezőben adja mag a vállalat engedélyének számát.
    - A **Csomagolóanyag díja** szakaszban az **Licenc száma** mezőben adja mag a vállalat engedélyének számát.

Most, amikor olyan értékesítési rendelést hoz létre és számláz, amely egy vagy több olyan cikket tartalmaz, amelyek csomagolóanyagokat használnak, a számlán fel lesznek tüntetve a csomagolóanyag-díjak.

Azoknak a vevőknek, akik nem fizetnek csomagolóanyag-díjakat, hajtsa végre ugyanezeket a lépéseket, de törölje az engedélyszámokat a **Csomagolási díj engedélyszáma** és a **Licenc száma** mezőkből. Azoknak a vevőknek a számlái, akik nem fizetnek csomagolóanyag-díjat, a csomagolóanyagok súlya fel van tüntetve, de a díjak nem.

Olyan jelentés létrehozásához, amely megjeleníti a vállalat által fizetendő adott időszakra vonatkozó összes csomagolóanyag-díjat, nyissa meg a **Készletkezelés \> Lekérdezések és a jelentések \> Csomagolóanyag-jelentések \> Csomagolóanyag-díjak számítása** elemet, adja meg a dátumtartományt, majd válassza az **OK** lehetőséget.

## <a name="print-packing-material-weights-on-invoices"></a>Csomagolóanyag-súlyok nyomtatása a számlákra

A számlákra rá lehet nyomtatni a csomagolóanyag súlyadatait, és jelezni lehet, hogy ki fizeti a kapcsolódó csomagolóanyag-díjakat. A súlyok összegzése a csomagolóanyag-kód alapján történik.

1. Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.
1. A **Frissítések** lap **Számla** gyorslapján állítsa be a **Csomagolóanyag-súly nyomtatása** beállítást **Igen** értékre.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]