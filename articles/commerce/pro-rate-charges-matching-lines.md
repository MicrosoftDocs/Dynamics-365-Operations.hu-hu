---
title: Fejlécdíjak arányosítása a megfelelő értékesítési sorokhoz
description: Ez a témakör további képességeket mutat be a Commerce csatorna rendeléseihez kapcsolódó automatikus költéségek kiszámításához és alkalmazásához a haladó automatikus költségek funkcióval..
author: hhaines
manager: annbe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: f458ce6ea4fa3efdfa470e90efa1e267047a8e37
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231127"
---
# <a name="prorate-header-charges-to-matching-sales-lines"></a>Fejlécdíjak arányosítása a megfelelő értékesítési sorokhoz


[!include [banner](includes/banner.md)]

Ez a témakör leírja a fejléc szintű automatikus díjak csoportosításához, illetve azok arányosításához a kereskedelmi értékesítési csatornákhoz funkciókat. Ez a funkció a Retail 10.0.1 verzióban a pénztárnál (POS) létrehozott tranzakciók érhető el és olyan értékesítésekhez, amelyek a Retail 10.0.2 verziójának hívásközpontjában lettek létrehozva.

Ez a funkció csak akkor érhető el, ha a [speciális automatikus költségek](https://docs.microsoft.com/dynamics365/unified-operations/retail/omni-auto-charges) szolgáltatás be van kapcsolva a **Commerce paraméterek** lap beállításával. Ezenkívül a továbbfejlesztett számítási módok az automatikus költségekhez csak a kereskedelmi értékesítési rendelésekhez rendelhetők hozzá, amelyeket kereskedelmi csatornákon keresztül hoztak létre (a POS egy hívásközpont és a Dynamics elektronikus kereskedelmi platform).

Ez az új funkció nagyobb rugalmasságot nyújt szervezeteknek úgy, hogy a fejlécszintű automatikus díjak kiszámítás megtörténik, és alkalmazva lesznek az értékesítési tranzakciókra.

Az alkalmazás 10.0.1 verziónál korábbi verzióiban, a fejlécszintű automatikus díjak, amelyekhez egy konkrét szállításimód-kapcsolat tartozik csak akkor lesznek kiszámítva, ha van egyezés a szállítási móddal, amely meg van határozva az értékesítési rendelés fejlécében.

Például fejlécszintű automatikus díjak vannak meghatározva a **99**-es szállítási módhoz és a **11**-es szállítási módhoz. Egy értékesítési rendelés jön létre, és a **99**-es szállítási mód van megadva a rendelés fejlécében. Azonban egyes értékesítési sorok úgy vannak beállítva, hogy azok a **11**-es szállítási mód használatával lesznek szállítva. Ebben az esetben csak azon fejlécszintű díjak, amelyek a **99**-es szállítási módhoz vannak kapcsolva lesznek figyelembe véve és alkalmazva az értékesítési rendelésre vonatkozóan.

A Commerce rendszerben a fejlécszintű díjak egy további funkcióval is rendelkeznek amely lehetővé teszi egy [többszintű költségkonfigurációs](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery) meghatározását, amely a rendelés értékén alapul. Például, ha a rendelés értéke $50,00 és $200,00 között van, lehet hogy egy szervezet a $5,00 szállítási költséget szeretne felszámolni. Azonban, ha a rendelés értéke $200,01 és $500,00 között van a szállítási költéség $4,00 lehet.

Egyes szervezetek szeretnék kihasználni a többszintű díjkalkuláció előnyeit, amelyek elérhetők a fejlécszintű díjakkal. Azonban több szállítási módot tartalmazó esetekben, arról is gondoskodni szeretnének, hogy a számított költségek az illeszkedő szállítási módon alapulnak, amely meg van határozva az egyes értékesítési sorokon.

Immár fejlécszintű automatikus díjakat is beállíthat, hogy az összes a szállítási mód figyelembe legyen véve a díjak számításakor. Ez a funkció összetettebb számítási logikát igényel a fejlécszintű díjak számításához. A logikai egy csoportba rendezi az összes azonos szállítási móddalan leszállított cikkek, majd ezt a csoport tekinti a számítási csoportnak, a cikkekhez a fejlécszintű automatikus díjak számításakor. Ugyanazzal szállítási móddal rendelkező cikkekhez az automatikus díjak a cikkek összesített eladásai értéke alapján lesznek számítva. Így meghatározásra kerül a megfelelő automatikus díj szintje.

Miután a megfelelő fejlécszintű díjak le lettek kérve az értékesítési sorokhoz, amelyek ugyanazon a szállítási mód használatával lettek leszállítva, a költségek az értékesítési sorok szintjéig lesznek arányosítva. Mivel ezeket a díjakat a sor szintjén és nem a fejléc szintjén tartja számon s rendszer, egy konkrétabb hivatkozás a jön létre a cikk és a költségérték között, amely ki lett hozzá számítva. Ez a viselkedés akkor lehet hasznos, ahol szervezet a díj csak egy részét szeretné visszatéríteni a teljes díj helyett, ha csak a cikkek egy részét küldik vissza.

## <a name="scenarios"></a>Esetek

A következő két mintaeset vázolja fel ezen díjak számítási módját az új funkciók használatakor, akkor is, ha az nincs használva.

### <a name="scenario-1"></a>1. eset

Ez a forgatókönyv ismerteti, amikor az **Arányosítása a megfelelő értékesítési sorokhoz** beállítás értéke **Nem** az automatikus díjak beállításánál. (A viselkedés megegyezik a fejlécszintű díjak viselkedésével az alkalmazás 10.0.1-nél korábbi verzióiban)

Ebben az esetben a szervezet definiált fejlécszintű díjakat a **99**-es szállításimód-kapcsolathoz és a **11**-es szállításimód-kapcsolathoz. Nincsnek automatikus díjak konfigurálva a **21**-es szállítási módhoz..

![Automatikus-díjak a 99-es szállítási módhoz, az illeszkedő sorok arányosítása ki van kapcsolva](media/99_disabled.png)

![Automatikus-díjak a 11-es szállítási módhoz, az illeszkedő sorok arányosítása ki van kapcsolva](media/11_disabled.png)

A hívásközpont egy értékesítési rendelést hoz létre, és a szállítási mód értéke **99**. Ehhez a rendelés öt cikket tartalmaz. Két rendelési sor van ugyanazon **99**-es szállítási mód használatára konfigurálva, két sor **11**-es szállítási mód használatára konfigurálva, és egy sor úgy van beállítva, hogy a **21**-es a szállítási módot használja, amint azt a következő a táblázatban látható.

| Tétel  | Sor mennyisége | Kézbesítés módja | Egységenkénti ár |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | $10            |
| 81332 | 1             | 99            | 50 USD            |
| 81333 | 2             | 11            | $30            |
| 81334 | 3             | 99            | $10            |
| 81334 | 3             | 21            | $5             |

Ebben au esetben a teljes rendelés értékelve van az automatikus díjak táblázatához képest a **99**-es szállítási módhoz. Az értékesítési sorok teljes összege szolgál az automatikus díjkonfiguráció illeszkedő szintjének meghatározására, és ez a díj fejlécszinten lesz alkalmazva. Ebben a példában a teljes rendelés $165,00, és a rendelés fejlécében a $15,00 szállítási költség vonatkozik. A **11**-es szállítási módhoz beállított automatikus díjakra rendszer sosem hivatkozik, és nem alkalmazza azokat.

Ebben az esetben, ha a vevő visszaküld egyes cikkeket a rendelésből, és a [díjkód úgy van beállítva, hogy az vissza lesz térítve](https://docs.microsoft.com/dynamics365/unified-operations/retail/omni-auto-charges#setup-and-configuration-2), a teljes fejléc szintű díj rendszerszerűen lesz alkalmazva a visszatérítésre, akkor is, ha csak néhány cikk lestt visszaküldve.

### <a name="scenario-2"></a>2. eset

Ebben az esetben vannak fejlécszintű díjak konfigurálva a **99**-es szállításimód-kapcsolathoz és a **11**-es szállításimód-kapcsolathoz. Azonban az **Arányosítás a megfelelő értékesítési sorokhoz** beállítása **Igen** ezekhez az automatikus díjtáblázatokhoz.

![Automatikus-díjak a 99-es szállítási módhoz, az illeszkedő sorok arányosítása be van kapcsolva](media/99_enabled.png)

![Automatikus-díjak a 11-es szállítási módhoz, az illeszkedő sorok arányosítása be van kapcsolva](media/11_enabled.png)

Ebben a példában ugyanazt az öt sort tartalmazó értékesítési rendelést használjuk. A rendelési fejlécben szereplő szállítási mód értéke **99**, de minden egyes cikkhez az értékesítési rendelésben a szállítási mód az alábbi táblázatban látható módon van konfigurálva.

| Tétel  | Sor mennyisége | Kézbesítés módja | Egységenkénti ár |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | $10            |
| 81332 | 1             | 99            | 50 USD            |
| 81333 | 2             | 11            | $30            |
| 81334 | 3             | 99            | $10            |
| 81334 | 3             | 21            | $5             |

Mivel az automatikus díjkonfiguráció úgy van beállítva, hogy arányosítson, a megfelelő értékesítési sorokhoz a rendszer a következő számítási lépéseket hajtja végre.

1. Az ugyanazon szállítási móddal rendelkező összes cikk egy csoportba van rendezve, és a rendszer kiszámítja a teljes termékértéket a csoport a cikkeihez.

    **Kézbesítési mód 11**

    - Cikk 81331, mennyiség 1 = $10
    - Cikk 81333, mennyiség 2 = nettó $60 ($30 egységenként)
    - **Teljes termékkérték a 11-es szállítási módhoz = $70**

    **Kézbesítési mód 99**

    - Cikk 81332, mennyiség 1 = $50
    - Cikk 81334, mennyiség 3 = $30 nettó
    - **Teljes termékkérték a 99-es szállítási módhoz = $80**

    **Kézbesítési mód 21**

    - Cikk 81334, mennyiség 3 = $15 nettó
    - **Teljes termékkérték a 21-es szállítási módhoz = $15**

2. A rendszer megkeresi a konfigurációt, a fejléc szintű automatikus díjakhoz, amely megfelel a vevőnek és a szállítási mód beállításainak az egyes cikkcsoportokhoz.. Ha a konfiguráció rendelkezésre áll, a rendszer megkeresi a többszintű konfigurációt, hogy megtalálj az alkalmazandó díjat a szállítási csoportban található teljes termékérték alapján.

    **Kézbesítési mód 11**

    - Termék összértéke = $70
    - **Díj értéke = $7**

    **Kézbesítési mód 99**

    - Termék összértéke = $80
    - **Díj értéke = $15**

    **Kézbesítési mód 21**

    - Termék összértéke = $15
    - **Díj értéke = $0** (Nincsenek automatikus költségek konfigurálva vevő és a szállítási mód kombinációhoz.)

    ![A Szállítási mód 11 díjai a kiemelt szinthez tartoznak](media/step2mode11.png)

    ![A Szállítási mód 99 díjai a kiemelt szinthez tartoznak](media/step2mode99.png)

3. A rendszer kiszámítja a díj értékét, amelyet minden sor esetében alkalmazni, az arányosítási logika alapján, amely figyelembe veszi a sor arányosított értékét a teljes termékértékhez képest.

    **Kézbesítési mód 11**

    - Díj értéke = $7
    - Csoport termékértéke = $70
    - 1. sor értéke = $10 (= 14,2857 százaléka a csoport értékének)
    - 3. sor értéke = $60 (= 85,7143 százaléka a csoport értékének)
    - **Sor díja az 1. sorhoz = $1**
    - **Sor díja az 3. sorhoz = $6**

    **Kézbesítési mód 99**

    - Díj értéke = $15
    - Csoport termékértéke = $80
    - 2. sor értéke = $50 (= 62,5 százaléka a csoport értékének)
    - 4. sor értéke = $30 (= 37,5 százaléka a csoport értékének)
    - **Sor díja az 2. sorhoz = $9,38**
    - **Sor díja az 4. sorhoz = $5,62**

    **Kézbesítési mód 21**

    - Díj értéke = $0
    - Csoport termékértéke = $15
    - 5. sor értéke = $15 (= 100 százaléka a csoport értékének)
    - **Sor díja az 5. sorhoz = $0**

Ezért az ebben a példában a 81334 cikkhez $5,62 szállítási díj lesz hozzárendelve. Ezeket a költségeket a **Költségek karbantartása** lapon tekintheti meg az értékesítési sorhoz. Az alábbi ábra azt mutatja, hogyan néz ki ez az oldal 81334-es cikkhez.

![Arányosított díjak a 81334-es cikk értékesítési sorához](media/proratedlinecharge.png)

Ezen számítási mód használatakor részleges visszáru esetén, ha a költségkód visszatéríthető, a díjnak csak a sorhoz hozzárendelt része lesz visszatérítve a cikk visszaküldése esetén.

## <a name="additional-resources"></a>További erőforrások

[Többcsatornás speciális automatikus költségek](omni-auto-charges.md)

[Automatikus költségek csatorna szerinti engedélyezése és konfigurálása](auto-charges-by-channel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]