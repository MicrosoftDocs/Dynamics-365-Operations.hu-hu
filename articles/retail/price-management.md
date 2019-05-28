---
title: Kiskereskedelmi eladási ár kezelése
description: Ez a témakör leírja a kiskereskedelmi eladási árak létrehozása és kezelése koncepcióit a Microsoft Dynamics 365 for Retail rendszerben.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 04/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: ShalabhjainMSFT
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28a095588bd3c312a2d1c4b83e668487a209077f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549400"
---
# <a name="retail-sales-price-management"></a>Kiskereskedelmi értékesítési ár kezelése

[!include [banner](includes/banner.md)]

Ez a témakör leírja a kiskereskedelmi eladási árak létrehozásának és kezelésének folyamatait a Microsoft Dynamics 365 for Retail rendszerben. A folyamatban szerepet játszó fogalmakra, valamint a különböző beállítások eladási árra gyakorolt hatására koncentrál.

## <a name="terminology"></a>Fogalmak

A témakör a következő fogalmakat használja.

| Időszak | Definíció, felhasználás és megjegyzések |
|---|---|
| Ár | Egyedi egységár, amelyért a terméket értesítik a pénztár (POS) ügyfélben vagy egy értékesítési rendelésen. Ez a témakör az *ár* alatt mindig az eladási árat érti, nem a készletárat vagy az önköltségiárat. |
| Alapár | Az ár, amely be van állítva az **Ár** mezőben a kiadott termékhez. |
| Kereskedelmi megállapodások ára | Az ár, amely be van állítva egy termék vagy változat esetében egy kereskedelmi megállapodás használatával az **Ár (eladási)** típusból. |
| Legkedvezőbb ár | Ha egynél több ár vagy engedmény alkalmazható a termékre, a legkisebb árösszeg és/vagy a legnagyobb engedményösszege, amely a legkisebb lehetséges nettó összeget eredményezi, amelyet a vevőnek fizetnie kell. Ez a témakör a legjobb ár fogalmát mindig „a legkedvezőbb árnak” nevezi. Ez a legkedvezőbb ár eltér, és nem szabad összekeverni a **Legkedvezőbb ár** felsorolási értékkel, az engedmény párhuzamossági módjára nézve. |

## <a name="price-groups"></a>Árcsoportok

Az árcsoportok a Retail ár- és engedménykezelésének középpontjában állnak. Az árcsoportok használatával árakat és engedményeket lehet hozzárendelni a kereskedelmi entitásokhoz (csatornákhoz, fiókokhoz, katalógusokhoz és hűségprogramokhoz). Mivel árcsoportokat használunk az összes árképzéshez és engedményhez, nagyon fontos, hogy megtervezze, hogyan használja őket, még a használat megkezdése előtt.

Önmagában az árcsoport csak név, leírás és opcionálisan árképzési prioritás. A legfontosabb tudnivaló az árcsoportokkal kapcsolatban az, hogy a több a többhöz kapcsolatok kezelésére szolgálnak, amelyekkel az engedmények és az árak rendelkeznek a kiskereskedelmi entitásokkal.

A következő ábrán az árcsoportok használata látható. Az ábrán láthatja, hogy az „Árcsoport” szó szerint az árképzés és az engedmények kezelésének középpontjában van. A kiskereskedelmi entitások, amelyek segítségével kezelheti a különbözeti árakat és engedményeket a bal oldalon láthatók, és a tényleges ár- és engedményrekordok vannak a jobb oldalon.

![Árcsoportok](./media/PriceGroups.png "Árcsoportok")

Árcsoportok létrehozása esetén ne használjon egyetlen árcsoportot többféle kiskereskedelmi entitástípushoz. Ellenkező esetben nehéz meghatározni, hogy miért meghatározott ár vagy engedmény van alkalmazva adott tranzakcióhoz.

Ahogy piros szaggatott vonal az ábrán bemutatja, a Retail támogatja a Microsoft Dynamics 365 árcsoport alapszolgáltatását, amely közvetlenül a vevőhöz van állítva. Azonban ebben az esetben csak eladási árra vonatkozó kereskedelmi megállapodásokat fog kapni. Ha vevőspecifikus árak kíván alkalmazni, azt ajánljuk, hogy ne állítson be árcsoportokat közvetlenül a vevőhöz. Ehelyett fiókokat kell használnia.

