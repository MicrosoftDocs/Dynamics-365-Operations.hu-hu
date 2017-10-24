---
title: "Ajánlatkérések"
description: "Ez a témakör betekintést nyújt az árajánlat kérés folyamatába. Egy szervezet akkor ad ki árajánlatkérést, amikor cikkeket és szolgáltatásokat szeretne beszerezni, és ehhez egymással versenyző különböző szállítóktól kér ajánlatokat."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8b817ffd905f1d3e99befc149416006e1a51f5e2
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="request-for-quotations-rfqs"></a>Ajánlatkérések

[!include[banner](../includes/banner.md)]


Ez a témakör betekintést nyújt az árajánlat kérés folyamatába. Egy szervezet akkor ad ki árajánlatkérést, amikor cikkeket és szolgáltatásokat szeretne beszerezni, és ehhez egymással versenyző különböző szállítóktól kér ajánlatokat. Az ajánlatkérésben arra kéri a szállítókat, hogy adják meg a meghatározott számú cikkekhez ajánlott áraikat és szállítási idejüket. Emellett kérheti a szállítóktól annak meghatározását, hogy vannak-e egyéb járulékos költségek, például szállítási költséget, illetve kínálnak-e nagyobb rendelések vagy a szállítói számla korai kifizetése esetén engedményeket.

Az ajánlatkérési folyamat az alábbi feladatokat tartalmazza:

-   Ajánlatkérés létrehozása és küldése egy vagy több szállítónak.
-   Az ajánlatkérésre érkezett válaszok (ajánlatok) érkeztetése és rögzítése.
-   Az elfogadott ajánlatok átvitele beszerzési rendeléshez, beszerzési szerződéshez vagy beszerzési igényléshez.

A következő ábrán áttekinthető az ajánlatkérési folyamat.  

