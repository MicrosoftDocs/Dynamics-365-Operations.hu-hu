---
title: Vevői rendelések a pénztárban (POS)
description: Ez a témakör a pénztár (POS) vevői rendeléseivel kapcsolatban tartalmaz információkat. A vevői rendelések speciális rendelések néven is ismertek. A témakör a kapcsolódó paramétereket és tranzakciófolyamatokat is tárgyalja.
author: josaw1
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom:
- "260594"
- intro-internal
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 44beb4515bf0d2f8fc7ad75feb3164bf1c7c2d5737552b1a06ce59c2edcaf8fe
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755083"
---
# <a name="customer-orders-in-point-of-sale-pos"></a>Vevői rendelések a pénztárban (POS)

[!include [banner](includes/banner.md)]

Ez a témakör a pénztár (POS) alkalmazásban a vevői rendelések létrehozásának és kezelésének módjáról tartalmaz információkat. A vevői rendelések arra használhatók fel, hogy olyan értékesítéseket rögzítsenek, amelyeknél a vásárlók egy későbbi időpontban kívánnak termékeket felvenni, másik helyről szeretnének termékeket átvenni, vagy kiszállítást kérnek. 

A sokcsatornás kereskedelmi világ számos kiskereskedő biztosít lehetőséget vevői rendelésekre vagy speciális rendelésekre, hogy így elégítsen ki termékkel és teljesítéssel kapcsolatos különböző igényeket. Íme néhány tipikus forgatókönyv:

- Egy vevő azt szeretné, ha a termékeket egy adott napon egy adott címre szállítanák ki.
- Egy vevő egy olyan üzetben vagy helyen szeretné átvenni a termékeket, amely eltér attól az üzlettől vagy helytől, ahol az ügyfél megvásárolta az adott termékeket.
- Egy üzletben lévő vevő a mai napon rendeli a termékeket, és egy későbbi időpontban ugyanabból az üzletből veszi fel őket.

A kiskereskedők a készlethiány által okozott elmaradt értékesítések minimálisra csökkentése érdekében használják a vevői rendeléseket, mivel így az áru más időben vagy helyen is kiszállítható vagy átvehető.

## <a name="set-up-customer-orders"></a>Vevői rendelések beállítása
Mielőtt megpróbálja használni a POS rendszer vevői rendelés funkcióját, győződjön meg arról, hogy a Commerce-központ összes szükséges konfigurálását végrehajtja.

### <a name="configure-modes-of-delivery"></a>Szállítási módok beállítása

