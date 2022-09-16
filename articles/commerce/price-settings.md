---
title: Díjszabási beállítások
description: Ez a témakör a központi ár- és engedménykezelés különféle beállításait ismerteti Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-11
ms.openlocfilehash: 79130e0ef285d6bd5e544f2d6a6368c0393fa7fa
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474042"
---
# <a name="pricing-settings"></a>Díjszabási beállítások

[!include [banner](../includes/banner.md)]

Ez a témakör a központi ár- és engedménykezelés különféle beállításait ismerteti Microsoft Dynamics 365 Commerce. Ezek a beállítások lehetővé teszik, hogy a szervezetek meghatározott üzleti igényeknek megfelelően meghatározzák az árképzés működését a Commerce-megoldásban.

## <a name="company-level-pricing-settings"></a>Vállalatszintű árképzési beállítások

A legtöbb árképzési beállítás vállalati **szintű, és a Commerce Headquarters árak és engedmények paramétereinél \>** találhatók.

### <a name="best-price-and-compound-concurrency-control-model"></a>Legkedvezőbb ár és összetett párhuzamos alkalmazásának vezérlőmodellje

A **legjobb ár és** **·** **összetett** egyidejűség ellenőrzési modelljének beállítása határozza meg, hogy hogyan dolgozza fel az árképzési motor a legjobb ár vagy összetett egyidejűség módban a több engedményt. 

Ha a paraméter a **prioritáson belül a Legjobb ár és összetett beállításra van beállítva,** **akkor** a prioritáson belül soha nem összetett, csak az azonos árképzési prioritású összetett engedmények összetettek. Az összetett **eredmény** ezt követően az azonos árképzési prioritású legjobb árengedményekkel versenyző, a legjobb árat alkalmazza, és minden alacsonyabb árképzési prioritású engedményt figyelmen kívül hagy.

Ha a paraméter csak a **prioritáson belüli legjobb árra van állítva,** akkor minden prioritást összetetten kell kezelni, **·** **akkor minden összetett engedmény a legjobb árengedménynek lesz kezelve.** Az árképzési prioritáson belül csak egyetlen kedvezményes kedvezmény engedménye engedmény. Ha az egyetlen engedmény a **legjobb** **ár** vagy összetett engedmény, **·** **akkor** összetetten tartalmaz minden további, alacsonyabb árképzési prioritású legjobb árat vagy összetett engedményt.

### <a name="discount-compound-behavior"></a>Összetettengedmény-viselkedés

Az **Engedmény összetett viselkedésének** beállítása határozza meg, hogy hogyan számítja ki az árképzési motor a több összetett engedményt.

Ha a paraméter összetettre **van állítva**, akkor az egyik engedményt a program a másikon alkalmazza. Ha az eredeti ár **összetettre** van állítva, akkor a rendszer minden engedményt egymástól függetlenül kezel, és ugyanazon eredeti árra alkalmazza.

Például egy olyan terméknél 10 és 20 százalékos engedményt szeretne tartalmazni, amelynél a kedvezmény eredeti ára $100. Ha az Összetett **engedmény** **viselkedése paramétert Összetett** beállításra adja meg, a végső ár $72 lesz (100 90&times;% &times; 80%). Ha az eredeti árat **Összetettre** jelöli, a végső ár $70 lesz (100 usd – $10 – $20).

### <a name="enable-competition-between-exclusive-threshold-and-other-periodic-discounts"></a>Az kizárólagos küszöbérték és más időszaki kedvezmények közötti verseny engedélyezése

Ha az **kizárólagos küszöbérték és** **az** egyéb időszaki engedmények közötti verseny engedélyezése paraméter Igen beállítású, akkor az árkalküldő az kizárólagos küszöbértékű engedményeket kizárólagos, nem küszöbértékű engedményekkel versenyzővé teszi. Az árképzési prioritás továbbra is érvényes. A legjobb ár- **és összetett küszöbérték** engedményének **viselkedése** változatlanul marad. Más szóval nem a küszöbértéken kívüli engedményekkel versenyzők.

### <a name="manual-line-discount-and-system-discount"></a>Manuális sorengedmény és rendszerengedmény

A **manuális sorengedmény és** rendszerengedmény beállítása határozza meg, hogy az árképzési motor hogyan alkalmazza ugyanannak a sornak a manuális sorengedményét és rendszerengedményét. A manuális sorengedmény a rendszerengedményen felüli engedményt is tartalmazhatja, de a rendszerengedmény helyére is lecserélhető. Amikor a kézi sorengedmény és a rendszerengedmény összetételt ad, a számítási logika figyelembeja az **Engedmény összetett viselkedésének** beállítását. A teljes rendelésre vonatkozó kézi összengedmény nem vonatkozik erre a beállításra.