A következő szakaszok további tájékoztatást tartalmaznak a kiskereskedelmi entitásokról, amelyeket különböző árak beállításához használhat az árcsoportok használatakor. Az árak és engedmények konfigurációja az összes entitáshoz két lépésből áll. Ezeket a lépéseket tetszőleges sorrendben teheti meg. Azonban a logikai sorrend először az árcsoportok beállítása az entitásokon, mivel ez a lépés valószínűleg a telepítés során végrehajtott, egyszer végrehajtandó beállítást. Ezután, az árak és engedmények létrehozásakor, az árak és engedmények esetében egyenként állíthatók be az árcsoportok.

### <a name="channels"></a>Csatornák

A kiskereskedelemben nagyon jellemző, hogy különböző árakat alkalmaznak a különböző csatornákon. A két elsődleges, a csatornaspecifikus árakat befolyásoló tényező a költségek és a helyi piaci feltételek.

- **Költségek** – Minél messzebb van egy csatorna a termék forrásától, annál költségesebb termék készleten tartása. Például a friss termékeknek van egy korlátozott eltarthatósági ideje és meghatározott termelési követelményei (például termesztési időszak). Télen a friss saláta várható költségek magasabb az északi klímájú helyeken, mint a déli klímájúakon. Ha nagy földrajzi területen állítjuk be a csatornák árait, valószínűleg érdemes különböző árakat beállítani a különböző csatornákon.
- **Helyi piaci feltételek** – Egy üzletet, amelynek közvetlen versenytársa van az utca másik oldalán, sokkal árérzékenyebb lesz, mint a közeli közvetlen versenytárssal nem rendelkező üzletek.

### <a name="affiliations"></a>Fiókok

A fiók általános meghatározása egy hivatkozás vagy társítás egy csoporttal. A Retail esetében a fiókok vevők csoportjai. A fiókok sokkal rugalmasabb eszközt jelentenek a vevői árképzéshez és engedményekhez, mint a Microsoft Dynamics 365 vevőcsoport- és engedménycsoport alapvető koncepciói. Először, a fiók használható mind az árakhoz, mind az engedményekhez, miközben a nem kiskereskedelmi árképzésnek mindegyik típusú engedményhez és árhoz másik csoportja van. Ezt követően, a vevő tartozhat több fiókhoz, de csak egy nem kiskereskedelmi árképzési csoporthoz tartozhat az egyes típusokban. Végül, annak ellenére, hogy a fiókokat be lehet állítani úgy, hogy egy vevőhöz legyenek csatolva, ennek nem kell így lennie. A pénztárnál a névtelen vevőkhöz alkalmi fiók is használható. Egy jellemző névtelen fiók engedmény lehet például a nyugdíjas vagy a hallgató engedmény, ahol a vevő úgy kaphatja meg az engedményt, hogy csak a csoport tagsági kártyáját kell megmutatnia.

Annak ellenére, hogy fiókok leggyakrabban kedvezményekkel vannak társítva, különbözeti árképzés beállítására is felhasználhatja őket. Ha például egy kiskereskedő alkalmazottnak ad el, érdemes módosítani az eladási árat a rendes árból adott engedmény alkalmazása helyett. Másik példa egy kiskereskedő, aki lakossági és üzleti partnereket egyaránt kiszolgál, felajánlhat kedvezőbb árakat a céges ügyfeleknek a beszerzési mennyiség alapján. A fiókok engedélyezik mindkét esetet.

### <a name="loyalty-programs"></a>Hűségprogramok

