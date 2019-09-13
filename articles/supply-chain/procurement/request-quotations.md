---
title: Ajánlatkérések (RFQ-k) áttekintése
description: Ez a témakör áttekintést nyújt az ajánlatkérésekről (RFQ-król). Egy szervezet akkor ad ki ajánlatkérést (RFQ-t), amikor cikkeket és szolgáltatásokat szeretne beszerezni, és ehhez egymással versenyző különböző szállítóktól kér ajánlatokat.
author: mkirknel
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e2276f5296a77d620e0084c0247b1e25071fe029
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865280"
---
# <a name="requests-for-quotation-rfqs-overview"></a>Ajánlatkérések (RFQ-k) áttekintése

[!include [banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt az ajánlatkérésekről (RFQ-król). Egy szervezet akkor ad ki ajánlatkérést (RFQ-t), amikor cikkeket és szolgáltatásokat szeretne beszerezni, és ehhez egymással versenyző különböző szállítóktól kér ajánlatokat. Az ajánlatkérésben arra kéri a szállítókat, hogy adják meg a meghatározott számú cikkekhez ajánlott áraikat és szállítási idejüket.
Emellett kérheti a szállítóktól annak meghatározását, hogy vannak-e egyéb járulékos költségek, például szállítási költséget, illetve kínálnak-e nagyobb rendelések vagy a szállítói számla korai kifizetése esetén engedményeket.

Az ajánlatkérés folyamata a következő feladatokból áll:

1.  Ajánlatkérés létrehozása és küldése egy vagy több szállítónak.

2.  Ajánlatok (ajánlatkérési válaszok) fogadása és rögzítése.

3.  Az Ön által elfogadott ajánlatok átvitele beszerzési rendeléshez, beszerzési szerződéshez vagy beszerzési igényléshez.

A következő ábrán látható az ajánlatkérési folyamat.

[![RFQ-folyamat](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

Ajánlatkérési esetet tervezett rendelésekből, beszerzési igénylésből és manuális bevitelből is létrehozhat. Az ajánlatkérési eset az az alapdokumentum, amelynek segítségével ajánlatkérést küld az egyes szállítóknak.+

Miután előkészítette az ajánlatkérési esetet és hozzáadta a szállítókat, válassza a **Küldés** (**Küldés és közzététel** az állami szektor esetében) lehetőséget az ajánlatkérési esetnél. Ajánlatkérési napló jön létre minden egyes olyan szállítóra vonatkozóan, amelyek számára elküldte az ajánlatkérést. A Küldés művelet nyomtatási beállításait módosítva megadhatja, hogy a rendszer külön jelentést nyomtasson minden szállítóhoz az archívumba, vagy a jelentést e-mailben küldje a szállítók e-mail-címére. Ezenkívül az egyes szállítók ajánlatkérési naplóját olyan napló létrehozására is felhasználhatja, amelyet később elküldhet vagy újraküldhet a szállítónak. A Küldés műveletet úgy is beállíthatja, hogy a rendszer a szállító által kitölthető válaszlapot is generáljon.

Ez a témakör az ajénlatkérések kezelését foglalja össze arra az esetre, amikor a szállítói együttműködés nincs használatban. Ha a rendszer be van állítva szállítói együttműködéshez a szállítók közvetlenül vihetnek be ajánlatokat a Microsoft Dynamics 365 for Finance and Operations rendszerbe. További tudnivalók: [Szállítói együttműködés a vevőkkel](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations) és [A külső szállítókkal történő szállítói együttműködés](vendor-collaboration-work-external-vendors.md).

Ha módosítania kell az ajánlatkérést, miután elküldte azt, újra elküldheti az ajánlatkérést a szállítóknak, ha elkészült a két módosítási művelettel: ezek a Létrehozás és a Véglegesítés.+

Ha e-mailben kap ajánlatokat, az **Ajánlatkérés** oldalon kezelheti őket.

Ha egy szállító által küldött válasz esetében második ismétlésre is szüksége van, válassza a **Vissza** lehetőséget az **Ajánlatkérés** oldalon. A Vissza művelet új naplót és egy jelentést hoz létre, amelyet a rendszer a nyomtatási beállításoktól függően kinyomtat, archivál és elküld.

> [!NOTE]
> Az **Ajánlatkérés** oldal neve módosult. A Dynamics 365 for Finance and Operations korábbi változataiban ezen oldal neve **Ajánlatkérésekre adott válasz** volt.

Ha pontozási feltételeket adott hozzá az ajánlatkérési esethez, az ajánlatkérés egy pontozási panelt is tartalmaz, amelyen megadhatja a pontokat. Az összesített pontszámok megjelennek az ajánlatkérésen, valamint ha összehasonlítja a válaszokat a **Válaszok összehasonlítása** oldalon. A **Válaszok összehasonlítása** oldalon összehasonlíthatja a többi válaszadatot is, például a sorárakat, a szállítási dátumot és a teljes árat.

Miután kiválasztott egy ajánlatot vagy néhány sort egy ajánlatban, elfogadhatja az összes vagy néhány sort, és elutasíthatja a többit. Az elfogadási naplók, elutasítási naplók és a kapcsolódó jelentések létrejönnek, amelyeket a rendszer a nyomtatási beállításoktól függően kinyomtat, archivál és elküld. Egy ajánlat vagy bizonyos ajánlati sorok elfogadásakor az ajánlatkérés beszerzés típusától függően egy beszerzési szerződés vagy beszerzési rendelés jön létre, vagy frissül a beszerzési igénylés. Létrehozhat kereskedelmi megállapodást, amelyet később bármelyik válasz esetében felhasználhat, függetlenül attól, hogy azt elfogadta vagy elutasította.

Az ajánlatkérési eset két állapottal rendelkezik: legalacsonyabb és legmagasabb állapot. Az állapotot **Az összes ajánlatkérés** listalapon tekintheti meg. Legalacsonyabb állapota az ajánlatkérési eset minden sorban a legkevésbé készültségi foka, és a lehető legnagyobb készültségi foka minden olyan sor, az ajánlatkérési eset legmagasabb állapota. Tegyük fel, hogy egy három sorral rendelkező ajánlatkérési esetet két szállítónak küldenek el, így két ajánlatkérés van, egyenként három sorral. Minden sor **Elküldve** állapotú. Az egyik szállító ajánlatot ír be, és az ajánlatkérés sorai **Beérkezett** állapotúak lesznek. Ez azt jelenti, hogy az ajánlatkérési eseten három sorából mindegyik **Elküldve** állapotú egy ajánlatkérés esetében, és **Beérkezett** egy másik ajánlatkérés esetében. A legalacsonyabb állapot **Elküldve**, a legmagasabb állapot pedig **Beérkezett** értékű lesz.

Az ilyen állapotokról részletesen a jelen témakör későbbi szakaszaiban olvashat.

## <a name="setting-up-rfq-functionality"></a>Ajánlatkérési funkció beállítása

Az ajánlatkérési eset létrehozása előtt be kell állítania az ajánlatkérési információt a **Beszerzési és forrásparaméterek** oldalon. Az ajánlatkérési eset létrehozásakor megadhat alapértelmezett értékeket, amelyek aztán átkerülnek az ajánlatkérésre. Az alábbi alapértelmezett értékeket határozhatja meg:

-   Az új ajánlatkérések beszerzési típusa: **Beszerzési rendelés** vagy **beszerzési szerződés**

-   A lejárati dátum és időpont eltolása az ajánlatkérési eset létrehozásától kezdve

-   Meghirdetési típus, amely alapértelmezett pontozási módszert kapcsolhat az ajánlatkérési esethez

-   Szállítási adatok és fizetési feltételek

-   Mezők, amelyeknek szerepelnie kell az ajánlatban

Egy konkrét ajánlatkérési esetnél felülírhatja ezeket az értékeket.

A módosítási folyamatot és érdemes beállítani. A konfiguráció részeként a mezők zárolását is beállíthatja. Ha bekapcsolja a mezők zárolását, és egy beszerző módosítani szeretné az ajánlatkérést, először válassza az **Árajánlat** fül **Módosítás** szakaszában a **Létrehozás** lehetőséget az ajánlatkérési esetben. Majd miután frissítette az ajánlatkérési esetet a módosítással, a beszerzési szakértőnek kell befejeznie a folyamatot a **Véglegesítés** pont kiválasztásával. A Véglegesítés művelet e-mailt hoz létre, amely értesíti a szállítókat a módosított ajánlatkérésről.

A szállítóknak elküldött e-mailes értesítés sablonját a **Beszerzési és forrásparaméterek** oldalon választhatja ki. Az **E-mail sablonok** pontban létrehozott sablon az alábbi helyettesítő tokeneket tartalmazhatja:

-   %RFQ case%

-   %Ajánlat visszaküldésének oka%

-   %Módosítás oka%

-   %A módosítást készítette%

-   %Vállalat%

-   %RFQ case name%

-   %Expiry Date Time%

-   %Date%

Az %Ajánlat visszaküldésének oka% és %Módosítás oka% tokeneket a rendszer olyan szöveggel helyettesíti, amelyet a beszerző adhat meg a **Módosítás** varázslóban elvégzett módosítások befejezésével. Az %A módosítást készítette% és %Vállalat% tokeneket a rendszer automatikusan az árajánlatkérés alapján tölti ki. A %Date% token helyére az aktuális dátum kerül.

Ha vissza szeretne vonni egy ajánlatkérést az elküldés után, ezt az ajánlatkérési esetben teheti meg. A visszavonáshoz egy e-mail sablon szükséges, amellyel elküldheti az érvénytelenítési értesítést a szállítói kapcsolattartóknak. A sablont ki kell jelölni a **Beszerzési és forrásparaméterek** lapon. A létrehozott sablon az alábbi helyettesítő tokeneket tartalmazhatja:

-   %Reason for cancellation%

-   %RFQ case%

-   %RFQ cancelled by%

-   %Vállalat%

-   %RFQ case name%

-   %Date%

A %Reason for cancellation% token helyére az a szöveg kerül, amelyet a beszerző adhat meg az **Érvénytelenítés** varázslóban. A %Date% token helyére az aktuális dátum kerül.

Ha az ajánlatban okkódot kíván használni az ajánlat elfogadásának vagy elutasításának okához, az okkódokat a **Szállítói okok** oldalon állíthatja be.

A nyomtatott vagy tárolt ajánlatkérési dokumentumok megjelenését a Beszerzés és forrás menü **Képernyő-beállítás** oldalán állíthatja be.

> [!NOTE]
> A közszféra beállításainál a már elküldött ajánlatkérés módosításához a javítási folyamat használata szükséges. Az ajánlatkérés elküldésekor a mezők zárolva lesznek.
Ennek megfelelően az ajánlatkérés módosításához ki kell jelölnie a **Létrehozás** lehetőséget a módosítási folyamat megkezdéséhez a fentebb leírt módon. A zárolási viselkedést az **Ajánlatkérések zárolása kiküldés után** lehetőség irányítja a **Beszerzési és forrásparaméterek** lapon. A paraméter értéke alapértelmezetten **Igen**, és a közszféra konfigurációjánál ez egy olyan alapérték, amelyet nem lehet megváltoztatni. Ezért, bár a módosítási eljárást manuálisan is lehet kezelni egy nem állami szektorbeli konfigurációban, azt használni kell az állami szektorbeli konfigurációknál.

Beszerzési rendelési típushoz tartozó ajánlatkérési eset létrehozásakor és egy készletcikk ajánlatkéréshez történő rendelésekor egy készlettranzakció is létrehozásra kerül **Árajánlat-bevételezés** bevételezési állapottal. Csak az ilyen típusú ajánlatkérési esetek sorainak állapota lesz figyelembe véve, ha az alapterv segítségével számolja a cikkeket. Ha azt szeretné, hogy az alapterv várható bevételezésként tartalmazza az ajánlatkérési eset sorait, ezt a viselkedést az alapterv beállításai között konfigurálnia kell.

Beszerzési vezetőként vagy ügynökként létrehozhatja, és karbantarthatja az ajánlatkérési típusokat, hogy megfeleljenek szervezete beszerzési követelményeinek. A meghirdetési típusok mindegyike társítható egy pontozási módszerrel. A pontozási módszerek olyan feltételeket tartalmaznak, amelyeket az ajánlatok pontozásához használhat. Be kell állítania a meghirdetési típusokat, pontozási módszereket és pontozási feltételeket a **Meghirdetés típusa** és **Pontozási módszer** oldalon.

## <a name="creating-and-sending-an-rfq"></a>Létrehozása és egy Ajánlatkérés küldése

Hozza létre az ajánlatkérési esetet, válassza ki az ajánlatkérési esethez kívánt szállítókat, majd küldje ki nekik az ajánlatkérést. A nyomtatási beállítások segítségével csatolhatja az ajánlatkérési jelentést és a válaszlapjelentéseket a kívánt célhoz.

Manuálisan létrehozhat ajánlatkérést a **Beszerzési rendelés** vagy **Beszerzési szerződés** beszerzési típushoz.

Ha az Ajánlatkérési eset **Beszerzési rendelés** típusú, a következő történik, amely eltér a más típusú ajánlatkérési esetektől:

-   Az ajánlatkérési esetek sorainak létrehozásakor olyan készlettranzakciók létrehozása történik, amelyek bevételezési állapota **Árajánlat-bevételezés**.

-   Egy ajánlat elfogadásakor létrejön egy beszerzési rendelés.

Ha az Ajánlatkérési eset **Beszerzési szerződés** típusú, a következő történik, amely eltér a többi ajánlatkérési esettől:

-   Az ajánlatkérési eset felhasználásra kerül egy megállapodáshoz adott mennyiségű vagy értékű termék vásárlásáról hosszabb idő alatt. Ki kell jelölnie a beszerzési megállapodásra vonatkozó dátumtartományt, illetve a beszerzési megállapodást kezelő személy nevét.

-   Egy ajánlat elfogadásakor létrejön egy beszerzési szerződés.

Ha az ajánlatkérési eset létrehozása beszerzési igénylésből történik, a **Beszerzési igénylés** típust a rendszer automatikusan hozzárendeli. Manuálisan nem hozhat létre **Beszerzési igénylés** típusú ajánlatkérési esetet.

Csak akkor hozhat létre ajánlatkérési esetet egy beszerzési igénylésből, ha a beszerzési igénylés állapota **Ellenőrzés alatt**, és Ön van hozzárendelve a munkafolyamat következő feladatához. A beszerzési igénylés sorainak frissítése automatikusan történik, amikor elfogadja a szállítóktól kapott ajánlatok (ajánlatkérési válaszok) sorait. Nem hajthat végre, nem utasíthat el, nem hagyhat jóvá és nem végezhet el semmilyen más műveletet a beszerzési igénylésen addig, amíg az igénylési sor az elfogadott ajánlatkérési sorral nem frissül vagy amíg az ajánlatkérési esetet nem érvényteleníti.

Az ajánlatkérési eset létrehozásakor kiválaszthat egy meghirdetési típust. A meghirdetési típus az ajánlatkérési esetre érkező ajánlatkérési válaszok pontozási feltételét határozza meg.

Az ajánlatkérési esethez hozzáadhat kérdőívet. Ez a kérdőív az ajánlatkérés elküldését követően minden ajánlatkérési válaszon megjelenik. A kérdőív kitöltése kötelező az ajánlat elküldése előtt.


Háromféleképp választhatja ki az ajánlatkérési esethez hozzáadni kívánt szállítókat:

- Egyesével hozzáadhatja a szállítókat.
- Megkeresheti az adott feltételnek megfelelő szállítókat.
- Automatikusan hozzáadhat minden, az ajánlatkérési esetek soraihoz használt beszerzési kategóriákban jóváhagyott szállítót.

Ha az ajánlatkérési eset elkészült, válassza a **Küldés** lehetőséget. A Küldés művelet naplókat és egy jelentéseket hoz létre, amelyeket a rendszer a nyomtatási beállításoktól függően kinyomtat, archivál és elküld.

Ha az **Az ajánlatkérés elküldése** oldalon a **Szállító használata az árak újraszámításához** és a **Szállítófüggő cikkadatok használata** beállításoknál az **Igen** lehetőséget választja az ajánlatkérés szállítónak történő elküldésekor, egyes szállítóspecifikus információkat a rendszer automatikusan kitölt az ajánlatkérésben.


## <a name="amending-an-rfq-case"></a>Ajánlatkérési eset módosítása

Időnként előfordulhat, hogy elküldés után módosítani kell egy ajánlatkérési esetet. Előfordulhat, hogy módosítania kell egy ajánlatkérési esetet például akkor, ha a szállítási dátum megváltozott, vagy további termékeket, esetleg módosított mennyiségeket szeretne hozzáadni. A módosítási folyamatot beállíthatja kevésbé vagy jobban korlátozóra is.

Ha a módosítási folyamatot úgy állítja be, hogy szigorúbb legyen, akkor ahhoz, hogy módosíthassa egy már elküldött ajánlatkérési eset mezőit, először ki kell választania a **Létrehozás** lehetőséget az ajánlatkérési esetnél a módosítás megkezdéséhez. A módosítások befejezését követően válassza a **Véglegesítés** lehetőséget. A rendszer ezt követően végigvezeti a folyamaton, amelyben további információkat adhat hozzá a módosításról tájékoztató e-mailhez, amelyet a szállítók is megkapnak. A frissített ajánlatkérési jelentés, amely tartalmazza a módosítási megjegyzést, automatikusan csatolva lesz az e-mailhez.

A kevésbé korlátozó módosítási folyamat konfigurálása esetén a már elküldött ajánlatkérési eset mezőinek módosítása előtt nem szükséges a **Létrehozás** lehetőséget kiválasztani a módosításhoz. Azonban manuálisan hozzá kell adnia egy módosítási megjegyzést az ajánlatkéréshez, és újra be kell küldenie az esetet. Ne feledje, hogy ez a módszer csak akkor használható, ha egyik válasz (ajánlat) sem módosult. Ha megadott egy választ, és az **Beérkezett** állapotú, akkor a **Küldés** gomb nem érhető el. Ebben az esetben ki kell választania a **Létrehozás**, majd a **Véglegesítés** elemet, ahogyan az a korlátozóbb folyamatban elvárt. A válasz ekkor visszaáll, és megjeleníti az ajánlatkérési eset módosításait.

Ha a szállítók a szállítói együttműködési felületet használják az ajánlatok beadására, mindig a módosítási folyamatot kell használnia ahhoz, hogy értesítse a szállítókat az ajánlatkérési esetben bekövetkezett változásokról. Ez a folyamat segít megelőzni azt a helyzetet, amikor a szállítók lejárt ajánlatkérési ügyben tesznek ajánlatot, miközben az ajánlatuk folyamatban van. Az új szállítói együttműködéssel kapcsolatos további tudnivalókat lásd: [A szállítói együttműködés a külső szállítókkal való együttműködésre történő használata](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-external-vendors).

Ha szeretne meghívni további szállítókat is az ajánlatkérésre, és nem hajtott végre módosítást az ajánlatkérési eseten, akkor használhatja a **Küldés** gombot. Az Ön által felvett szállítók megjelennek a **Küldés** lapon, és megkapják az e-mailes meghívót.


## <a name="receiving-and-registering-rfq-replies"></a>Az ajánlatkérésre érkezett válaszok érkeztetése és rögzítése

Ajánlatkérés küldésekor automatikusan létrejön egy válaszlap. Amikor ajánlatokat kap az ajánlatkérésre, meg kell adnia azokat az **Ajánlatkérés** lapon az **Ajánlatkérésre adott válasz szerkesztése** műveletre kattintva. Ennek segítségével egy külön ajánlatkérési képernyőn adhatja meg az ajánlattal kapcsolatos adatokat. Első lépésként a **Válasz állapota** **Nincs elindítva** lesz. Amikor rákattint az **Ajánlatkérésre adott válasz szerkesztése** lehetőségre, a folyamat állapota **Vevő általi frissítés** lesz mindaddig, amíg az ajánlatot el nem küldi. Kattintson a **Küldés** lehetőségre, miután beírta az ajánlattal kapcsolatos adatokat. A Válasz állapota **Vevő által elküldött** állapotúra módosul. Ehhez hasonlóan a szállító együttműködés engedélyezése esetén a **Válasz állapota** annak megfelelően frissül, hogy milyen módosításokat hajtott végre a szállító az ajánlatban. Az állapot ekkor **A szállító frissítést végez** állapotról **Szállító által elküldve** állapotra módosul. Az ajánlat elküldésekor egy napló jön létre **Beérkezett** névvel. A választ (ajánlatot) el kell küldeni annak érdekében, hogy a beérkezettként regisztrálja a rendszer, és csak ezután dolgozható fel tovább elfogadottként vagy elutasítottként.

Ha frissíteni szeretné az ajánlatot, végezze el újból a fenti eljárást, és küldje el ismét az ajánlatot.

Ne feledje, hogy az **Ajánlatkérés** képernyőn csak olyan adatok megadása engedélyezett, amelyek az ajánlat feldolgozásához kapcsolódnak, nem pedig az ajánlattételhez. Az ajánlattételhez vagy az ajánlat módosításához kattintson az **Ajánlatkérésre adott válasz szerkesztése** lehetőségre.

Az ajánlat adatainak megadásakor – amennyiben az Ajánlatkérési eset lehetővé teszi – alternatívasorokat adhat hozzá azon sorokhoz, amelyek csak egy beszerzési kategóriával rendelkeznek, és nem tartozik hozzájuk katalóguscikk. Kattintson az **Alternatíva hozzáadása** lehetőségre alternatívasorok felvételéhez.

Ha megadott választ, de új ajánlatra van szükség a szállítótól, visszaküldheti az ajánlatkérést. A rendszer egy új naplót és egy új jelentést hoz létre, amelyeket elküldhet a szállítónak.

Az **Árajánlatkérések követése** oldalon áttekintheti az összes ajánlatkérést és a hozzájuk tartozó válaszok állapotát: **Elküldve, Beérkezett, Jóváhagyva, Elutasítva, Visszavonva, Visszautasítva**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Ajánlatok elfogadása és elutasítása, valamint az elfogadott ajánlatok átvitele a feldolgozott dokumentumokhoz

A legjobb, például legkedvezőbb árat nyújtó ajánlat azonosítása után elfogadhatja az ajánlatot. Egy ajánlat egyes sorait elfogadhatja, miközben másokat visszautasít.
Elfogadhatja különböző szállítók egyes sorait is. Kérjük, ügyeljen arra, hogy bizonyos sorok elfogadásakor minden más sort vissza kell utasítania. Ezért ha más sorokat is el akar fogadni, először az utasítás megjelenésekor az **Érvénytelenít** lehetőséget kell választania. Az ajánlatkérésre adott válasz állapota minden olyan szállítónál, akiknek ajánlatait vagy sorait elfogadja, frissül **Elfogadott** értékre.

Amennyiben a beszerzési rendelés vagy a beszerzési szerződés előkészítése során további sort kell hozzáadnia az ajánlatkéréshez, ezt elvégezheti a **Sor hozzáadása** lehetőségre kattintva az **Ajánlatkérés** lap sorrácsában. Ezt a sort csak megtekintheti és szerkesztheti az **ajánlatkérés** oldalon. A sor az elfogadás után válik láthatóvá az ajánlatkérési oldalon.

Ha elfogad egy ajánlatot vagy egy ajánlat egy vagy több sorát, a rendszer automatikusan egy beszerzési rendelést vagy egy beszerzési szerződést hoz létre. Ezt követően visszautasíthatja az összes többi szállítótól származó minden ajánlatot.

A válaszban hozzáadhat okkódot, amelyben megmagyarázza az elfogadás vagy elutasítás okát.

Amikor **Beszerzési igénylés** típusú ajánlatot fogad el, a rendszer frissíti a beszerzési igénylési sorokat azokkal az adatokkal, amelyek tükrözik az elfogadott ajánlat adatait:

-   Egységár

-   Engedmény százaléka

-   Engedmény összege

-   Beszerzés költségei

-   Sorköltségek

-   Szállító

-  Külső szám

-   Külső leírás


Az alábbi táblázat bemutatja, hogyan változik az ajánlatkérési állapot, ha elfogadja vagy visszautasítja egy szállító ajánlatát.

<a name="statuses--highest-and-lowest"></a>Állapotok – legalacsonyabb és legmagasabb
-----------------------------

Az ajánlatkérési eset Szállító lapján megtekintheti a legmagasabb és legalacsonyabb állapotú sorokat egy adott szállítóhoz kapcsolódóan. Ha hozzáad egy szállítót, és még egyetlen sort sem küldött el, a legalacsonyabb és legmagasabb állapot is <strong>Létrehozva</strong> lesz. Amikor az ajánlatkérést minden sorral elküldi a szállítónak, a két sor állapota <strong>Elküldött</strong> lesz. Amennyiben egy szállítói ajánlat bizonyos sorait elfogadja, és másokat elutasít, az elutasított sorok kapják a legalacsonyabb állapotot (<strong>Elutasítva</strong>), az elfogadott sorok pedig a legmagasabb állapotot (<strong>Elfogadva</strong>).

Az ajánlatkérési eset soraiban megtekintheti a legmagasabb és legalacsonyabb állapotot soronként az összes szállítóra lebontva. Amennyiben az ajánlatkérési esetben szereplő minden szállítónak egy sort küldött el, és még senki sem választ, a legalacsonyabb és a legmagasabb állapot is **Elküldve** lesz. Ha legalább egy szállító válaszol, a legmagasabb állapot **Beérkezett** állapotra módosul. Ha az esethez új szállítót ad hozzá, a legalacsonyabb állapot **Létrehozva** lesz.

Az ajánlatkérési eset legmagasabb és legalacsonyabb állapota a \<Szállító és a Sorok lap állapotának összesítése.

Az állapotokat a rendszer a legalacsonyabbtól a legmagasabbig rangsorolja a következő módon: Létrehozva, Elküldve, Beérkezett, Jóváhagyva, Elutasítva, Visszavonva.

Az alábbi táblázat bemutatja, hogy változik az ajánlatkérési eset állapota, ha az ajánlatkérési esetet sorokkal hozza létre, majd elküldi a szállítóknak.

| **Művelet**                                | **Legalacsonyabb ajánlatkérési eset állapota** | **Legmagasabb ajánlatkérési eset állapota** | **Legalacsonyabb ajánlatkérési eset sorának állapota** | **Legmagasabb ajánlatkérési eset sorának állapota** |
|-------------------------------------------|----------------------------|-----------------------------|---------------------------------|----------------------------------|
| Az ajánlatkérési eset fejlécének és adatsorának létrehozása      | Létrehozva                    | Létrehozva                     | Létrehozva                         | Létrehozva                          |
| Ajánlatkérések küldése az ajánlatkérési esetben található az összes szállítónak. | Elküldve                       | Elküldve                        | Elküldve                            | Elküldve                             |
| További szállító hozzáadása.                       | Létrehozva                    | Elküldve                        | Létrehozva                         | Elküldve                             |
| Az Ajánlatkérés elküldése a második szállítónak.        | Elküldve                       | Elküldve                        | Elküldve                            | Elküldve                             |

Az ajánlatkérési esethez kapcsolódó összes ajánlatkérési sor **Elküldve** állapotú lesz.

Az alábbi táblázat bemutatja, hogyan változik az ajánlatkérési állapot az ajánlatok beérkezésekor, miután rögzítette az információkat az ajánlatkérési válaszlapon.

| **Művelet**                                               | **Legalacsonyabb állapot az összes ajánlatkérés összes sora közül** | **Legmagasabb állapot az összes ajánlatkérés összes sora közül** | **Ajánlatkérési eset legalacsonyabb állapotú fejléce** | **Ajánlatkérési eset legmagasabb állapotú fejléce** | **Legalacsonyabb ajánlatkérési eset sorának állapota** | **Legmagasabb ajánlatkérési eset sorának állapota** |
|----------------------------------------------------------|------------------------------------------------|-------------------------------------------------|-----------------------------------|------------------------------------|---------------------------------|----------------------------------|
| Egy szállító ajánlatának regisztrálása egy ajánlatkérési esethez, majd mentés.        | Elküldve                                           | Fogadott                                        | Elküldve                              | Fogadott                           | Elküldve                            | Fogadott                         |
| A második szállító ajánlatának regisztrálása egy ajánlatkérési esethez, majd mentés. | Fogadott                                       | Fogadott                                        | Fogadott                          | Fogadott                           | Fogadott                        | Fogadott                         |


Az alábbi példában látható a legmagasabb és legalacsonyabb állapot az ajánlatkérési eseten, ahova egy ajánlat megérkezett, és a másik ajánlatot fogadták el. Beérkezett ajánlat elutasításakor a legalacsonyabb állapot beérkezettről elutasított állapotra módosul az ajánlatkérési eset fejlécében és sorában.


|            <strong>Művelet</strong>             | <strong>Legalacsonyabb állapot az összes ajánlatkérés összes sora közül</strong> | <strong>Legmagasabb állapot az összes ajánlatkérés összes sora közül</strong> | <strong>Ajánlatkérési eset legalacsonyabb állapotú fejléce</strong> | <strong>Ajánlatkérési eset legmagasabb állapotú fejléce</strong> | <strong>Legalacsonyabb ajánlatkérési eset sorának állapota</strong> | <strong>Legmagasabb ajánlatkérési eset sorának állapota</strong> |
|------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------------|------------------------------------------------|-------------------------------------------------|----------------------------------------------|-----------------------------------------------|
| Az ajánlatok fogadása (vagy legalább egy sor) |                          Fogadott                           |                           Elfogadva                           |                    Fogadott                    |                    Elfogadva                     |                   Fogadott                   |                   Elfogadva                    |
|           Az összes többi ajánlat elutasítása.           |                          Elutasítva                           |                           Elfogadva                           |                    Elutasítva                    |                    Elfogadva                     |                   Elutasítva                   |                   Elfogadva                    |