[![Ajánlatkérési folyamat](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)  

Ajánlatkérést tervezett rendelésekből, beszerzési igénylésből és manuális bevitelből is létrehozhat. A létrehozott ajánlatkérés neve ajánlatkérési eset, amely az egyes szállítóknak kiadott ajánlatkérés alapdokumentuma. Az ajánlatkérési eset előkészítése és a szállítók hozzáadása után kattintson a **Küldése** lehetőségre az ajánlatkérési eseten; ekkor egy ajánlatkérési napló jön létre minden olyan szállítóhoz, amelynek elküldte az ajánlatkérést. A Küldés művelet nyomtatáskezelési beállításait módosítva megadhatja, hogy a rendszer külön jelentést nyomtasson minden szállítóhoz az archívumba, vagy a jelentést e-mailben küldje a szállítók e-mail címére. Ezenkívül az egyes szállítók ajánlatkérési naplóját olyan napló létrehozására is felhasználhatja, amelyet később elküldhet vagy újraküldhet a szállítónak. A Küldés műveletet úgy is beállíthatja, hogy a rendszer a szállító által kitölthető válaszlapot is generáljon.  

Ha egy ajánlatkérést az elküldés után módosítania kell, elküldheti az ajánlatkérést a szállítóknak, ha végzett a módosításokkal.  

Ha ajánlatot kap, azokat az **Ajánlatkérési válaszok** oldalon adhatja meg. Ha az **Adatok másolása a válaszba** lehetőséget választja, a mennyiséget és az ajánlatkérés egyéb adatait a rendszer a válaszba másolja. Módosíthatja ezeket az adatokat, hogy azok a szállító ajánlatát tükrözzék.  

Ha egy szállítónak a válasz második ismétlésére is szüksége van, kattintson a **Vissza** lehetőségre az **Ajánlatkérési válasz** oldalon. A Vissza művelet új naplót és egy jelentést hoz létre, amelyet a rendszer a nyomtatáskezelési beállításoktól függően kinyomtat, archivál és elküld.  

Ha pontozási feltételeket adott hozzá az ajánlatkérési esethez, az ajánlatkérési válasz egy pontozási panelt is tartalmaz, amelyen a pontok megadhatók. Az összesített pontszám akkor jelenik meg, ha a **Válaszok összehasonlítása** oldalon összehasonlítja azokat; ezen az oldalon egyéb válaszadatokat is összehasonlíthat, például az árat, a szállítási dátumot és a teljes árat.  

Ha egy ajánlattal vagy részleges ajánlattal kapcsolatban döntést hozott, elfogadhatja azt, és visszautasíthatja a többit. A rendszer létrehozza az elfogadási naplót, visszautasítási naplót és a megfelelő jelentéseket. Ezeket a rendszer a nyomtatáskezelési beállításoknak megfelelően kinyomtatja, archiválja és elküldi. Egy ajánlat vagy bizonyos ajánlati sorok elfogadásakor az ajánlatkérési beszerzés típusától függően egy beszerzési szerződés vagy beszerzési rendelés jön létre, vagy frissül a beszerzési igénylés. Létrehozhat kereskedelmi megállapodást, amelyet később bármelyik válasz esetében felhasználhat, függetlenül attól, hogy azt elfogadta vagy elutasította.  

Az ajánlatkérés állapota megjelenik az ajánlatkérés fejlécében, és az ajánlatkérési sorok állapotától függ. Az állapot azt jelzi, hogy milyen mértékben, amelyhez az Ajánlatkérés feldolgozta. Az egyes Ajánlatkérési van állapotára vonatkozó két érték: legalacsonyabb és legmagasabb. Legalacsonyabb állapota az ajánlatkérés minden sorban a legkevésbé készültségi foka, és a lehető legnagyobb készültségi foka minden olyan sor, az ajánlatkérés legmagasabb állapota. Például ha legalább speciális állomása egy ajánlatkérési sorhoz korábban létrehozott tartozik, az ajánlatkérés legalacsonyabb állapota **Létrehozott**. Ha az Ajánlatkérés legmagasabb szintű állomása sor el lett küldve a szállítókhoz, van-e az ajánlatkérés legmagasabb állapota **Elküldött**. Az Ajánlatkérés dolgozza fel az állapotokat automatikus frissítését.  

Az Ajánlatkérés fejlécében a legalacsonyabb és legmagasabb állapotok tekintheti meg **Az összes ajánlatkérés** oldalán. Az Ajánlatkérési sorban a legalacsonyabb és legmagasabb állapotok tekintheti meg **Sorok** fülön az **Ajánlatkérés** oldalon belül.  

Az Ajánlatkérés feldolgozásához az állapotok sorozata a következő:

1.  **Létrehozva**
2.  **Elküldve**
3.  **Beérkezett**
4.  **Elfogadva**/**Visszavonva**/**Elutasítva**

Az állapotokról részletesen a jelen témakör későbbi szakaszaiban olvashat.

## <a name="setting-up-rfq-functionality"></a>Ajánlatkérési funkció beállítása
Az ajánlatkérési eset létrehozása előtt be kell állítania az ajánlatkérési információt a **Beszerzési és forrásparaméterek** oldalon. Az ajánlatkérési eset létrehozásakor megadhat alapértelmezett értékeket, amelyek aztán átkerülnek az ajánlatkérésre. Az alábbi alapértelmezett értékeket határozhatja meg:

-   Az új ajánlatkérések beszerzési típusa: **Beszerzési rendelés** vagy **beszerzési szerződés**.
-   A lejárati dátum és időpont beállításai.
-   Szállítási adatok és fizetési feltételek.
-   Mezők, amelyeknek szerepelnie kell az ajánlatkérési válaszban.

Egy konkrét ajánlatkérési esetnél felülírhatja ezeket az értékeket. A módosítási folyamatot és érdemes beállítani. A konfiguráció részeként a mezők zárolását is beállíthatja. Ha bekapcsolja a mezők zárolását, és egy beszerző módosítani szeretné az ajánlatkérést, először az **Árajánlat** fül **Módosítás** szakaszában a **Létrehozás** lehetőségre kell kattintania. Miután frissítette az ajánlatkérést a módosítással, a beszerzési szakértőnek kell befejeznie a folyamatot a **Véglegesítés** pontra való kattintással. A **Véglegesítés** művelet e-mailt hoz létre, amely értesíti a szállítókat a módosított ajánlatkérésről. A szállítóknak elküldött e-mailes értesítést sablonját a **Beszerzési és forrásparaméterek** oldalon választhatja ki. A létrehozott sablon az alábbi helyettesítő tokeneket tartalmazhatja:

-   %Ajánlat visszaküldésének oka%
-   %Módosítás oka%
-   %A módosítást készítette%
-   %Vállalat%

Az %Ajánlat visszaküldésének oka% és %Módosítás oka% tokeneket a rendszer olyan szöveggel helyettesíti, amelyet a beszerző adhat meg a **Módosítás** varázslóban elvégzett módosítások befejezésével. Az %A módosítást készítette% és %Vállalat% tokeneket a rendszer automatikusan az árajánlatkérés alapján tölti ki.  

Ha az ajánlatkérésre küldött válaszban okkódot kíván használni az ajánlat elfogadásának vagy elutasításának okához, az okkódokat a **Szállítói okok** oldalon állíthatja be.  

A nyomtatott vagy tárolt ajánlatkérési dokumentumok megjelenését a Beszerzés és forrás menü **Képernyő-beállítás** oldalán állíthatja be. 

**Megjegyzés:** A közszféra beállításainál az ajánlatkérés bármely már elküldött módosításánál szükséges a javítási folyamat használata. Az ajánlatkérés elküldésekor a mezők zárolásra kerülnek, így a **Létrehozás** pontra való kattintás a javítási folyamat fent leírt lépései kötelezőek az ajánlatkérés módosítása esetén.
Ezt a **Ajánlatkérések zárolása kiküldés után** mezőzárolási paraméter irányítja a **Beszerzési és forrásparaméterek** menüben. A paraméter értéke **Igen**, és a közszféra konfigurációjánál ez egy olyan alapérték, amelyet nem lehet megváltoztatni. Ez azt jelenti, hogy bár a módosítási folyamat manuálisan is végrehajtható a nem közszférabeli konfigurációknál, a közszféránál a módosítások kezelése a mezők ajánlatkérés elküldése utáni zárolása által kötelező.

Beszerzési rendeléshez tartozó ajánlatkérés létrehozásakor és egy készletcikk ajánlatkéréshez történő rendelésekor egy készlettranzakció is létrehozásra kerül **Árajánlat-bevételezés** bevételezési állapottal. Csak az ilyen típusú ajánlatkérési állapotok lesznek figyelembe véve, ha az alapterv segítségével számolja a cikkeket. Ha azt szeretné, hogy az alapterv várható bevételezésként tartalmazza az ajánlatkérési sorokat, ezt a viselkedést az alapterv beállításai között konfigurálnia kell.  

Beszerzési vezetőként vagy ügynökként létrehozhatja, és karbantarthatja az ajánlatkérési típusokat, hogy megfeleljenek a szervezet beszerzési követelményeinek. Az egyes meghirdetési típusok befolyásolhatják a pontozási módszereket. A pontozási módszerek olyan feltételeket tartalmaznak, amelyeket az ajánlatok pontozásához használhat. Be kell állítania a meghirdetési típusokat, pontozási módszereket és pontozási feltételeket a **Meghirdetés típusa** és **Pontozási módszer** oldalon.

## <a name="creating-and-sending-an-rfq"></a>Létrehozása és egy Ajánlatkérés küldése
Hozza létre az ajánlatkérést, válassza ki az kívánt szállítókat, majd küldje ki nekik az ajánlatkérést. A nyomtatáskezelési beállítások segítségével csatolhatja az ajánlatkérési jelentést és a válaszlapjelentéseket a kívánt célhoz.  

Létrehozhat ajánlatkérést a **Beszerzési rendelés** vagy **beszerzési szerződés** beszerzési típushoz.  

Ha az ajánlatkérés létrehozása beszerzési igénylésből történik, a **beszerzési igénylés** típust a rendszer automatikusan hozzárendelni. Manuálisan nem hozhat létre **beszerzési igénylés** típusú ajánlatkérést. Ha az ajánlatkérés **beszerzési rendelés** típusú:

-   Az ajánlatkérési sorok létrehozásakor olyan készlettranzakciók létrehozása történik, amelyek bevételezési állapota **árajánlat-bevételezés**.
-   Egy ajánlat elfogadásakor létrejön egy beszerzési rendelés.

Ha az ajánlatkérés **beszerzési szerződés** típusú:

-   Az ajánlat felhasználásra kerül egy megállapodáshoz adott mennyiségű vagy értékű termék vásárlásáról hosszabb idő alatt. Ki kell jelölnie a beszerzési megállapodásra vonatkozó dátumtartományt, illetve a beszerzési megállapodást kezelő személy nevét.
-   Egy ajánlat elfogadásakor létrejön egy beszerzési szerződés.

Csak akkor hozhat létre ajánlatkérést egy beszerzési igénylésből, ha a beszerzési igénylés állapota **Ellenőrzés alatt**, és Ön van hozzárendelve a munkafolyamat következő feladatához. A beszerzési igénylés sorainak frissítése automatikusan történik, amikor elfogadja a szállítóktól kapott ajánlatkérési válaszok (ajánlatok) sorait. Amíg az ajánlatkérés folyamatban van, a beszerzési igénylésen nem lehet semmiféle műveletet végezni, például befejezést, elutasítást vagy jóváhagyást.  

Az ajánlatkérés létrehozásakor kiválaszthat egy adott meghirdetési típust. A meghirdetési típus az ajánlatkérésre érkező válaszok pontozási feltételét határozza meg.  

Az ajánlatkérési esethez hozzáadhat kérdőívet. Ez a kérdőív az ajánlatkérés elküldését követően minden válaszon megjelenik.  

Háromféleképp választhatja ki az ajánlatkérési esethez hozzáadni kívánt szállítókat:

-   Egyesével hozzáadhatja a szállítókat.
-   Megkeresheti az adott feltételnek megfelelő szállítókat.
-   Automatikusan hozzáadhat minden, az ajánlatkérési sorokhoz használt beszerzési kategóriákban jóváhagyott szállítót.

Ha az ajánlatkérési eset elkészült, kattintson a **Küldés** lehetőségre. A Küldés művelet naplókat és egy jelentéseket hoz létre, amelyeket a rendszer a nyomtatáskezelési beállításoktól függően kinyomtat, archivál és elküld.  

Ha az **Az ajánlatkérés elküldése** oldalon a **Szállító használata az árak újraszámításához** és **Szállítófüggő cikkadatok használata** jelölőnégyzeteket kiválasztja az ajánlatkérések elküldésekor, egyes szállítóspecifikus információkat a rendszer automatikusan kitölt. Ezeket az információkat az **Ajánlatkérésre adott válasz** oldalon módosíthatja.  

Az alábbi táblázat bemutatja, hogy változik az ajánlatkérési állapot, ha az ajánlatot létrehozza és a szállítóknak elküldi.

|                                    |                              |                                                 |                            |                             |
|------------------------------------|------------------------------|-------------------------------------------------|----------------------------|-----------------------------|
| **Művelet**                         | **Ajánlatkérés-fejléc legalacsonyabb állapota** | **A legnagyobb Ajánlatkérési fejléc állapota**                   | **Legkisebb Ajánlatkérési sor állapota** | **A legnagyobb Ajánlatkérési sor állapota** |
| Az ajánlatkérés fejlécének és adatsorának létrehozása    | Létrehozva                      | Létrehozva                                         | Létrehozva                    | Létrehozva                     |
| Az Ajánlatkérés küldése egy adott szállítóra. | Elküldött                         | Elküldött                                            | Elküldött                       | Elküldött                        |
| További szállító hozzáadása.                | Létrehozva                      | Elküldött (az Ajánlatkérés el lett küldve csak egy szállítónak.) | Létrehozva                    | Elküldött                        |
| Az Ajánlatkérés elküldése a második szállítónak. | Elküldött                         | Elküldött                                            | Elküldött                       | Elküldött                        |

**Megjegyzés:** Az ajánlatkéréshez bármikor hozzáadhat további szállítókat is, a legalacsonyabb és legmagasabb állapotok pedig az új szállítók szerint változnak. Ha például minden szállítótól kapott ajánlatot, és legalább egy sort elfogadott egy ajánlaton, az ajánlatkérési fejléc legalacsonyabb állapota az **Elutsítva**, a legmagasabb pedig az **Elfogadva** lesz. Új szállító hozzáadásakor az egyes sorok legalacsonyabb állapota a **Létrehozott**. Ennek megfelelően az ajánlatkérési fejléc állapota **Létrehozott**, míg a legmagasabb továbbra is **Elfogadott**.

## <a name="amending-an-rfq"></a>Ajánlatkérés módosítása
Időnként előfordulhat, hogy elküldés után módosítani kell egy ajánlatkérést. Ez például akkor történhet meg, ha a szállítási dátum megváltozott, vagy további termékeket, esetleg módosított mennyiségeket szeretne hozzáadni. A módosítási folyamatot beállíthatja kevésbé vagy jobban korlátozóra is.  

A jobban korlátozó módosítási folyamat esetén kattintson a **Létrehoz** lehetőségre az ajánlatkérési eseten a módosítás elindításához, mert csak így módosíthatja az ajánlatkérési eset mezőit. A módosítások befejezéséhez kattintson a **Véglegesítés** lehetőségre. A rendszer ezután végigvezeti a folyamaton, amelyben további információkat adhat hozzá a módosításról tájékoztató e-mailhez, amelyet a szállítók is megkapnak. A frissített ajánlatkérési jelentés, amely tartalmazza a módosítási megjegyzést, automatikusan csatolva lesz az üzenethez.  

A kevésbé korlátozó módosítási folyamat használata esetén a már elküldött ajánlatkérési eset mezőinek módosítása előtt nem szükséges módosítást létrehoznia. Azonban manuálisan hozzá kell adnia egy módosítási megjegyzést az ajánlatkéréshez.

## <a name="receiving-and-registering-rfq-replies"></a>Az ajánlatkérésre érkezett válaszok érkeztetése és rögzítése
Ajánlatkérés küldésekor automatikusan létrejön egy válaszlap. Amint beérkeznek az ajánlatkérésre adott válaszok, az egyes szállítók adatait szállítóspecifikus ajánlatkérési válaszlapon kell rögzítenie. Ha vett fel pontozási feltételeket, pontozhatja a válaszokat. A szállítói válaszokat ezután különböző pontozási feltételek, például a legjobb ár vagy a legjobb szállítási idő szerint is rangsorolhatja.  

Ha az ajánlatkérési esethez kérdőív is tartozik, a válaszlapra manuálisan meg kell adnia a válaszokat.  

Ha egyéb sorokat kell megadnia, és az ajánlatkérési eset ezt megengedi, a **Beszerzési árajánlat sora** gyorslapon kattintson a **Sor hozzáadása** lehetőségre. Ezután írjon be a termékkel kapcsolatos információkat, mint például a cikkszámot vagy a beszerzési kategóriát, a mennyiséget, az árat és az engedményt.  

Ha megadott választ, de új ajánlatra van szükség a szállítótól, újra kiküldheti az ajánlatkérést. A rendszer erre új naplót és jelentést hoz létre, amelyben módosításokat kérhet a szállítótól.  

Az **Árajánlatkérések követése** oldalon áttekintheti az összes ajánlatkérést és a hozzájuk tartozó válaszok állapotát.  

Az alábbi táblázat bemutatja, hogyan változik az ajánlatkérési állapot az ajánlatok beérkezésekor, miután rögzítette az információkat az ajánlatkérési válaszlapon.

|                                                |                       |                        |                              |                               |                            |                             |
|------------------------------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Művelet**                                     | **Az ajánlatot legalacsonyabb állapota** | **Legmagasabb ajánlat állapota** | **Ajánlatkérés-fejléc legalacsonyabb állapota** | **A legnagyobb Ajánlatkérési fejléc állapota** | **Legkisebb Ajánlatkérési sor állapota** | **A legnagyobb Ajánlatkérési sor állapota** |
| Egy szállítóval az ajánlatot regisztrálja, majd a mentéshez.        | Elküldött                  | Bevételezve               | Elküldött                         | Bevételezve                      | Elküldött                       | Bevételezve                    |
| A második szállítónak ajánlat regisztrálja, majd a mentéshez. | Bevételezve              | Bevételezve               | Bevételezve                     | Bevételezve                      | Bevételezve                   | Bevételezve                    |

**Megjegyzés:** Ha ajánlatot küld vissza a szállítónak további tárgyalásra, a legalacsonyabb és legmagasabb állapot **Fogadva** marad.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Ajánlatok elfogadása és elutasítása, valamint az elfogadott ajánlatok átvitele a feldolgozott dokumentumokhoz

A legjobb, például legkedvezőbb árat nyújtó ajánlat azonosítása után elfogadhatja az ajánlatot. Az adott szállító ajánlatkérési válaszának állapota ezután **Elfogadva** állapotra frissül. Ha elfogad egy ajánlatot vagy egy ajánlat bizonyos sorait, a rendszer automatikusan egy beszerzési rendelést vagy beszerzési szerződést hoz létre, Ön pedig elutasíthatja a többi szállító ajánlatát.  

Ha elfogad egy **beszerzési igénylés** típusú ajánlatkérési választ, az ajánlatkérés válaszsorok frissítik a beszerzési igénylési sorokat az alábbi információkkal:

-   Egységár
-   Engedmény százaléka
-   Engedmény összege
-   Beszerzés költségei
-   Sorköltségek
-   Szállító
-   Külső szám
-   Külső leírás

A válaszban hozzáadhat okkódot, amelyben megmagyarázza az elfogadás vagy elutasítás okát.  

Egy ajánlat egyes sorait elfogadhatja, miközben másokat visszautasít. Elfogadhatja különböző szállítók egyes sorait is. Kérjük, ügyeljen arra, hogy bizonyos sorok elfogadásakor minden más sort vissza kell utasítania. Ezért ha más sorokat is el akar fogadni, először az utasítás megjelenésekor az **Érvénytelenít** lehetőségre kell kattintania.  

Az alábbi táblázat bemutatja, hogyan változik az ajánlatkérési állapot, ha elfogadja vagy visszautasítja egy szállító ajánlatát.

|                         |                       |                        |                              |                               |                            |                             |
|-------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Művelet**              | **Az ajánlatot legalacsonyabb állapota** | **Legmagasabb ajánlat állapota** | **Ajánlatkérés-fejléc legalacsonyabb állapota** | **A legnagyobb Ajánlatkérési fejléc állapota** | **Legkisebb Ajánlatkérési sor állapota** | **A legnagyobb Ajánlatkérési sor állapota** |
| Az ajánlatok fogadása | Bevételezve              | Elfogadva               | Bevételezve                     | Elfogadva                      | Bevételezve                   | Elfogadva                    |
| A többi ajánlat elutasítása.  | Elutasítva              | Elfogadva               | Elutasítva                     | Elfogadva                      | Elutasítva                   | Elfogadva                    |