Az árakkal és engedményekkel kapcsolatban a hűségprogramok alapvetően egyszerűen egyedi névvel rendelkező fiókok. Árak és engedmények is beállíthatók a hűségprogramhoz, ugyanúgy, mint a fiókhoz. Ugyanakkor az, ahogyan a vevők hűség árképzést kapnak egy tranzakció vagy rendelés során, különbözik attól, ahogy a fiók árképzést kapják. A vevők csak akkor igényelhetnek hűség árképzést, ha a hűségkártya hozzá van rendelve egy tranzakcióhoz. Ha a hűségkártya hozzá van adva egy tranzakcióhoz, a hűségprogram is hozzá van adva. A hűségprogram ezután lehetővé teszi a speciális árakat és engedményeket.

A hűségprogramokhoz több szint tartozhat, és az engedmények különbözhetnek a különböző szinteken. Ezzel a módszerrel a kiskereskedők a gyakori vevőknek nagyobb jutalmazást adhatnak anélkül, hogy a vevőket egy speciális csoportba kellene tenniük manuálisan.

A hűségprogramoknak az árak és engedmények mellett további funkcióik vannak. Azonban árképzés és engedmények szempontjából ugyanolyanok, mint a fiókok.

### <a name="catalogs"></a>Katalógusok

Egyes kiskereskedők fizikai vagy virtuális katalógus segítségével hirdetik a termékeket, és fókuszált vevőcsoportok számára árazzák őket. A katalóguson keresztüli marketingcélzás üzleti modelljének részeként ezek a kiskereskedők különbözeti árakat adhatnak meg a különböző katalógusokhoz. A Microsoft Dynamics 365 támogatja ezt a lehetőséget, így meghatározhatja a katalógusspecifikus engedményeket és árakat, hasonlóan ahhoz, ahogy csatornaspecifikus vagy fiókspecifikus engedményeket lehet definiálni. Ha szerkeszti a katalógust, társíthat árcsoportokat a katalógushoz, ahogy a csatornával, a fiókkal vagy a hűségprogrammal is társíthatja őket.

### <a name="best-practices-for-price-groups"></a>Az árcsoportokkal kapcsolatos ajánlott eljárások

Több kiskereskedelmi entitástípushoz ne használjon egy árcsoportot. Ehelyett használjon egy árcsoportkészletet a csatornákhoz, egy másik árcsoportkészletet a fiókokhoz vagy hűségprogramokhoz, és így tovább. Elő- vagy utótagot használhat az árcsoport nevében, hogy a segítségükkel vizuálisan csoportosítása a használt különböző típusú árcsoportokat.

Ne beállítása be az árcsoportokat közvetlenül a vevőhöz. Fiókot használja helyette. Ily módon minden típusú árat és engedményt hozzárendelheti a vevőkhöz, nem csak az eladási árra vonatkozó kereskedelmi megállapodásokat.

## <a name="pricing-priority"></a>Árképzési prioritás

Önmagában egy árképzési prioritás csak egy szám és egy leírást. Árképzési prioritásokat árcsoportokra lehet alkalmazni, vagy közvetlenül az engedményekre is alkalmazni lehet őket. Árképzési prioritások alkalmazása esetén a kiskereskedő felülbírálhatja a legjobb ár elvét a rendelés kontrolljával, amelyben árakat és engedményeket alkalmaznak a termékekre. A nagyobb árképzési prioritást a program előbb értékeli ki az alacsonyabb árképzési prioritásnál. Ezenkívül, ha bármely prioritás számon ár vagy engedmény található, az összes árat vagy engedményt, amelyekhez alacsonyabb prioritási szám tartozik, a rendszer figyelmen kívül hagyja.

Az ár és az engedmény két különböző árképzési prioritásból származhat, mivel árképzési prioritások az árakra és az engedményekre egymástól függetlenül vonatkoznak.

Árképzési prioritás használatakor az árakra, árképzési prioritást kell hozzárendelni egy árcsoporthoz, és ezután létre kell hozni az eladási ár kereskedelmi megállapodást az adott árcsoportra.

Az árképzési prioritás szolgáltatás bevezetése azokat az eseteket szolgálja ki, ahol a kiskereskedő magasabb árakat kíván alkalmazni az üzletek meghatározott körében. Például a kiskereskedő regionális árakat ad meg az Amerikai Egyesült Államok keleti partjára, de magasabb árakat akar beállítani bizonyos árukra a New York-i üzletekben, mivel egyes termékek költsége magasabb a városban, illetve mert a helyi piac elviseli a magasabb árat.