### <a name="keep-items-on-the-same-sales-line-for-discount-price-rounding"></a>Cikkek megtartása ugyanabban az értékesítési sorban az árengedmény kerekítéséhez

Bizonyos esetekben a mennyiségi engedmény összegét nem lehet egyenlően elosztni a minősítési mennyiséggel (például ha az engedmény összege három beszerzett egységnél $10 le). Ebben az esetben az árkerekítési beállítás ugyanazon értékesítési sorban található cikkek megtartása határozza meg, hogy hogyan működik az árképzési motor, **és** osztja fel az engedmény összegét. Ha a paraméter Értéke **Igen**, a program az egész összegre alkalmazza az engedmény összegét, és nem osztja fel. Ha Nemre van **állítva**, akkor az engedmény összege fel lesz osztva a minősítési mennyiségre, és kerekít. Például egy három egységre $10 engedményösszeg $3.33 le, a második egységnél $3.33 le, a harmadik egységnél $3.34 le.

### <a name="apply-discounts-to-key-in-price-products"></a>Engedmények alkalmazása az ártermékek kulcsára

Az **engedmények alkalmazása az** ártermékek beállításában kulcsra határozza meg, hogy az engedmények alkalmazhatók-e a pénztárnál megadott "bekulcsos árak" mellett. A **termékkonfiguráció** árbeállítási kulcsa határozza meg, hogy a termék támogatja-e az árbevallást, és hogyan.

### <a name="apply-discounts-to-price-overrides"></a>Engedmények alkalmazása az árfelülbírálásokra

Az **engedmények alkalmazása az árfelül** bírálati beállításokra határozza meg, hogy az engedmények az árfelül felülbírálásokkal együtt alkalmazhatók-e.

### <a name="distribute-discounts-for-least-expensive-discounts"></a>A legolcsóbb engedmények engedményének elosztása

A "legolcsóbb" **számítási** típust használt kombinációs engedmények esetén a legolcsóbb engedmények engedményének elosztása beállítás határozza meg, hogy az árkalkulációs motor több sorban elosztja-e az engedményt.

Ha a paraméter Értéke **Nem**, az engedmény csak a legolcsóbb sorokra lesz érvényes. Például egy "2 vásárlása 1 ingyenes" kombinációs engedménynél a legolcsóbb cikk lesz ingyenes, a másik két cikk pedig megmarad a teljes áron. Ebben az esetben azok a vevők, akik mindkét teljes árú cikket visszaadják, még mindig ingyen kapják a harmadik cikket. Ez az eset a kiskereskedő veszteségét okozhatja.

Ha a paraméter Értéke **Igen**, az árképzési motor az összes vonatkozó sorra elosztja az engedményt. Ez a beállítás csökkentheti a visszaküldések veszteségét.

### <a name="manually-calculate-multi-line-prices-and-discounts"></a>Többsoros árak és engedmények manuális számítása

A **többsoros árak és engedmények manuális számítása meghatározza, hogy az árkalkuláltak a késleltetett ár- és engedményszámítást használják-e a POS-alkalmazáshoz** és a hívásközponti csatornához. **Ha** a paraméter Beállítása Igen, az árképzési motor nem számítja ki azonnal a többsoros engedményeket (például a mennyiségi engedményeket, a küszöbérték-engedményeket és a kombinációs engedményeket) minden alkalommal, amikor értékesítési rendelést hoznak létre vagy szerkesztnek a POS-alkalmazásban vagy a hívásközponti csatornában.

> [!NOTE]
> A Commerce rendszer 10.0.30-as **és** korábbi verzióiban a többsoros árak és engedmények manuális számítása csak a hívásközpont csatornáját szabályozza. A funkcióprofil **több cikkengedmény-beállításának** manuális kiszámítása külön, amely szabályozza az árkalkuláció viselkedését a POS-alkalmazásban. A Commerce rendszer 10.0.31-es verziójában a két beállítás egy vállalatszintű beállításba konszolidálható.

### <a name="retention-period-in-days"></a>Megőrzési időszak (nap)

**A** Megőrzési időszak napokban beállítása jelzi, hogy a lejárati dátum (ha be van állítva lejárati dátum) vagy a letiltás dátuma (ha nincs beállítva lejárati dátum) után hány nappal kell módszeresen törölni az engedményt. Ha a paraméter értéke **0 (nulla**), nem történik automatikus törlés.

