---
title: "Projektvezetés és könyvelés"
description: "A projektvezetési és könyvelési funkció több ágazatban használható egy szolgáltatás nyújtásához, egy termék előállításához vagy egy eredmény eléréshez."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cd30c9278c58f8e0ca9b50f67a999708bd64c0a2
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="project-management-and-accounting"></a>Projektvezetés és könyvelés

[!include[banner](../includes/banner.md)]


A projektvezetési és könyvelési funkció több ágazatban használható egy szolgáltatás nyújtásához, egy termék előállításához vagy egy eredmény eléréshez.  

A projekt olyan tevékenységek csoportja, amelyekkel szolgáltatás nyújtható, termék gyártható vagy eredmény érhető el. A projektek erőforrásokat használnak, és bevételek vagy eszközök formájában pénzügyi eredményeket generálnak.

## <a name="projects-across-industries"></a>Projektek ágazatokban között
A projektvezetési és könyvelési funkció több ágazatban is használható a következő ábrán látható módokon. [![Ágazatokon átívelő projektek](./media/projects-accross-industries.jpg)](./media/projects-accross-industries.jpg) 

Egy telefonos ügyfélszolgálat esetében, ún. „ticket” használható, amely összefoglalja azt az eljárásmenetet, amely végrehajtásával az adott probléma megoldható. A tanácsadó vállalatok, például a menedzsment- vagy műszaki tanácsadó szervezetek vagy a hirdetési ügynökségek, projektként hivatkoznak a tevékenységükre. A marketingben a kampány egy leszállítandó munkakészletet jelöl. Projekt-alapú gyártás esetén, a termelési rend határozza meg a késztermék előállításához elvégezendő különböző munkafolyamatokat. Akárhogyan is hívják őket, ezek a projektek nyersanyagokat, ütemterveket és költségeket foglalnak magukban, és a Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás projektvezetési és könyvelési funkciói ezeknek a projekteknek a tervezésében, kivitelezésében és elemzésében nyújthatnak segítséget.

## <a name="project-phases"></a>A projekt fázisai
Ugyan a következő folyamatábra olyan külső projektre vagy projektekre vonatkozik, amelyek egy vagy több ügyfél számára kerülnek teljesítésre, ez a funkció a házon belüli, csak kiadással járó projektekre is alkalmazható. 

![Egy projekt 3 fázisa](./media/3-stages-of-a-project.png) 

Ahogy az előző ábrán is látható, a projektvezetés és a könyvelés három fázisra osztható:

1.  Kezdeti - halasztott adó - eszköz vagy halasztott adó - forrás
2.  Végrehajtás
3.  Elemzés

## <a name="initiate-the-project"></a>Projekt beindítása
A projekt kezdeményezése során számos kulcsfontosságú folyamat fordul elő. A projektajánlat segítségével az anyagok, a költségek és a becsült munka kommunikálható az ügyfélnek. A számlázási feltételeket, a korlátozásokat és a megállapodásokat a projektszerződésben rögzítheti. A munkalebontási struktúra (WBS) segítségével tervezheti és becsülheti meg a munkát. A projekt végrehajtásának irányításához előrejelzéseket és költségvetéseket állíthat be. A következő ábra mutatja a projekt szerkezetét. [![projekt szerkezetét](./media/project-structure1.jpg)](./media/project-structure1.jpg)  

### <a name="create-project-quotations"></a>Projektajánlatok létrehozása

Egy projekt első értékesítési fázisában a beszállítói árajánlat lehetővé teszi, hogy nem kötelező érvényű ajánlatot tegyen a megrendelőnek. Az ajánlat kiterjedhet az ajánlat tárgyául szolgáló cikkekre és szolgáltatásokra, alapvető kapcsolattartási információkra, különleges kereskedelmi megállapodásokra és árengedményekre, valamint a lehetségesen felmerülő adókra és pótdíjakra.

Ön egy, az Ön szervezete és a megrendelő között megtörtént beszállítói árajánlat-tételről garancialevelet állíthat ki. A beszállítói árajánlattétel után a megrendelő számára Ön a bank felé garancialevél-kérelmet állíthat ki. Ha a bank elfogadja a kérelmet, a garancialevél a megrendelő részére kiállításra kerül. 

További információért lásd [Beszállítói árajánlatok](project-quotations.md).

### <a name="create-project-contracts"></a>Projektszerződések létrehozása

Ha egy projekt teljesítéséről a megrendelővel, vagy más szponzorral megállapodás születik, projektszerződést kell írni. Ezután a projekt létrehozásakor azt hozzá kell rendelni a megfelelő szerződéshez. A projektszerződés teljesítésére létrehozott projekt típusa határozza meg a megrendelő felé történő számlakiállítás módszerét. A projektszerződés és a hozzá kapcsolódó projekt módosítható, de a projekt típusa nem. Projekttípusokkal kapcsolatos további információért lásd: "Projekt létrehozása".

Projektszerződésekkel kapcsolatos további információkért lásd: [Projektszerződések](project-contracts.md).

### <a name="create-work-breakdown-structures"></a>Munkalebontási struktúra létrehozása

A WBS részletességének mértéke attól függ, hogy milyen mértékű pontosság szükséges a becslésekben, és hogy milyen szintű nyomon követés szükséges ezen becslések figyelembevételével. Azoknál a projekteknél, melyek fokozottan ütemterv- vagy költségérzékenyek, részletesebb WBS-re van szükség, valamint arra, hogy a munka előrehaladása és WBS-hez viszonyított tényleges költségei folyamatosan figyelemmel legyenek kísérve. 

További információért lásd: [Munkalebontási szerkezetek](work-breakdown-structures.md)

### <a name="create-project-forecasts-and-budgets"></a>Projekt-előrejelzések és költségvetési tervezetek létrehozása