A témakör „Legkedvezőbb ár” részében ismertetetteknek megfelelően a kiskereskedelmi árképzési motor általában a két ár közül a kisebbet választja. Ez általában megakadályozza a kiskereskedőt a két ár közül a nagyobb használatában azokban az üzletekben, amelynek keleti parti és a New York-i árcsoportjai is vannak. A probléma megoldásához, mielőtt az árképzési prioritás szolgáltatást bevezettük, a kiskereskedőnek az összes termék árát kétszer kellett meghatároznia, és nem rendelhette hozzá mindkét árcsoportot. Másik megoldásként a kiskereskedőnek extra árcsoportokat kellett létrehoznia, hogy elkülönítse a magasabb árú termékeket a szokásos, alacsonyabb árú terméktől.

Azonban az árképzési prioritás funkcióval a kiskereskedő árképzési prioritást hozhat létre az üzletárakra, amely nagyobb, mint a regionális árak árképzési prioritása. Azt is megteheti a kiskereskedő, hogy létrehoz egy árképzési prioritást csak az üzlet áraira, és a regionális árakat hagyja az alapértelmezett árképzési prioritás, amely a 0 (nulla). Mindkét beállítás segít garantálni, hogy üzlet árak mindig a regionális árak előtt legyenek használva.

### <a name="pricing-priority-example"></a>Árképzési prioritás példa

Most nézzük meg példát, amelyben az üzlet árak felülbírálják a többi árat.

Egy nemzeti kiskereskedő régiónként állítja be a legtöbb árat, és négy régiója van: északkelet, délkelet, középnyugat és nyugat. Több magas értékű piacot azonosított, amelyek elbírják a magasabb árakat. Ezek a piacok New York (NYC), Chicago és San Francisco öbölmenti területe.

Ebben a példában az északkeleti régiót vizsgáljuk meg részletesebben. Az 1. üzlet Bostonban, a 2. üzlet Manhattanben van. A bostoni üzlet esetében két árcsoport kapcsolódik a csatornához: északkelet és 1. üzlet. A manhattani üzlet esetében három árcsoport kapcsolódik a csatornához: északkelet, NYC és 2. üzlet.

A kiskereskedő két árképzési prioritást állít be: a magas költség prioritási száma 5, és az üzlet árak prioritási száma 10. (Ne feledje, hogy alapértelmezés szerint az árképzési prioritás értéke 0 \[nulla\], és az ár vagy engedmény, amely magasabb prioritással rendelkezik, előbb kerül felhasználásra, min az alacsonyabb prioritású ár vagy engedmény.) Az északkelet árcsoport árképzési prioritása marad az alapértelmezett értékű, **0** (nulla). A NYC árcsoport árképzési prioritás értéke **5**, mivel New York magas költségű piac. Az 1. és 2. üzlet árcsoportoknál az árképzési prioritás értéke **10**.

Két, a kiskereskedő által értékesített termék az 1. termék, egy átlagos, márkázatlan póló, és a 2. termék, egy márkaspecifikus divat farmernadrág.

| Termék | Északkeleti ár | NYC-ár | Üzletbeli ár |
|---|---|---|---|
| Póló | 15 USD | Nincs megadva | Nincs megadva |
| Divat farmernadrág | 50 USD | 70 USD | Nincs megadva |

A póló azonos árért kel el a bostoni és a manhattani üzletekben (15 dollárért), mivel csak egy ár van beállítva az északkeleti árcsoportban, amely kapcsolódik mindkét csatornához. A divat farmernadrág ára a bostoni üzletben 50 USD, mivel ez az ár az egyetlen, az adott üzletben elérhető ár. Azonban a manhattani üzletben két ár áll rendelkezésre: 50 USD és 70 USD. Mivel a NYC árcsoport 5-ös árképzési prioritása magasabb, mint a 0 (nulla) árképzési prioritás az északkelet árcsoport esetében, az ár 70 USD lesz a pénztárrendszerben.

