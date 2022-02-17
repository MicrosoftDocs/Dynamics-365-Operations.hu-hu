---
title: Mozgóátlagon alapuló önköltségi ár
description: A készletzárási folyamat a cikk cikkmodellcsoportjában kiválasztott készletértékelési módszer alapján a kiadási tranzakciókat a bevételezési tranzakciókkal szemben egyenlíti ki. Azonban, a készletzárás futtatása előtt a rendszer kiszámít egy mozgóátlagon alapuló önköltségi árat, amely általában a bevételi tranzakciók feladásakor kerül felhasználásra.
author: AndersGirke
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79003
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 871b3ffce45848f95d132eff3fd327295bc5084c
ms.sourcegitcommit: fefe93f3f44d8aa0b7e6d54cc4a3e5eca6e64feb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092189"
---
# <a name="running-average-cost-price"></a>Mozgóátlagon alapuló önköltségi ár

[!include [banner](../includes/banner.md)]

A készletzárási folyamat a cikk cikkmodellcsoportjában kiválasztott készletértékelési módszer alapján a kiadási tranzakciókat a bevételezési tranzakciókkal szemben egyenlíti ki. Azonban, a készletzárás futtatása előtt a rendszer kiszámít egy mozgóátlagon alapuló önköltségi árat, amely általában a bevételi tranzakciók feladásakor kerül felhasználásra.

A rendszer a cikkek mozgóátlagon alapuló önköltségi árát a következő képlet alkalmazásával becsüli meg:

becsült ár = (fizikai összeg + pénzügyi összeg) ÷ (fizikai mennyiség + pénzügyi mennyiség)

## <a name="default-item-cost"></a>Alapértelmezett cikkköltség

A kiadott termék alapértelmezett cikkköltsége kétféleképpen konfigurálható az oldalon **Megjelent a termék részletei** oldal:

- Hozzon létre egy szabványos költséget a kiválasztásával **Darab ár** ban,-ben **Beállít** csoport a **Költségek kezelése** a Műveletpanel lapján. Ha ezt a módszert használja, akkor szabványos költségszámítási verziót kell használnia, és a költséget aktiválni kell.
- Határozzon meg egy alapértelmezett cikk önköltségi árat egy kiadott termékhez úgy, hogy beír egy értéket a **Ár** mező a **Költségek kezelése** FastTab.

Az ár megadása vagy létrehozása mellett kiválaszthatja a **Használja a legújabb önköltségi árat** jelölőnégyzet a **Költségek kezelése** FastTab a **Megjelent a termék részletei** oldalon. Ebben az esetben a rendszer automatikusan frissíti a **Ár** mezőben, amikor pénzügyi frissítést tesz közzé. Például, ha felad egy beszerzési megrendelés számlát, a mező az adott számlán szereplő vételárra lesz beállítva.

Ha van önköltségi ára egy aktív költségszámítási verzióban, és megad egy árat a **Költségek kezelése** FastTab, a rendszer az aktív költségszámítási verzió árat fogja használni, mielőtt a **Költségek kezelése** FastTab.

## <a name="using-the-running-average-cost-price"></a>A mozgóátlagon alapuló önköltségi ár alkalmazása

A következő táblázat két eshetőséget mutat be. Az első során a rendszer a mozgóátlagon alapuló önköltségi ár alapján ad fel készlettranzakciókat, a második esetben pedig a cikk törzsadataiban meghatározott önköltségi ára alapján teszi meg ugyan ezt.

| Feltétel | A rendszer a becsült mozgóátlagon alapuló önköltségi árat alkalmazza. | A rendszer az alapértelmezett cikk önköltségi árat használja |
| --- | --- | --- |
| A számláló\* és a nevező\*\* is pozitív. | Igen | Nem |
| A számláló\*, a nevező\*\* vagy mind a kettő negatív. | Nem | Igen |
| Ha a nevező\*\* 0 (nulla). | Nem | Igen |

\* Számláló = (fizikai összeg + pénzügyi összeg)  
\*\* Nevező = (fizikai mennyiség + pénzügyi mennyiség)