A vevői rendelések használatához konfigurálni kell azokat a szállítási módokat, amelyeket az üzlet csatornája használhat. Legalább egy szállítási módot meg kell határoznia, amely akkor használható, ha a rendelési sorokat egy üzletből a vevőhöz szállítják. Legalább egy átvételi módot is meg kell határoznia, amely akkor használható, ha a rendelési sorokat egy üzletben veszik át. A szállítási módok a Commerce-központ **Szállítási módok** oldalán vannak meghatározva . A szállítási módok konfigurálásával kapcsolatos további információkat a Kereskedelmi csatornákon lásd: [Szállítási módok definiálása](./configure-call-center-delivery.md#define-delivery-modes).

![Szállítási módok oldal.](media/customer-order-modes-of-delivery.png)


### <a name="set-up-fulfillment-groups"></a>Teljesítési csoportok beállítása

Előfordulhat, hogy egyes raktárak vagy raktári helyek nem tudják teljesíteni a vevői rendeléseket. A teljesítési csoportok konfigurálásával egy szervezet meghatározhatja, hogy mely üzletekben és raktárakban jelenjen meg a vevői rendeléseket létrehozásának lehetősége a felhasználók számára a POS rendszerben. A teljesítési csoportok konfigurálása a **Teljesítési csoportok** oldalon történik. A szervezetek tetszőleges számú teljesítési csoportot hozhatnak létre. Ha definiálva van egy teljesítési csoport, társítsa egy üzlethez a **Teljesítési csoport hozzárendelése** lehetőség kiválasztásával, amely az **Üzletek** lap műveleti ablakának **Beállítás** lapján található.

A Commerce 10.0.12 és újabb verzióiban a vállalatok meghatározhatják, hogy a teljesítési csoportokban definiált raktár vagy raktár- és üzletkombinációk használhatók-e vagy szállításra, felvételre vagy szállításra és felvételre is. Ezzel még nagyobb rugalmasságot biztosít a vállalat számára annak meghatározásához, hogy mely raktárak választhatók ki a szállítandó cikkek vevői rendelésének létrehozásakor, illetve, hogy a szállítandó cikkek vevői rendelésének létrehozásakor mely üzleteket lehet kiválasztani. Ezen konfigurációs beállítások hasznáaltához be kell kapcsolni azt a **Helyek meghatározása „Szállításra” vagy „Átvételre” engedélyezve Teljesítési csoportban** funkciót. Ha egy teljesítési csoporthoz csatolt raktár nem üzlet, akkor csak szállítási helyként konfigurálható. Nem használható, ha a pénztárban átvételre konfigurálták a rendelést.

![Teljesítési csoportok oldal.](media/customer-order-fulfillment-group.png)

### <a name="configure-channel-settings"></a>Csatornabeállítások megadása

Amikor a vevői rendelésekkel dolgozik a pénztárban, figyelembe kell vennie az üzlet csatornájának néhány beállítását. Ezek a beállítások a Commerce Headquarters **Áruházak** lapján találhatók.

- **Raktár** – Ez a mező azt a raktárat jelzi, amelyet a rendszer az áruházhoz kötött készpénzzel fizetett, azonnal átvett és vevői átvételes rendelések készletének csökkentésekor fog használni. Legjobb gyakorlatként javasoljuk egyedi raktárak használatát az egyes áruházi csatornákhoz, hogy megelőzzük az áruházakban az egymásnak ellentmondó üzleti logikával kapcsolatos problémákat.
- **Szállítási raktár** – Ez a mező azt a raktárat jelzi, amelyet a rendszer az áruházhoz kötött, a kiválasztott áruházból szállítandó vevői átvételes rendelések készletének csökkentésekor fog használni. Ha a környezetében engedélyezve van a **Helyek „Szállítási” és „Felvételi” minősítéssel való megadása engedélyezett a teljesítési csoporton belül**, akkor a pénztárfelhasználók kiválaszthatnak egy adott raktárat a pénztárban a szállítás forrásaként ahelyett, hogy egy áruházat választanának a szállítás forrásaként. Ezért ha ez a szolgáltatás engedélyezve van, a szállítási raktár már nem lesz használva, mivel a felhasználó az adott raktárt választja ki a rendelés szállításának forrásaként a rendelés létrehozásakor.
- **Teljesítési csoport hozzárendelése** – Arra válassza ezt a gombot (a művelet ablaktábla **Beállítás** lapján), hogy kapcsolja a teljesítési csoportokat, amelyekre hivatkozik, hogy megjelenítse az átvételi lehetőségeket vagy a szállítások eredetét, amikor ügyfélrendeléseket hoznak létre a pénztárban.
- **Célhelyen alapuló adó használata** – Ez a beállítás azt jelzi, hogy a szállítási cím használatos-e a vevő címére leszállított rendeléssorok esetében alkalmazott áfacsoportok meghatározására.
- **Vevőn alapuló adó használata** – Ez a beállítás azt jelzi, hogy a vevő szállítási címéhez megadott adócsoport van-e alkalmazva a vevő otthonába történő szállításhoz a POS rendszerben létrehozott vevői rendelésekre.

![A csatorna beállításának használat az Áruházak lapon.](media/customer-order-all-stores.png)

### <a name="set-up-customer-order-parameters"></a>Ügyfélrendelés paramétereinek beállítása

Mielőtt megpróbálkozna a vevői rendelések létrehozásával a POS rendszerben, konfigurálnia kell a megfelelő paramétereket a Commerce-központban. Ezek a paraméterek a **Vevői rendelések** fülön találhatók a **Commerce paraméterek** oldalon.

- **Alapértelmezett rendeléstípus** – A POS rendszerben létrehozott vevői rendelésekhez alapértelmezettként hozzárendelt rendelés típusának megadása. Ezek a vevői rendelések lehetnek értékesítési rendelések vagy árajánlati rendelések. Az alapértelmezett rendelés típustól függetlenül a felhasználó a pénztárból is létrehozhatja az értékesítési rendeléseket és a vevői rendeléseket.
- **Letét alapértelmezett százalékos értéke** – A teljes rendelési összeg százalékának megadása, amelyet a vevőnek ki kell fizetnie letétként, mielőtt a megrendelést meg lehet erősíteni. A jogosultságaiktól függően az áruházi munkatársak képesek lehetnek az összeg felülbírálására a pénztár **Letét felülbírálása** műveletével, ha ez a művelet be van állítva a tranzakciós képernyő elrendezésén.
- **Átvételi szállítási mód** – Határozza meg azt a szállítási módot, amelyet a pénztár rendszerben az átvételre konfigurált értékesítésirendelés-sorokra kell alkalmazni.
- **Kiszállítás szállítási módja** – Adja meg a szállítási módot, amelyet olyan értékesítésirendelés-sorokra kell alkalmazni, amelyek kiszállítandó értékesítési sornak minősülnek, amikor vegyes kosár jön létre, ahol egyes sorok át lesznek véve vagy ki lesznek szállítva, míg más sorokat az ügyfél azonnal átvesz.
- **Lemondási díj százalékos értéke** – ha vevői rendelés visszavonásakor díjfizetés szükséges, úgy adja meg ezen díj összegét.
- **Lemondás költségkódja** – adja meg a Kinnlevőség költségkódját, amelyet akkor kell alkalmazni, ha a lemondott vevői rendelésekre a lemondási költséget alkalmaz a program a pénztárban. A költségkód határozza meg a lemondási díj pénzügyi feladási logikáját.
- **Szállítás költségkódja** – Ha a **Speciális automatikus költségek használata** beállítás értéke **Igen**, akkor ennek a paraméterbeállításnak nincs hatása. Ha ez a beállítás **Nem** értékre van állítva, akkor a program felkéri a felhasználót, hogy manuálisan adja meg a szállítási költséget, amikor vevői rendeléseket hoz létre a pénztárban. Ezzel a paraméterrel hozzárendelheti a Kinnlevőségek költségkódját, amelyet a program a rendelésekre alkalmaz, amikor a felhasználók szállítási költséget határoznak meg. A költségkód határozza meg a szállítási díj pénzügyi feladási logikáját.
- **Speciális automatikus költség használata** – Ezt a beállítást **Igen** értékre kell állítani, ha a rendszer által kiszámított automatikus költséget kívánja használni a vevői rendelések létrehozásakor a POS rendszerben. Ezek az automatikus költségek szállítási költségek vagy más rendelés vagy tételspecifikus költségek kiszámítására használhatók. A speciális automatikus költség funkció beállításával és használatával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Többcsatornás speciális automatikus költségek](./omni-auto-charges.md).

