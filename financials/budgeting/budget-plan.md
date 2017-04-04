---
title: "Költségvetés-tervezés"
description: "A lab célja egy Microsoft Dynamics 365 interaktív képet ad a műveletek funkció frissítések költségvetés-tervezési területen. Ezen oktatóanyag célja, hogy illusztrálja a költségvetés tervező modul egy gyors konfigurációs példáját, valamint bemutassa, hogyan vihető véghez a költségvetés tervezés ennek a konfigurációnak a használatával.  A lab középpontjában kifejezetten a következő üzleti folyamatok és feladatok – a szervezeti hierarchia létrehozása a költségvetés-tervezési és felhasználói biztonság beállítása - költségvetési terv esetek, a költségvetési terv oszlopokra, elrendezések és Excel sablonok - létrehozása és aktiválása a költségvetési tervezési folyamat - létrehozása költségvetés-tervezési dokumentum szerint jogosultak-e a tényleges adatok a főkönyvből - hozzárendelések segítségével állítsa be a költségvetési terv dokumentumadatok - Szerkesztés költségvetési terv dokumentum adatokat az Excel programban"
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 81b44aa7af3a05ebc28963f406fab98bfbbb340d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning"></a>Költségvetés-tervezés

A lab célja egy Microsoft Dynamics 365 interaktív képet ad a műveletek funkció frissítések költségvetés-tervezési területen. Ezen oktatóanyag célja, hogy illusztrálja a költségvetés tervező modul egy gyors konfigurációs példáját, valamint bemutassa, hogyan vihető véghez a költségvetés tervezés ennek a konfigurációnak a használatával.  A lab középpontjában kifejezetten a következő üzleti folyamatok és feladatok – a szervezeti hierarchia létrehozása a költségvetés-tervezési és felhasználói biztonság beállítása - költségvetési terv esetek, a költségvetési terv oszlopokra, elrendezések és Excel sablonok - létrehozása és aktiválása a költségvetési tervezési folyamat - létrehozása költségvetés-tervezési dokumentum szerint jogosultak-e a tényleges adatok a főkönyvből - hozzárendelések segítségével állítsa be a költségvetési terv dokumentumadatok - Szerkesztés költségvetési terv dokumentum adatokat az Excel programban 

<a name="prerequisites"></a>Előfeltételek 
------------------

Az oktatóanyag esetében szüksége lesz a Dynamics 365 műveletek környezet Contoso demó adatok elérésére és a példány rendszergazdaként kell építenie. A privát böngésző módban nem használja a lab - szükség esetén más fiókot a böngészőben a Kijelentkezés és a műveletek rendszergazdai hitelesítő adatok Dynamics 365 bejelentkezni. Dynamics 365 műveletek esetében történő bejelentkezéskor, **kell** a "Legyenek naplózva" jelölőnégyzetet. Ez az Excel alkalmazáshoz aktuálisan szükséges cookie-t hoz létre. Ha megkísérel bejelentkezni a Dynamics 365 műveletek nem az Internet Explorer böngészőt használ, majd kérni fogja naplózni az belül az Excel alkalmazás. Ha az Excel alkalmazásban a „Bejelentkezés” lehetőségre kattint, megnyílik egy Internet Explorer felugró ablak, a bejelentkezéskor pedig **KÖTELEZŐ** bejelölni a „Szeretnék bejelentkezve maradni” jelölőnégyzetet. Ha a „Bejelentkezés” lehetőség bejelölése az Excel alkalmazásban látszólag nem vezet eredményre, akkor törölje az Internet Explorer cookie-gyorsítótárat.

## <a name="scenario-overview"></a>**Scenario overview**
Ágnes a Contoso Szórakozási Rendszerekben (DEMF) pénzügyi vezetőjeként dolgozik Németországban. Közeleg a 2016-os pénzügyi év, és Ágnesnek be kell állítania vállalat jövő évi költségvetését. A költségvetés előkészítése az alábbiak szerint történik:

1.  Ágnes a tavalyi évi tényadatokat használja a költségvetés kiindulási pontjaként.
2.  Az előző évi tényadatok alapján létrehozza az elkövetkező év 12 hónapjára érvényes becsléseket
3.  Ágnes ezután átnézi a költségvetést a pénzügyi igazgatóval. Ezt követően végrehajtja a szükséges módosításokat a költségvetési terven, majd véglegesíti a költségvetés-készítést.

Költségvetés-tervezési eset konfigurációs séma a következőképpen néz ki:

![Screenshot1](./media/screenshot1-300x152.png)

