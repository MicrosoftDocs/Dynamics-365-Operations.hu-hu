---
title: Hitelkezelés beállítása
description: Ez a témakör a Hitelkezeléshez szükséges beállításokat írja le.
author: mikefalkner
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 640d81920dad391a77b58942972660b01f11b003
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830640"
---
# <a name="credit-management-setup"></a>Hitelkezelés beállítása 

[!include [banner](../includes/banner.md)]

## <a name="credit-management-workflows"></a>Hitelkezelési munkafolyamatok

A **Hitel -és a beszedések \> Beállítások \> Hitelkezelési munkafolyamatok** helyen megadhatja azokat a munkafolyamatokat, amelyek a hitelkeret-kiigazítások kezelésére használatosak.

- Létrehozhat egy olyan munkafolyamatot, amely lehetővé teszi a hitelkeretkorrekció-kötegek egyetlen jóváhagyással történő jóváhagyását.
- A munkafolyamatot felveheti sorszinten, így a hitelkeret-korrekciók egyenként is jóváhagyhatók.
- Létrehozhat egy olyan felszabadítási munkafolyamatot, amely automatikusan átirányítja a várakoztatásokat egy munkafolyamathoz.

## <a name="blocking-rules"></a>Zárolási szabályok

### <a name="ranking-payment-terms"></a>Fizetési feltételek rangsorolása

Ha a rendelésben szereplő fizetési feltételek nem egyeznek meg a vevő alapértelmezett fizetési feltételeivel, akkor egy értékesítési rendelést várakoztathat. Előfordulhat azonban, hogy a fizetési feltételek eltérők, de elég hasonlóak, így nem szeretné várakoztatni a rendelést. A fizetési feltételeket úgy is rangsorolhatja, hogy egy részük azonos helyezésű legyen, míg mások magasabb vagy alacsonyabb helyezést kapjanak.

Ha a fizetési feltételek rangsora aktív, és a rendelésen szereplő fizetési feltételek magasabb rangúak a vevő alapértelmezett fizetési feltételeinél, az értékesítési rendelések várakoztatott állapotba kerülnek.

A fizetési feltételek rangsorát a **Követelések és beszedések \> Beállítások \> Hitelkeret beállítása \>Fizetési feltételek rangsorolása** lapon állíthatja be.  

### <a name="ranking-settlement-discounts"></a>Kiegyenlítési kedvezmények rangsorolása

Ha a rendelésben készpénzfizetési engedmény nem egyez meg a vevő alapértelmezett készpénzfizetési engedményével, akkor egy értékesítési rendelést várakoztathat. Előfordulhat azonban, hogy a készpénzfizetési engedmény eltér, de elég hasonló, így nem szeretné várakoztatni a rendelést. A készpénzfizetési engedményeket úgy is rangsorolhatja, hogy egy részük azonos helyezésű legyen, míg mások magasabb vagy alacsonyabb helyezést kapjanak.

Ha a készpénzfizetési engedmények rangsora aktív, és ha a rendelésen szereplő készpénzfizetési engedmény magasabb rangú a vevő alapértelmezett készpénzfizetési engedményénél, az értékesítési rendelés várakoztatott állapotba kerül.

A fizetési feltételek rangsorát a **Követelések és beszedések \> Beállítások \> Hitelkeret beállítása \>Kiegyenlítési engedmények rangsorolása** lapon állíthatja be.  

## <a name="reasons"></a>Okok

A Hitelkezelésben számos típusú okot használunk:

- A várakoztatási okok azt jelzik, hogy miért van várakoztatva egy értékesítési rendelés.
- A felszabadítási okok olyan rendeléshez vannak hozzárendelve, amelyet felszabadítottak a várakoztatásból.
- Az állapotokok azt jelzik, hogy miért rendeltek egy számlaállapotot egy vevőhöz.

Az okokat a **Hitelkezelési okok** lapon adhatja meg (**Követelések és beszedések \> Beállítások \> Hitelkezelés beállításai \> Hitelkezelési okok**).

1. Az **Ok típusa** mezőben válassza ki a kívánt okot: **Várakoztatás**, **Felszabadítás** vagy **Állapot**.
2. Írja be az ok nevét az **OK** mezőbe.
3. A **Leírás** mezőbe írja be az okkód leírását.

## <a name="credit-management-groups"></a>Hitelkezelési csoportok

A hitelkezelési csoportok olyan vevők és vevőcsoportok azonosítására használhatók, amelyek azonos hitelkezelési tulajdonságokkal rendelkeznek. A hitelkezelési csoportok segítségével például meghatározhatja a vevőkre vonatkozó zárolási és kizárási hitelkezelési szabályokat.