> [!NOTE]
> Ha a **Tartalmazza a fizikai értéket** opció nincs kiválasztva egy cikkhez, a rendszer 0-t (nulla) használ mind a fizikai mennyiséghez, mind a fizikai mennyiséghez. Az ezzel a beállítással kapcsolatos további tudnivalókért: [Tényleges értékkel együtt](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>A túlárazás elkerülése

Nagyritkán a rendszer több kiadást áraz be azelőtt, hogy elégséges számú bevételezéssel rendelkezne az ár megállapításához. Az ilyen esetek a mozgóátlagon alapuló önköltségi ár túlbecslésével járhatnak. Vannak azonban olyan lépések, amelyekkel elkerülhető a túlárazási probléma, illetve annak előfordulása esetén enyhíthető a hatása.

**Forgatókönyv:** A következő tranzakciók az Ön által kiválasztott cikkhez kapcsolódnak **Tartalmazza a fizikai értéket** opció:

1. Pénzügyileg a 100 mennyiséget kapja 100,00 USD-nél.
2. Pénzügyileg a 200-at adja meg, mint mennyiség.
3. Fizikailag a 101 mennyiséget kapja 202,00 USD-nél.

Amikor megvizsgálja a cikk becsült mozgóátlagon alapuló önköltségi árát, a várt önköltségi ár 1,51 USD. Ehelyett a USD 102.00 becsült futóátlagát találja, amely a következő képleten alapul:

Becsült ár =\[ 202 + (-100)\] ÷\[ 101 + (-100)\] = 102 ÷ 1 = 102

Ez az árnövekedés azért következik be, mert amikor a 2. lépésben 200 tételt bocsátanak ki pénzügyileg, a rendszernek 100 tételt kell beáraznia, mielőtt megkapja a megfelelő nyugtákat. Ez a helyzet negatív készletet okoz. A rendszer ezután megbecsüli a USD 1.00 egységárat, ahogyan azt Ön is várná. Azonban a megfelelő 100 bevételezés megérkezésekor, már 2,00 USD az egységár.

> [!NOTE]
> Bár a kibocsátások negatív készletet hoznak létre, a készlet pozitív a kibocsátási ár kiszámításakor. Ezért, a cikktörzsben szereplő ár helyett, inkább a mozgóátlagon alapuló önköltségi árat használja a rendszer. Ekkor a rendszerben a készlet ellenoldali értéke 100,00 USD. Noha ez az eltolás több mint 100 darabból állt, ahol egyenként USD 1.00 volt, most már csak egy darab van a készletben. Emiatt a 100,00 USD értékű ellenoldal, ehhez az egy darabhoz van hozzárendelve. Ennek eredménye a becsült önköltségi ár túlbecslése.
>
> Összehasonlításképpen vegye figyelembe, hogy ha a forgatókönyvben a 2. és 3. lépést felcseréljük, 200 tételt adnak ki USD 1.51 egységáron, egy darab pedig USD 1.51 egységáron marad. Mivel ez a túlárazási helyzet negatív készlet előfordulása esetén állhat elő, a következő helyzetekben nehéz elkerülni:
>
> - A kiadási árakat az aktuális készlet értéke és mennyisége alapján kell megbecsülni.
> - Az aktuális készlet értékét és mennyiségét korrigálni kell a kiadások és a bevételezések alapján.
> - Az ön üzleti modellje lehetővé teszi az aktuális mennyiségnél több darab kiküldését vagy beárazását.
> - Az önnek benyújtott bármely bevételezési értéket és mennyiséget el kell fogadnia.

Ha az ön üzleti modellje lehetővé teszi a következő gyakorlatokat, azok segíthetik a túlárazást lehetővé tevő negatív mennyiségek elkerülését.

- Ha kiválasztja a **Tartalmazza a fizikai értéket** lehetőség egy elemhez, törölje a **Fizikai negatív készlet** jelölőnégyzet a **Tételmodell csoportok** oldalon.
- Amennyiben **nem** jelöli be a **Tényleges értékkel együtt** lehetőséget egy cikkhez, törölje a jelet a **Pénzügyi negatív készlet** jelölőnégyzetből, a **Cikkmodell csoportok** oldalon.

Érdemes azt is szem előtt tartani, hogy a fizikai készletérték maximális ellenoldali értékét korlátozza a fizikai tranzakciók száma, illetve a fizikai és pénzügyi árak közötti különbség. Feltéve, hogy megtörténik az összes fizikai tranzakció pénzügyi frissítése, a fizikai érték nem emelkedhet extrém szintre. Végül pedig, vegye figyelembe, hogy a túlárazási hatás jelentős mértékben csökken, amikor az összesített ellenérték egy helyett, számos aktuális készleten lévő darab között kerül elosztásra.

## <a name="avoid-a-zero-cost-price-on-issues"></a>Kerülje el a nulla önköltséget a problémáknál

Amikor az **Tartalmazza a fizikai értéket** opció nincs kiválasztva a **Tételmodell csoport** oldalon, a készletből származó kiadás nulla önköltségi árat tartalmazhat, ha nincsenek pénzügyileg frissített bizonylatok a készletben. Ennek a forgatókönyvnek a elkerülése érdekében fontolja meg a következő lehetőségeket:

- Válaszd ki a **Tartalmazza a fizikai értéket** opció a **Tételmodell csoport** oldalon. Ez a beállítás megakadályozza a nulla önköltségi árat egy probléma esetén, feltéve, hogy a nyugta fizikailag frissül. Ha nem engedélyezi a negatív fizikai készletet, a problémák a futó átlagot a fizikailag frissített tranzakciókból számítják ki.
- Hozzon létre egy alapértelmezett cikk önköltségi árat egy szabványos költséggel rendelkező költségszámítási verzió aktiválásával, vagy írja be az árat a **Költségek kezelése** FastTab a **Megjelent a termék részletei** oldalon. Ez a lehetőség akkor a legjobb, ha a **Tartalmazza a fizikai értéket** opció nincs kiválasztva a **Tételmodell csoport** oldalon, mert a rendszernek mindig lesz tartalék ára.
- Válaszd ki a **Használja a legújabb önköltségi árat** opció a **Költségek kezelése** FastTab a **Megjelent a termék részletei** oldalon. Ez az opció megtartja a **Ár** mező minden alkalommal naprakész legyen, amikor pénzügyileg frissíti a nyugtát. Ha ezt a lehetőséget választja, de nem ad meg alapértelmezett árat, vagy nem aktivál egy költséget egy szabványos költségszámítási verzióban, továbbra is nulla költséggel rendelkezhet egy probléma esetén.

Ha olyan kiadási tranzakciói vannak, amelyeknek nincs költsége, a *Leltárzárás és beállítás* folyamat korrigálja az önköltségi árat úgy, hogy a bevételek pénzügyi frissítése után korrekciót hoz létre. Ne feledje, hogy a pénzügyi időszak, amikor ez a frissítés megtörténik, eltérhet attól a pénzügyi időszaktól, amikor a tételeket fizikailag megkapták vagy kiadták.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