Használja a projekt-előrejelzést, amennyiben a szervezetnek van működési terve, és ha az a meghatározott tranzakciókból származtatott bevételekre és költségekre fókuszál. Használja a projekt költségvetés-tervezéshez, ha a szervezet inkább a pénzügyi összegekre összpontosít. Minden metódus előnyökkel jár. További információért lásd: [Projekt-előrejelzések és a költségvetési tervezetek](project-forecasts-budgets.md).

### <a name="create-projects"></a>Projektek létrehozása

A Microsoft Finance and Operations hat projekttípus létrehozását teszi lehetővé. Minden projekttípus beállításai eltérők a költségek és bevételek elszámolása szempontjából. A projekttípus kiválasztása a projekt célkitűzésétől függ. A következő táblázat ismerteti az egyes projekttípusok jellemző használatát.

                                                                                                                                                                         |
| Projekt típusa      | Leírás                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Idő és anyag | Az idő- és anyagelszámolású projektek esetén a vevőnek minden olyan költséget kiszámlázunk, amely a projektben előfordul. Ezek a költségek magukban foglalják a munkabéreket, a költségeket, az eszközöket, és díjakat.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Rögzített ár       | A rögzített árú projekteknél a számlák a részszámlázási tranzakciókból állnak. A rögzített árú projekteknek a számlázása olyan számlázási ütemezés szerint történik, amely egy projektszerződésen alapul. Rögzített árú projekteknél a jövedelem a projekt során a teljesített munka százaléka alapján kiszámítható. Ezen kívül a jövedelem a projekt befejeztekor, a teljesített szerződés-módszertannal is kiszámítható. A vállalatoknak gyakran előnyös lehet a folyamatban lévő munka értékének használata a projekt vagy projektcsoport feldolgozottsági fokának kiszámításához.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Befektetés        | A beruházási projektek olyan projektek, amelyekből nem származik azonnali bevétel. Ezeket általában hosszú távú belső projektekhez használják, amelyekben a költségeket tőkésíteni kell. Egy beruházási projektnél csak eszközök, munkaórák, és költségek regisztrálhatók. Egy beruházási projekt költségei a Becslés funkcióval ellenőrizhetők és nyomon követhetők. A beruházási projektek igény szerint tőkésítési maximum értékkel láthatóak el. Egy beruházási projekt előrehaladtával a költségeket a folyamatban lévő termelési (WIP) könyvekben kell rögzíteni, ahol a költségek addig maradnak rögzítve, amíg a projekt be nem fejeződik. A projekt megszüntetésekor a WIP-értéket tárgyi eszközbe, főkönyvi számlára vagy új projektbe kell átvinni. Megjegyzés: A beruházási projektek tranzakciói nem jelennek meg a **Költségek feladása**, **Elhatárolt bevétel** vagy **Számlajavaslatok létrehozása** oldalon.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Költségprojekt      | A beruházási projektekhez hasonlóan a költségprojektek segítségével általában nyomon követheti a belső projekteket, és csak órák, költségek, és cikkek rögzíthetők a projektek költségeihez. A költségprojektek általában rövidebb idejűek, mint a beruházási projektek. A beruházási projektekkel ellentétben a költségprojektek nem tőkésíthetők mérlegszámlákra. Ehelyett a projekttranzakcióik csak eredményszámlákra adhatók fel. **MEGJEGYZÉS:** A költségprojektek tranzakciói nem jelennek meg a **Költségek feladása**, **Elhatárolt bevétel** vagy **Számlajavaslatok létrehozása** oldalon. Mivel a költségprojektek általában belső projektek nyomon követésére használatosak, általában nem kell őket vevőfiókhoz társítani. Ha azonban a telepítő megköveteli, hogy cikkszükségleteket hozzon létre a beszerzési rendelésekhez, akkor mégis hozzá kell rendelni a költségprojektet a vevőhöz. Ennek oka, hogy a cikkszükségleteket értékesítési rendeléssorokként kezeli, és a rendszer megköveteli, hogy a vevő meg legyen adva. Ez a beállítás azonban eredményezi azt, hogy a cikkszükségletek automatikusan létrejönnek egy beszerzési rendelésből. A költségprojektek a **Cikkszükséglet létrehozása** figyelmen kívül hagyja a beállítást. Ha mégis cikkszükségletre van szüksége egy költségprojektben, elkészítheti manuálisan, mindaddig, amíg a vevő társítva van a projekthez. |
| Belső          | A belső projektek olyan projektek, amelyek a szervezeten belüli projektek költségeinek nyomon követésére szolgálnak. A belső projekt tervezési eszközt biztosíthat az erőforrás-felhasználás kezelésére. **Megjegyzés:** A belső projektek tranzakciói nem jelennek meg a **Elhatárolt bevétel** vagy a **Számlajavaslatok létrehozása** oldalon.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Idő              | Az időelszámolású projektek olyan idő nyomon követésére használatosak, amely nem számlázható és nem termelési tevékenységekhez kötődik, például egy dolgozók betegszabadságának nyomon követésére szolgáló projekt. Az időelszámolású projektek tranzakciói nem kerülnek feladásra a főkönyvbe. Ehelyett dolgozói kihasználtsági jelentésekbe kerülnek. Az időelszámolású projektekben csak óratranzakciók regisztrálására van lehetőség. Ezeket az órákat óranapló vagy idő-nyilvántartás használatával regisztrálhatja a projekthez. Az órák regisztrálása után projekttranzakciókként jelennek meg, de megfelelő bizonylattranzakciók nélkül. **Megjegyzés:** Az időelszámolású projektek tranzakciói nem jelennek meg a **Költségek feladása**, **Elhatárolt bevétel** vagy **Számlajavaslatok létrehozása** oldalon.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |


### <a name="assign-workers-categories-and-resources"></a>Dolgozók, kategóriák és erőforrások hozzárendelése

A lehetővé teszi a dolgozói erőforrások ütemezését egy projekt követelményei és ütemezése alapján, illetve a dolgozók szakértelme és elérhetősége alapján. Az erőforrás-ütemezési funkciók használatával hatékonyan és gazdaságosan foghatja munkára a szervezet dolgozóit. Gyorsan megtalálhatja a legalkalmasabb dolgozók számára, hogy a projektben elérhető. Hogyan munkavállalók lehet használni a hatékonyabb a projekt során is könnyen látható. 