> [!NOTE]
> Minden egyes árképzési prioritás esetében a kiskereskedelmi árképzési motornak le kell futtatnia a teljes logikát. Emiatt, az ár- és engedményszámítási teljesítmény fenntartása érdekében, ajánlott az árképzési prioritások takarékos használata.

## <a name="types-of-prices"></a>Árak típusai

A Microsoft Dynamics 365 esetében a termék ára három helyen adható meg:

- Közvetlenül a terméken (alapár)
- Az eladási áras kereskedelmi megállapodásban
- Az ármódosításban

Az alapár és a kereskedelmi megállapodás ára részét képezik a Microsoft Dynamics 365 alapvető funkcióinak, és rendelkezésre állnak, még ha nem használja a Retail alkalmazást. Az ármódosítási funkció csak a Retail esetében érhető el. A következő szakasz mindegyik ilyen ármegadási lehetőségről további információkat ad, és bemutatja, hogyan működnek a beállítások együtt.

## <a name="setting-prices"></a>Árak beállítása

### <a name="base-price"></a>Alapár

A legegyszerűbb hely egy termék árának beállítására közvetlenül a termék. A közvetlenül a terméken beállított értéket gyakran nevezzük a termék alapárának. Az alapár megadása az **Ár** mezőben történik az **Értékesítés** lapján a **Kiadott termék részletei** lapnak. A bevitt érték a vállalat által használt pénznemben van megadva. Alapértelmezés szerint az ár a mértékegység (UoM) 1 darabra vetített mennyisége, amelynek a beállítása az **Egység** mezőben történik az **Értékesítés** lapon. A termék tényleges egységára a mértékegységen, az árhoz kapcsolódó mennyiségen és a pénznemen alapul.

Ha egy termék ára mindenkinek ugyanaz, az alapár a leghatékonyabb a termék árának kezelésére. Az alapárat akkor is beállíthatja a terméken, ha az árak a kereskedelmi megállapodások segítségével vannak meghatározva. Ezután, ha nem használ egy **Minden** kereskedelmi megállapodást, akkor lesz egy tartalék ár, amelyik akkor használatos, ha nincs érvényes kereskedelmi megállapodás.

Ha a kiskereskedelmi csatorna pénzneme eltér a vállalati pénznemétől, az alapárat a kiskereskedelmi csatornára nézve pénznemátváltás határozza meg arra az árra, amelyik be van állítva a termékhez.

Bár az áregység nem gyakori kiskereskedelmi forgatókönyv, a kiskereskedelmi árképzés motor támogatja. Ha az áregység nem **0** (nulla) értékre van állítva, az egységár egyenlő ár ÷ áregység. Például, a termék ára 10,00 USD, az áregység pedig 50, 1 mennyiség ára 0,20 USD (= 10,00 ÷ 50).

### <a name="sales-price-trade-agreement"></a>Az eladási áras kereskedelmi megállapodás

A kereskedelmi megállapodási napló használata esetén minden termékhez értékesítési kereskedelmi megállapodásokat hozhat létre. A Microsoft Dynamics 365 megoldásban három vevői hatókör van az eladási árra vonatkozó kereskedelmi megállapodásokhoz: **Tábla**, **Csoport** és **Minden**. A vevőhatókör határozza meg a vevőket, akikre az adott kereskedelmi megállapodás eladási ár vonatkozik.

A **Tábla** eladási árra vonatkozó kereskedelmi megállapodás egyetlen vevőre vonatkozik, és közvetlenül a kereskedelmi megállapodásban állítják be. Ez a forgatókönyv nem tipikus kiskereskedelmi cég és ügyfél (B2C) közötti helyzet. Azonban ha előfordul, a kiskereskedelmi árképzés motor a **Tábla** kereskedelmi megállapodásokat használja árak meghatározásakor.

A **Csoport** eladási árra vonatkozó kereskedelmi megállapodás a kiskereskedelmi funkcióval leggyakrabban használt típus. A Retail keretein kívül a **Csoport** eladási árra vonatkozó kereskedelmi megállapodások egyszerű vevőcsoportra vonatkoznak. Azonban a Retail alkalmazásban a vevőcsoport fogalma ki lett bővítve úgy, hogy általánosabb kiskereskedelmi árcsoport lett. Árcsoport a következőkhöz kapcsolható: kiskereskedelmi csatorna, fiók, hűségprogram vagy katalógus. Az árcsoportokkal kapcsolatos részletes tudnivalókat lásd az „Árcsoportok” című részben korábban ebben a témakörben.