Hitelkezelési csoportokat a **Hitelkezelési csoportok** oldalon hozhat létre (**Követelések és beszedések \> Beállítások > Hitelkezelés beállítása \> Hitelkezelési csoportok**).

1. Új sor létrehozásához válassza az **Új** elemet.
2. Adja meg a csoport azonosítóját. Az azonosító legfeljebb 10 karakterből állhat.
3. A **Leírás** mezőbe írja be a csoport nevét. A név legfeljebb 60 karakterből állhat.

A hitelkezelési csoport egy ügyfélhez van hozzárendelve a **Hitel és beszedések** gyorslapon, az **Összes ügyfél** oldalon (**Kinnlevőségek \> Ügyfelek \> Összes ügyfél**).

## <a name="account-statuses"></a>Számlaállapotok

A számla állapotának létrehozásával meghatározhatja a vevői számla hitelminősítését. A számlázásra és a szállítás várakoztatására vonatkozó folyamatok állapota és hatása is meghatározható. A számlaállapotok a vevők zárolási szabályainak meghatározására is használhatók.

A számlaállapotokat a **Számlaállapotok** oldalon (**Követelések és beszedések \> Hitelkezelés > Csoportok beállítása \> Számlaállapotok**) lehet létrehozni.

1. Adjon hozzá egy számlaállapotot, és adjon meg egy leírást, amely a vevő hitelminősítését jelzi. A **Normál** értékkel jelezheti például, hogy a vevő hitelképessége jó, és a nyitott rendelésekre pedig normál hitelezési folyamat vonatkozik.
2. A **Számlázás** és **Szállítás várakoztatva** mezőkben válassza ki azt a várakoztatási típust, amelyet azon vevőknél kell végrehajtani, akik ezzel a számlaállapottal rendelkeznek. A hitelkeret-szabályok alkalmazása esetén az összes feldolgozást várakoztathatja, várakoztathatja csak a számla feldolgozását, vagy azt is megteheti, hogy semmilyen feldolgozást nem várakoztat.

## <a name="scoring-groups"></a>Pontozási csoportok

A pontozási csoportok beállításával meghatározhatja a kockázati tényezőket, valamint a rájuk vonatkozó mérési feltételeket. Amikor egy vevőre vonatkozó információt egy pontozási csoportra alkalmaznak, minden kockázati tényezőhöz egy pontszám számítása történik, és ez a vevőnek a kockázati csoportokba történő betárolására szolgál. A kockázati csoport felhasználható a hitelképesség azonosítására és az automatikus hitelkeretek kiszámítására is.

A pontozási csoportokat a **Pontozási csoportok** lapon hozhatja létre (**Követelések és beszedések \> Beállítások \> Hitelkezelés beállítása \> Kockázat \> Pontozási csoportok**).

1. Hozzon létre egy pontozási csoportot, és adjon neki egy nevet.
2. Adjon meg további leírást a pontozási csoporthoz.
3. Válasszon egy csoporttípust. Nyolc előre definiált típus van. Választhatja a **Felhasználó által meghatározott** lehetőséget is, hogy definiáljon egy olyan csoportot, amely jobban megfelel a szervezetnek.
4. A pontszám típusának kiválasztásával határozza meg, hogy a pontozási csoport hogyan számolja ki a kockázat pontszámot. Ehhez a következő lehetőségek állnak rendelkezésre:

    - **Tartomány** – Ezzel a beállítással megadhatja a pontszám számításához használandó értéktartomány értékét.
    - **Felhasználó által meghatározott** – Ezzel a beállítással manuálisan határozhatja meg a pontszámhoz használandó értékek listáját.

5. Ha a pontszám típusaként a **Tartomány** beállítást választotta, a sorok hozzáadásával határozza meg az értékek tartományát és az azokhoz tartozó pontszámokat.

    1. A **Kezdő érték** mezőben adja meg a tartomány legalacsonyabb értékét.
    2. A **Befejező érték** mezőben adja meg a tartomány legmagasabb értékét.
    3. A **Pontszám** mezőbe írja be azt a pontszámot, amelyet akkor kell hozzárendelni, amikor a megadott érték a „kezdő”/„záró” tartományban van.

    Ha a pontszám típusaként a **Felhasználó által meghatározott** beállítást választotta, a sorok hozzáadásával határozza meg a felhasználó által meghatározott értékeket és az azokhoz tartozó pontszámokat.

    1. Az **Érték** mezőbe írja be azt a felhasználó által definiált értéket, amelyet a vevő adatai alapján kell megadni.
    2. A **Pontszám** mezőbe írja be azt a pontszámot, amelyet akkor kell hozzárendelni, amikor a megadott érték a „kezdő”/„záró” tartományban van.