Az alábbiakban néhány, az erőforrás-ütemezési funkciók használatát bemutató módszer olvasható:

-   A dolgozó attribútumai (például képzettség, szakértelem, bizonyítványok és projekttapasztalat) alapján rendelheti őt hozzá egy projekt követelményeihez.
-   A dolgozó naptárinformációi és elérhetősége alapján rendelheti össze egy dolgozó ütemezését a projektnaptárral.
-   Áttekintheti az egyes dolgozók kapacitását, és meghatározhatja annak kihasználtságát. Ha például egy dolgozó kihasználtsága alacson, akkor hozzárendelhető egy olyan projekthez, amely megfelel elérhetőségének és attribútumainak.
-   A dolgozó elérhetőségét ellenőrizve meggyőződhet róla, hogy nincsenek-e ütközések a naptárban egyéb megbízásokkal.
-   A munkaerő kihasználtságát összefoglaló formában is megtekintheti, például részlegre vagy dolgozóra levetítve, vagy részletes formában például egy adott részleg dolgozóira, vagy egy adott dolgozó heti részleteire.
-   Az erőforrás-hozzárendeléseket különböző időegységekre (nap, hét, hónap) vonatkozóan is módosíthatja, ezzel optimalizálhatja a dolgozó kihasználtságát.

## <a name="execute-the-project"></a>Projektek végrehajtása
Projekt végrehajtásakor csapattagok vagy azokkal a vezetőkkel rögzítése munka és a költségek felmerült, használja a munkaidő-nyilvántartások költségjelentések és más üzleti dokumentumokhoz. A projektvezetők eszközök, amelyek segítségével azokat a projekt költségvetési összegek fogyasztását figyelése rendelkezik. A projektvezetők rendelés, kiválasztása vagy is szerzik be a projektekhez használt anyagok beszerzési rendelések és más üzleti dokumentumokhoz. Számlák előkészített és jóváhagyták, úgy, hogy a vevők számlázható folyamatban lévő munka. Végül bevétel elszámolása a folyamat során, amelyek befolyásolják a vállalat pénzügyi adatok.

### <a name="manage-work-breakdown-structures"></a>Munkalebontási struktúra létrehozása

A WBS-t a projekt végrehajtandó munka leírása. A WBS-t feladatok hierarchiáját. Azt jelöli, hogy a feladatokra, de is a méret, költség, és vegye figyelembe, hogy a feladat nem csak a munka. 

További információért lásd: [Munkalebontási szerkezetek](work-breakdown-structures.md)

### <a name="manage-project-forecasts-and-budgets"></a>Projektköltségvetések és előrejelzések kezelése

Két lehetőség van a projektek intézésére és irányítására: a projekt-előrejelzések és a projektköltségvetések. Használja a projekt-előrejelzést, amennyiben a szervezetnek van működési terve, és ha az a meghatározott tranzakciókból származtatott bevételekre és költségekre fókuszál. Használja a projekt költségvetés-tervezéshez, ha a szervezet inkább a pénzügyi összegekre összpontosít.

További információért lásd: [Projekt-előrejelzések és a költségvetési tervezetek](project-forecasts-budgets.md).

### <a name="create-production-orders"></a>Termelési rendelés létrehozása

A projekthez kapcsolódó termelési rendelés a befejezett cikk módszer vagy a felhasznált cikk módszer használatával kapcsolható egy értékesítési rendelés vagy cikk-követelménybe. Továbbá a termelési rendelést manuálisan hozták létre, ha nem áll fenn kapcsolat a termelési rendelés és az értékesítési rendeléshez vagy cikkszükséglethez (nincs kapcsolás rendeléshez) között. Azonban a termelési rendelés automatikusan jött létre egy értékesítési rendelést vagy egy cikkszükséglet kielégítésére, ha nincs hivatkozás a termelési rendelés és az értékesítési rendeléshez vagy cikkszükséglethez (kapcsolás rendeléshez) között. 

Ilyen tényező kategóriakombinációkon alapuló, a következő módszerek valamelyikével:

-   A **Kész cikk/kapcsolás rendeléshez** módszer választása esetén a projekt értékesítési rendeléshez vagy cikkszükséglethez kapcsolható. A módszer alkalmazása a tényleges projektköltségeket feladja az értékesítési rendelés számlázásakor vagy a csomagjegyzék cikkszükségletnek megfelelő frissítésekor. A költség feladása befejezett cikként történik.
-   **Kész cikk/nincs kapcsolás rendeléshez** – tényleges költségeket nem adható fel, amíg a termelési folyamatról a cikk állapota **Befejezve**. A költség feladása a befejezett cikk egyetlen tranzakciójaként történik.
-   A **Kész cikk/kapcsolás rendeléshez** módszer választása esetén a projekt értékesítési rendeléshez vagy cikkszükséglethez kapcsolható. A módszer alkalmazása esetén a a tényleges projektköltségek megtekinthetők, amikor a termelés **Elindítva** vagy Készként jelentve állapotú. A költség feladása a nyersanyagok esetében több projektcikk tranzakcióiként, illetve a termelés esetében a felhasznált órák formájában történik. Amikor megtörténik a cikkszükségletre vonatkozóan a csomagjegyzék frissítése, nem történik projektköltségek feladása. Definiálni lehet, hogy az anyagjegyzék-hierarchia (BOM) melyik szintje legyen nyomon követve a termelési projektekben.
-   ****A Kész cikk/kapcsolás rendeléshez**** módszer választása esetén a projekt értékesítési rendeléshez vagy cikkszükséglethez kapcsolható. A módszer alkalmazása esetén a a tényleges projektköltségek megtekinthetők, amikor a termelés **Elindítva** vagy Készként jelentve állapotú. A költség feladása a nyersanyagok esetében több projektcikk tranzakcióiként, illetve a termelés esetében a felhasznált órák formájában történik. Definiálni lehet, hogy az anyagjegyzék-hierarchia (BOM) melyik szintje legyen nyomon követve a termelési projektekben.