> [!NOTE]
> A kereskedelmi megállapodás ár mindig az alapár előtt használatos.

### <a name="price-adjustment"></a>Ár beállítása

Ahogy a név is mutatja, az ármódosítással lehet módosítani az árat, amelyet vagy közvetlenül a terméken, vagy kereskedelmi megállapodás használatával állítottak be. Az ármódosítás segítségével csak az ár csak csökkenthető, nem lehet emelni. Az ármódosítás az ajánlott módja az árleszállítások létrehozására, nyomon követésére és kezelésére a termékekre nézve az idő múlásával.

Az ármódosításoknak három típusa van: százalékos levonás, összeg levonása és az ár. Az ármódosítások százalékos levonás vagy összeg levonása típusát mindig értékesítési tranzakcióra alkalmazzák. Az ár típusú ármódosítást ugyanakkor csak akkor alkalmazzák, ha a módosított ár kisebb az alapárral vagy a kereskedelmi megállapodással beállított árnál. Ezért ha az ármódosítással beállított ár magasabb, mint a nem módosított ár, az ármódosítás nem használt.

## <a name="determining-price-for-a-product-in-a-transaction"></a>Egy termék árának meghatározása egy tranzakcióban

Az ár és az engedmény számítása egy tranzakció esetében azt az elvet használja, hogy meg kell keresni a vevő számára legjobb árat. Ennek az elvnek megfelelően, ha egynél több ár áll rendelkezésre, a legalacsonyabb árát használja. Ezenkívül az engedményeknek az a kombinációja használatos, amely a legnagyobb engedményösszeget eredményezi a teljes tranzakcióra. Bizonyos esetekben kisebb engedményt kell használni egy adott termékre, hogy a tranzakcióban más termékekre további engedmények legyenek alkalmazhatók.

A legjobb ár keresése a vevőhöz elv alóli egyetlen kivétel a kombinációs, legkevésbé költséges engedmények beállítási lehetősége. Ez a beállítás lehetővé teszi a kiskereskedő számára kedvező legkevésbé költséges engedmények alkalmazását a termékek kiválasztásakor és csoportosításakor. Ezért, ha egy tranzakciót több terméket tartalmaz, mint amennyi a legkevésbé költséges engedményre való jogosultsághoz szükséges, a kiskereskedelmi árképzés motor kiválasztja a vevő számára a legkisebb engedményösszeget eredményező termékeket.

A kiskereskedelmi árképzés motor három árat ad vissza minden termékre: alapár, kereskedelmi megállapodás ár és aktív ár.

Az alapár csak a termék tulajdonsága, és azonos mindenki számára, mindenhol.

Az eladási áras kereskedelmi megállapodás esetében, amennyiben a **Következő keresése** beállítása **Igen**, az alkalmazható eladási áras kereskedelmi megállapodásokhoz található legalacsonyabb ár lesz használva kereskedelmi megállapodás árként. Az árcsoportok segítségével találhatók meg a kereskedelmi megállapodások, vagy a **MINDEN** számlakóddal. A kereskedelmi megállapodások másik megoldásként közvetlenül is a vevőhöz rendelhetők. Ha a **Következő keresése** beállítás értéke **Nem**, az első megtalált kereskedelmi megállapodás ár lesz használatos. Ha nincsenek eladási árra vonatkozó kereskedelmi megállapodások, a kereskedelmi megállapodás ár az alapárral egyenlő értékre lesz állítva.

Az aktív ár kiszámítása úgy történik, hogy a kereskedelmi megállapodás árat vesszük alapul, és alkalmazzuk rá a termékre vonatkozó legnagyobb ármódosítást. Ha nem találhatók ármódosítások, vagy ha a számított aktív ár több, mint a kereskedelmi megállapodás ár, az aktív ár értéke a kereskedelmi megállapodás árra lesz állítva. Ne feledje, hogy Ön nem emelheti a termék árát ármódosítás használatával. Az alkalmazandó ármódosítások csak egy csatornához, katalógushoz, fiókhoz vagy hűségkártyához rendelt árcsoportok segítségével találhatók meg.