![Vevői rendelések lap a Commerce-paraméterek oldalon.](media/customer-order-parameters.png)

### <a name="update-transaction-screen-layouts-in-pos"></a>Tranzakciós képernyő-elrendezések frissítése a pénztár rendszerben

Győződjön meg róla, hogy a pénztár [képernyő elrendezése](./pos-screen-layouts.md) úgy van beállítva, hogy támogassa a vevői rendelések létrehozását és kezelését, valamint az összes szükséges POS-művelet konfigurálva legyen. Az alábbiakban néhány olyan Pénztári művelet szerepel, amelyeket a vevői rendelések helyes létrehozásához és kezeléséhez ajánlott használni:
- **Minden termék szállítása** – Ennek a műveletnek a segítségével megadhatja, hogy a program a tranzakciós kosár minden sorát egy célhelyre szállítsa ki.
- **Kiválasztott termékek szállítása** – Ennek a műveletnek a segítségével megadhatja, hogy a program a tranzakciós kosár kiválasztott sorait egy célhelyre szállítsa ki.
- **Minden termék átvétele** – Ennek a műveletnek a segítségével megadhatja, hogy a tranzakciós kosár minden sora a kiválasztott áruházi helyről lesz átvéve.
- **Kiválasztott termékek átvétele** – Ennek a műveletnek a segítségével megadhatja, hogy a tranzakciós kosár kiválasztott sorai a kiválasztott áruházi helyről lesznek átvéve.
- **Az összes termék kiszállítása** – Ennek a műveletnek a segítségével megadhatja, hogy a tranzakciós kosár minden sora ki lesz szállítva. Ha ez a művelet a POS rendszerben használatos, akkor a program a vevői rendelést készpénz-és szállítási tranzakcióra fogja átalakítani.
- **A kiválasztott termékek elvitele** – Ennek a műveletnek a segítségével megadhatja, hogy a vevő a vásárláskor a tranzakciós kosárban szereplő kiválasztott sorokat elviszi. Ez a művelet csak [hibrid rendelés](./hybrid-customer-orders.md) esetén hasznos.
- **Rendelés előhívása** – Ennek a műveletnek a használatával lehet megkeresni és előhívni a vevői rendeléseket, hogy a pénztári felhasználók igény szerint szerkesszék érvénytelenítsék vagy végrehajtsák a teljesítéssel kapcsolatos műveleteiket.
- **Szállítási mód módosítása** – Ezzel a művelettel gyorsan megváltoztathatja a szállítási módot azoknál a soroknál, amelyek már be vannak állítva a szállításhoz, anélkül, hogy a felhasználó ismét végigmenne az „összes termék szállítása” vagy a „kiválasztott termék szállítása” folyamaton.
- **Letét felülbírálása** – Ezzel a művelettel módosítható a vevő által a kiválasztott vevői rendeléshez fizetett letét összege.