### <a name="procure-products-and-services"></a>Termékek és szolgáltatások rendelése

A beszerzési és a cikkek értékesítése olyan projekt foglalkozó vállalkozások számos elterjedt tevékenységeket.

#### <a name="purchase-orders-for-projects"></a>Projekt beszerzési rendelései

A beszerzési rendelés célja határozza meg, hogy mikor történik meg a beszerzési rendelés felhasználása, és így azt is, hogy mikor kerül sor a cikkek elszámolására a projektnél.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mód</th>
<th>Cél</th>
<th>Cikkek felhasználása</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Beszerzési rendelés létrehozása közvetlen módon.</td>
<td>Beszerzés külső szállítótól egy projektben történő felhasználására. A beszerzési rendelést az alábbi módokon hozhatja létre:
<ul>
<li>Magából a projektből. Ilyenkor eleve definiálva van a beszerzési rendelés projektje.</li>
<li>A projekt beszerzési rendelés kikeresésével. Ki kell választani a létrehozandó beszerzési rendelés szállítóját és projektjét is.</li>
</ul></td>
<td>A cikkek felhasználása a szállítói számla frissítésekor történik.</td>
</tr>
<tr class="even">
<td>Beszerzési rendelés létrehozása egy értékesítési rendelés alapján.</td>
<td>Cikkeket beszerezni, amikor egy értékesítési rendelést hoz létre a projektben.</td>
<td>A cikkek felhasználása az értékesítési rendelés vevőnek való számlázása esetén történik meg.</td>
</tr>
<tr class="odd">
<td>Beszerzési rendelés létrehozása cikkszükségletből.</td>
<td>Beszerzési rendelés létrehozása cikkszükségletből a Projekt modulban.</td>
<td>A cikkek felhasználása akkor történik meg, amikor a cikkszükséglet csomagjegyzéke frissül.</td>
</tr>
</tbody>
</table>

#### <a name="sales-orders-for-projects"></a>Saját projekt értékesítési rendelések

A Projektkezelés és könyvelés a felhasznált cikkek többféle módon lehet regisztrálni. Lehetőség van a projektből történő eladásra és beszerzésre, valamint a cikkek lefoglalására a projekt számára. 

A rendelés-felhasználás a vállalat a készletben szereplő cikkeket projekteken. Azt is megteheti vagy külső szállítótól beszerezhető cikkeket. Az Idő típusú projekteket kivéve minden projekttípusban lehetőség van cikkek felhasználására. 

A cikkek megrendelésének módszere attól függ, honnan rendeli őket:

-   Ha a vállalat készletéből rendel cikkeket, akkor cikkszükségletként kell megadnia a rendelést. Ha a **Cikkszükséglet** oldalt használja, a követelményt beállíthatja úgy, hogy a cikkeket részleges szállításként kapja. Így egy cikkmennyiség felhasználását elhalaszthatja arra az időre, amikor a cikkre szükség lesz.
-   Ha külső szállítótól rendeli meg a cikkeket, akkor egy beszerzési rendelést kell létrehoznia a **Beszerzési rendelés** oldalon.

> [!NOTE] 
> A projektspecifikus értékesítési rendelés szállítólevele nem törölhető, ha a cikkek már meg vannak jelölve csomagolásra. 

Az alábbi táblázat felsorolja a cikkek rendezési módjait, és bemutatja, hogyan kerülnek azok felhasználásra.

| Mód            | Cél                                                                                                                                                        | Jogdíj-felhasználási tranzakció                                                                                                                  |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| Értékesítési rendelés       | Értékesítési tranzakció rögzítése közvetlenül egy idő- és anyagelszámolású projektben.                                                                                                   | A cikktranzakciók felhasználása a vevői számla feladásakor történik.                                                                               |
| Készletnapló | Gyorsan megadhat és karbantarthat cikkrekordokat. Ha például egy nyomtatott lista alapján szeretne cikkszükségletet rögzíteni, akkor alkalmazhatja a készletnaplót. | A cikktranzakciók felhasználása a napló feladásakor történik.                                                                                        |
| Cikkszükséglet  | Olyan cikkeket rögzíthet, amelyeket nem azonnal használnak fel. A felhasználó ezzel a módszerrel nyomon követheti az egyes cikkszükséglet-rekordokon belül felhasznált cikkek számát.    | A cikktranzakciók felhasználása a csomagjegyzék frissítésekor történik. A cikkszükséglet tehát akkor jön létre, amikor a csomagjegyzéket feladják. |
| Beszerzési rendelések   | A beszerzési módtól függően három különböző helyen rögzítheti a tranzakciókat.                                                                              | A cikktranzakciók felhasználása a csomagjegyzékek frissítésekor, illetve a vevő vagy a szállító számlájának kiállításakor történhet.                                      |

### <a name="process-project-invoices"></a>Projektszámlákra vonatkozó jelentések

A projekt típusa határozza meg, hogy melyik számlázási eljárást kell alkalmazni. Kizárólag a két külső projekttípus, az (Idő- és anyagelszámolású, illetve a Rögzített árú) projektek számlázhatók. Az Idő- és anyagelszámolású projektek és a Rögzített árú projektek mindig projektszerződéshez kapcsolódnak. 

Mielőtt létrehozná egy projekt vevői számláját, létrehozhat egy előzetes számlát, más néven számlajavaslatot. A számlajavaslatban tudja kiválasztani, hogy a projektszámlán mely projekttranzakciók szerepeljenek. A projektszámla feladása, illetve a vevő vagy a finanszírozási forrás részére történő megküldése előtt át tudja nézni a számla részletes adatait. 


Az almunkafolyamat hozzáadásáról és konfigurálásáról kapcsolatban az alábbi témakör tartalmaz további tájékoztatást: [Projektszámlázás](../accounts-payable/project-invoicing.md).


