---
title: "Ajánlatkérések (RFQ-k)"
description: "Ez a témakör áttekintést nyújt az ajánlatkérésekről (RFQ-król). Egy szervezet akkor ad ki ajánlatkérést (RFQ-t), amikor cikkeket és szolgáltatásokat szeretne beszerezni, és ehhez egymással versenyző különböző szállítóktól kér ajánlatokat."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: 42ab7beb8a269cd37fd9100385bd302e4945c1e0
ms.contentlocale: hu-hu
ms.lasthandoff: 12/14/2017

---

# <a name="requests-for-quotation-rfqs"></a>Ajánlatkérések (RFQ-k)

[!include[banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt az ajánlatkérésekről (RFQ-król). Egy szervezet akkor ad ki ajánlatkérést (RFQ-t), amikor cikkeket és szolgáltatásokat szeretne beszerezni, és ehhez egymással versenyző különböző szállítóktól kér ajánlatokat. Az ajánlatkérésben arra kéri a szállítókat, hogy adják meg a meghatározott számú cikkekhez ajánlott áraikat és szállítási idejüket. Emellett kérheti a szállítóktól annak meghatározását, hogy vannak-e egyéb járulékos költségek, például szállítási költséget, illetve kínálnak-e nagyobb rendelések vagy a szállítói számla korai kifizetése esetén engedményeket.

Az ajánlatkérés folyamata a következő feladatokból áll:

1. Ajánlatkérés létrehozása és küldése egy vagy több szállítónak.
2. Ajánlatkérési válaszok (ajánlatok) fogadása és rögzítése.
3. Az Ön által elfogadott ajánlatok átvitele beszerzési rendeléshez, beszerzési szerződéshez vagy beszerzési igényléshez.

A következő ábrán látható az ajánlatkérési folyamat.

[![RFQ-folyamat](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

Ajánlatkérést tervezett rendelésekből, beszerzési igénylésből és manuális bevitelből is létrehozhat. A létrehozott ajánlatkérés neve ajánlatkérési eset. Az ajánlatkérési eset az az alapdokumentum, amelynek segítségével ajánlatkérést küld az egyes szállítóknak.

Miután létrehozta az RFQ-esetet, és megadta a szállítókat, válassza ki a **Küldés** lehetőséget az RFQ-esetnél. Ajánlatkérési napló jön létre minden egyes olyan szállítóra vonatkozóan, amelyek számára elküldte az ajánlatkérést. A Küldés művelet nyomtatáskezelési beállításait módosítva megadhatja, hogy a rendszer külön jelentést nyomtasson minden szállítóhoz az archívumba, vagy a jelentést e-mailben küldje a szállítók e-mail-címére. Ezenkívül az egyes szállítók ajánlatkérési naplóját olyan napló létrehozására is felhasználhatja, amelyet később elküldhet vagy újraküldhet a szállítónak. A Küldés műveletet úgy is beállíthatja, hogy a rendszer a szállító által kitölthető válaszlapot is generáljon.

Ez a témakör az ajénlatkérések kezelését foglalja össze arra az esetre, amikor a szállítói együttműködés nincs használatban. Ha a rendszer a szállítói együttműködésre van beállítva, az ajánlatok közvetlenül a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition felületén adhatók meg. További tájékoztatás: [A vevőkkel történő szállítói együttműködés](vendor-collaboration-work-customers-dynamics-365-operations.md).
 
Ha módosítania kell az ajánlatkérést, miután elküldte azt, újra elküldheti az ajánlatkérést a szállítóknak, ha elkészült a két módosítási művelettel: ezek a Létrehozás és a Véglegesítés.

Ha ajánlatokat kap e-mailen, azokat az **Ajánlatkérési válaszok** oldalon adhatja meg. Ha az **Adatok másolása a válaszba** lehetőséget választja, a mennyiséget és az ajánlatkérés egyéb adatait a rendszer a válaszba másolja. Módosíthatja ezeket az adatokat, hogy azok a szállító ajánlatát tükrözzék.

Ha egy szállítónak a válasz második ismétlésére is szüksége van, válassza a **Vissza** lehetőséget az **Ajánlatkérési válasz** oldalon. A Vissza művelet új naplót és egy jelentést hoz létre, amelyet a rendszer a Nyomtatáskezelés beállításaitól függően kinyomtat, archivál és elküld.

Ha pontozási feltételeket adott hozzá az ajánlatkérési esethez, az ajánlatkérési válasz egy pontozási panelt is tartalmaz, amelyen a pontok megadhatók. Az összesített pontszámok akkor jelennek meg, ha összehasonlítja a válaszokat a **Válaszok összehasonlítása** oldalon. Ezen az oldalon összehasonlíthatja a többi válaszadatot is, például a sorárakat, a szállítási dátumot és a teljes árat.

Ha egy ajánlattal vagy részleges ajánlattal kapcsolatban választott, elfogadhatja azt, és visszautasíthatja a többit. Az elfogadási naplók, elutasítási naplók és a kapcsolódó jelentések létrejönnek, amelyeket a rendszer a nyomtatáskezelési beállításoktól függően kinyomtat, archivál és elküld. Egy ajánlat vagy bizonyos ajánlati sorok elfogadásakor az ajánlatkérés beszerzés típusától függően egy beszerzési szerződés vagy beszerzési rendelés jön létre, vagy frissül a beszerzési igénylés. Létrehozhat kereskedelmi megállapodást, amelyet később bármelyik válasz esetében felhasználhat, függetlenül attól, hogy azt elfogadta vagy elutasította.

Az ajánlatkérés állapota megjelenik az ajánlatkérés fejlécében, és az ajánlatkérési sorok állapotától függ. Az állapot azt jelzi, hogy milyen mértékben dolgozta fel az ajánlatkérést. Az ajánlatkérési állapotok két értékkel rendelkeznek: legalacsonyabb és legmagasabb. Legalacsonyabb állapota az ajánlatkérés minden sorban a legkevésbé készültségi foka, és a lehető legnagyobb készültségi foka minden olyan sor, az ajánlatkérés legmagasabb állapota. Például ha legalább speciális állomása egy ajánlatkérési sorhoz korábban létrehozott tartozik, az ajánlatkérés legalacsonyabb állapota **Létrehozott**. Ha az Ajánlatkérés legmagasabb szintű állomása sor el lett küldve a szállítókhoz, van-e az ajánlatkérés legmagasabb állapota **Elküldött**. Az Ajánlatkérés dolgozza fel az állapotokat automatikus frissítését.

Az Ajánlatkérés fejlécében a legalacsonyabb és legmagasabb állapotok tekintheti meg **Az összes ajánlatkérés** oldalán. Az Ajánlatkérési sorban a legalacsonyabb és legmagasabb állapotok tekintheti meg **Sorok** fülön az **Ajánlatkérés** oldalon belül.

Az ajánlatkérés feldolgozásához az állapotok sorozata a következő:

1. **Létrehozva**
2. **Elküldve**
3. **Beérkezett**
4. **Elfogadva**, **Visszavonva**, illetve **Elutasítva**

Az ilyen állapotokról részletesen a jelen témakör későbbi szakaszaiban olvashat.

## <a name="setting-up-rfq-functionality"></a>Ajánlatkérési funkció beállítása

Az ajánlatkérési eset létrehozása előtt be kell állítania az ajánlatkérési információt a **Beszerzési és forrásparaméterek** oldalon. Az ajánlatkérési eset létrehozásakor megadhat alapértelmezett értékeket, amelyek aztán átkerülnek az ajánlatkérésre. Az alábbi alapértelmezett értékeket határozhatja meg:

- Az új ajánlatkérések beszerzési típusa: **Beszerzési rendelés** vagy **beszerzési szerződés**
- A lejárati dátum és idő
- Szállítási adatok és fizetési feltételek
- Mezők, amelyeknek szerepelnie kell az ajánlatkérési válaszban

Egy konkrét ajánlatkérési esetnél felülírhatja ezeket az értékeket.

A módosítási folyamatot és érdemes beállítani. A konfiguráció részeként a mezők zárolását is beállíthatja. Ha bekapcsolja a mezők zárolását, és egy beszerző módosítani szeretné az ajánlatkérést, először az **Árajánlat** fül **Módosítás** szakaszában a **Létrehozás** lehetőségét kell kiválasztania. Miután frissítette az ajánlatkérést a módosítással, a beszerzési szakértőnek kell befejeznie a folyamatot a **Véglegesítés** pont kiválasztásával. A Véglegesítés művelet e-mailt hoz létre, amely értesíti a szállítókat a módosított ajánlatkérésről.

A szállítóknak elküldött e-mailes értesítés sablonját a **Beszerzési és forrásparaméterek** oldalon választhatja ki. A létrehozott sablon az alábbi helyettesítő tokeneket tartalmazhatja:

- %RFQ case%
- %Ajánlat visszaküldésének oka%
- %Módosítás oka%
- %A módosítást készítette%
- %Vállalat%
- %RFQ case name%
- %ExpiryDateTime%
- %Date%

Az %Ajánlat visszaküldésének oka% és %Módosítás oka% tokeneket a rendszer olyan szöveggel helyettesíti, amelyet a beszerző adhat meg a **Módosítás** varázslóban elvégzett módosítások befejezésével. Az %A módosítást készítette% és %Vállalat% tokeneket a rendszer automatikusan az árajánlatkérés alapján tölti ki. A %Date% token helyére az aktuális dátum kerül.

E-mail sablon olyankor is szükséges, ha töröl egy ajánlatkérést az elküldést követően. Ezen e-mail sablon használatával küldheti el az érvénytelenítési értesítést a szállítói kapcsolattartóknak. A sablont ki kell jelölni a **Beszerzési és forrásparaméterek** lapon. A létrehozott sablon az alábbi helyettesítő tokeneket tartalmazhatja:

- %Reason for cancellation%
- %RFQ case% 
- %RFQ cancelled by%
- %Vállalat%
- %RFQ case name%
- %Date%

A %Reason for cancellation% token helyére az a szöveg kerül, amelyet a beszerző adhat meg az **Érvénytelenítés** varázslóban. A %Date% token helyére az aktuális dátum kerül.

Ha az ajánlatkérésre küldött válaszban okkódot kíván használni az ajánlat elfogadásának vagy elutasításának okához, az okkódokat a **Szállítói okok** oldalon állíthatja be.

A nyomtatott vagy tárolt ajánlatkérési dokumentumok megjelenését a Beszerzés és forrás menü **Képernyő-beállítás** oldalán állíthatja be.

> [!NOTE]
> A közszféra beállításainál a már elküldött ajánlatkérés módosításához a javítási folyamat használata szükséges. Az ajánlatkérés elküldésekor a mezők zárolva lesznek. Ennek megfelelően az ajánlatkérés módosításához ki kell jelölnie a **Létrehozás** lehetőséget a módosítási folyamat megkezdéséhez a fentebb leírt módon. A zárolási viselkedést az **Ajánlatkérések zárolása kiküldés után** lehetőség irányítja a **Beszerzési és forrásparaméterek** lapon. A paraméter értéke alapértelmezetten **Igen**, és a közszféra konfigurációjánál ez egy olyan alapérték, amelyet nem lehet megváltoztatni. Ezért, bár a módosítási eljárást manuálisan is lehet kezelni egy nem állami szektorbeli konfigurációban, azt használni kell az állami szektorbeli konfigurációknál.

Beszerzési rendeléshez tartozó ajánlatkérés létrehozásakor és egy készletcikk ajánlatkéréshez történő rendelésekor egy készlettranzakció is létrehozásra kerül **Árajánlat-bevételezés** bevételezési állapottal. Csak az ilyen típusú ajánlatkérési állapotok lesznek figyelembe véve, ha az alapterv segítségével számolja a cikkeket. Ha azt szeretné, hogy az alapterv várható bevételezésként tartalmazza az ajánlatkérési sorokat, ezt a viselkedést az alapterv beállításai között konfigurálnia kell.

Beszerzési vezetőként vagy ügynökként létrehozhatja, és karbantarthatja az ajánlatkérési típusokat, hogy megfeleljenek szervezete beszerzési követelményeinek. A meghirdetési típusok mindegyike társítható egy pontozási módszerrel. A pontozási módszerek olyan feltételeket tartalmaznak, amelyeket az ajánlatok pontozásához használhat. Be kell állítania a meghirdetési típusokat, pontozási módszereket és pontozási feltételeket a **Meghirdetés típusa** és **Pontozási módszer** oldalon.

## <a name="creating-and-sending-an-rfq"></a>Létrehozása és egy Ajánlatkérés küldése

Hozza létre az ajánlatkérést, válassza ki az kívánt szállítókat, majd küldje ki nekik az ajánlatkérést. A nyomtatáskezelési beállítások segítségével csatolhatja az ajánlatkérési jelentést és a válaszlapjelentéseket a kívánt célhoz.

Létrehozhat ajánlatkérést a **Beszerzési rendelés** vagy **Beszerzési szerződés** beszerzési típushoz.

Ha **Beszerzési rendelés** típusú az ajánlatkérés, akkor a következők történnek:

- Az ajánlatkérési sorok létrehozásakor olyan készlettranzakciók létrehozása történik, amelyek bevételezési állapota **árajánlat-bevételezés**.
- Egy ajánlat elfogadásakor létrejön egy beszerzési rendelés.

Ha **Beszerzési megállapodás** típusú az ajánlatkérés, akkor a következők történnek:

- Az ajánlat felhasználásra kerül egy megállapodáshoz adott mennyiségű vagy értékű termék vásárlásáról hosszabb idő alatt. Ki kell jelölnie a beszerzési megállapodásra vonatkozó dátumtartományt, illetve a beszerzési megállapodást kezelő személy nevét.
- Egy ajánlat elfogadásakor létrejön egy beszerzési szerződés.

Ha az ajánlatkérés létrehozása beszerzési igénylésből történik, a **beszerzési igénylés** típust a rendszer automatikusan hozzárendelni. Manuálisan nem hozhat létre **beszerzési igénylés** típusú ajánlatkérést.

Csak akkor hozhat létre ajánlatkérést egy beszerzési igénylésből, ha a beszerzési igénylés állapota **Ellenőrzés alatt**, és Ön van hozzárendelve a munkafolyamat következő feladatához. A beszerzési igénylés sorainak frissítése automatikusan történik, amikor elfogadja a szállítóktól kapott ajánlatkérési válaszok (ajánlatok) sorait. Amíg az ajánlatkérés folyamatban van, a beszerzési igénylésen nem lehet semmiféle műveletet végezni, például befejezést, elutasítást vagy jóváhagyást.

Az ajánlatkérés létrehozásakor kiválaszthat egy meghirdetési típust. A meghirdetési típus az ajánlatkérésre érkező válaszok pontozási feltételét határozza meg.

Az ajánlatkérési esethez hozzáadhat kérdőívet. Ez a kérdőív az ajánlatkérés elküldését követően minden válaszon megjelenik.

Háromféleképp választhatja ki az ajánlatkérési esethez hozzáadni kívánt szállítókat:

- Egyesével hozzáadhatja a szállítókat.
- Megkeresheti az adott feltételnek megfelelő szállítókat.
- Automatikusan hozzáadhat minden, az ajánlatkérési sorokhoz használt beszerzési kategóriákban jóváhagyott szállítót.

Ha az ajánlatkérési eset elkészült, válassza a **Küldés** lehetőséget. A Küldés művelet naplókat és egy jelentéseket hoz létre, amelyeket a rendszer a nyomtatáskezelési beállításoktól függően kinyomtat, archivál és elküld.

Ha az **Az ajánlatkérés elküldése** oldalon a **Szállító használata az árak újraszámításához** és a **Szállítófüggő cikkadatok használata** beállításoknál az **Igen** lehetőséget választja az ajánlatkérések elküldésekor, egyes szállítóspecifikus információkat a rendszer automatikusan kitölt. Ezeket az információkat az **Ajánlatkérésre adott válasz** oldalon módosíthatja.

Az alábbi táblázat bemutatja, hogy változik az ajánlatkérési állapot, ha az ajánlatot létrehozza és a szállítóknak elküldi.

| Művelet                             | Ajánlatkérés-fejléc legalacsonyabb állapota | A legnagyobb Ajánlatkérési fejléc állapota                        | Legkisebb Ajánlatkérési sor állapota | A legnagyobb Ajánlatkérési sor állapota |
|------------------------------------|--------------------------|--------------------------------------------------|------------------------|-------------------------|
| Az ajánlatkérés fejlécének és adatsorának létrehozása    | Létrehozva                  | Létrehozva                                          | Létrehozva                | Létrehozva |
| Az Ajánlatkérés küldése egy adott szállítóra. | Elküldött                     | Elküldött                                             | Elküldött                   | Elküldött |
| További szállító hozzáadása.                | Létrehozva                  | Elküldött (az Ajánlatkérés el lett küldve csak egy szállítónak.) | Létrehozva                | Elküldött |
| Az Ajánlatkérés elküldése a második szállítónak. | Elküldött                     | Elküldött                                             | Elküldött                   | Elküldött |

> [!NOTE]
> Az ajánlatkéréshez bármikor hozzáadhat további szállítókat is, a legalacsonyabb és legmagasabb állapotok pedig az új szállítók szerint változnak. Ha például minden szállítótól kapott ajánlatot, és legalább egy sort elfogadott egy ajánlaton, az ajánlatkérési fejléc legalacsonyabb állapota az **Elutsítva**, a legmagasabb pedig az **Elfogadva** lesz. Új szállító hozzáadásakor az egyes sorok legalacsonyabb állapota a **Létrehozott**. Ennek megfelelően az ajánlatkérési fejléc állapota **Létrehozott** értékre frissül, míg a legmagasabb továbbra is **Elfogadott** marad.

## <a name="amending-an-rfq"></a>Ajánlatkérés módosítása

Időnként előfordulhat, hogy elküldés után módosítani kell egy ajánlatkérést. Előfordulhat, hogy módosítania kell egy ajánlatkérést például akkor, ha a szállítási dátum megváltozott, vagy további termékeket, esetleg módosított mennyiségeket szeretne hozzáadni. A módosítási folyamatot beállíthatja kevésbé vagy jobban korlátozóra is.

Ha a módosítási folyamatot úgy állítja be, hogy szigorúbb legyen, akkor ahhoz, hogy módosíthassa egy már elküldött ajánlatkérési eset mezőit, először ki kell választania a **Létrehozás** lehetőséget az ajánlatkérési esetnél a módosítás megkezdéséhez. A módosítások befejezését követően válassza a **Véglegesítés** lehetőséget. A rendszer ezt követően végigvezeti a folyamaton, amelyben további információkat adhat hozzá a módosításról tájékoztató e-mailhez, amelyet a szállítók is megkapnak. A frissített ajánlatkérési jelentés, amely tartalmazza a módosítási megjegyzést, automatikusan csatolva lesz az e-mailhez.

A kevésbé korlátozó módosítási folyamat konfigurálása esetén a már elküldött ajánlatkérési eset mezőinek módosítása előtt nem szükséges a **Létrehozás** lehetőséget kiválasztani a módosításhoz. Azonban manuálisan hozzá kell adnia egy módosítási megjegyzést az ajánlatkéréshez, és újra be kell küldenie az esetet. Ne feledje, hogy ez a módszer csak akkor használható, ha egyik válasz (ajánlat) sem módosult. Ha megadott egy választ, és az **Beérkezett** állapotú, akkor a **Küldés** gomb nem érhető el. Ebben az esetben ki kell választania a **Létrehozás**, majd a **Véglegesítés** elemet, ahogyan az a korlátozóbb folyamatban elvárt. A válasz ekkor visszaáll, és megjeleníti az ajánlatkérési eset módosításait. 

Ha a szállítók a szállítói együttműködési felületet használják az ajánlatok beadására, mindig a módosítási folyamatot kell használnia ahhoz, hogy értesítse a szállítókat az ajánlatkérési esetben bekövetkezett változásokról. Ez a követelmény segít megelőzni azt a helyzetet, amikor a szállítók lejárt ajánlatkérési ügyben tesznek ajánlatot, miközben az ajánlatuk folyamatban van. Az új szállítói együttműködéssel kapcsolatos további tudnivalókat lásd: [A szállítói együttműködés a külső szállítókkal való együttműködésre történő használata](vendor-collaboration-work-external-vendors.md). 

Ha szeretne meghívni további szállítókat is az ajánlatkérésre, és nem hajtott végre módosítást az ajánlatkérési eseten, akkor használhatja a **Küldés** gombot. Az Ön által felvett szállítók megjelennek a **Küldés** lapon, és megkapják az e-mailes meghívót.

## <a name="receiving-and-registering-rfq-replies"></a>Az ajánlatkérésre érkezett válaszok érkeztetése és rögzítése

Ajánlatkérés küldésekor automatikusan létrejön egy válaszlap. Amint beérkeznek az ajánlatkérésre adott válaszok, az egyes szállítók adatait szállítóspecifikus ajánlatkérési válaszlapon kell rögzítenie. Ha vett fel pontozási feltételeket, pontozhatja a válaszokat. A szállítói válaszokat ezután különböző pontozási feltételek, például a legjobb ár vagy a legjobb szállítási idő szerint is rangsorolhatja.

Ha az ajánlatkérési esethez kérdőív is tartozik, a válaszlapra manuálisan meg kell adnia a válaszokat.

Megadhat alternatívasorokat is, amennyiben az ajánlatkérési eset engedélyezi az alternatívasorokat. A **Beszerzési árajánlat sorai** gyorslapon válassza a **Sor hozzáadása** lehetőséget. Ezután írjon be a termékkel kapcsolatos információkat, mint például a cikkszámot vagy a beszerzési kategóriát, a mennyiséget, az árat és az engedményt.

Ha megadott választ, de új ajánlatra van szükség a szállítótól, újra kiküldheti az ajánlatkérést. A rendszer erre új naplót és jelentést hoz létre, amelyekben módosításokat kérhet a szállítótól.

Az **Árajánlatkérések követése** oldalon áttekintheti az összes ajánlatkérést és a hozzájuk tartozó válaszok állapotát.

Az alábbi táblázat bemutatja, hogyan változik az ajánlatkérési állapot az ajánlatok beérkezésekor, miután rögzítette az információkat az ajánlatkérési válaszlapon.

| Művelet                                         | Az ajánlatot legalacsonyabb állapota. | Legmagasabb ajánlat állapota. | Ajánlatkérés-fejléc legalacsonyabb állapota | A legnagyobb Ajánlatkérési fejléc állapota | Legkisebb Ajánlatkérési sor állapota | A legnagyobb Ajánlatkérési sor állapota |
|------------------------------------------------|-------------------|--------------------|--------------------------|---------------------------|------------------------|-------------------------|
| Egy szállító ajánlatának regisztrálása, majd mentés.        | Elküldve              | Fogadott           | Elküldve                     | Fogadott                  | Elküldve                   | Fogadott |
| A második szállító ajánlatának regisztrálása, majd mentés. | Fogadott          | Fogadott           | Fogadott                 | Fogadott                  | Fogadott               | Bevételezve |

> [!NOTE]
> Ha ajánlatot küld vissza a szállítónak további tárgyalásra, a legalacsonyabb és legmagasabb állapot **Fogadva** marad.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Ajánlatok elfogadása és elutasítása, valamint az elfogadott ajánlatok átvitele a feldolgozott dokumentumokhoz

A legjobb, például legkedvezőbb árat nyújtó ajánlat azonosítása után elfogadhatja az ajánlatot. Egy ajánlat egyes sorait elfogadhatja, miközben másokat visszautasít. Elfogadhatja különböző szállítók egyes sorait is. Kérjük, ügyeljen arra, hogy bizonyos sorok elfogadásakor minden más sort vissza kell utasítania. Ezért ha más sorokat is el akar fogadni, először az utasítás megjelenésekor az **Érvénytelenít** lehetőséget kell választania. Az ajánlatkérésre adott válasz állapota minden olyan szállítónál, akiknek ajánlatait vagy sorait elfogadja, frissül **Elfogadott** értékre. 

Ha elfogad egy ajánlatot vagy egy ajánlat bizonyos sorait, a rendszer automatikusan egy beszerzési rendelést vagy beszerzési szerződést hoz létre. Ezt követően visszautasíthatja az összes többi szállítótól származó minden ajánlatot.

A válaszban hozzáadhat okkódot, amelyben megmagyarázza az elfogadás vagy elutasítás okát.

Ha elfogad egy **beszerzési igénylés** típusú ajánlatkérési választ, az ajánlatkérés válaszsorok frissítik a beszerzési igénylési sorokat az alábbi információkkal:

- Egységár
- Engedmény százaléka
- Engedmény összege
- Beszerzés költségei
- Sorköltségek
- Szállító
- Külső szám
- Külső leírás

Az alábbi táblázat bemutatja, hogyan változik az ajánlatkérési állapot, ha elfogadja vagy visszautasítja egy szállító ajánlatát.

| Művelet                      | Az ajánlatot legalacsonyabb állapota | Legmagasabb ajánlat állapota | Ajánlatkérés-fejléc legalacsonyabb állapota | A legnagyobb Ajánlatkérési fejléc állapota | Legkisebb Ajánlatkérési sor állapota | A legnagyobb Ajánlatkérési sor állapota |
|-------------------------    |-------------------|--------------------|--------------------------|---------------------------|------------------------|-------------------------|
| Az ajánlatok fogadása     | Fogadott          | Elfogadva           | Fogadott                 | Elfogadva                  | Fogadott               | Elfogadva |
| Az összes többi ajánlat elutasítása.  | Elutasítva          | Elfogadva           | Elutasítva                 | Elfogadva                  | Elutasítva               | Elfogadva |