![Műveletek a pénztár tranzakciós képernyőjén.](media/customer-order-screen-layout.png)

## <a name="work-with-customer-orders-in-pos"></a>Vevői rendelések használata a pénztárban

> [!NOTE]
> A bevételelszámolás funkció jelenleg nem támogatott a Commerce-csatornákban (e-kereskedelem, pénztár, hívásközpont). A bevételelszámolással konfigurált cikkeket nem szabad hozzáadni a Commerce-csatornákban létrehozott rendelésekhez. 

### <a name="create-a-customer-order-for-products-that-will-be-shipped-to-the-customer"></a>Vevői rendelés létrehozása a vevőnek szállítandó termékekhez

1. A pénztár tranzakciós képernyőjén vegyen fel egy vevőt a tranzakcióba.
2. Adjon hozzá termékeket a kosárhoz.
3. Válassza ki a **Kijelöltek szállítása** vagy az **Összes szállítása** lehetőséget a terméknek a vevői fiókban található címre történő szállításához.
4. Válassza ki a lehetőséget a vevői rendelés létrehozásához.
5. Nyugtázza vagy módosítsa a „szállítás kiindulási helye” helyet, nyugtázza vagy módosítsa a szállítási címet, és válassza ki a szállítási módot.
6. Adja meg a vevő kívánt rendelési szállítási dátumát.
7. Használja a fizetési funkciókat a kiszámított esedékes összegek kifizetésére , vagy használja a **Letét felülbírálása** műveletet, ha módosítani szeretné az esedékes összegeket, majd alkalmazza a kifizetést.
8. Ha a teljes rendelés teljes összege nem lett kifizetve, akkor adja meg azt a hitelkártyát, amelyet a program a számlán esedékes egyenleghez rögzít.

### <a name="create-a-customer-order-for-products-that-the-customer-will-pick-up"></a>Vevői rendelés létrehozása termékekhez vevői átvételhez

1. A pénztár tranzakciós képernyőjén vegyen fel egy vevőt a tranzakcióba.
2. Adjon hozzá termékeket a kosárhoz.
3. Válassza ki a **Kiválasztott átvétele** vagy az **Összes átvétele** lehetőséget a rendelés átvételre konfiguráció kezdeményezéséhez.
4. Válassza ki azt az áruházi helyet, amelyben a vevő a kiválasztott termékeket átveszi.
5. Válassza ki a cikk felvételének dátumát.
6. Használja a fizetési funkciókat a kiszámított esedékes összegek kifizetésére , vagy használja a **Letét felülbírálása** műveletet, ha módosítani szeretné az esedékes összegeket, majd alkalmazza a kifizetést.
7. Ha a teljes rendelés teljes összege nem lett kifizetve, válassza ki, hogy a vevő később fizeti-e ki a kifizetést (felvételkor), vagy hogy a hitelkártyát már most beolvassák, majd a felvételkor használják.