### <a name="calculate-the-cost-to-complete-a-project"></a>A teljesítési költség kiszámítása

Becslés létrehozása esetén választhatja lehet kiszámítani a költséget a projekt teljesítésére használt mód. Kiválaszt egy metódust a a **Metódus teljes költsége** mezőjét a **Létrehozása becsült** oldalon. A program a kiválasztott teljesítendő költség módszert alkalmazza a költségbecslés költségsoraiban. Miközben egy sor állapota **Létrehozott**, módosíthatja a módot, amely azt a vonatkozik a **Költségbecslés** lap. 

A következő táblázat leírja a projekt a teljesítési költség kiszámításához használt módszerek.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mód</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Teljes költség – Tényleges</td>
<td>Becsült költségek manuálisan kell megadni. Után a <strong>Teljes költség</strong> vagy <strong>Mennyiségének</strong> oszlopában meg a <strong>Költségbecslés </strong>lap elkészült, a felhasználó által megadott összegek összegből a tényleges költségeket. A projekt a teljesítési költség eredménye. Általában költségek állapotának nem nyomon követhetők alapján, például a szállodai tartózkodás és a étkezés időszakonként rögzített száma. Helyette. Nyomon követési általában alapul összehasonlítása szemben a becsült órák teljes összege. Ezzel a módszerrel nem szükséges előrejelzési modell, és a teljes költség vagy a teljes mennyiség manuálisan módosítható. Amikor beír egy értéket a <strong>Teljes költség</strong> vagy <strong>Összmennyiség</strong> oszlopban a Finance and Operations összehasonlítja ezt az értéket az időszakra feladott tényleges tranzakciókat szemben, és ezután a értéke csökken a <strong>Befejezendő mennyiség</strong> vagy <strong>Teljesítendő költség</strong> oszlopban.</td>
</tr>
<tr class="even">
<td>Teljes költségvetés – Tényleges</td>
<td>Tényleges költségek összehasonlítja a költség meghatározása a kiválasztott előrejelzési modellt. Ez a módszer az előre jelzett a tranzakciókat tartalmazó teljes költségvetési modell használ. A projekt pontosabb képet kaphat, hogy a költségvetési modell folyamatban van a projekt során állíthatja be. Az előrejelzés beállításához hajtsa végre az a főkönyvi folyamat:
<ol>
<li>Előrejelzési sorok másolása egy másik előrejelzési modellbe.</li>
<li>Előrejelzés-tranzakciók tényleges tranzakciók összehasonlítása.</li>
<li>Karbantartása, csökkenti vagy növeli a becslések a következő időszakra.</li>
</ol>
A Finance and Operations automatikusan nem csökkenti az előre jelzett becsléseket. Ezért célszerű karbantartása rögzített árú projekten összehasonlítás alaptervet létrehozására, a projekt befejezésekor az eredeti előrejelzési modellel. 
> [!NOTE] Ha ezt a módszert választja, legalább két előrejelzési modellt használjon. Egy modell tartalmaznia kell az eredeti előrejelzés. A modell, az előrejelzési tranzakciókat kell másolása egy másik modellbe. Ez a mező csak rögzített árú és beruházási projektekre vonatkozik.</td>
> </tr>
<tr class="odd">
<td>Fennmaradó költségvetés</td>
<td>Ezzel a módszerrel lehet kiszámítani a költséget a projekt teljesítésére használja a fennmaradó költségvetési modellt. Ezt a módszert, ha a tényleges költség és az előre jelzett összegeket a fennmaradó költségvetési modell össze kell adni. A teljes költség eredménye. Ezt a módszert, mielőtt fennmaradó költségvetési modell be kell állítani, amelyet a rendszer rögzíti a tényleges tranzakciók alapján tranzakciók levonandó. Az <strong>Előrejelzési modellek</strong> oldalon, győződjön meg arról, hogy meg vannak jelölve a mezőket a <strong>Automatikus előrejelzés csökkentése</strong> csoport. Általában a fennmaradó költségvetés másolja a rendszer az eredeti költségvetés. Tranzakciók kerülnek, mint a fennmaradó költségvetési tranzakcióihoz csökken. A projekt előrehaladtával, ha úgy dönt, hogy a fennmaradó költségvetés úgy kell beállítani, akkor terhelve a fennmaradó költségvetés-előrejelzési tranzakciók. <strong>Megjegyzés:</strong> A módszer csak akkor alkalmazható, ha van előrejelzési modell társítva a becsléshez.</td>
</tr>
<tr class="even">
<td>Korábbi becslésként</td>
<td>Ugyanez a becslés az előző időszakban használt módszert alkalmazza a rendszer. Ehhez a módszerhez előrejelzési modell, ha az előző időszakban az előrejelzési modell szükséges.</td>
</tr>
<tr class="odd">
<td>Teljesítési költség nullára állítása</td>
<td>Általában ezt a módszert használják a becsült projekt eltávolítása előtt. Ez a módszer feladott tényleges tranzakciókat tartalmazó teljes becslés megegyezik, és törli a <strong>Teljesítendő költség</strong> oszlopban. A megjelenő feldolgozottsági százalék mindig kell lennie 100 százalék. Az <strong>Előrejelzés</strong>jelölőnégyzetből az összes létrehozott költségsornál törölve van a jelölés, és a becsült összköltséget a program a korábbi költségbecslésből másolja át. A becslési időszak tényleges felhasználását a projekt a teljesítési költség vonni. Ehhez a módszerhez nem szükséges előrejelzési modell.</td>
</tr>
<tr class="even">
<td>Költségsablonból</td>
<td>A teljes módszer van beállítva a költségsablon a kijelölt becsült projekthez társított költség lesz érvényes.</td>
</tr>
</tbody>
</table>

## <a name="analyze-the-project"></a>A projekt elemzése
A legtöbb szinten projektté csoportosítására szolgál költségek rögzítése, és ezeket a költségeket a főkönyvbe történő feladása tranzakciókkal kapcsolatban. 