> [!NOTE]
> A Commerce rendszer 10.0.30-as **és korábbi verzióiban a beállítás neve Ennyi nap után kell törölni a lejárt engedményeket**.

### <a name="coupon-bar-code"></a>Utalvány vonalkódja

Az **utalvány vonalkód-beállítása** határozza meg, hogy melyik konkrét vonalkód használatos az utalványok vonalkódok előállításához. A felhasználók választhatnak egyet **a** vonalkód-beállítási lapon beállított előre meghatározott vonalkódok közül. A vonalkódokkal és vonalkódmaszkokkal [kapcsolatos](set-up-bar-codes.md) további tudnivalókat lásd: Vonalkódok beállítása és [Vonalkódmaszkok beállítása](set-up-bar-code-masks.md).

### <a name="coupon-code-must-be-manually-applied-to-return-transactions"></a>Az utalványkódot manuálisan kell alkalmazni a visszáru-tranzakciókra.

Az **utalványkódot manuálisan kell alkalmazni a** visszáru-tranzakciók beállítására, csak olyan visszáru-tranzakciókra alkalmazható, amelyekhez nem áll rendelkezésre értékesítési bevételezés. Állítsa Nem beállításra a **paramétert**, ha a tranzakcióra automatikusan utalványkódokat kell alkalmazni. Állítsa Igen **beállításra**, ha az utalványkódokat kézzel kell hozzáadni a tranzakcióhoz.

### <a name="use-sales-agreements-set-up-for-the-organization"></a>A szervezethez beállított értékesítési szerződések használata

A vállalat közötti (B2B) rendelések esetén, **·** **ha** a szervezeti paraméterhez beállított Értékesítési szerződések használata beállítás Igen, az árképzési motor a szervezethez a felhasználói vevőhierarchiában meghatározott értékesítési szerződések alapján határozza meg a szerződésen alapuló árat. **Ha a paraméter Értéke Nem**, vagy ha nincs megadva a vevői hierarchia, az árkalkul szolgáló motor a felhasználó számára meghatározott értékesítési szerződéseket keres a szerződésen alapuló ár meghatározása érdekében. A B2B e-commerce [rendszer vevőhierarchiáiról a B2B üzleti partnerek kezelése a vevőhierarchiák használatával kapcsolatban tartalmaz további tájékoztatást](b2b/partners-customer-hierarchies.md).

## <a name="channel-level-pricing-settings"></a>Csatornaszintű árképzési beállítások

A következő beállítások segítségével a szervezetek szabályozhatjak az egyes értékesítési csatornák árképzési működését.

### <a name="enable-order-price-control"></a>Rendelési árellenőrzés engedélyezése

A **Rendelés engedélyezése árellenőrzés** paramétere a **Hívásközpont** konfigurációs oldal **általános gyorslapján** található. Ez a beállítás határozza meg, hogy az árképzési motor érvényesíti-e az ár-felülbírálási művelet korlátozását a hívásközponti csatornában. Az árkorreknál a termékszintű **beállítással** együtt működik.

Ha a rendelés árellenőrzése ki van kapcsolva, a hívásközponti felhasználók árváltozásokat tudnak végezni a hívásközponti csatorna értékesítési soraiban, függetlenül attól, hogy a megfelelő termékek engedélyezik-e az árkorrekciót.

Ha a rendelés árellenőrzése be van kapcsolva, **·** **akkor csak azok a termékek biztosítanak okkódot, amelyeknél az Árkorrekrektálás engedélyezése paraméter Beállítása Igen** beállítással történik hívásközponti csatorna értékesítési rendelés esetén, és a megfelelő értékesítési sorokban meg kell adni az okkódot. A hívásközponti felhasználók **csak** **a Kiskereskedelmi és Commerce \> Csatorna \>\> beállítás hívásközpont-beállításának Felülbírálati engedélyeinek értékére módosíthatják az eladási árat.** Ha egy ár felülbírálása meghaladja ezt a százalékot, a felhasználónak egy kérést kell benyújtania, amelyet ezután egy előre meghatározott Commerce-munkafolyamat feldolgoz ellenőrzésre és jóváhagyásra. A Commerce rendszer munkafolyamatokkal kapcsolatos további tudnivalókat lásd [a Munkafolyamat rendszer áttekintésében](/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system).

## <a name="product-level-pricing-settings"></a>Termékszintű árképzési beállítások

A következő beállítások az árképzési szabályokat a termék szintjén érvényesítik, **és a szervezet Termékkonfigurációs lapján találhatók**.

### <a name="allow-price-adjust"></a>Árkorrekció engedélyezése

