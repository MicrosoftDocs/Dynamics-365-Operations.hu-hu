---
title: Negatív napok és dinamikus negatív napok
description: Ez a témakör a negatív napokkal és a dinamikus negatív napokkal kapcsolatos tudnivalókat ismerteti, és azt, hogyan segítik az ilyen napok vállalkozása működését.
author: t-benebo
ms.date: 06/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2019-06-07
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7440a6a0b9093664a0d717b3bfa011ee3100639f
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907741"
---
# <a name="negative-days-and-dynamic-negative-days"></a>Negatív napok és dinamikus negatív napok

[!include [banner](../includes/banner.md)]

Ez a témakör a negatív napokkal és a dinamikus negatív napokkal kapcsolatos tudnivalókat ismerteti, és azt, hogyan segítik az ilyen napok vállalkozása működését. A *negatív napok időkorlátja* azoknak a napoknak a számát jelenti, amennyit Ön hajlandó várni új feltöltés rendelése előtt, ha a készlet negatív.

Ebből a témakörből az alábbiakat tudhatja meg:

- Hogyan jönnek létre a tervezett rendelések
- A negatív napok időkorlátja és a cikk átfutási ideje közötti összefüggés
- Hogyan számítja ki a rendszer a dinamikus negatív napok időkorlátját, valamint azt, hogy a cikk átfutási ideje milyen módon szerepeljen a számításban
- A negatív napokhoz kapcsolódó, [az anyagszükséglet tervezéséhez (MRP) (alaptervezés) rendelkezésre álló futási idő javítására vonatkozó javaslatok](https://blogs.msdn.com/b/axmfg/archive/2015/01/02/checklist-for-improving-mrp-performance-part-2-how-to-setup-planning-parameters.aspx) értelmezése

Ez a témakör három elméleti forgatókönyv szemléltetésével segít megérteni ezt az információt. A forgatókönyvek között az igény beérkezési idejében tapasztalható különbség: az igény a cikk átfutási időszaka előtt, közben vagy után érkezik be.

## <a name="scenario-1-you-get-demand-before-the-items-lead-time-period"></a>1. forgatókönyv: az igény a cikk átfutási időszaka előtt érkezik be

Az igény beérkezhet jóval azelőtt, hogy a cikk átfutási ideje elkezdődik, de beérkezhet közvetlenül az átfutási időszak kezdete előtt is. Példa erre a forgatókönyvre:

- A DemoProduct cikkhez hatnapos beszerzési átfutási idő tartozik.
- A nulladik napon (január 1.) a DemoProduct cikk készletszintje 0 (nulla).
- A nulladik napon (január 1.) értékesítési rendelést kap 10 darab DemoProduct cikkre.
- A hetedik napon (január 7.) már van egy meglévő beszerzési rendelés a DemoProduct 10 darabos cikkmennyiségéhez.

Az alábbi ábra bemutatja a forgatókönyv grafikus nézetét.

![Az 1. forgatókönyv grafikus nézete](./media/negative-days-1.jpg)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>A eset: a negatív nap kevesebb, mint a cikk átfutási ideje.

Ha a negatív napokat a cikk átfutási idejénél kisebb számra állítja be, az MRP a negatív napok időkorlátján belül megkeresi a DemoProduct cikkhez tartozó bevételezéseket. Mivel nem talált bevételezést, az MRP új tervezett beszerzési rendelést hoz létre. Ez a tervezett rendelés azonnal hat nappal (átfutási idő) késik. Emiatt január 7-én érkezik meg. A meglévő beszerzési rendelés **Érvénytelenít** műveletkérő üzenetet kap, mivel az új tervezett beszerzési rendelés létrehozása miatt redundáns.

Az alábbi ábra bemutatja az eset képernyőképét.

![Az 1. forgatókönyv A esetének képernyőképe](./media/negative-days-2.png)

Az alábbi ábra bemutatja annak grafikus nézetét, hogy mi történik ebben az esetben.

![Az 1. forgatókönyv A esetének grafikus nézete](./media/negative-days-3.png)

Ha figyelembe veszi az MRP teljesítményét és a terv bizonytalanságát, akkor ez az eset nem megfelelő. Az MRP-nek új tervezett rendelést kell létrehoznia, és ki kell számítania a késéseket és a műveleteket. Ezek a feladatok időigényesek. Ez az eset két további tranzakcióval egészíti ki az Ön tervét. Másrészről az értékesítési rendelés csak hat nappal, nem pedig hét nappal késik.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>B eset: a negatív nap több, mint a cikk átfutási ideje.

Az MRP teljesítményének javítása érdekében a negatív napokat a cikk átfutási idejénél nagyobb számra is beállíthatja. Mivel ebben a forgatókönyvben nem tudja a készletet az átfutási időn belül teljesíteni, a bevételezéseket mindaddig keresheti, amíg ennek a keresésnek értelme van. Annak ellenére, hogy az MRP-nek a futási ideje rövidebb lesz, Önnek figyelnie kell a rendelésekre vonatkozó további késésekre.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>C eset: A cikk átfutási ideje és a negatív napok időkorlátja automatikusan összefügg egymással

Ahhoz, hogy a cikk átfutási ideje és a negatív napok időkorlátja automatikusan összefüggjön egymással, használjon dinamikus negatív napokat. A dinamikus negatív napok használatához nyissa meg az **Alaptervezés \> Beállítás \> Alaptervezés paraméterei** menüpontot, majd az **Általános** lapon, a **Fedezet** részben állítsa a **Dinamikus negatív napok használata** lehetőséget **Igen** értékre. Az MRP ezután a dinamikus negatív napok időkorlátján belül megkeresi a bevételezéseket. Az időkorlát a következő képlet segítségével számítható ki:

Dinamikus negatív napok időkorlátja = Beszerzési átfutási idő + Negatív napok időkorlátja + (Aktuális dátum – Igény dátuma)

(Ha a DemoProduct cikk alapértelmezett rendelési típusa **Termelés** vagy **Átmozgatás**, akkor az átfutási idő a **készlet** átfutási ideje.)

Ha dinamikus negatív napokat használ, akkor az időkorlát, amelyet az MRP megnéz a bevételezésekhez, jelenleg 6 + 2 + 0 = 8 nap. Az MRP megkeresi a meglévő beszerzési rendelést, és az értékesítési rendeléshez rögzíti. Nem jön létre új tervezett rendelés. Ezért az MRP futási ideje rövidebb. A következő ábra bemutatja a DemoProduct cikkhez megállapított nettó igényeket.

![Nettó igények az 1. forgatókönyv C esetéhez](./media/negative-days-4.png)

Az alábbi ábra bemutatja annak grafikus nézetét, hogy mi történik ebben az esetben.

![Az 1. forgatókönyv C esetének grafikus nézete](./media/negative-days-5.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>D eset: Csak dinamikus negatív napok használata

Ha a negatív napokat **0-ra** (nulla) állítja, és csak a dinamikus negatív napok időkorlátját használja, akkor a dinamikus negatív napok időkorlátja 6 + 0 + 0 = 6 nap. Ebben az esetben az eredmény ugyanaz, mint az ehhez a forgatókönyvhöz tartozó A esetben. Az MRP-nek új tervezett rendelést kell létrehoznia, és ki kell számítania a késéseket és a műveleteket. Ezek a feladatok időigényesek és bosszantóak lehetnek. További két tranzakciót is fel kell dolgoznia. Mivel az igény nem teljesíthető időben az adott cikk érkezéséhez, ez az eset szükségtelenül túlbonyolítja a tervet.

Az alábbi ábra bemutatja az eset képernyőképét.

![Az 1. forgatókönyv D esetének képernyőképe](./media/negative-days-6.png)

Az alábbi ábra bemutatja annak grafikus nézetét, hogy mi történik ebben az esetben.

![Az 1. forgatókönyv D esetének grafikus nézete](./media/negative-days-7.png)

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>E eset: Használja mindkét negatív napot, amelyek meghaladják a cikk átfutási idejét és a dinamikus negatív napok időkorlátját.

Ha a negatív napokat a cikk átfutási idejénél nagyobb számra állítja, és ha a dinamikus negatív napok időkorlátját is használja, akkor a dinamikus negatív napok időkorlátja 6 + 6 + 0 = 12 nap. Ez a megközelítés nagyon hosszú időkorlátot jelenthet, amelyben az MRP-nek keresnie kell az eredményt. Ha további tájékoztatást szeretne arról, hogyan kapcsolódik az E eset egy olyan helyzethez, amikor a negatív napokat hosszú időkorláttal állítja be, olvassa el a témakör [Következtetés,](#conclusion) című szakaszát.

## <a name="scenario-2-you-get-demand-during-the-items-lead-time-period"></a>2. forgatókönyv: az igény a cikk átfutási időszaka közben érkezik be

Előfordulhat, hogy a cikk átfutási ideje alatt érkezik be igény. Példa erre a forgatókönyvre:

- A DemoProduct cikkhez hatnapos beszerzési átfutási idő tartozik. 
- A nulladik napon (január 1.) a DemoProduct cikk készletszintje 0 (nulla).
- A negyedik napon (január 5.), amely az átfutási időn belül van, egy értékesítési rendelést kap 10 darab DemoProduct cikkre.
- A hetedik napon (január 8.) már van egy beszerzési rendelés a DemoProduct 10 darabos cikkmennyiségéhez.

Az alábbi ábra bemutatja a forgatókönyv grafikus nézetét.

![Az 1. forgatókönyv grafikus nézete](./media/negative-days-8.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>A eset: a negatív nap kevesebb, mint a cikk átfutási ideje.

Ha a negatív napokat a cikk átfutási idejénél kisebb számra állítja be, az MRP a negatív napok időkorlátján belül megkeresi a DemoProduct cikkhez tartozó bevételezéseket. Mivel a program nem talált bevételezést, az MRP olyan új tervezett beszerzési rendelést hoz létre, amely az aktuális dátumot használja rendelési dátumként. Ez a tervezett rendelés azonnal hat nappal (átfutási idő) késik. Emiatt január 7-én érkezik meg. A meglévő beszerzési rendelés **Érvénytelenít** műveletkérő üzenetet kap, mivel az új tervezett beszerzési rendelés létrehozása miatt redundáns.

Az alábbi ábra bemutatja az eset képernyőképét.

![A 2. forgatókönyv A esetének képernyőképe](./media/negative-days-9.png)

Az alábbi ábra bemutatja annak grafikus nézetét, hogy mi történik ebben az esetben.

![Az 2. forgatókönyv A esetének grafikus nézete](./media/negative-days-10.png)

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>B eset: a negatív nap több, mint a cikk átfutási ideje.

Ez az eset hasonlít az 1. forgatókönyv B esetéhez. Ha a negatív napokat a cikk átfutási idejénél nagyobb számra állítja be, akkor nem kap új tervezett rendelést. Az értékesítési rendelés a meglévő beszerzési rendeléshez van hozzákapcsolva.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>C eset: A cikk átfutási ideje és a negatív napok időkorlátja automatikusan összefügg egymással

Ez az eset hasonlít az 1. forgatókönyv C esetére, mert a dinamikus negatív napok ugyanúgy működnek, mint abban az esetben. A dinamikus negatív napok időkorlátja most 6 + 2 – 4 = 4 nap. Ha ezt a módszert alkalmazza, az MRP megtalálja a meglévő beszerzési rendelést, és azt az értékesítési rendeléshez csatolja hozzá. Mivel a program nem hoz létre új tervezett rendeléseket, az MRP futási ideje rövidebb.

Az alábbi ábra bemutatja az eset képernyőképét.

![A 2. forgatókönyv C esetének képernyőképe](./media/negative-days-11.png)

Az alábbi ábra bemutatja annak grafikus nézetét, hogy mi történik ebben az esetben.

![Az 2. forgatókönyv C esetének grafikus nézete](./media/negative-days-12.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>D eset: Csak dinamikus negatív napok használata

Ha a negatív napokat **0-ra** (nulla) állítja, és csak a dinamikus negatív napok időkorlátját használja, akkor a dinamikus negatív napok időkorlátja most 6 + 0 – 4 = 2 nap. Ebben az esetben az eredmény ugyanaz, mint az ehhez a forgatókönyvhöz tartozó A esetben. Az eset grafikus nézete ennek a forgatókönyvnek az A eseténél látható.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>E eset: Használja mindkét negatív napot, amelyek meghaladják a cikk átfutási idejét és a dinamikus negatív napok időkorlátját.

Ha a negatív napokat a cikk átfutási idejénél nagyobb számra állítja, és ha a dinamikus negatív napok időkorlátját is használja, akkor a dinamikus negatív napok időkorlátja 6 + 6 – 4 = 8 nap. Ez a megközelítés nagyon hosszú időkorlátot jelenthet, amelyben az MRP-nek keresnie kell az eredményt. Ha további tájékoztatást szeretne arról, hogyan kapcsolódik az E eset egy olyan helyzethez, amikor a negatív napokat hosszú időkorláttal állítja be, olvassa el a témakör [Következtetés,](#conclusion) című szakaszát.

## <a name="scenario-3-you-get-demand-after-the-items-lead-time-period"></a>3. forgatókönyv: az igény a cikk átfutási időszaka után érkezik be

Előfordulhat, hogy az igény a cikk átfutási időszaka után érkezik be. Példa erre a forgatókönyvre:

- A DemoProduct cikkhez hatnapos beszerzési átfutási idő tartozik.
- A nulladik napon (január 1.) a DemoProduct cikk készletmennyisége 0 (nulla).
- A hetedik napon (január 8.), amely az átfutási időn kívül van, értékesítési rendelést kap 10 darab DemoProduct cikkre.
- A tízedik napon (január 11.) már van egy beszerzési rendelés a DemoProduct 10 darabos cikkmennyiségéhez.

Az alábbi ábra bemutatja a forgatókönyv grafikus nézetét.

![A 3. forgatókönyv grafikus nézete](./media/negative-days-13.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>A eset: a negatív nap kevesebb, mint a cikk átfutási ideje.

Ha a negatív napokat a cikk átfutási idejénél kisebb számra állítja be, az MRP az értékesítési rendelés igényének dátumánál két nappal korábban keres. Mivel nem talált semmit, az MRP új tervezett beszerzési rendelést hoz létre január 2-án. A tervezett beszerzési rendelés kiszállítására pont időben kerül sor, hogy teljesüljön az értékesítési rendelés iránti igény. A meglévő beszerzési rendelés **Érvénytelenítési** műveletkérő üzenetet kap, mivel nem kötelező.

Az alábbi ábra bemutatja az eset képernyőképét.

![A 3. forgatókönyv A esetének képernyőképe](./media/negative-days-14.png)

Az alábbi ábra bemutatja annak grafikus nézetét, hogy mi történik ebben az esetben.

![Az 3. forgatókönyv A esetének grafikus nézete](./media/negative-days-15.png)

> [!NOTE]
> Az előző képernyőképen a beszerzési rendelés igénylési dátuma január 12. Mivel ez a képernyőkép 2015-ben készült, amikor január 11-e vasárnapra esett, az MRP áthelyezte az igénylés dátumát a következő munkanapra, hétfőre, január 12-re. Mindazonáltal a beszerzési rendelés szállítási dátuma január 11.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>B eset: a negatív nap több, mint a cikk átfutási ideje.

Ha a negatív napokat a cikk átfutási idejénél nagyobb számra állítja be, akkor nem kap új tervezett rendelést. Az értékesítési rendelés a meglévő beszerzési rendeléshez van rögzítve. Emiatt az értékesítési rendelés késik. Ha tervezett rendelést hoz létre, akkor az értékesítési rendelést időben szállíthatja.

Az alábbi ábra bemutatja az eset képernyőképét.

![A 3. forgatókönyv B esetének képernyőképe](./media/negative-days-16.png)

Az alábbi ábra bemutatja annak grafikus nézetét, hogy mi történik ebben az esetben.

![A 3. forgatókönyv B esetének grafikus nézete](./media/negative-days-17.png)

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>C eset: A cikk átfutási ideje és a negatív napok időkorlátja automatikusan összefügg egymással

Ez az eset hasonlít az 1. forgatókönyv C esetére, mert a dinamikus negatív napok legalább ugyanolyan jól használhatók, mint a forgatókönyv B esetében.

A dinamikus negatív napok időkorlátja 6 + 2 – 7 = 1 nap. Ebben az esetben azonban a rendszer továbbra is alkalmazza a negatív napok átfutási idejét (2), mivel az MRP a negatív napok átfutási ideje és a dinamikus negatív napok átfutási ideje közötti maximális értéket veszi figyelembe. Ezért ebben az esetben az eredmény ugyanaz, mint az ehhez a forgatókönyvhöz tartozó A esetben.

Az alábbi ábra bemutatja annak grafikus nézetét, hogy mi történik ebben az esetben.

![Az 3. forgatókönyv C esetének grafikus nézete](./media/negative-days-18.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>D eset: Csak dinamikus negatív napok használata

Ha a negatív napokat **0-ra** (nulla) állítja, és csak a dinamikus negatív napok időkorlátját használja, akkor a dinamikus negatív napok időkorlátja most 6 + 0 – 7 = –1 nap. Ebben az esetben a rendszer továbbra is figyelembe veszi a negatív napok átfutási idejét (2). Ezért ebben az esetben az eredmény ugyanaz, mint az ehhez a forgatókönyvhöz tartozó A esetben, és pontosan ugyanazokkal a hátrányokkal rendelkezik. Az eset grafikus nézete a 2. forgatókönyv A eseténél látható.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>E eset: Használja mindkét negatív napot, amelyek meghaladják a cikk átfutási idejét és a dinamikus negatív napok időkorlátját.

Ez az eset megegyezik az 1. és a 2. forgatókönyv E esetével. Lényegében ugyanolyan előnyökkel és hátrányokkal bír.

## <a name="conclusion"></a>Összefoglalás

Az ebben a témakörben szereplő három esetnek megfelelően célszerű a negatív napokat a fedezeti csoportba tartozó cikkek átfutási idejénél nagyobb értékre beállítani. Célszerű csak dinamikus negatív napokat használni, és a negatív napokat annyi napra beállítani, amennyit negatív készlet esetén hajlandó várakozni, mielőtt új feltöltést rendel (vagyis amíg hajlandó tovább halasztani az igény teljesítését). Ezenkívül ugyanazon fedezeti csoport cikkeinek hasonló átfutási időkkel kell rendelkezniük.

Ha a negatív napokat **0** (nulla) értékre állítja, és nem használ dinamikus negatív napokat, akkor az MRP mindig új tervezett rendelést hoz létre az igény teljesítéséhez. Ebben a helyzetben fontos, hogy a műveletkérő üzenetekkel dolgozzon, hogy ne történjen készletfelhalmozás.

A negatív napokat hosszú időkorlátra is beállíthatja, és ezt követően a műveletkérő üzenetekkel dolgozhat. Ez a megközelítés jó tervezési eredményekkel jár, de kicsit lassítja a munkát. Emellett az elemzést is megnehezítheti, mivel a műveletkérő üzeneteket is elemezni és alkalmazni kell. Egy példa:

- A DemoProduct cikkhez hatnapos beszerzési átfutási idő tartozik.
- A nulladik napon (január 1.) a DemoProduct cikk készletmennyisége 0 (nulla).
- A nulladik napon (január 1.) értékesítési rendelést kap 10 darab DemoProduct cikkre.
- A tízedik napon (január 10.) értékesítési rendelést kap 10 darab DemoProduct cikkre.
- A tizenkettedik napon (január 12.) már van egy beszerzési rendelés 10 darab DemoProduct cikkre.
- A negatív napok beállítása **20**, ami jóval több, mint a cikk átfutási ideje.

Az alábbi ábra grafikus nézetben mutatja be, mi történik ebben az esetben.

![A példa grafikus áttekintése](./media/negative-days-19.png)

Az MRP a következő eredményeket produkálja.

![Eredmények](./media/negative-days-20.png)

Az előző képernyőképen az értékesítési rendelés igénylésének dátuma január 9., nem pedig január 10. Mivel ez a képernyőkép 2015-ben készült, amikor január 10-e szombatra esett, a rendelés igénylési dátumának az előző munkanapra, péntekre, azaz január 9-re kell esnie.

Az MRP létrehoz egy tervezett beszerzési rendelést, amely teljesíti az első értékesítési rendelésben megadott igénylési igényt, de azt is ajánlja, hogy a tervezett rendelést érvénytelenítse, mert a meglévő beszerzési rendelést előre elvégezheti, és a mennyiségét növeli.

Az eredmények nem hibásak, de előfordulhat, hogy az MRP futási ideje hosszabb, mivel az MRP-nek minden késést és javaslatot létre kell hoznia. Ezenkívül előfordulhat, hogy a tervezőnek több időre van szüksége az MRP-eredmények megértéséhez. A legfontosabb ebben az esetben, hogy a tervező mindenképpen értse és használja a műveletkérő üzeneteket.

Ha Ön csökkenti a negatív napokat a cikk átfutási idejéhez közelebb eső számra, és dinamikus negatív napokat használ, akkor az MRP a következő eredményeket hozza létre.

![Eredmények](./media/negative-days-21.png)

Az MRP létrehoz egy tervezett rendelést, amely az első értékesítési rendeléshez van csatolva. Ezt követően az elvárásoknak megfelelően a rendszer a második értékesítési rendelést a negatív napok beállításától függően a meglévő beszerzési rendeléshez rögzíti. Ez a tervezési eredmény is helyes, és az MRP futási ideje rövidebb lehet. Ebben az esetben nem feltétlenül szükséges a műveletkérő üzenetek megértése és az, hogy tudja, hogyan kell dolgoznia velük.

Azért, hogy biztosan a helyes értékeket adja meg a vállalata számára, mind a funkcionalitást, mind az MRP futási idejét figyelembe kell vennie. Ezért az optimális értékek meghatározásához próbálgatásra is szükség lehet.

## <a name="see-also"></a>Lásd még

További információkért lásd a [További tudnivalók a (dinamikus) negatív napokról](/archive/blogs/axmfg/more-about-dynamic-negative-days) eredeti blogbejegyzést.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]