Ezek a tranzakciók általában az üzleti dokumentumok, például a munkaidő-nyilvántartások, a költségjelentéseket, a szállítói számlák vagy a készlettranzakciók eredményét. Az életciklus a projekt általában a becslések előrejelzések és a költségvetési terv Súgó és a munka és a projekt becsült pénzügyi hatását megjósolják kezdődik. Elemezhetők egy projektet, mivel döntheti el, nem csak azokat a tranzakciókat, amelyek a projekt, hanem a becslések és az előrejelzés pontosságát, a projekt csapattagok kihasználtsági mértékét és a projekt teljes sikeres történt.

### <a name="analyze-cash-flow"></a>Pénzforgalom elemzése

A pénzforgalom-figyelés lehetővé teszi egy projekt mind előre jelzett, mind tényleges pénzforgalmának figyelemmel kísérését. Ez a projekt lefolyása közben is megtehető, de dönthet úgy, hogy egy már elvégzett projekt pénzforgalmát utólag tekinti meg. 

Ezzel a funkcióval kiértékelhet egyetlen projektet, használhatja a jelentéseket több projekt megtekintésére, és átutalhatja a pénzforgalmat a pénzforgalmi előrejelzésébe.

#### <a name="cash-inflow-forecasting"></a>A pénzbeáramlás előrejelzése

A beállításoktól függően a kiválasztott projekt pénzbeáramlások előrejelzési. Például ha a program a projektdátumot 2012. március 5., és számlázás 2012. március 31., Íme hogyan előre jelezhető a határidőt és a várható értékesítési kifizetési dátumhoz:

-   **Projekt dátuma:** 2012. március 5.
-   **Számla dátuma:** 2012. március 31. A dátum meghatározása a számlázási gyakoriság alapján történik. Ebben a példában a Számlagyakoriság meg az aktuális hónaphoz. Emiatt a március hónapban feladott összes tranzakció számlázása a hónap utolsó napját.
-   **Határidő:** 2012. április 14. A dátum meghatározása a projekthez beállított fizetési feltételek alapján történik. Ebben a példában a kiválasztott fizetési feltételek 14 napos. Ezért 14 nap hozzáadódnak rakódó határidő 2012. április 14. a számla dátumát.
-   **Várható értékesítési kifizetési dátuma:** 2012. április 27. A dátum kiszámítása a napok összeadásával történik: először az **Általános puffernapok** mező, **Projektvezetési és könyvelési paraméterek** oldal napjai lesznek összeadva az **Egyedi puffernapok** mező, **Projektszerződések** oldal napjaival, majd az összeg össze lesz adva a **Határidő** mező teljes napszámával. Ebben a példában a beírt **3** a **Általános puffernapok** mező és **10** a **Egyedi puffernapok** mező. Ezért 13 nap hozzáadódnak rakódó határidő 2012. április 27. a számla dátumát.

Az Általános puffernapok vagy cserélhető meg az egyedi puffernapok, vagy hozzá kell adni az egyedi Puffernapok:

-   Az egyedi puffernapok pótol az Általános puffernapok alkalmazásához vevők adja meg az esedékességi dátum és a tényleges fizetési dátum közötti napok átlagos száma.
-   Az egyedi Puffernapok az Általános puffernapok hozzáadása a **Általános puffernapok** mezőbe írja be a nap, amikor a felhasználó elküldi a kifizetés és a nap, amikor a szervezet kifizeti a között eltelt napok száma a becslést.

A projektszerződés egyedi puffernapok beállítása. A napok kiszámításának alapja az értékesítési és a vállalat tapasztalata szerinti vevői fizetési szokások.

#### <a name="actual-cash-inflow"></a>Tényleges pénzbeáramlás

A tényleges pénzbeáramlás nagyon hasonló az előrejelzéshez, kivéve azt, hogy a számításokat az első után lehet megkezdheti. Egy példa:

-   **Számla dátuma:** 2012. március 2.
-   **Határidő:** 2012. március 16. A fizetési feltételek beállítása 14 nap.
-   **Várható értékesítési kifizetési dátuma:** 2012. március 29. A számítás magában foglal három általános puffernapot és 10 egyedi puffernapot.

#### <a name="cost-forecasting"></a>Költség-előrejelzés

A meghatározott napok alapján, a költségkifizetési dátumot eltérhet a projekt dátumát. Ebben az esetben a költségkifizetési dátumot a program a projektdátumot azon napok számának hozzá a fizetési feltételeket a napok számát számítja ki. 

Például a tranzakció projektdátuma 2012. március 5., és a következő fizetési feltételek vannak beállítva:

-   **Órák:** A jelenlegi hónap (**M**)
-   **Költségek:** 14 nap (**D14**)
-   **Cikkek:** 30 nap (**D30**)

Ezek a beállítások alapján, a költségkifizetési dátumot minden tranzakciótípushoz Íme:

-   **Óra:** 2012. március 31., vagyis a kijelölt hónap utolsó napját.
-   **Költségek:** 14 nappal a tranzakció egyben 2012. március 19.
-   **Költségek:** 30 nappal a tranzakció egyben 2012. április 4.

> [!NOTE] 
> A beszerzési rendelés határidejének alapja a szállítói tranzakció alapja, amikor a projektbeszerzési rendeléskor létrejön. A határidő nem alapértelmezett beállításait határozza meg. 

A költségkifizetési dátumot puffernapok nem számítja ki. Amikor egy projekt lezárult, és az összes költség és számla teljesült, a költség és az értékesítés feladása megtörténik az számlákra. 

Amikor minden értékesítési és szállítói számla teljesült, megtekintheti a mezők közötti kapcsolatot a **Pénzforgalmi** lapot, majd a mező a **Projekt kimutatások** lap.

| Banki pénzforgalom | Projektkimutatások megjelenítése |
|----------------|-------------------------|
| Pénzbeáramlások   | Bevétel                 |
| Pénzkiáramlások  | Összes költség              |
| Nettó pénzforgalom | Bruttó nyereség            |