Ha az **Árkorrek beállított** **paraméter** Értéke Igen, a hívásközponti értékesítési rendeléseken árfelülbrendelések alkalmazhatók a termékre.

### <a name="key-in-price"></a>Ár beírása

Az **árbeállítás kulcsa** határozza meg, hogy kötelező-e megadni a bebillentyűzendő árat, amikor egy terméket hozzáadnak egy értékesítési tranzakcióhoz a POS-terminálon. Meghatározza a megfelelő árérték-korlátozásokat is.

### <a name="zero-price-valid"></a>Nullás ár érvényes

A **Nullás ár érvényes** beállítás határozza meg, hogy egy termék előre meghatározott, rendszer által számított vagy manuálisan módosított eladási ára 0 (nulla) lehet-e. Ha engedélyezve van a **nulla** ár, állítsa Igen paraméterre. Ez a beállítás kategóriaszinten is meg lehet adni a Commerce termékhierarchiából.

### <a name="prevent-all-discounts"></a>Minden engedmény megakadályozása

Az "Összes **engedmény** **megakadályozása**" paraméter Igen beállításával megakadályozza, hogy minden engedménytípust (beleértve a manuális engedményeket) alkalmazzanak egy termékre. Ez a beállítás kategóriaszinten is meg lehet adni a Commerce termékhierarchiából.

> [!NOTE]
> Ez a beállítás nem korlátozza az ár-felülbírálási műveletet, mivel a művelet beállítja az árat, és nem kezeli engedményként.

### <a name="prevent-manual-discounts"></a>Manuális engedmények megakadályozása

A Manuális engedmények **megakadályozása** paraméter Igen **beállításával** megakadályozza, hogy manuális sorengedményeket vagy tranzakcióengedményeket alkalmazzanak egy termékre. Az összes többi engedményt továbbra is alkalmazni lehet. Ez a beállítás kategóriaszinten is meg lehet adni a Commerce termékhierarchiából.

> [!NOTE]
> Ez a beállítás nem korlátozza az ár-felülbírálási műveletet, mivel a művelet beállítja az árat, és nem kezeli engedményként.

### <a name="prevent-retail-discounts"></a>Kiskereskedelmi engedmények megakadályozása

Ha a **Kiskereskedelmi engedmények** **megakadályozása** paraméter Értéke Igen, **egyszerű**, **mennyiség**, **küszöbérték**, **·** **kombinációs** és szállítási engedmény nem alkalmazható egy termékre. Minden más engedmény (a kézi engedményeket is beleértve) továbbra is alkalmazható.

### <a name="prevent-tender-based-discounts"></a>Ajánlatalapú engedmények megakadályozása

Ha a **Fizetőeszköz-alapú** **engedmények megakadályozása paraméter Értéke Igen**, akkor egy **termékre nem lehet fizetőeszköz-alapú** engedményt alkalmazni. Minden más engedmény (a kézi engedményeket is beleértve) továbbra is alkalmazható.

A kiskereskedők gyakran úgy döntik, hogy bizonyos termékeket, például új cikkeket vagy igénycikkeket kizárnak a cikk alapú kedvezményekből (például egyszerű engedmények és mennyiségi engedmények). Előfordulhat azonban, hogy akkor is fizetőeszköz-alapú engedményeket kell alkalmazni, ha a vevő a preferált fizetőeszköz használatával fizet. Ennek az **eredménynek** **·** **az** elérése érdekében a kiskereskedők Az összes engedmény megakadályozása és a fizetőeszköz-alapú engedmények megakadályozása paramétert Nem beállításra állíthatják, **·** **·** **valamint** a Kiskereskedelmi engedmények megakadályozása és a Manuális engedmények megakadályozása paramétert Igen beállításra állíthatják.

## <a name="deprecated-or-removed-settings"></a>Elavult vagy eltávolított beállítások

A következő árképzési beállítások már el vannak távolítva, vagy el vannak tervezve eltávolításra a következőből Dynamics 365 Commerce.