## <a name="category-price-rules"></a>Kategória árszabályai

A Retail kategória ár szabályok funkciója lehetővé teszi, hogy egyszerűen hozzon létre új kereskedelmi megállapodásokat az összes termékhez a kategóriában. Ez a funkció lehetővé teszi továbbá a kategória termékihez tartozó meglévő kereskedelmi szerződések automatikus megkeresését, és a lejárásuk kikényszerítését.

Ha a meglévő kereskedelmi szerződések lejárása kikényszerítésének a lehetőségét választja, a rendszer új kereskedelmi megállapodási napló hoz létre azokhoz a termékekhez a kategóriában, amelyhez van aktív kereskedelmi megállapodás. Azonban a naplót manuálisan fel kell adni. Ezenkívül a kategória árszabályai csak akkor találják meg a meglévő kereskedelmi megállapodásokat, ha ugyanazt az árszabályt használja (vagyis ha új árszabályt hoz létre, amelyik a korábbi kategóriát használja). Ha nem ugyanazt az árszabályt használja, a meglévő kereskedelmi megállapodások nem járnak le.

Az árak növelhetők vagy csökkenthetők a kategória árszabályok **Árszabály** és **Ár alapja** mezőivel.

- Az **Árszabály** mezőben, jelölje ki a használni kívánt árváltozás típusát:

    - **Haszonkulcs** – Az áralap százalékosértéke szolgál az eladási ár kiszámítására. Példa: Egy 10,00 költségű és 15,00 eladási árú termék hasznonkulcsa 50 százalék.
    - **Árrés** – Az ár alapja százalékos az eladási ár kiszámítására szolgál. Példa: Egy 10 költségek és 15 egységára termékhez az árrés 33,3 százalék.
    - **Rögzített összeg** – Árhoz hozzáadott összeg, az eladási ár kiszámításához használt ár alapja. Példa: Egy 10,00 költségű és 15,00 eladási árú termék rögzített összege 5,00.

- Az **Ár alapja** mezőben, jelölje ki a használni kívánt árváltozás típusát:

    - **Alapköltség** – Az összeg, amelyet a kiskereskedő fizetett a szállítónak.
    - **Alapár** – Az eladási ár, kereskedelmi megállapodások és ármódosítások alkalmazza előtt.
    - **Aktuális ár** – Az eladási ár, kereskedelmi megállapodások és ármódosítások alkalmazza után.

Különböző termékkategóriák különböző termékeinek árainak könnyű frissítéséhez a kiegészítő termékkategóriákat a kategória árszabályaival használhatja.

## <a name="best-practices"></a>Gyakorlati tanácsok

A Microsoft SQL Server Express alkalmazást gyakran használják a csatorna-adatbázisokhoz a költségei miatt (ingyenes). Ne feledje, hogy az SQL Server Express hardveres korlátozásokkal rendelkezik, és korlátozott az adatok mérete. Ha nem megfelelően tervez, gyorsan elérheti az SQL Server Express adatméretkorlátját. Ez a megfontolás nem csak az árképzésre vonatkozik, hanem a termék más területeire is. Az alábbiakban néhány gyakorlati tanács található, amelyek segítséget nyújtanak az adatok méretének csökkentésére:

- Ha kereskedelmi megállapodásokat használ, és az árak módosulnak, akkor ki kell váltania a régi kereskedelmi megállapodások lejáratát záró dátum megadásával. Az idő múlásával ez a megközelítés csökkenti a kereskedelmi megállapodások számát, amelyek a csatorna-adatbázisokban maradnak. Emellett csökkenti az adatmennyiséget, amellyel az árszámítási algoritmusnak dolgoznia kell.
- Ha az árak termékváltozat szerint változnak, fontolja meg a termék alapárának használatát a leggyakrabban használt változó árként. A kereskedelmi megállapodásokat ezután csak a kivétel változatárakhoz használja. Ez a megközelítés csökkenti a kereskedelmi megállapodás rekordok számát. Mivel nagyon könnyű adatokat importálni a Microsoft Dynamics 365 alkalmazásba, vonzónak tűnhet kereskedelmi megállapodást importálni minden termék minden változatához. Azonban ez a megközelítést számos, azonos értékkel rendelkező kereskedelmi megállapodást hozhat létre. Ezért feleslegesen növelheti az adatok méretét.
- A Retail a változatspecifikus árat a legspecifikusabbtól a legkevésbé specifikus felé haladva dolgozza fel. Ha egy termékdimenzió nem befolyásolja az árat, nem kell kereskedelmi megállapodásokat meghatározni hozzá. Például egy termék három színben és négy méretben áll rendelkezésre, de csak a méret szerint változik az ár. Ha minden változathoz kereskedelmi megállapodást határozz meg, 12 rekordot hoz létre. Ehelyett adjon meg kereskedelmi megállapodást csak az egyes méretekhez, és a szín dimenziót hagyja üresen. Ebben az esetben csak négy rekord jön létre.

    Alternatív megoldásként, ha az értéknek nem minden dimenziója eredményez eltérő árat, meghatározhat egy kereskedelmi megállapodást az alaptermékhez, és hagyja üresen az összes termékdimenziót. Majd határozzon meg külön kereskedelmi megállapodást minden egyes dimenzióértékhez, amely eltérő árat eredményez. Például, ha az XXL méret magasabb árral rendelkezik, de minden más méretnek ugyanaz az ára, csak két kereskedelmi megállapodásra van szüksége: egyre az alaptermékhez, és egyre az XXL mérethez.

## <a name="prices-that-include-tax-vs-prices-that-exclude-tax"></a>Adót tartalmazó és adó nélküli árak

A Microsoft Dynamics 365 alkalmazásban eladási árak beállításakor nem adja meg, hogy beállított ár értéke tartalmazza, vagy nem tartalmazza az adót. Az érték egyszerűen csak az ár. Azonban az **Ár tartalmazza az áfát** beállítása a kiskereskedelmi csatornákon lehetővé teszi a kiskereskedelmi csatornák konfigurálását úgy, hogy azok befoglalják vagy kizárják az áfát az árból. Ez a beállítás a csatornára van beállítva, és még egy vállalaton belül is módosulhat.

Ha befoglalt és kizárt áfával egyaránt dolgozik, nagyon fontos az árak megfelelő beállítása, mert teljes összeg, amelyet a vevő fizet, változni fog, ha az **Ár tartalmazza az áfát** beállítása a csatornán módosul.

## <a name="differences-between-retail-pricing-and-non-retail-pricing"></a>A kiskereskedelmi árképzés és a nem kiskereskedelmi árképzés közötti különbségek

A kiskereskedelmi árak kiszámítására egyetlen árképzési motor használatos az összes csatornán: hívásközpont, kiskereskedelmi üzlet és online áruházak. Ez segít abban, hogy megvalósíthatók legyenek az egyesített kereskedelmi esetek.

A kiskereskedelmi árképzést úgy tervezték, hogy kiskereskedelmi entitásokkal működjön, nem kiskereskedelmi entitások helyett. Konkrétabban arra tervezték, hogy az árakat üzlet, nem pedig raktár szerint állítsa be.

A kiskereskedelmi árképzés motor nem támogatja a következő árképzési funkciókat:

- Ár beállítása a telephely és a raktár dimenziók használatával
- Attribútumalapú árképzés
- Szállítói engedmény átadása

Emellett **csak** a kiskereskedelmi árképzés motor támogatja a következő árképzési funkciókat:

- Az ár a termékdimenziókon alapul, a következő sorrendben: a leginkább specifikus változatártól a legkevésbé specifikus változatárig, majd az alaptermékárig. A két termékdimenzió (például szín és méret) használatával beállított ár a csak egy termékdimenzió használatával beállított ár (például a méret) előtt használatos.
- Ugyanaz az árcsoport használható az árképzés és az engedmények kezelésére.