### <a name="edit-an-existing-customer-order"></a>Meglévő vevői rendelés szerkesztése

Az online vagy az áruházi csatornában létrehozott kiskereskedelmi rendelések igény szerint visszahívhatók és szerkeszthetők a pénztári rendszer használatával.

> [!IMPORTANT]
> Nem minden kiskereskedelmi rendelés szerkeszthető a pénztáralkalmazáson keresztül. Egy hívásközpont-csatornában létrehozott rendelések nem szerkeszthetők a pénztárban ha a [Rendeléskiegészítés engedélyezése](./set-up-order-processing-options.md#enable-order-completion) beállítás be van kapcsolva a hívásközpont csatornához. A helyes fizetésfeldolgozásbiztosításához a hívásközpont-csatornából származó és a rendelés kiegészítését engedélyező szolgáltatásokat a Commerce-központ hívásközpont alkalmazásán keresztül kell szerkeszteni.

> [!NOTE]
> Azt ajánljuk, hogy a Commerce Headquarters alkalmazásban ne szerkessze a nem hívásközponti felhasználó által létrehozott rendeléseket és árajánlatokat a POS-ban. Ezek a rendelések és árajánlatok nem használják a Commerce árképzési motort, ezért ha a POS-ban szerkesztik őket, akkor a Commerce árképzési motor újra fogja árazni őket.


A 10.0.17-es és újabb verziókban a felhasználók még akkor is szerkeszthetik a felveendő rendeléseket a pénztáralkalmazáson keresztül, ha a rendelést részlegesen teljesítették. A teljesen kiszámlázott rendelések azonban a pénztári rendszerből továbbra sem szerkeszthetők. A funkció engedélyezéséhez kapcsolja be az **(Előzetes verzió) Részben teljesített rendelések szerkesztése** funkciót a **Funkciókezelés** munkaterületen a Pénztárban. Ha ez a funkció nincs engedélyezve, vagy ha a 10.0.16-os vagy korábbi verziót használja, a felhasználók csak akkor szerkeszthetik a vevői rendeléseket a pénztárban, ha a rendelés teljesen nyitva van. Ezenkívül ha a funkció engedélyezve van, korlátozhatja, hogy mely üzletek szerkeszthetik a részlegesen teljesített rendeléseket. Ezen képesség adott üzletekre vonatkozó letiltását az **Általános** gyorslap **Funkcióprofil** pontjában állíthatja be.


1. Válassza a **Rendelés előhívása** lehetőséget.
2. A **Keresés** segítségével megadhatja a rendelés megtalálásához használandó szűrőket, majd válassz az **Alkalmaz** lehetőséget.
3. Válassza ki a rendelést az eredménylistában, majd válassza a **Szerkesztés** parancsot. Ha a **Szerkesztés** gomb nem érhető el, akkor a rendelés olyan állapotban van, hogy nem szerkeszthető.
4. Végezze el a vevői rendelés szükséges módosításait a tranzakciós kosárból. Szerkesztés közben előfordulhat, hogy bizonyos módosítások tiltottak.
5. Fejezze be a szerkesztési folyamatot egy kifizetési művelet kiválasztásával.
6. He ki szeretne lépni a szerkesztési folyamatból a módosítások mentése nélkül, akkor használja a **Tranzakciós érvénytelenítése** műveletet.

#### <a name="pricing-impact-when-orders-are-edited"></a>Árképzés hatása a megrendelések szerkesztésekor

Amikor a megrendeléseket a POS-ban vagy egy Commerce e-kereskedelmi webhelyen adják le, a vevők elkötelezik magukat egy összeg mellett. Ez az összeg tartalmaz egy árat, valamint tartalmazhat engedményt is. Az a vevő, aki rendelést ad fel, majd később kapcsolatba lép a hívásközponttal, és módosítja a rendelést (például egy másik cikk felvétele érdekében), különleges elvárásai lesznek az engedmények alkalmazásával kapcsolatban. Még ha a meglévő rendeléssorok promóciói le is járnak, a vevő arra számít, hogy az eredetileg az ilyen sorokra alkalmazott kedvezmények érvényben maradnak. Ha viszont a rendelés eredeti leadásakor nem volt érvényben engedmény, de azóta hatályba lépett egy engedmény, akkor a vevő azt várja, hogy az új engedményt a módosított rendelésre alkalmazzák. Ellenkező esetben előfordulhat, hogy a vevő egyszerűen érvényteleníti a meglévő rendelést, és létrehoz egy új rendelést, amely az új engedményt is tartalmazza. Ahogy ez a helyzet is mutatja, meg kell őrizni azokat az árakat és engedményeket, amelyekre a vevők kötelezettséget vállalnak. Ugyanakkor a POS és a hívásközpont felhasználóinak is rugalmasan kell újraszámolniuk szükség szerint az értékesítésirendelés-sorok árait és engedményeit.

Amikor a rendeléseket a POS-ban visszahívják és szerkesztik, a meglévő rendeléssorok árai és engedményei "zároltnak" minősülnek. Más szóval nem módosulnak akkor sem, ha bizonyos rendeléssorokat visszavonnak vagy módosítnak, vagy új rendeléssorokat adnak hozzá. A meglévő értékesítési sorok árainak és engedményeinek módosításához a POS felhasználónak az **Újraszámítás** lehetőséget kell választania. Ezt követően a rendszer eltávolítja az árzárolást a meglévő rendeléssorokból. A Commerce 10.0.21-es verziója előtt azonban ez a képesség nem volt elérhető a hívásközpontban. Ehelyett a rendeléssorok módosításai az árak és engedmények újraszámításával jártak.

A Commerce rendszer 10.0.21-es verziójának kiadásában egy új, **Nem szándékos árszámítás megakadályozása kereskedelmi rendelésekhez** nevű funkció érhető el a **Funkciókezelés** munkaterületen. Ez a funkció alapértelmezés szerint be van kapcsolva. Ha be van kapcsolva, minden e-kereskedelmi rendelés számára egy új, **Zárolt ár** nevű tulajdonság érhető el. Miután a rendelésrögzítés befejeződött a bármely csatornából származó rendelésekhez, ez a tulajdonság automatikusan engedélyezett lesz (azaz a jelölőnégyzete be lesz jelölve) az összes rendeléssornál. A Commerce árképző motor ezután kizárja ezeket a rendeléssorokat az összes ár- és engedményszámításból. Ezért ha módosítja a rendelést, akkor alapértelmezés szerint a rendeléssorok ki lesznek zárva az árképzési és engedményszámításból. A hívásközponti felhasználók azonban letilthatják a tulajdonságot (azaz törölhetik a jelölőnégyzetet) bármely rendelési sorhoz, majd az **Újraszámítás** kiválasztásával a meglévő rendeléssorokat belefoglalhatják az árképzési számításokba.

Még akkor is, ha manuális engedményt alkalmaznak egy meglévő értékesítési sorra, a hívásközponti felhasználóknak le kell tiltaniuk az értékesítési sor **Zárolt ár** tulajdonságát, mielőtt a manuális engedményt alkalmazhatják.

A hívásközponti felhasználók szintén letilthatják a **Zárolt ár** tulajdonságot a tömeges rendeléssorok esetén, ha az **Értékesítési rendelés** lap Művelet ablaktáblájának **Eladás** lapján a **Számítás** csoportban az **Árzárolás eltávolítása** lehetőséget választják. Ebben az esetben a rendszer eltávolítja az árzárolást minden rendeléssorból, kivéve azokat a sorokat, amelyek nem szerkeszthetők (más szóval a **Részlegesen számlázott** vagy **Számlázott** állapotú sorokat). Ezután a rendelés módosításainak befejezését és beküldését követően a rendszer az összes rendeléssorhoz újrarendeli az árzárolást.

> [!IMPORTANT]
> Ha be van kapcsolva a **Kereskedelmi rendelések véletlen árszámításának megakadályozása** funkció, az árképzési munkafolyamatokban figyelmen kívül lesznek hagyva a kereskedelmi megállapodások kiértékelésének beállítása. Más szóval a kereskedelmi megállapodás kiértékelése párbeszédpaneleken nem jelenik meg az **Árhoz kapcsolódó** szakasz. Ez a viselkedés azért következik be, mert mind a kereskedelmi megállapodás kiértékelési beállításának, mind az árrögzítési funkciónak hasonló a célja: a nem szándékos árváltozások megakadályozása. A kereskedelmi megállapodások kiértékelésében szerzett felhasználói tapasztalat azonban nem megfelelő a nagy rendelésekhez, ahol a felhasználóknak ki kell választaniuk egy vagy több rendelési sort az ismételt árképzéshez.

> [!NOTE]
> A **Zárolt ár** tulajdonság csak akkor tiltható le egy vagy több kiválasztott sorra, ha a **Hívásközpont** modult használják. A POS működése változatlan marad. Más szóval a POS-felhasználó nem tudja feloldani a kiválasztott rendeléssorok árait. Választhatja azonban az **Újraszámítás** lehetőséget, hogy az árzárolást eltávolítsa az összes meglévő rendeléssorból.

### <a name="cancel-a-customer-order"></a>Vevői visszavonása

1. Válassza a **Rendelés előhívása** lehetőséget.
2. A **Keresés** segítségével megadhatja a rendelés megtalálásához használandó szűrőket, majd válassz az **Alkalmaz** lehetőséget.
3. Válassza ki a rendelést az eredménylistában, majd válassza az **Érvénytelenít** parancsot. Ha az **Érvénytelenít** gomb nem érhető el, akkor a rendelés olyan állapotban van, hogy már nem vonható vissza.
4. Ha be van állítva lemondási költéség, akkor erősítse meg. A lemondási költséget a jóváhagyás előtt módosíthatja. 
5. A tranzakciós kosárból végezze el a lemondási folyamatot a kifizetési művelet kiválasztásával. Ha a kifizetett letét túllépi a lemondási díjat, akkor a visszatérítési kifizetések lehetnek esedékesek.
6. He ki szeretne lépni a visszavonása folyamatból a módosítások mentése nélkül, akkor használja a **Tranzakciós érvénytelenítése** műveletet.

## <a name="finalizing-the-customer-order-shipment-or-pickup-from-pos"></a>A vevői rendelési szállításának vagy felvételének véglegesítése a pénztárból

Miután létrehozta a rendelést, a cikkeket a vevő egy üzletből veszi fel, vagy ki lesznek szállítva a rendelés konfigurációjától függően. A folyamattal kapcsolatos további tudnivalókat lásd az [áruházi rendelés teljesítése](./order-fulfillment-overview.md) dokumentációt.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Tranzakció aszinkron folyamata vevői rendeléseknél

Vevői rendelések pénztárból szinkron vagy aszinkron üzemmódban hozhatók létre. Ha a vevői rendelések létrehozásakor a pénztárból problémákat vagy késedelmet tapasztal, gondolkozzon el az aszinkron rendeléslétrehozás létrehozásán.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Vevői rendelések aszinkron módban történő létrehozásának engedélyezése

1. A Commerce-központ **Profilok** lapján válassza ki azt a funkcióprofilt, amely megfelel a konfigurálni kívánt áruháznak.
2. Az **Általános** gyorslapon állítsa a **Vevői rendelés létrehozása aszinkron módban** lehetőséget **Igen** értékre.

Ha a **Vevői rendelés létrehozása aszinkron módban** beállítása **Igen**, a vevői rendelések mindig aszinkron módban jönnek létre, akkor is, ha a Retail Transaction Service (RTS) elérhető. Ha ennél a beállításnál **Nem** értéket ad meg, a vevői rendelések mindig szinkron módban jönnek létre az RTS segítségével. Ha a vevői rendelések aszinkron módon jönnek létre, akkor a Commerce-központ lekéri és kiskereskedelmi tranzakcióként hozza létre azokat Commerce Pull (P) munkaként. A megfelelő vevői rendelések a kiskereskedelmi tranzakciókhoz a **Rendelések szinkronizálása** manuális futtatásakor vagy kötegelt feldolgozás révén jönnek létre.

## <a name="additional-resources"></a>További erőforrások

[Hibrid vevői rendelések](hybrid-customer-orders.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