| Beállítás | Értékcsökkenés vagy eltávolítás oka | Értékcsökkenés vagy eltávolítás állapota |
|---------|-----------------------------------|-------------------------------|
| Átfedő engedmények kezelése | A Commerce rendszer ezt a beállítást biztosította annak szabályozására, hogy hogyan keres az árképzési motor, és meghatározza az alkalmazandó legjobb engedménykombinációt. A Legjobb **engedmény beállítás** az árkalkuláció során az összes lehetséges engedménykombinációt kényszeríti. A **legjobb teljesítmény** beállítás egy olyan optimalizált beállítás, amely heuristic algoritmust és a számítás szerinti érték rangsorolási módszert használ a fontossági sorrend meghatározására, értékelésére és a legjobb kombináció időben való meghatározására. A **kódalap** Kiegyensúlyozott számítási lehetősége ugyanaz, mint a **Legjobb teljesítmény**. Emiatt gyakorlatilag egy ismétlődő beállításról van szó. A jobb teljesítmény érdekében **az** árképzési motort frissítették, hogy az általános beállításként csak a legjobb teljesítményt használja. Emiatt ez a beállítás már nem alkalmazható. | A 10.0.21-es verzióban elavult, 2022. októberben lesz eltávolítva. |
| Árkorrekciók engedélyezése a termék árának növeléséhez | Ezzel a beállítással adhatja meg, hogy az árkorrekciós funkció növelheti-e a termékárakat. Ha a paraméter ki van kapcsolva, a szervezetek csak a termék egységárának beállítására használhatja az árkorrekciót, hogy kisebbek, mint az alapár és a kereskedelmi megállapodás eladási ára. Ezt a beállítást elavulta a rendszer, mert az árkorrekciós funkciót frissítették, hogy a mezőből kivehető a kétes visszaigazítás (csökkentés vagy csökkentés). | A 10.0.30-as verzióban elavult, 2023. októberben lesz eltávolítva. |
| Árjelentés engedélyezése kiskereskedelmi üzlet esetén | Ennek a beállításnak az használatával szabályozható, hogy az Árjelentés **funkció** elérhető-e az üzlet konfigurációs lapján való használatra. Ezt a beállítást elavulta **a** rendszer, mert az üzlet konfigurációs lapja frissült, így mindig az Ár jelentés lesz az alapértelmezett funkció. | A 10.0.31-es verzióban elavult, 2023. októberben lesz eltávolítva. |
| A mai dátum használata az árak kiszámításához | Az Dynamics 365 Supply Chain Management árképzési motor támogatja a kért szállítási dátumon vagy a kért kézhezvételi dátumon alapuló árképzési számítást a mai dátummal együtt. A Commerce pricing kalkulátum csak a mai dátumon alapuló árképzési számítást támogat. Az Ellátásilánc-kezelés és a Commerce funkciókat egyaránt használó vevők esetében ezt a beállítást meg lehet adni, **és** javasolt, hogy a vevők mindig Igen beállítással működik együtt, hogy a két árképzési motor együtt működjön. Ezt a beállítást elavultuk, mivel az alapvető módon nem módosítja a számítás viselkedését, ezért redundáns. | A 10.0.31-es verzióban elavult, 2023. októberben lesz eltávolítva. |
| Maximális ár | Ezt a beállítást a funkcióprofilban adták meg, annak szabályozására, hogy csak a megadott maximális árnál alacsonyabb eladási árú termékeket lehet-e adott üzletekben a POS-terminálon keresztül értékesíteni. A beállítás értékcsökkenése az alacsony funkcióhasználat miatt elavult. | A 10.0.31-es verzióban elavult, 2023. októberben lesz eltávolítva. |
| Engedmények alkalmazása az egységárra | Ez a beállítás az árkalkuláció során szabályozható, hogy az árak és az engedmények kerekítése az egységár vagy az értékesítési sor szintjén történik-e. Elavult, mert az aktuális kódalapban nem lesz felhasználva. | A 10.0.31-es verzióban elavult, 2023. októberben lesz eltávolítva. |
| Több cikkengedmény manuális számítása | Ennek a beállításnak a segítségével szabályozható, hogy az árképzési motor késve számítsa-e ki az árat a kiskereskedelmi üzlet csatornájában. **Ha** a paraméter Beállítása Igen, az árképzési motor nem számítja ki azonnal a többsoros engedményeket (például a mennyiségi engedményeket, a küszöbérték-engedményeket és a kombinációs engedményeket) minden alkalommal, amikor értékesítési rendelést hoz létre vagy szerkeszt a POS-alkalmazásban. Úgy döntünk, hogy a Commerce paramétereiben hasonló beállítással összevonjuk ezt a beállítást, és így egychannel vezérlőt lehet eszközölni. | A 10.0.31-es verzióban elavult, 2023. októberben lesz eltávolítva. |

Az eltávolított és Dynamics 365 Commerce [elavult funkciók teljes listáját lásd: Eltávolítva vagy Elavult funkciók a következőben Dynamics 365 Commerce](get-started/removed-deprecated-features-commerce.md):

[!INCLUDE[footer-include](../includes/footer-banner.md)]