### <a name="review-costs"></a>Közvetett költségek áttekintése

A szervezet a projekt során felmerülő, a költségek nyomon követheti a **Költségellenőrzés** oldalon. Az aktuális tényleges költsége és a vállalt költségek a projekt eredeti költségvetésében szereplő költségeket összehasonlításával meghatározhatja, hogy a projekt rendben van, költségkeret-túllépésről és a költségvetést. 

> [!NOTE] 
> Ha a **Költségellenőrzés** oldalt használja a projektköltségek aktuális állapotának megjelenítésére, használja az előrejelzési modelleket, amelyek ki lettek választva az eredeti és a fennmaradó költségvetéshez. Ha más előrejelzési modellek költségeinek kiszámítása, a számítási eredmények nem lesznek pontosak.

#### <a name="viewing-the-remaining-budgeted-amounts"></a>A fennmaradó költségvetési összegek megtekintése

Ha a **Fennmaradó költségvetés** kiválasztott költség ellenőrzési módszerként a **Projektvezetési és könyvelési paraméterek** lapot, a **Költségellenőrzés** lap számítja ki a tényleges és vállalt megjelölt még nem feladott költségek. Konkrétabban az összegeket a **Általános** lap alsó részén a **Költségellenőrzés** lap számítása a következőképpen történik:

-   **Tényleges költség** – Teljes összeg lett projektalkalmazott a projekten kiválasztott költségsorra vonatkozó. A tényleges költség összege a számítása a **Főkönyvi frissítések** oldalon.
-   **Vállalt költség** – A kiegészítő összeg, amely a jogi személy vállalt fizetendő költségek. Az adott vállalt költség összegének számítása a a **Vállalt költségek** oldalon.
-   **Fennmaradó költségvetés** – Összege az eredeti költségvetési összeg, amely a kiválasztott költségsorra vonatkozó továbbra is elérhető. A fennmaradó költségvetés összege a számítása a **Főkönyv előnézete** oldalon.
-   **Teljes költség** – Összege a tényleges költség, a vállalt költség és a fennmaradó költségvetés összege.

Az **Költségellenőrzés** oldalon a **Eltérés** lapon meg lehet tekinteni a teljes várható költség és az eredeti költségvetés összevetését. Ez az összevetés mutatja az ezeket az összegeket közötti esetleges különbségeket. Ezért látható, ahol az adat nem felel meg. Az eltérések összegének számítása a következőképpen történik:

-   **Eredeti költségvetés** – Az eredetileg kiválasztott költségsorra vonatkozó tervezett összeget. A fennmaradó költségvetés összege a számítása a **Főkönyv előnézete** oldalon.
-   **Teljes költség** – A **Általános** lapon szereplő tényleges költség, a vállalt költség és fennmaradó költségvetés összege.
-   **Eltérés** – Az eredeti költségvetési összeg és a teljes költség különbségének megjelenítése.
-   **Mennyiségalapú eltérés** – Az eredeti előrejelzésben és a teljes előrejelzésben lévő eltérés teljes összege. Ez a különbség a következő egyenlettel fejezhető ki: (összes előrejelzett mennyiség) * (eredeti átlagár - összesített átlagár). Ez a beállítás csak a projekt óratranzakcióira vonatkozik.
-   **Áralapú eltérés** – Az eredeti előrejelzésben és a teljes előrejelzésben lévő eltérés teljes összege. Ez a különbség a következő egyenlettel fejezhető ki: (eredeti előrejelzett ár) * (eredeti előrejelzett mennyiség - összes előrejelzett mennyiség). Ez a beállítás csak a projekt óratranzakcióira vonatkozik.

#### <a name="viewing-the-total-budgeted-amounts"></a>A teljes előirányzott összegek megtekintése

Ha **Teljes költségvetés** kiválasztott költség ellenőrzési módszerként a **Projektvezetési és könyvelési paraméterek** lapot, a **Költségellenőrzés** lap kiszámítja a tényleges költségeket, és segítséget nyújt a kettő közötti különbség észlelése a projekt teljes költsége. Konkrétabban az összegeket a **Költségellenőrzés** lap alsó részén a **Általános** lap számítása a következőképpen történik:

-   **Teljes előirányzott költség** – A teljes költségvetési összeg a kijelölt költségsorhoz.
-   **Tényleges költség** – Teljes összeg lett projektalkalmazott a projekten kiválasztott költségsorra vonatkozó.
-   **Tényleges költség** – Teljes összeg lett projektalkalmazott a projekten kiválasztott költségsorra vonatkozó.
-   **Eltérés** – A teljes költségvetési költség tényleges és elismert költsége közötti különbség megjelenítése. Az eltérés megmutatja, hogy a teljes költségvetéshez további költségeket kell-e hozzáadni.

Az **Költségellenőrzés** oldalon, a **Eltérés** lapon megtekintheti a teljes költségvetés és az eredeti költségvetés közötti különbség megnézzük a következő mezőket:

-   **Eredeti költségvetés** – Az eredetileg kiválasztott költségsorra vonatkozó tervezett összeget. A fennmaradó költségvetés összege a számítása a **Főkönyv előnézete** oldalon.
-   **Teljes költségvetés** – Az eredetileg kiválasztott költségsorra vonatkozó tervezett összeget. A fennmaradó költségvetés összege a számítása a **Főkönyv előnézete** oldalon.
-   **Eltérés** – az eltérést a költségsorhoz. Az eltérést úgy számítja ki a program, hogy kivonja az összes költséget az eredeti költségvetésből.
-   **Mennyiségalapú eltérés** – Az eredeti előrejelzésben és a teljes előrejelzésben lévő eltérés teljes összege. Ezt az összeget úgy számítja ki a program, hogy kivonja a költségvetésben szereplő összesített óraszámot az eredeti költségvetés óraszámából, és megszorozza a különbözetet az eredeti költségvetésben szereplő önköltségi árral. Ez a különbség lehet matematikai kifejezve (eredeti költségvetésben szereplő önköltségi ár) x (eredeti költségvetés óraszámából – teljes előirányzott óra). Ez a beállítás csak a projekt óratranzakcióira vonatkozik.
-   **Áralapú eltérés** – ezt az összeget úgy számítja ki a program, hogy kivonja a költségvetésben szereplő összesített óraszámot az eredeti költségvetés óraszámából, és megszorozza a különbözetet a ténylegesen felhasznált órák számával. Ez a különbség lehet matematikai kifejezve (Teljes felhasznált órák) x (eredeti költségvetés óraszámából – teljes előirányzott óra). Ez a beállítás csak a projekt óratranzakcióira vonatkozik.

