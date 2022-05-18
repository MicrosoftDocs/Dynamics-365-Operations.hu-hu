---
title: Mozgóátlagon alapuló önköltségi ár
description: A készletzárási folyamat a cikk cikkmodellcsoportjában kiválasztott készletértékelési módszer alapján a kiadási tranzakciókat a bevételezési tranzakciókkal szemben egyenlíti ki. Azonban, a készletzárás futtatása előtt a rendszer kiszámít egy mozgóátlagon alapuló önköltségi árat, amely általában a bevételi tranzakciók feladásakor kerül felhasználásra.
author: JennySong-SH
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79003
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d324324312ce9e47b07de8e3de952b8d7c53647
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672178"
---
# <a name="running-average-cost-price"></a>Mozgóátlagon alapuló önköltségi ár

[!include [banner](../includes/banner.md)]

A készletzárási folyamat a cikk cikkmodellcsoportjában kiválasztott készletértékelési módszer alapján a kiadási tranzakciókat a bevételezési tranzakciókkal szemben egyenlíti ki. Azonban, a készletzárás futtatása előtt a rendszer kiszámít egy mozgóátlagon alapuló önköltségi árat, amely általában a bevételi tranzakciók feladásakor kerül felhasználásra.

A rendszer a cikkek mozgóátlagon alapuló önköltségi árát a következő képlet alkalmazásával becsüli meg:

becsült ár = (fizikai összeg + pénzügyi összeg) ÷ (fizikai mennyiség + pénzügyi mennyiség)

## <a name="default-item-cost"></a>Alapértelmezett cikk-költség

A kiadott termékek alapértelmezett **cikkköltsége kétféleképpen konfigurálható a Kiadott termékek részletei lapon**:

- Hozzon létre egy **elszámolóárat** **·** **a** Munkaablak Költség kezelése lapjának Beállítás csoportjában a Cikkár beállításával. Ha ezt a módszert használja, elszámoló költségszámítási verziót kell használnia, és a költséget aktiválni kell.
- Határozza meg egy kiadott termék alapértelmezett önköltségi árát **a** **Költségek** kezelése gyorsábra Ár mezőjében.

Az ár beírásán és létrehozásán kívül bejellheti a Legutóbbi önköltségi ár használata jelölőnégyzetet **a** **·** **Kiadott termékek részletei lap Költségek kezelése gyorslapján.** Ebben az esetben a rendszer automatikusan frissíti az **Ár** mezőt a pénzügyi frissítések feladja. Ha például beszerzési rendelési számlát ad fel, a mezőben a számlán szereplő beszerzési ár lesz beállítva.

Ha az önköltségi ár aktív költségszámítási verzióban van megadva, és beír egy árat a Költségek kezelése gyorsábra, **akkor** a rendszer az aktív költségszámítási verzióban megadott árat fogja használni, mielőtt felhasználja a **Költségek** kezelése gyorsábra által meghatározott árat.

## <a name="using-the-running-average-cost-price"></a>A mozgóátlagon alapuló önköltségi ár alkalmazása

A következő táblázat két eshetőséget mutat be. Az első során a rendszer a mozgóátlagon alapuló önköltségi ár alapján ad fel készlettranzakciókat, a második esetben pedig a cikk törzsadataiban meghatározott önköltségi ára alapján teszi meg ugyan ezt.

| Feltétel | A rendszer a becsült mozgóátlagon alapuló önköltségi árat alkalmazza. | A rendszer a cikk alapértelmezett önköltségi árát használja. |
| --- | --- | --- |
| A számláló\* és a nevező\*\* is pozitív. | Igen | Nem |
| A számláló\*, a nevező\*\* vagy mind a kettő negatív. | Nem | Igen |
| Ha a nevező\*\* 0 (nulla). | Nem | Igen |

\* Számláló = (Tényleges összeg + Pénzügyi összeg)  
\*\* Nevező = (Tényleges mennyiség + Pénzügyi mennyiség)