## <a name="risk-classification"></a>Kockázat osztályozása

A kockázati pontszám alapján meghatározhatók a vevőkhöz hozzárendelhető kockázatértékelések. A kockázat pontszámát úgy számítja ki a rendszer, hogy összeveti a vevői adatokat a pontozási csoporttal. A pontszámok összegezve vannak, és a program összehasonlítja a kockázati csoport beállításának értékeit, hogy azonosítsa azt a kockázati csoportot, amelyhez a vevő tartozik. Ezt követően a kockázati csoport pontszáma lesz felhasználva az ügyélhez tartozó zárolási és a kizárási szabályokat.

A **Kockázatértékelések** lapon lehet beállítani a kockázati csoportokat (**Követelések és beszedések \> Beállítás \> Hitelkezelés beállítása \> Kockázat \> Kockázat osztályozása**).

1. Adjon meg egy kockázaticsoport-azonosítót.
2. Adjon meg egy leírást a pontozási csoport további magyarázatához.
3. Adja meg a kockázati csoportba tartozó vevők meghatározásához használt pontszámtartományt.
4. Válassza ki a kockázati csoport jelölőjét a kockázati csoportot jelölő szimbólum meghatározásához.

## <a name="guaranteeinsurance-types"></a>Garancia/biztonság típusa

A garancia/biztosítás típusait lapon **Garancia/biztonság típusai** lapon lehet beállítani (**Követelések és beszedések \> Beállítás \> Hitelkezelés beállítása \> Biztosítás és garanciák \> Garancia/biztosítás típusai**).

1. Adja meg a kezes vagy biztosítási ügynök nevének azonosítására szolgáló garancia vagy biztosítási típusát.
2. A kezes vagy biztosítási ügynök leírásának megadása.

## <a name="coverage-types"></a>Fedezet típusai

A fedezeti típusok a biztosítási kötvények további osztályozására használhatók. Nem használhatók garanciákkal.

A **Fedezeti típusok** oldalon hozzáadhat fedezeti típusokat (**Követelések és beszedések \> Beállítás \> Hitelkezelés beállítása \> Biztosítás és garanciák \> Fedezeti típusok**).

1. A fedezet típusának megadásával határozza meg, hogy milyen típusú fedezetet kell biztosításként vagy garanciaként adni.
2. Adjon meg egy leírást a fedezettípus leírásához.

## <a name="automatic-credit-limits"></a>Automatikus hitelkeretek

Az automatikus hitelkeretek feltételeit az **Automatikus hitelkeretek** oldalon hozhat létre (**Követelések és beszedések \> Beállítások \> Hitelkezelés beállítása \> Kockázat \> Automatikus hitelkeretek**).

1. Válasszon egy kockázati csoportot, amelyhez az automatikus hitelkeretet társítani kell.
2. Válassza ki az automatikus hitelkorlát pénznemét. Ugyanannak a kockázati csoportnak a több automatikus hitelkeretet is létre lehet hozni különböző pénznemekben.
3. Adja meg azt a bevételi összeget, amely az automatikus hitelkerethez használható maximális vállalati árbevételt jelöli. Hitelkeretek létrehozása során, az árbevétel összegét összeveti a rendszer a **Pénzügyek** oldalon található bevételi értékkel (**Kinnlévőségek \> Minden ügyfél \> Válasszon ügyfelet \> Általános \> Statisztika \> Pénzügyi**). A rendszer az **Áttekintés** szakaszban szereplő legújabb értéket használja.

Kövesse az alábbi lépéseket a kiválasztott feltételek alapján létrejövő hitelkeretet képviselő sorok hozzáadásához.

1. Válassza ki azt a pontozási csoportot, amely meghatározza a hitelkeret számításához használandó vevői adatokat.
2. Válassza ki azt az összehasonlító operátort, amely meghatározza, hogy hogyan kell kiértékelni a pontozási csoport adatait.
3. Írja be azt az értéket, amelyet a pontozási csoporthoz megadott értékkel kell összehasonlítani.
4. Adja meg azt a hitelkorlátot, amelyet akkor kell hozzárendelni, ha a vevő adatai megfelelnek a pontozási csoporthoz megadott értéknek. Létrehozhat például egy automatikus hitelkeretet az **Alacsony** pontozási csoport számára. Ha az üzletben eltöltött évek egyike a pontozási csoportoknak, akkor egy olyan sor definiálható, amely egy 100 000 összegű hitelkeretet rendel hozzá, ha a vevő öt éve működik, és egy másik sort, amely 200 000 összegű hitelkeretet rendel hozzá, ha a vevő 10 éve működik.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]