### <a name="analyze-utilization"></a>Kihasználtsági elemzése

A kihasználtsági ráta százalékos dolgozó munkaidő adott időszak számlázható vagy termelési munka hajt végre. Számlázható órák a dolgozó munkaóráinak, amely egy adott vevőhöz miatt fizetendő kamatszázalékot. 

Egy adott időszakban munkaórák számával számlázható órák száma egy dolgozó kihasználtsági ráta kiszámítása. Például egy dolgozó rendelkezik egy időszakban 30 számlázható órák, és 40 ugyanabba az időszakba esik munkaórák száma, a dolgozó kihasználtsági ráta esetén 75 százaléka. 

Válassza ki, hogy a számlázhatósági rátán vagy a hatékonysági rátán alapuljon a kihasználtsági ráta:

-   **Számlázhatósági ráta** – Számlázhatósági és a nem számlázható órák vagy normaidő közötti különbség.
-   **Hatékonysági ráta** – Számlázhatósági és a nem számlázható órák vagy normaidő közötti különbség. Idő az órákat, amelyek a dolgozó tölt egy adott projekt hozzájáruló. Idő általában számlázásra kerülő a vevőknek, kivéve abban az esetben, ha belső projekteket. Nem produktív idő soha nem számlázásra kerülő egy vevőnek.

Az órákon alapuló számítás eredményeként kapott **Kihasználtsági ráta**, százalékban. A számítások alapját az alapértelmezett beállításokat. Ezek a beállítások is adja meg, hogyan óra hozzárendelésével számítása **Kihasználtsági** vagy **Haszontalan** egyes projekttípusok. A számlázhatósági ráta kiszámításában, és a hatékonysági ráta kiszámításában vonatkozik.

-   **Kihasználtsági** – A kiválasztott projekttípus jelzett órák mindig figyelembe számlázhatósági és hatékonysági kihasználtság.
-   **Haszontalan** – A kiválasztott projekttípus jelzett órák mindig figyelembe számlázhatósági és hatékonysági kihasználtság.
-   **Sortulajdonság szerint** – sortulajdonságok egy adott óra tranzakció határozzák meg, hogy az órák vegye figyelembe számlázhatósági és hatékonysági kihasználtság.
-   **Nem szerepel** – óra nem a hatékonysági fokok számlázhatósági számítás vagy a hatékonysági kihasználtsági.

Az **Időkihasználtság** oldalon, a teljes százalékos kihasználási arány dolgozó vagy projekt, mellett meg lehet tekinteni a kihasználtsági ráta kiszámításában minden, a következő óra típusú előállításához ténylegesen felhasznált órák száma:

-   **Nem tartalmazott óra** – ezeket az órákat a nem szerepelnek az kihasználtsági ráta.
-   **Tartalmazott órák** – A kihasznált idő és a haszontalan idő összege, szerepel a kihasználtsági rátában. Ezeket az órákat a kihasználtsági ráta szerepelnek.
-   **Órák terheljék** – is szeretnénk számítani a számlázhatósági ráta, ha ezeket az órákat megegyeznek a nem számlázható idő. Ha meg van hatékonysági fokának számítása, ezeket az órákat ugyanazok, mint improduktív.
-   **Kihasználtsági órák** – is szeretnénk számítani a számlázhatósági ráta, ha ezeket az órákat megegyeznek a nem számlázható idő. Ha meg van hatékonysági fokának számítása, ezeket az órákat ugyanazok, mint improduktív.

Dolgozó számításakor a kihasználtsági ráta használhatja a normaidő vagy beleszámított idő. Beleszámított idő használatakor gondoskodnia kell arról, hogy a munkavállalók azok az idő-nyilvántartási időszakok összes munkaidő rögzítése, mert a költségsorokba írt órák százalékában fejezik ki a számításban. Az a projekt, projektszerződés, vevőrekord vagy kategória az időkihasználtsági ráta kiszámításakor a számítás beleszámított idő kell használnia.

### <a name="review-project-statements"></a>Projektkimutatások megjelenítése

Megtekintheti egy adott projekt előrehaladását gyors pillanatképe Projektkimutatás hozhat létre. Projektkimutatás futtatja, megadhatja a feltételeket, amelyek segítségével a kimutatás számítása a kijelölések alapján a **Általános** lapjáról a **Projekt kimutatások** lap. Választhat, amely felveszi / kizárja a következő adatokat:

-   Projekttípusok
-   Tranzakciótípusok
-   Projekt dátum/főkönyv frissítése
-   Adat

A kimutatás kiszámítása után megtekintheti az egyes lapokon a következő adatokat a **Kimutatások projekt** lap:

-   **Általános** – a Projekt eredmény alapvető szerkezetét vonatkozó általános információkat.
-   **Nyereség és veszteség** – elhatárolt bevétel adatait.
-   **Folyamatban lévő munka** – folyamatban lévő munka-számla egyenlegét adatait.
-   **Felhasználás** – a felhasználás az órák, kiadások, cikkek és bérlista-tranzakciók adatait.
-   **Számla** – számlákat és a részszámla készítésére vonatkozó információk.
-   **Órabér** – Az eredményszámlákra feladott órák órabérének megtekintése.





