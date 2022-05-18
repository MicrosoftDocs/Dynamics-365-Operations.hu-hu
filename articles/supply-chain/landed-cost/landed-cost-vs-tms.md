---
title: Partraszállítási költség és Szállításkezelés
description: A Microsoft Dynamics 365 Supply Chain Management két különböző modult biztosít a szállítás kezelésére, a Szállításkezelés (TMS) és a Partraszállítási költség modult. Ez a témakör összefoglalja a két modul közös funkcióit, és kiemeli a két modul közötti különbségeket.
author: Weijiesa
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8c59d7d1887986d308cb591ece077cff9f4648a5
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690372"
---
# <a name="landed-cost-vs-transportation-management"></a>Partraszállítási költség és Szállításkezelés

[!include [banner](../../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management két különböző modult biztosít a szállítás kezelésére, a **Szállításkezelés** (TMS) és a **Partraszállítási költség** modult. Ez a témakör összefoglalja a két modul közös funkcióit, és kiemeli a két modul közötti különbségeket. Az információk alapján eldöntheti, hogy melyik modul a legmegfelelőbb az üzleti gyakorlatához. Előfordulhat, hogy egyes üzleti gyakorlatok jobban működnek a TMS-sel, míg mások a Partraszállítási költséggel működnek a legjobban. Ezután az üzleti követelményektől függően dönthet úgy, hogy csak egy modult használ, vagy kombinálhatja a két modult.

Ez a témakör nem nyújt teljes áttekintést egyik modul összes funkciójáról sem. Ehelyett a rendelkezésre álló funkciókat emeli ki, mivel az áruk szállítótól a vállalat raktárába történő szállítására vonatkozik, ahol azokat fel lehet használni.

## <a name="terminology-reference-data-and-reporting-differences"></a>Terminológia, hivatkozási adatok és jelentéskészítési különbségek

### <a name="terminology-comparison"></a>Terimnológia összehasonlítása

A TMS és a Partraszállítási költség eltérő kifejezéseket használ a hasonló fogalmakhoz. A következő táblázat összefoglalja ezeket a kifejezéseket és azok használatát a két modulban.

| TMS kifejezés | Partraszállítási költség kifejezés | Jegyzetek |
|----------|------------------|-------|
| **Betöltés**<p>A *rakomány* olyan szállítmányok gyűjteménye, amelyek egyszerre, ugyanazon a szállítási egységen (például teherautón vagy hajón) szállíthatók. A rakományok kimenők vagy bejövők is lehetnek.</p> | **Út**<p>Az *hajóút* általában egy hajó, amely egyetlen *úton* halad végig. Egy hajóút több *szállítási konténert* is tartalmazhat, valamint a szervezet különböző jogi személyeitől származó bejövő rendeléseket is. Az hajóutak csak bejövők lehetnek.</p> | A TMS a *hajóút számát* is használja, amely egy információs mezőre vonatkozik, amelyben meg lehet adni egy azonosítót. A TMS mezőhöz azonban nincs társítva funkció, és nincs kapcsolatban a Partraszállítási költség *hajóút* koncepciójával. |
| **Útvonal**<p>Az *útvonal* a szállításnak a forrástól a célig vezető fizikai útvonala.</p> | **Utazás**<p>Az *út* a szállításnak a forrástól a célig vezető fizikai útvonala. Minden hajóutat egy úthoz kell hozzárendelni.</p> | |
| **Útvonalszakaszok**<p>Egy útvonalnak több *útvonalszakasza* is lehet, amelyek mindegyike az út egy lépését képviseli. Egy útvonal több szállítmányozót vagy szolgáltatást is tartalmazhat, amelyek mindegyike útvonalszakasznak tekinthető.</p> | **Szakaszok**<p>Egy útnak több *szakasza* is lehet, amelyek mindegyike az út egy lépését képviseli. A szakasz lehet a szállítás, a vámkezelés vagy más tevékenység része.</p> | |
| **Tárolók**<p>A *konténer* bármilyen csomag vagy csomagolás lehet, amelyet a TMS használ.</p> | **Szállítási konténerek**<p>A *szállítókonténer* egy szó szerinti, fizikai szállítókonténer, amely a konténerszállító hajókról ismert.</p> | |
| **Árucikk-kódok**<p>A TMS-ben (és a Supply Chain Management alkalmazásban) az *árucikk kódok* azonosítják az árucikktípusokat. Hatással lehetnek a vámtarifaszámra, a veszélyes anyagok kezelésére stb.</p> | **Árucikk-kódok**<p>A Partraszállítási költségben az *árucikk kódok* a jogi személy szintjén vannak létrehozva. Leginkább jelentésre szolgálnak.</p> | A Partraszállítási költség felhasználhatja a TMS-hez és más helyen a Supply Chain Management alkalmazáshoz használt árucikk kódokat is. A Partraszállítási költség árucikk kódjait azonban csak a Partraszállítási költség használja. |

### <a name="some-reference-data-isnt-shared"></a>Egyes hivatkozási adatok nincsenek megosztva

A TMS és a Partraszállítási költség nem osztja meg a hivatkozási adatokat olyan entitások esetében, mint a költségbeállítás, az utak és a szakaszok. Ha mindkét modult használja, akkor újra létre kell hoznia a nem megosztott hivatkozási adatokat.

### <a name="intercompany-reports-dont-work-with-goods-in-transit"></a><a name="intercompany-reports"></a>A vállalatközi jelentések nem működnek az átmenő árukkal

A következő jelentések nem működnek a Partraszállítási költség által biztosított átszállítási funkcióval:

- [Úton lévő vállalatközi áruk összesen jelentés](/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)
- [Úton lévő vállalatközi áruk összesen jelentés](/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)

Ezek a jelentések feltételezik, hogy az áru a szállítólevél kiállítása után azonnal szállításra kerülnek, illetve az átszállításból való bevételezéskor a készletbe kerülnek. Az úton lévő áruk feldolgozása azonban nem így történik. Ezért ha az úton lévő árukat és a vállalatközi funkciókat együtt használja, mindkét jelentés eredményei helytelenek lesznek.

## <a name="using-the-two-modules-together"></a>A két modul együttes használata

A TMS a bejövő és a kimenő műveletekhez is használható. Bár a Partraszállítási költség biztosítja a legtöbb alapvető funkciót, mint a bejövő műveletek TMS szolgáltatása, bizonyos funkciókat is hozzáad. Ezért érdemes megfontolni a TMS használatát a kimenő műveletekhez és Partraszállítási költségét bejövő műveletek esetén.

Általában nem javasoljuk, hogy mindkét modult együtt használja a bejövő műveletekhez. A követelményeknek leginkább megfelelő modult kell használnia. Ha a két modult együtt használja, akkor nem oszthatja meg közöttük a forrásdokumentumokat. Ne használja például ugyanazt a beszerzési rendelést egy TMS-rakományhoz és egy hajóúthoz a Partraszállítási költségben. Különösen biztosítani kell, hogy a rendszer ne legyen beállítva a bejövő rakományok automatikusan létrehozására. Ha a beszerzési rendelésekből származó cikkeket egy hajóút tartalmazza, nem kezelhetők rakomány részeként.

## <a name="goods-in-transit"></a>Úton lévő áruk

A Partraszállítási költség egyik elsődleges jellemzője az úton lévő áruk feldolgozása. Az átszállítás alatt lévő áruk feldolgozása lehetővé teszi, hogy átvegye a leszállított cikkek pénzügyi tulajdonjogát, mielőtt fizikailag átérnek a célraktárba. Az úton lévő áruk feldolgozása gyakran szükséges a nemzetközi kereskedelemhez.

### <a name="tms-goods-in-transit-features"></a>TMS úton lévő áruk funkciói

A TMS jelenleg nem támogatja az úton lévő áruk feldolgozását.

### <a name="landed-cost-goods-in-transit-features"></a>Partraszállítási költség úton lévő áruk funkciói

Az úton lévő áruk feldolgozása a Partraszállítási költség elsődleges szolgáltatása, amely a következő funkciókat biztosítja:

- **Úton lévő áruk raktárai** – Az úton lévő áruk raktárai a Supply Chain Management minden raktárához társíthatók. Az áruk átkerülnek az úton lévő áruk raktáraiba az eredeti beszerzési rendelés számlázása után. Azok a cikkek, amelyek ténylegesen le vannak ott foglalva, felhasználásra elérhetetlenné válnak, amíg nem bevételezik őket a fizikai raktárban. Ebből következően a beszerzési rendelés számlázása esetén a cikkek pénzügyi tulajdonjogát is átveheti.
- **Úton lévő áruk főkönyvi számlája** – A Partraszállítási költség hozzáad egy konkrét főkönyvi feladási számlát a beszerzési rendelés feladási profiljához, hogy kezelni tudja az úton lévő áruk feldolgozását. Ez az úton lévő áruk főkönyvi számlája „számlázott de nem bevételezett áruk” típusú számlaként működik. Amikor az eredeti beszerzési rendelést kiszámlázták, és létrejöttek az úton lévő áruk rendelésen szereplő áruk, a közvetlen beszerzési rendelés költségét feladja a program az úton lévő áruk főkönyvi számlájára, amíg az árukat nem bevételezik a végső fizikai helyen.
- **Nyomon követési vezérlő frissítései** – Az úton lévő áruk rendelések támogatják a nyomon követési funkciókat a Partraszállítási költségben. A nyomon követési ellenőrzés segítségével frissítheti az áruk várható érkezési dátumát szállítás közben. A nyomon követés ellenőrzése ezután frissíti az hajóutat és a kapcsolódó beszerzésirendelés-sorokat. A várható szállítási dátum ezután elérhető lesz az alaptervezés és a logisztika számára.
- **Többlet/hiány tranzakciók aktiválása** – Ha eltérés van egy hajóúton várható áruk és a raktárba bevételezett tényleges áruk között, akkor a Partraszállítási költség többlet és vagy hiány tranzakciók létrehozásával oldja meg. Ezt követően, attól függően, hogy hogyan szeretné feldolgozni őket, beszerzési rendelésen vagy mozgatási naplón keresztül kezelheti ezeket a tranzakciókat. A többlet és hiány tranzakciók hivatkozást biztosítanak a hajóútra, az eredeti beszerzési rendelésre, valamint az eltérés új mozgási naplójára vagy beszerzési rendelésére.
- **Úton lévő áruk rendelések** – A Partraszállítási költség egy új forrásdokumentumot, más néven *úton lévő áruk rendelést* vezet be. Az úton lévő áruk rendelés lehetővé teszi, hogy kiszámlázza az eredeti beszerzési rendelést, hogy átvegye a cikkek pénzügyi tulajdonjogát. A beszerzési rendelés számlázása esetén új forrásdokumentum jön létre minden olyan beszerzésirendelés-sorhoz, amely készletdimenziók kombinációját tartalmazza. Az áruk ezután ténylegesen átkerülnek az úton lévő áruk egyik raktárába, ahol ténylegesen le vannak foglalva az úton lévő áruk rendelésének megfelelően, és csak akkor lehet őket felhasználni, ha az úton lévő árukat bevételezték.

## <a name="miscellaneous-charges-and-shipment-costs"></a>Vegyes költségek és szállítási költségek

Az áruk szállításának és szállításkezelésének egyik legfontosabb szempontja a szállítmányok járulékos költségeinek rögzítése. Ezek a járulékos költségek nem a beszerzési rendeléshez és a szállításhoz vagy hajóúthoz kapcsolódó közvetlen készletköltségek. Ehelyett ezek további költségeket jelentek, amelyek a cikkek szállítótól a szervezethez történő mozgásának jellege miatt merülnek fel. Ezek közé tartozhatnak az olyan fuvarozási költségek, amelyek az áruk egyik fizikai helyről a másikra történő szállításával kapcsolatosak, vagy az olyan vámköltségek, amelyek egy külföldi szállítótól származó áruk importálásával kapcsolatosak.

A Partraszállítási költség ezeket a költségeket egy új típusú, *automatikus költségek* néven is ismert költségszerkezet létrehozásával kezeli. A TMS a vegyes költségek funkcióival kezeli ezeket a költségeket.

### <a name="tms-charge-and-cost-features"></a>TMS és költség funkciói

A TMS vegyes költségeket használ a rakományok további költségeinek kezelésére, amelyek a kapcsolódó forrásdokumentumsorok között vannak felosztva. Ezek a vegyes költségek a beszerzésirendelés-sor vagy a beszerzési rendelés fejlécének szintjén is beállíthatók.

A TMS-ben a vegyes költségek arányosíthatók vagy feloszthatók a készlet súlya, térfogata vagy mennyisége szerint. A díjak feloszthatók fuvar- vagy egyéb díjak szerint. További fejlesztés szükséges a TMS további felosztási módszereinek alkalmazásához.

### <a name="landed-cost-charge-and-cost-features"></a>Partraszállítási költség díj és költség funkciói

A Partraszállítási költség olyan költségfunkciók halmazát biztosítja, amelyek az áruk szállításához kapcsolódó további költségeket kezelik. Ezeket a költségeket automatikus költségnek is nevezik, és a szállítás kezdeti számlázásakor a becsült költség összegének használatával lehet őket alkalmazni. Minden költségtípus kezelése a saját feladásában történik. A többletköltségek tényleges számláinak feladása után a becsült költségek automatikusan frissülnek, hogy tükrözzék a tényleges költségeket.

Ezenkívül az áruk szállításával kapcsolatos járulékos költségek számlázhatóak a származási kikötőből induló hajóút során vagy az áruk beszállítását követően bármikor. Ez a képesség nagyobb rugalmasságot biztosít az áruk felhasználásában.

Az alábbi lista a Partraszállítási költség díj- és költségfunkcióival kapcsolatos fogalmakat ismertet:

- **Költségterület** – Hajóúton a díjak és a költségek több szinthez, más szóval *költségterülethez* is hozzárendelhetők. A költség a hajóút szintjén alkalmazható, és a hajóút minden egyes cikkjére le van bontva. Ezenkívül a költségek a konténer, a beszerzési rendelés, a cikk vagy az átszállítási rendelés szintjén is alkalmazhatók. Minden költség külön kezelhető a különböző területeken, és cikkenkénti költségre bontható.
- **Arányosítási módszerek** – A Partraszállítási költségben többféle arányosítási módszer érhető el. A költségdíjak arányosíthatók mennyiség, dollárban megadott összeg, érték, súly, térfogat, mérték vagy egy felhasználó által megadott térfogatmérték szerint.
- **Elszámolás/különbözet ellenőrzése** – A költségdíjak saját költségkódtípusként vannak beállítva a Partraszállítási költségben. Minden költségkódtípusnál meg lehet határozni a becsült költségek elszámolószámláját, valamint a becsült költségek és a tényleges költségek különbözeteire vonatkozó könyvelési és beszerzésiár-eltérési számlákat. A becsült költségek kezdeti feladási idejekor követel összeg áll az elszámolószámlán. A tényleges számlák feladása után a tényleges költségdíjak feladásra kerülnek, és a becsült költségek terhelésként kerülnek ki az elszámolószámláról.

## <a name="matching-freight-bills-and-invoices"></a>Fuvarlevelek és számlák egyeztetése

### <a name="tms-bill-and-invoice-matching-features"></a>TMS fuvarlevél- és számlaegyeztetési funkciói

A TMS egyeztetheti a becsült költségeket tartalmazó fuvarleveleket a fuvar tényleges költségét tartalmazó számlákkal. A számla elektronikus úton vagy nyomtatott papíron érkezhet. A becsült költség és a tényleges költség egyeztetési eltérése nem befolyásolja a készletértékelést.

A további tudnivalókat lásd: [Fuvar egyeztetése a szállításkezelésben](../transportation/reconcile-freight-transportation-management.md).

### <a name="landed-cost-bill-and-invoice-matching-features"></a>Partraszállítási költség fuvarlevél- és számlaegyeztetési funkciói

A Partraszállítási költség képes egyezteni a fuvarleveleket a becsült költségekkel, és számlázni a tényleges költségeket a becsült költségekhez. A számlázáskor a fuvardíj egy számlanaplóban van, és a becsült költségek törlődnek az elszámolószámláról. Ezenkívül a tényleges költségek feladása a cikkhez az eladott áruk beszerzési értékével szemben történik, a becsült költségek és a tényleges költségek közötti különbözetekkel együtt. Ez a viselkedés lehetővé teszi a számlázási folyamat rugalmasságát.

## <a name="tracking"></a>Nyomon követés

A TMS és a Partraszállítási költség fontos funkciója az áruk nyomon követésének lehetősége, és annak azonosítása, hogy hol vannak az úton a kiindulási ponttól a végső célraktárig. A nyomon követés segítségével nyomon követheti és frissítheti az áruk helyét, valamint azt, hogy várhatóan mikor érkeznek meg a raktárba felhasználásra. Az áruk állapota mellett az út során, a Partraszállítási költség az út minden egyes lépésének várható és tényleges dátumát biztosítja.

### <a name="tms-tracking-features"></a>TMS követési funkciói

A TMS korlátozott funkciókat biztosít a bejövő rakományok nyomon követéséhez. Dátumokat mutat, és lehetővé teszi az integráció kialakítását a pontos pozíciót megkereséséhez (például a **Szállítási állapot** oldalon).

Minden útvonalszakaszhoz megadhatja a becsült ütemezéseket és érkezési időket.

### <a name="landed-cost-tracking-features"></a>Partraszállítási költség követési funkciói

A Partraszállítási költség minden egyes hajóút nyomon követését biztosíthatja, a származási kikötőtől a végső célig. A követési ellenőrzés beállítja a hajóút állapotát. Az állapot azt jelzi, hogy a hajóút tengeren, vámellenőrzésen vagy helyi kiszállításon állapotban van-e a végső raktár felé. Az állapot a beszerzési rendelés sorának, a konténernek és a hajóút fejlécének szintjén állítható be. Így pontosabb az ellenőrzés.

Ezenkívül egy meghatározott átfutási időkön alapuló, visszaigazolt várható dátum is társítva van az uút egyes lépéseihez. A visszaigazolt és várható szállítási dátumokat hozzáadja a rendszer a beszerzési rendelés sorához és az úton lévő áruk rendelésekhez, és felhasználható az alaptervezés és a logisztika során. A várható dátumok mellett a tényleges dátumokat is frissíteni lehet. Az utazás további lépései ennek megfelelően frissülnek.

## <a name="multi-leg-journeys"></a>Több szakaszos utazások

Az út koncepciója azonosítja, hogy hol tartanak az áruk a folyamatban, és a szállítás közben szabályozza az áruk állapotát. Az áruk egy út több szakaszán is átmehetnek, és a különféle költségeket egy adott szakaszhoz lehet társítani. Ilyen költség lehet például egy hajó fuvarköltsége és a helyi szállítási költség az áruknak a kikötőtől a célig történő szállítása során.

### <a name="tms-multi-leg-journey-features"></a>TMS többszakaszos út funkciói

A TMS-ben az útvonalak útvonalszakaszokra bonthatók, így többszakaszos utakat képviselhetnek. A TMS az azonnali díjakat és a járulékos költségeket feloszthatja az egyes útvonalszakaszokra.

További információk: [Áruszállítási útvonalak tervezése több megállóval](../transportation/plan-freight-transportation-routes-multiple-stops.md).

### <a name="landed-cost-multi-leg-journey-features"></a>Partraszállítási költség többszakaszos út funkciói

A Partraszállítási költség keretként szolgál az áruk származási pontból a célhelyre történő átmozgatására egy sor útszakaszon, amelyek egy út megállói vagy lépései. A szakaszok kombinálásával útsablonok hozhatók létre, amelyek meghatározzák, hogyan haladnak az áruk a szállítótól a szervezete felé.

Az utak minden lépésében tovább lehet definiálni az egyes beszerzésirendelés-sorok állapotát, valamint a hozzájuk társított átfutási időket. Az összes szakasz kombinált átfutási ideje a becsült szállítási dátum azonosítására használható. A több szakaszos utak alkalmazásához úton lévő áruk feldolgozása szükséges. A hajóúton lévő áruk útja egy Partraszállítási költségre specifikus táblázatban kezelhető.

## <a name="receiving-by-container"></a>Bevételezés konténer szerint

Fontos lehet az áruk hajóra történő felosztásának és tárolásának kezelése. A hajón az áruk egy konténerben vagy több konténerben tarthatak. Az áruk bevételezésekor konténerekben kerülnek átvételre, és a hajóúton a különböző konténerek más-más időpontban vagy dátummal kerülhetnek bevételezésre.

Mind a TMS, mind a Partraszállítási költség biztosítja az áruk konténerekben történő bevételezését. A TMS a rakományok koncepcióját használja a szállítmány konténeréhez társított áruk, beszerzési rendelések és átszállítási rendelések kezelésére. A TMS lehetővé teszi a bevételezést egy olyan csomagolási szerkezet alapján, amely előzetes kiszállítási értesítésen (advance shipping notice – ASN) keresztül érkezik. A Partraszállítási költség a szállítókonténerek koncepcióját használja a beszerzési rendelések feldolgozására és a hajóra rakott konténerekhez kapcsolódó járulékos költségek szabályozására.

### <a name="tms-receiving-by-container-features"></a>TMS bevételezés konténer szerint funkciói

A TMS támogatja a bejövő ASN-eket, a Raktárkezelés mobilalkalmazáson keresztüli bevételezés összes változatát, valamint a Supply Chain Management ügyfélen keresztüli bevételezési módokat.

### <a name="landed-cost-receiving-by-container-features"></a>Partraszállítási költség bevételezés konténer szerint funkciói

A Partraszállítási költség a konténer szerinti bevételezés támogatása érdekében a szállítókonténer-rekordokat hoz létre, és a konténerazonosító alapján beszerzési rendeléseket társít egy adott szállítókonténerhez. Ezután a járulékos költségek alkalmazhatók a szállítókonténerre, és le lehet őket bontani, hogy a megfelelő beszerzési rendelésekhez legynek társítva.

A Partraszállítási költségben található konténerek bevételezése új típusú bevételezéssel, más *úton lévő áruk bevételezése* módszerrel, érkezési naplókkal vagy mobileszközös bevételezésen keresztül is történhet. Az érkezetési naplók használata esetén a mennyiségek inicializálhatók az úton lévő áruk rendeléséből vagy a konténer eredeti beszerzésirendelés-soraiból. A Partraszállítási költség két munkatípust biztosít a Raktárkezelés mobilalkalmazáson keresztüli bevételezéshez.

A Partraszállítási költség nem biztosít ASN-t az elektronikus árubevételezéshez. Ezenkívül nem támogatja a Raktárkezelés mobilalkalmazás folyamatait, amelyek a rakomány bevételezését, az azonosítótábla bevételezését vagy a vegyes azonosítótábla bevételezését dolgozzák fel.

## <a name="rate-shopping-by-vendor"></a>Díjkiválasztás szállító szerint

A díjkiválasztás lehetővé teszi a vállalat számára, hogy a legalacsonyabb ár, a leggyorsabb útvonal vagy mindkét szempont együttese alapján válasszon ki egy szállítót.

### <a name="tms-rate-shopping-features"></a>TMS díjkiválasztási funkciói

A TMS lehetővé teszi a bejövő és kimenő rendelések szállító- és útvonalmegoldásainak azonosítását. Például azonosíthatja a leggyorsabb vagy a legolcsóbb útvonalat a szállítmányhoz.

A TMS teljes díjkiválasztást és fuvaroptimalizálást biztosít a díjútvonal munkaterületen keresztül, rugalmas díjválasztási lehetőségeket a díjkalkulátorral, egy díjkalkulátor API-t a külső felekkel való integrációhoz, és támogatást a térfogattömeghez.

A további tudnivalókat lásd: [Szállításkezelési motorok](../transportation/transportation-management-engines.md).

### <a name="landed-cost-rate-shopping-features"></a>Partraszállítási költség díjkiválasztási funkciói

A Partraszállítási költség csak korlátozottan támogatja a szállítók szerinti díjkiválasztást. Annak ellenére, hogy beírhat fuvarozói értékeket, a Partraszállítási költség nem hasonlítja őket össze több szállítóval.

## <a name="driver-check-incheck-out-with-appointment-scheduling"></a>Gépjárművezetői be- és kijelentkezés találkozóütemezéssel

A gépjárművezetői be- és kijelentkezési funkciók segítségével a rendszer figyelni fogja az érkezéseket, és megakadályozza a feltorlódást a berakodási tárolókban.

### <a name="tms-driver-check-incheck-out-features"></a>TMS gépjárművezetői be- és kijelentkezés funkciói

A TMS lehetővé teszi *találkozók* létrehozását. A találkozók olyan események, amelyek például egy beszerzési rendelés bevételezésére szolgáló tárolóban, egy értékesítési rendelés kiszállításakor vagy kimenő és bejövő rakományok adott dátummal és adott időponttal való feldolgozása kapcsán merülnek fel. A találkozók biztosítják, hogy a tárolók rendelkezésre állnak az áruk be- és kirakodására, és segítik az olyan helyzetek megakadályozását, amikor egyszerre több szállítmányozó érkezik meg egy helyre.

A rendszer lehetővé teszi a járművezetők számára, hogy egy bizonyos tároló ajtajánál bejelentkezzenek.

### <a name="landed-cost-driver-check-incheck-out-features"></a>Partraszállítási költség gépjárművezetői be- és kijelentkezés funkciói

A Partraszállítási költség tárolhatja a konténer leszállításának dátumára és időpontjára vonatkozó becsléseket.

## <a name="transfer-orders-and-additional-costs"></a>Átszállítási rendelések és egyéb költségek

A vállalatoknak gyakran képesnek kell lenniük áruk raktárak közötti átszállítására. Ilyen típusú átszállítás esetén a költségek társítva vannak vele, és ezeket a költségeket érdemes lesz könyvelni. A Partraszállítási költségben az átmozgatási rendelések hozzáadhatók egy hajóúthoz vagy hajóhoz, hogy nyomon követhető legyen az áruk egyik raktárból vagy telephelyről a másikra történő szállítása, a szállítás ideje és a várható szállítási dátum becsülhető legyen, és járulékos költségeket lehessen hozzáadni az áruk átszállításához.

### <a name="tms-transfer-order-cost-features"></a>TMS átszállítási rendelés költsége funkciói

A TMS lehetővé teszi az átszállításokkal kapcsolatos fuvardíjak létrehozását. Bár ezek a költségek megtekinthetők az átszállítési rendelésből, a Partraszállítási költség nem lesz hozzáadva a cikk-költséghez. A fuvaregyeztetés az ezeken a költségeken alapuló fuvarlevél létrehozásával támogatott. Ez a fuvarlevél ezután egy szállítói fuvarszámlával szemben lesz egyeztetve.

### <a name="landed-cost-transfer-order-cost-features"></a>Partraszállítási költség átszállítási rendelés költsége funkciói

A Partraszállítási költség segítségével hozzáadhatók átszállítási rendelések egy a hajóhoz vagy hajóúthoz. Ily módon az hajóúthoz szállítási költségeket lehet hozzáadni készletelszámolásként az átszállítási rendelés bevételezésekor. A járulékos költségek számlázhatók a tényleges költségek esetében, és a hajóút alapján nyomon követhetők az eladott áruk beszerzési értékének frissítése érdekében. Bár az átszállítási rendelések nem használják az úton lévő áruk feldolgozását a standard kiadásban, hozzáadhatók a hajóúthoz. A Partraszállítási költség minden cikk összköltségéhez hozzáadásra kerül.