Ágnes a következő Excel sablon segítségével elkészíti a költségvetés:

[![](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

<a name="exercise-1-configuration"></a>1. sz. feladat: Konfigurálás
=========================

## <a name="task-1-create-organizational-hierarchy"></a>**1. feladat: A szervezeti hierarchia létrehozása**
A teljes költségvetés-tervezési folyamat a pénzügyi osztályon történik, ezért Ágnesnek egy nagyon egyszerű, csak a pénzügyi osztályt érintő szervezeti hierarchiát kell létrehoznia. 1.1. Keresse meg azt a szervezeti hierarchiák (szervezet felügyelete &gt;szervezetek &gt;szervezeti hierarchiák), és kattintson az új gombra

![Screenshot3](./media/screenshot3.png) 

1.2. Írja be a nevét a szervezeti hierarchia, és kattintson a hozzárendelés célja gomb

[![Screenshot4](./media/screenshot4.png)](./media/screenshot4.png) 

1.3. Válassza ki a költségvetés-tervezési cél, kattintson a Hozzáadás gombra, és hozzárendelése az újonnan létrehozott szervezeti hierarchia: 

[![Screenshot5](./media/screenshot5.png)](./media/screenshot5.png)

1.4. Ismételje meg a fenti lépést a Biztonsági szervezeti cél kapcsán is. Ha elkészült, zárja be a képernyőt.

[![Screenshot6](./media/screenshot6.png)](./media/screenshot6.png)

1.5. Kattintson a Megtekintés gombra a Szervezeti hierarchiák képernyőn. Kattintson a Szerkesztés gombra a Hierarchiatervezőben, és kattintson a Beszúrás gombra hierarchia létrehozásához.

[![Screenshot7](./media/screenshot7.png)](./media/screenshot7.png) 

1.6. A költségvetés-tervezési hierarchiában válassza ki a Pénzügyi osztályt. 

[![Screenshot8](./media/screenshot8.png)](./media/screenshot8.png)

1.7. Ha elkészült, kattintson a Közzététel és Bezárás gombokra. Válassza a 2015.01.01-t a hierarchia-közzététel érvényességi dátumaként.

[![Screenshot9](./media/screenshot9.png)](./media/screenshot9.png)

## <a name="task-2-configure-user-security"></a>2. lépés: A felhasználói biztonság konfigurálása
A költségvetési tervadatokhoz történő hozzáférés kapcsán a költségvetés-tervezés speciális biztonsági irányelveket alkalmaz. Ágnesnek saját maga részére biztosítani szükséges a hozzáférést a költségvetési tervekhez. 2.1. DEMF jogi személy összefüggésben váltani: [![Screenshot10](./media/screenshot10.png)](./media/screenshot10.png) 2.2. Keresse meg a költségvetési &gt;a telepítő &gt;költségvetés-tervezési &gt;költségvetés-tervezési konfiguráció. A Paraméterek lap értéke biztonsági modell alapján a szervezetek biztonsági [![Screenshot11](./media/screenshot11.png)](./media/screenshot11.png) 2.3. Navigáljon a rendszerfelügyelet &gt;felhasználók &gt;felhasználók. Állítson be Rendszergazda Költségvetés-kezelő szerepkört a felhasználó (Major Ágnes) kapcsán. [![Screenshot12](./media/screenshot12.png)](./media/screenshot12.png) 2.4. Válassza ki a felhasználói szerepkört, majd a hozzárendelés szervezetek [![Screenshot13](./media/screenshot13.png)](./media/screenshot13.png)2.5. Válassza a „Hozzáférés engedélyezése adott szervezetekhez” lehetőséget. Válassza ki az első lépésben létrehozott Szervezeti hierarchiát. Válasszon késedelmi csomópont és gyermekek gombbal kattintson a támogatás ***fontos!*** *– Legyen arra, hogy a jogi személy DEMF összefüggésben a feladat végrehajtásakor, szervezeti szintű biztonsági alkalmazandó jogi személyenként*[![Screenshot14](./media/screenshot14.png)](./media/screenshot14.png)

## <a name="task-3-create-scenarios"></a>3. lépés: Változatok létrehozása
3.1. Keresse meg a költségvetési&gt;a telepítő &gt;költségvetés-tervezési &gt;költségvetés-tervezési konfiguráció. Jegyezze meg a Változatok lapon a jelen oktatóanyagban a továbbiakban használt változatok nevét: Előző évi tényadatok, illetve Költségvetési. *Megjegyzés: Ha szeretné, hozhat létre, illetve használhat a jelen feladathoz új változatokat is.* [![Screenshot15](./media/screenshot15.png)](./media/screenshot15.png)*Megjegyzés: Júlia hivatalos jóváhagyási folyamat nem használja a költségvetés elkészítése azt kihagyja a szakaszok, a munkafolyamatok és munkafolyamat-szakaszok beállítása a laboratóriumában és fogja használni a meglévő telepítés – automatikus jóváhagyási munkafolyamata. Lásd a munkafolyamat-konfiguráció.*

## <a name="task-4-create-budget-plan-columns"></a>4. lépés: Költségvetésiterv-oszlopok létrehozása
A költségvetésiterv-oszlopok a költségvetés-tervezési dokumentum elrendezésben felhasználható pénzügyi vagy mennyiségalapú oszlopok lehetnek. A jelen példában létre kell hoznunk egy oszlopot az Előző évi tényadatokhoz, valamint 12 oszlopot a költségvetési év hónapjaihoz. Az oszlopok létrehozása történhet a Hozzáadás gomb megnyomása, illetve az értékek kitöltése útján, vagy egy Adatentitás segítségével. A jelen oktatóanyagban Adatentitás segítségével töltjük ki az értékeket. 4.1. A költségvetési&gt;a telepítő &gt;költségvetés-tervezési &gt;költségvetési tervezési konfigurációs oszlopok lap megnyitása. A képernyő jobb felső sarkában lévő Office gombra, és válassza ki az oszlopokat (szűrés) [![Screenshot16](./media/screenshot16.png)](./media/screenshot16.png) 4.2. A rendszer megnyit egy, az értékek feltöltéséhez használandó Excel-munkafüzetet. Ha a rendszer kéri, kattintson a szerkesztésének engedélyezése, és megbízik az alkalmazás [![Screenshot18](./media/screenshot18.png)](./media/screenshot18.png)[![Screenshot17](./media/screenshot17.png)](./media/screenshot17.png) 4.3. További oszlopok kitöltése az értékeket fel kell. A Tervezés gombra kattintva felveheti az oszlopot a rács a jobb oldali ablaktáblában: [![Screenshot19](./media/screenshot19.png)](./media/screenshot19.png) 4.4. Elérhető oszlopok hozzáadása a rács megjelenítéséhez PlanColumns mellett kevés ceruza gombra [![Screenshot20](./media/screenshot20.png)](./media/screenshot20.png) 4.5. Kattintson duplán a kijelölt mezők hozzáadása őket, és kattintson a frissítés gombra minden rendelkezésre álló mezőben [![Screenshot21](./media/screenshot21.png)](./media/screenshot21.png) 4.6. Adja hozzá a létrehozni szükséges oszlopokat az Excel-táblában. Sorok az Excelben történő gyors hozzáadásához használja az Automatikus kitöltés funkciót. Ellenőrizze, hogy a sorok a táblázat részeként kerülnek (függőleges görgetősáv használatakor meg kell látni a rács tetején található oszlopfejlécek) [![Screenshot22](./media/screenshot22.png)](./media/screenshot22.png) 4.7. Dynamics 365 műveletekhez való visszatéréshez, és frissítse a lapot. Dynamics 365 műveletek közzétett értékeket fog megjelenni. [![Screenshot23](./media/screenshot23.png)](./media/screenshot23.png)

## <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>5. lépés: Költségvetési-tervezési dokumentum elrendezések és sablonok létrehozása
Az elrendezés azt határozza meg, hogy hogyan nézzen ki a költségvetési-tervezési dokumentum soraiból felépülő rács, amikor a felhasználó megnyitja a költségvetés-tervezési dokumentumot. Válthat is a különféle költségvetés-tervezési dokumentum elrendezések között, hogy megnézze, az adatok hogyan mutatnak a különféle elrendezésekben. Most, hogy már meghatároztuk a költségvetés-tervezési dokumentumban használandó oszlopokat, Ágnesnek létre kell hoznia egy, a költségvetési adatok létrehozásához használt Excel-táblázathoz hasonló költségvetési-tervezési dokumentum elrendezést (lásd az oktatóanyag A változatok áttekintése c. szakaszát) 5.1. A költségvetési&gt;a telepítő &gt;költségvetés-tervezési &gt;költségvetési tervezési konfigurációs elrendezés lap megnyitása. Hozzon létre egy új elrendezést a Havi költségvetési tételhez:

-   Válassza ki, hogy melyik MA és BU dimenziókészlet tartalmazza az elrendezés Fő számláit és Üzleti egységeit.
-   Listázza ki az előző lépésben, az Összetevők szakaszban létrehozott összes költségvetésiterv-oszlopot. Az Előző év tényadatai kivételével állítson minden mást szerkeszthetőre.
-   Kattintson a Leírások gombra annak kiválasztása érdekében, hogy mely pénzügyi dimenziók jelenjenek meg Leírásokat a rácsban.

[![Screenshot24](./media/screenshot24.png)](./media/screenshot24.png) alapján a költségvetési terv azt hozhat létre egy alternatív módot költségvetési adatok szerkesztése, használható egy Excel-sablon elrendezésének meghatározása. Mivel az Excel-sablonnak meg kell egyeznie a meghatározott költségvetési terv elrendezésével, az Excel-sablon létrehozása után nem fogja tudni szerkeszteni a költségvetési terv elrendezését, így ezt a feladatot csak az elrendezés összes részelemének meghatározása után végezze el. 5.2. Az elrendezés létrehozása az 5.1. Lépés, sablon gombra &gt;létrehozása. Hagyja jóvá a figyelmeztető üzenet. A sablon megtekintéséhez kattintson a sablon &gt;megtekintése. *Megjegyzés: Ügyeljünk arra, hogy válassza ki a "Mentés másként", és jelölje ki a helyet, ahol sablon szerkesztéséhez meg kell tárolni. Ha a felhasználó kiválasztja a "Megnyitás" mentés nélkül a párbeszédpanelen, a fájlon végrehajtott változtatások nem maradnak meg a fájl bezárásakor.* [![Screenshot25](./media/screenshot25.png)](./media/screenshot25.png) 5.3. &lt;Nem kötelező lépés&gt; megjelenését módosíthatjuk több felhasználó rövid – módosítása az Excel sablon hozzáadása teljes képletek, üzenetfejléc-mezők, formázás, stb. A változtatások mentéséhez és a költségvetési terv elrendezés elrendezés gombra kattintva a fájlt feltölteni &gt;feltöltése [![Screenshot26](./media/screenshot26.png)](./media/screenshot26.png)

## <a name="task-6-create-a-budget-planning-process"></a>6. lépés: Költségvetés-tervezési folyamat létrehozása
Ahhoz, hogy el tudja kezdeni kitölteni a költségvetési terveket, Ágnesnek létre kell hoznia és aktiválnia kell az összes fenti beállításra kiterjedő új költségvetés-tervezési folyamatot. A Költségvetés-tervezési folyamat határozza meg, hogy milyen költségvetési szervezetek, munkafolyamatok, elrendezések és sablonok kerülnek felhasználásra a költségvetési tervek létrehozásakor. 6.1. Keresse meg a költségvetési &gt;a telepítő &gt;költségvetés-tervezési &gt;költségvetés-tervezési folyamat, és hozzon létre egy új rekordot.

-   Költségvetés-tervezési folyamat – Költségvetés készítése a DEMF 2016-os pénzügyi évére
-   Költségvetési ciklus – 2016-os pénzügyi év
-   Főkönyv – DEMF
-   Alapértelmezett számlastruktúra – Gyártási eredmény
-   Szervezeti hierarchia – válassza ki az oktatóanyag elején létrehozott hierarchiát
-   Költségvetés-tervezési munkafolyamat – rendelje hozzá a Pénzügyi osztály kapcsán az Automatikus munkafolyamat-jóváhagyást
-   A költségvetés-tervezési szakasz szabályai és sablonjai lehetőségnél, minden egyes munkafolyamat Költségvetés-tervezési szakasz kapcsán válassza ki, hogy engedélyezi-e a Sorok hozzáadása és Sorok módosítása lehetőséget, illetve hogy mi legyen az alapértelmezett Elrendezés

*Megjegyzés: Létrehozhat további dokumentumelrendezéseket is, és azokat, az Alternatív elrendezések gomb segítségével hozzárendelheti a rendelkezésre álló költségvetés-tervezési munkafolyamat szakaszhoz.* [![Screenshot27](./media/screenshot27.png)](./media/screenshot27.png) 6.2. Válassza a műveletek &gt;aktiválása ehhez a költségvetés-tervezési munkafolyamat az aktiválás [![Screenshot28](./media/screenshot28.png)](./media/screenshot28.png)

<a name="exercise-2-process-simulation"></a>2. sz. feladat: Folyamat-szimuláció
==============================

## <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>7. lépés: Kezdeti adatok létrehozása a költségvetési tervhez a Főkönyvből
7.1. Keresse meg a költségvetési &gt;időszakos &gt;költségvetési terv létrehozása a főkönyvből. Töltse ki az időszaki folyamat paramétereit, majd kattintson a Létrehozás gombra. [![Screenshot29](./media/screenshot29.png)](./media/screenshot29.png) 7.2. Keresse meg a költségvetési &gt;költségvetési tervek létrehozása folyamat által létrehozott költségvetési terv kereséséhez. [![Screenshot30](./media/screenshot30.png)](./media/screenshot30.png) 7.3. A Dokumentumszám hivatkozásra kattintva nyissa meg a dokumentum részleteit. Költségvetési terv megjelenik az elrendezés létrehozása során a lab meghatározott [![Screenshot31](./media/screenshot31.png)](./media/screenshot31.png)

## <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>8. lépés: Tárgyévi költségvetés létrehozása az előző évi tényadatok alapján
Felosztási módszerek a költségvetési tervben történő felhasználásával egyszerűen átmásolhatja a költségvetési tervhez használandó információkat az egyik változatból a másikba/ azokat eloszthatja egy adott időszakra/ feloszthatja dimenziókhoz. A felosztások segítségével hozzuk létre a tárgyévi költségvetést az előző év tényadatokból. 8.1. Minden sor kiválasztása a költségvetési terv dokumentumrács és gombra költségvetés felosztása [![Screenshot32](./media/screenshot32.png)](./media/screenshot32.png) 8.2. Jelölje ki a felosztási módszert, az időszaki kulcs, forrás és cél forgatókönyvek, és kattintson a hozzárendelés 

[![Screenshot33](./media/screenshot33.png)](./media/screenshot33.png)

Előző év tényleges összegek bemásolja a folyó évi költségvetés és értékesítési görbe időszaki kulcs használatával időszakok közötti felosztás őket. 

[![Screenshot34](./media/screenshot34.png)](./media/screenshot34.png)

## <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>9. lépés: Módosítsa a költségvetés-tervezési dokumentumot az Excel segítségével, majd véglegesítse a dokumentumot
9.1. Kattintson a gombra munkalapot az Excel programban nyissa meg a dokumentum tartalma

[![Screenshot35](./media/screenshot35.png)](./media/screenshot35.png)

9.2. Az Excel-munkafüzet megnyitása után módosítsa a költségvetés-tervezési dokumentum számadatait, majd kattintson a Közzététel gombra.

[![Screenshot36](./media/screenshot36.png)](./media/screenshot36.png)

9.3. Költségvetés-tervezési dokumentum Dynamics 365 műveletekhez vissza. Kattintson a munkafolyamat &gt;a dokumentum automatikus jóváhagyására elküldése

[![Screenshot37](./media/screenshot37.png)](./media/screenshot37.png) 

A munkafolyamat befejeztét követően jóváhagyott költségvetés-tervezési dokumentum szakasza változik. [![Screenshot38](./media/screenshot38.png)](./media/screenshot38.png)

<a name="appendix"></a>Melléklet
========

### <a name="auto-approve-workflow-configuration"></a>Munkafolyamat-konfiguráció automatikus jóváhagyása

A. Költségvetés &gt;a telepítő &gt;költségvetés-tervezési &gt;költségvetési munkafolyamatok, hozzon létre egy új munkafolyamat-sablon költségvetés-tervezési munkafolyamatok használatával:

[![Screenshot39](./media/screenshot39.png)](./media/screenshot39.png)

A munkafolyamat csak egy feladat – a költségvetési terv szakaszváltása fogja tartalmazni. 

[![Screenshot40](./media/screenshot40.png)](./media/screenshot40.png) 

Mentse, majd aktiválja a munkafolyamatot. 

B. Keresse meg a költségvetési &gt;a telepítő &gt;költségvetés-tervezési &gt;költségvetés-tervezési konfiguráció. A szakaszok lapon hozzon létre 2 szakaszában – kezdeti és elküldve 

[![Screenshot41](./media/screenshot41.png)](./media/screenshot41.png)

C-ON. Keresse meg a költségvetési &gt;a telepítő &gt;költségvetés-tervezési &gt;költségvetés-tervezési konfiguráció. A munkafolyamat-szakaszok lapon a munkafolyamat automatikus társításához – jóváhagyja a kezdeti és elküldve fázisból egy lépésben létrehozott 

[![Screenshot42](./media/screenshot42.png)](./media/screenshot42.png)  