> [!NOTE]
> Ha egy **cikknél nincs bejelölve** a Tényleges értékkel együtt beállítás, a rendszer 0 (nulla) értéket használ mind a tényleges összeghez, mind a fizikai mennyiséghez. Az ezzel a beállítással kapcsolatos további tudnivalókért: [Tényleges értékkel együtt](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>A túlárazás elkerülése

Nagyritkán a rendszer több kiadást áraz be azelőtt, hogy elégséges számú bevételezéssel rendelkezne az ár megállapításához. Az ilyen esetek a mozgóátlagon alapuló önköltségi ár túlbecslésével járhatnak. Vannak azonban olyan lépések, amelyekkel elkerülhető a túlárazási probléma, illetve annak előfordulása esetén enyhíthető a hatása.

**Helyzet:** A következő tranzakciók fordulhatnak elő egy olyan cikk esetében, amelynél be van jelölve a **Tényleges** értékkel való betétel:

1. Pénzügyileg a 100 mennyiséget kapja 100,00 USD-nél.
2. Pénzügyileg a 200-at adja meg, mint mennyiség.
3. Fizikailag a 101 mennyiséget kapja 202,00 USD-nél.

Amikor megvizsgálja a cikk becsült mozgóátlagon alapuló önköltségi árát, a várt önköltségi ár 1,51 USD. Ehelyett meg lehet találni a becsült mozgóátlagot USD 102.00, amely a következő képleten alapul:

Becsült ár = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 ÷ 1 = 102

Erre a túlárazásra azért van sor, mert amikor 200 cikk kerül pénzügyileg kibocsátva a 2. lépésben, a rendszernek 100-nak kell árazva lennie a cikkekből, mielőtt megfelelő bevételezéssel rendelkezik. Ez a helyzet negatív készletet okoz. A rendszer ezután a vártnak USD 1.00 egységárat becsüli meg. Azonban a megfelelő 100 bevételezés megérkezésekor, már 2,00 USD az egységár.

> [!NOTE]
> Bár a kiadás negatív készletet hoz létre, a kiadási ár számítása esetén a készlet pozitív. Ezért, a cikktörzsben szereplő ár helyett, inkább a mozgóátlagon alapuló önköltségi árat használja a rendszer. Ekkor a rendszerben a készlet ellenoldali értéke 100,00 USD. Annak ellenére, hogy az ellenszámla 100 darabra épül, és USD 1.00 egységnyi eltérés volt, most csak egy darab van a készletben. Emiatt a 100,00 USD értékű ellenoldal, ehhez az egy darabhoz van hozzárendelve. Ennek eredménye a becsült önköltségi ár túlbecslése.
>
> Összehasonlításképpen figyelje meg, hogy ha a 2. és a 3. lépést sztornírozták az esetben, akkor 200 darab darabáron USD 1.51, és egy darab a cikk egységárán marad USD 1.51. Mivel ez a túlárazási helyzet negatív készlet előfordulása esetén állhat elő, a következő helyzetekben nehéz elkerülni:
>
> - A kiadási árakat az aktuális készlet értéke és mennyisége alapján kell megbecsülni.
> - Az aktuális készlet értékét és mennyiségét korrigálni kell a kiadások és a bevételezések alapján.
> - Az ön üzleti modellje lehetővé teszi az aktuális mennyiségnél több darab kiküldését vagy beárazását.
> - Az önnek benyújtott bármely bevételezési értéket és mennyiséget el kell fogadnia.

Ha az ön üzleti modellje lehetővé teszi a következő gyakorlatokat, azok segíthetik a túlárazást lehetővé tevő negatív mennyiségek elkerülését.

- Ha egy cikknél a **Tényleges** értékkel való elemet választja, **törölje a jelölést a Tényleges** **negatív készlet jelölőnégyzetből a Cikkmodellcsoportok** lapon.
- Amennyiben **nem** jelöli be a **Tényleges értékkel együtt** lehetőséget egy cikkhez, törölje a jelet a **Pénzügyi negatív készlet** jelölőnégyzetből, a **Cikkmodell csoportok** oldalon.

Érdemes azt is szem előtt tartani, hogy a fizikai készletérték maximális ellenoldali értékét korlátozza a fizikai tranzakciók száma, illetve a fizikai és pénzügyi árak közötti különbség. Feltéve, hogy megtörténik az összes fizikai tranzakció pénzügyi frissítése, a fizikai érték nem emelkedhet extrém szintre. Végül pedig, vegye figyelembe, hogy a túlárazási hatás jelentős mértékben csökken, amikor az összesített ellenérték egy helyett, számos aktuális készleten lévő darab között kerül elosztásra.

## <a name="avoid-a-zero-cost-price-on-issues"></a>Nulla önköltségi ár elkerülése a problémáknál

Ha a **Cikkmodellcsoport** **lapon** nincs bejelölve a Tényleges értékkel való beszámítás beállítás, akkor a készletből való kiadáshoz nulla önköltségi ár tartozhat, ha a készletben nincsenek pénzügyileg frissített bevételezések. Az eset elkerüléséhez vegye figyelembe a következő beállításokat:

- Válassza a **Tényleges értékkel való betételt** a Cikkmodellcsoport **lapon**. Ez a beállítás megakadályozza a nulla önköltségi ár kiadását, feltéve, hogy a bevételezés fizikailag frissítve van. Ha nem engedélyezi a negatív tényleges készletet, a problémák a ténylegesen frissített tranzakciókból számítják ki a mozgóátlagot.
- Hozzon létre egy alapértelmezett cikk-önköltségi árat egy elszámolóáras költségszámítási verzió aktiválásával, **·** **vagy adja meg az árat a Kiadott termékek részletei lap Költségek kezelése gyorslapján.** Ez a lehetőség akkor a legjobb, **·** **ha** a Cikkmodellcsoport lapon nincs kiválasztva a Tényleges értékkel való beszámolás beállítás, mert a rendszernek mindig lesz tartalékára.
- Válassza a **Legutóbbi önköltségi ár használata** lehetőséget **a** Kiadott termékek részletei **lap Költségek kezelése gyorslapján**. Ez a beállítás a **bevételezések** pénzügyi frissítésekjekor mindig naprakészen tartja az Ár mezőt. Ha ezt a lehetőséget választja, de nem ad meg alapértelmezett árat, vagy nem aktivál egy költséget az elszámolóár-verzióban, akkor is lehet nulla költség egy kiadásnál.

Ha nulla költségű kiadási tranzakciókat hoz létre, *akkor* a készletzárási és -helyesbítési folyamat korrigálja az önköltségi árat úgy, hogy helyesbítést hoz létre a bevételezések pénzügyi frissítése után. Ne feledje, hogy a frissítés pénzügyi időszaka eltérhet attól a pénzügyi időszaktól, amikor a cikkek ténylegesen beérkezettek vagy kiadták őket.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
