---
title: Költségvetés-tervezés
description: Az oktatóanyag célja, hogy betekintést nyújtson a Microsoft Dynamics 365 Finance költségvetés tervező részének frissített funkcióiba. Ezen oktatóanyag célja, hogy illusztrálja a költségvetés tervező modul egy gyors konfigurációs példáját, valamint bemutassa, hogyan vihető véghez a költségvetés tervezés ennek a konfigurációnak a használatával.
author: ShylaThompson
manager: AnnBe
ms.date: 06/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec62af4ec62de0d63b590c79db6a8164d59e72c4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971278"
---
# <a name="budget-planning"></a>Költségvetés-tervezés

[!include [banner](../includes/banner.md)]

Az oktatóanyag célja, hogy betekintést nyújtson a Microsoft Dynamics 365 Finance költségvetés tervező részének frissített funkcióiba. Ezen oktatóanyag célja, hogy illusztrálja a költségvetés tervező modul egy gyors konfigurációs példáját, valamint bemutassa, hogyan vihető véghez a költségvetés tervezés ennek a konfigurációnak a használatával.  Ez a labor az alábbi üzleti folyamatokra és feladatokra fókuszál:
- Költségvetés-tervezési és felhasználóbiztonsági konfigurálási célra szervezeti hierarchia létrehozása
- Költségvetési terv esetek, költségvetési terv oszlopok, elrendezések és Excel sablonok meghatározása
- Költségvetés-tervezési folyamat létrehozása és aktiválása
- Költségvetés-tervezési dokumentum létrehozása tényleges adatok lekérésével a főkönyvből
- A felosztások segítségével módosítsa a költségvetési terv dokumentumadatokat
- Az Excel programban a költségvetési terv dokumentum adatainak szerkesztése 

<a name="prerequisites"></a>Előfeltételek 
------------------

A jelen oktatóanyaghoz a Microsoft Dynamics 365 Finance környezetet Contoso bemutatóadatokkal kell elérnie, és a példányra vonatkozóan rendszergazdai hozzáférés szükségessel kell rendelkeznie. Az oktatóanyag kapcsán ne használja a Privát böngészőmód beállítást - szükség esetén jelentkezzen ki az eltérő böngészőfiókból, majd jelentkezzen be rendszergazda adatokkal. A bejelentkezéskor **KÖTELEZŐ** bejelölni a „Szeretnék bejelentkezve maradni” jelölőnégyzetet. Ez az Excel alkalmazáshoz aktuálisan szükséges cookie-t hoz létre. Ha Internet Explorertől eltérő böngészővel bejelentkezik be az alkalmazásba, a rendszer arra kéri majd, hogy jelentkezzen be az Excel alkalmazás segítségével. Ha az Excel alkalmazásban a „Bejelentkezés” lehetőségre kattint, megnyílik egy Internet Explorer felugró ablak, a bejelentkezéskor pedig **KÖTELEZŐ** bejelölni a „Szeretnék bejelentkezve maradni” jelölőnégyzetet. Ha a „Bejelentkezés” lehetőség bejelölése az Excel alkalmazásban látszólag nem vezet eredményre, akkor törölje az Internet Explorer cookie-gyorsítótárat.

## <a name="scenario-overview"></a>**Eset áttekintése**
Ágnes a Contoso Szórakozási Rendszerekben (DEMF) pénzügyi vezetőjeként dolgozik Németországban. Közeleg a 2016-os pénzügyi év, és Ágnesnek be kell állítania vállalat jövő évi költségvetését. A költségvetés előkészítése az alábbiak szerint történik:

1.  Ágnes a tavalyi évi tényadatokat használja a költségvetés kiindulási pontjaként.
2.  Az előző évi tényadatok alapján létrehozza az elkövetkező év 12 hónapjára érvényes becsléseket
3.  Ágnes ezután átnézi a költségvetést a pénzügyi igazgatóval. Ezt követően végrehajtja a szükséges módosításokat a költségvetési terven, majd véglegesíti a költségvetés-készítést.

A költségvetés-tervezési eset konfigurációs sémája a következőképpen néz ki a forgatókönyvnél:

![Költségvetés-tervezési konfigurációs séma megtekintése](./media/screenshot1-300x152.png)

Ágnes a következő Excel-sablon segítségével készíti a költségvetést:

[![Excel-sablon](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

## <a name="exercise-1-configuration"></a>1. sz. feladat: Konfigurálás

### <a name="task-1-create-organizational-hierarchy"></a>**1. lépés: Szervezeti hierarchia létrehozása**
A teljes költségvetés-tervezési folyamat a pénzügyi osztályon történik, ezért Ágnesnek egy nagyon egyszerű, csak a pénzügyi osztályt érintő szervezeti hierarchiát kell létrehoznia. 

1.1. Lépjen a Szervezeti hierarchiák részre (Szervezeti adminisztráció &gt; Szervezetek &gt; Szervezeti hierarchiák), majd kattintson az Új gombra.

![Szervezeti hierarchiák](./media/screenshot3.png) 

1.2. Írja be a szervezeti hierarchia nevét a Név mezőbe, majd kattintson a Cél hozzárendelése gombra.

1.3. Válassza ki a Költségvetés-tervezési célt, kattintson a Hozzáadás gombra, és rendelje hozzá az újonnan létrehozott szervezeti hierarchiát. 

[![Cél hozzárendelése](./media/screenshot5.png)](./media/screenshot5.png)

1.4. Ismételje meg a fenti lépést a Biztonsági szervezeti cél esetében is. Ha elkészült, zárja be a képernyőt.

1.5. Kattintson a Megtekintés gombra a Szervezeti hierarchiák képernyőn. Kattintson a Szerkesztés gombra a Hierarchiatervezőben, és hierarchia létrehozásához kattintson a Beszúrás gombra.

[![Beszúrás](./media/screenshot7.png)](./media/screenshot7.png) 

1.6. A költségvetés-tervezési hierarchiában válassza ki a Pénzügyi osztályt. 

[![Pénzügy](./media/screenshot8.png)](./media/screenshot8.png)

1.7. Ha elkészült, kattintson a Közzététel és bezárás elemre. Válassza a 2015.01.01. dátumot a hierarchia-közzététel érvénybe lépési dátumaként.

[![Érvényesség dátuma](./media/screenshot9.png)](./media/screenshot9.png)

### <a name="task-2-configure-user-security"></a>2. lépés: A felhasználói biztonság konfigurálása
A költségvetési tervadatokhoz történő hozzáférés kapcsán a költségvetés-tervezés speciális biztonsági irányelveket alkalmaz. Ágnesnek saját maga részére biztosítani szükséges a hozzáférést a költségvetési tervekhez. 

2.1. Váltson a DEMF jogi személlyel kapcsolatos szövegkörnyezetre. 


2.2. Lépjen a következőhöz: Költségvetés-készítés &gt; Beállítás &gt; Költségvetés-tervezés &gt; Költségvetés-tervezési konfiguráció. A Paraméterek lapon állítsa be a Biztonsági modell beállítást A biztonsági szervezetek alapján értékre. 

[![Paraméterek](./media/screenshot11.png)](./media/screenshot11.png) 

2.3. Lépjen a következőhöz: Rendszerfelügyelet &gt; Felhasználók &gt; Felhasználók. Állítson be Rendszergazda Költségvetés-kezelő szerepkört a felhasználó (Major Ágnes) kapcsán. 

[![Költségvetés-kezelő](./media/screenshot12.png)](./media/screenshot12.png) 

2.4. Válassza ki a felhasználói szerepkört, majd kattintson a Szervezetek hozzárendelése lehetőségre. 

[![Szervezetek hozzárendelése](./media/screenshot13.png)](./media/screenshot13.png)

2.5. Válassza a „Hozzáférés engedélyezése adott szervezetekhez” lehetőséget. Válassza ki az első lépésben létrehozott Szervezeti hierarchiát. Válassza ki a Pénzügyi csomópontot, majd kattintson a Hozzáférés biztosítása gyermekelemekkel együtt gombra. 

**_Fontos!_* _ _Győződjön meg arról, hogy a lépést a DEMF jogi személyre vonatkozó szövegkörnyezetben hajtsa végre, mivel a Szervezeti biztonsági beállítás az adott jogi személyre vonatkozik* 

### <a name="task-3-create-scenarios"></a>3. lépés: Változatok létrehozása
3.1. Lépjen a következőhöz: Költségvetés-készítés&gt;Beállítás &gt; Költségvetés-tervezés &gt; Költségvetés-tervezési konfiguráció. Jegyezze meg a Változatok lapon a jelen oktatóanyagban a továbbiakban használt változatok nevét: Előző évi tényadatok, illetve Költségvetési. 

*Megjegyzés: Ha szeretné, hozhat létre, illetve használhat a jelen feladathoz új változatokat is.* 

[![Új esetek](./media/screenshot15.png)](./media/screenshot15.png) 

*Megjegyzés: Ágnes nem hivatalos jóváhagyási folyamat keretében készíti el a költségvetést, így kihagyjuk a jelen oktatóanyaghoz beállított Munkafolyamatokat, Szakaszokat, illetve a Munkafolyamat szakaszok beállítását, és helyettük az automatikus munkafolyamat-jóváhagyási beállítást fogjuk alkalmazni. A munkafolyamat-konfiguráció kapcsán lásd a mellékletet.*

### <a name="task-4-create-budget-plan-columns"></a>4. lépés: Költségvetésiterv-oszlopok létrehozása
A költségvetésiterv-oszlopok a költségvetés-tervezési dokumentum elrendezésben felhasználható pénzügyi vagy mennyiségalapú oszlopok lehetnek. A jelen példában létre kell hoznunk egy oszlopot az Előző évi tényadatokhoz, valamint 12 oszlopot a költségvetési év hónapjaihoz. Az oszlopok létrehozása történhet a Hozzáadás gomb megnyomása, illetve az értékek kitöltése útján, vagy egy Adatentitás segítségével. A jelen oktatóanyagban Adatentitás segítségével töltjük ki az értékeket. 

4.1. Nyissa meg az Oszlopok oldalt a Költségvetés-készítés&gt;Beállítás &gt; Költségvetés-tervezés &gt; Költségvetés-tervezési konfiguráció lehetőségen belül. Kattintson a képernyő jobb felső sarkában található Office gombra, majd válassza az Oszlopok (szűrés nélkül) lehetőséget. 

[![Oszlopok szűrés nélkül](./media/screenshot16.png)](./media/screenshot16.png) 

4.2. A rendszer megnyit egy, az értékek feltöltéséhez használandó Excel-munkafüzetet. Ha szükséges, kattintson a Szerkesztés engedélyezése és a Megbízom ebben az alkalmazásban lehetőségre. 

4.3. További oszlopokra lesz szükségünk az értékek kitöltéséhez. A jobb oldali ablaktáblában a Tervezés gombra kattintva adja hozzá az oszlopokat a rácshoz. 

[![Terv](./media/screenshot19.png)](./media/screenshot19.png) 

4.4. Kattintson az Oszloptervezés melletti ceruza gombra a rácshoz adható oszlopok megtekintéséhez. 

[![Szerkesztés](./media/screenshot20.png)](./media/screenshot20.png) 

4.5. Kattintson duplán a rendelkezésre álló mezőre, hogy azt a rendszer hozzáadja a Kiválasztott mezőkhöz, majd kattintson a Frissítés lehetőségre. 

4.6. Adja hozzá a létrehozni kívánt oszlopokat az Excel-táblában. A sorok Excelben történő gyors hozzáadásához használja az Automatikus kitöltés funkciót. Győződjön meg arról, hogy a sorok a tábla részeként kerülnek hozzáadásra (a függőleges görgetősáv használata esetén oszlopfejléceknek kell megjelenniük a rács tetején). 

4.7. Térjen vissza az alkalmazásba, és frissítse az oldalt. A közzétett értékek jelennek meg. 

[![Újratöltés](./media/screenshot23.png)](./media/screenshot23.png)

### <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>5. lépés: Költségvetési-tervezési dokumentum elrendezések és sablonok létrehozása
Az elrendezés azt határozza meg, hogy hogyan nézzen ki a költségvetési-tervezési dokumentum soraiból felépülő rács, amikor a felhasználó megnyitja a költségvetés-tervezési dokumentumot. Válthat is a különféle költségvetés-tervezési dokumentum elrendezések között, hogy megnézze, az adatok hogyan mutatnak a különféle elrendezésekben. Most, hogy már meghatároztuk a költségvetés-tervezési dokumentumban használandó oszlopokat, Ágnesnek létre kell hoznia egy, a költségvetési adatok létrehozásához használt Excel-táblázathoz hasonló költségvetési-tervezési dokumentum elrendezést (lásd az oktatóanyag A változatok áttekintése c. szakaszát) 

5.1. Nyissa meg az Elrendezések oldalt a Költségvetés-készítés&gt;Beállítás &gt; Költségvetés-tervezés &gt; Költségvetés-tervezési konfiguráció lehetőségen belül. Hozzon létre egy új elrendezést a Havi költségvetési tételhez:

-   Válassza ki, hogy melyik MA és BU dimenziókészlet tartalmazza az elrendezés Fő számláit és Üzleti egységeit.
-   Listázza ki az előző lépésben, az Összetevők szakaszban létrehozott összes költségvetésiterv-oszlopot. Az Előző év tényadatai kivételével állítson minden mást szerkeszthetőre.
-   Kattintson a Leírások gombra annak kiválasztása érdekében, hogy mely pénzügyi dimenziók jelenjenek meg Leírásokat a rácsban.

[![Leírások](./media/screenshot24.png)](./media/screenshot24.png) 

A költségvetési terv elrendezés alapján létre tud hozni egy Excel-sablont, ami alternatív megoldást kínál a Költségvetési adatok szerkesztésére. Mivel az Excel-sablonnak meg kell egyeznie a meghatározott költségvetési terv elrendezésével, az Excel-sablon létrehozása után nem fogja tudni szerkeszteni a költségvetési terv elrendezését, így ezt a feladatot csak az elrendezés összes részelemének meghatározása után végezze el. 

5.2. Az 5.1. lépésben létrehozott elrendezéshez kattintson a Sablon &gt; Létrehozás gombra. Hagyja jóvá a figyelmeztető üzenet. A sablon megtekintéséhez kattintson a Sablon &gt; Megtekintés lehetőségre. 

*Megjegyzés: ügyeljen arra, hogy a „Mentés másként” elemet válassza, és jelölje ki a helyet, ahol sablon a szerkesztéséhez tárolásra kerül. Ha a felhasználó mentés nélkül a „Megnyitás” elemet választja a párbeszédpanelen, a fájlon végrehajtott változtatások nem maradnak meg a fájl bezárásakor.* 
[![Sablonnézet](./media/screenshot25.png)](./media/screenshot25.png) 

5.3. &lt; Opcionális lépés&gt; Módosítsa az Excel-sablont úgy, hogy felhasználóbarátabb legyen: adjon hozzá összesítő képleteket, fejlécmezőket, formázást stb. Mentse a módosításokat, majd töltse fel a fájlt a költségvetésiterv-elrendezésbe a következő lehetőség segítségével: Elrendezés &gt; Feltöltés. 


### <a name="task-6-create-a-budget-planning-process"></a>6. lépés: Költségvetés-tervezési folyamat létrehozása
Ahhoz, hogy el tudja kezdeni kitölteni a költségvetési terveket, Ágnesnek létre kell hoznia és aktiválnia kell az összes fenti beállításra kiterjedő új költségvetés-tervezési folyamatot. A Költségvetés-tervezési folyamat határozza meg, hogy milyen költségvetési szervezetek, munkafolyamatok, elrendezések és sablonok kerülnek felhasználásra a költségvetési tervek létrehozásakor. 

6.1. Lépjen a következő részre: Költségvetés készítése &gt; Beállítás &gt; Költségvetés-tervezés &gt; Költségvetés-tervezési folyamat, majd hozzon létre új rekordot.

-   Költségvetés-tervezési folyamat – Költségvetés készítése a DEMF 2016-os pénzügyi évére
-   Költségvetési ciklus – 2016-os pénzügyi év
-   Főkönyv – DEMF
-   Alapértelmezett számlastruktúra – Gyártási eredmény
-   Szervezeti hierarchia – válassza ki az oktatóanyag elején létrehozott hierarchiát
-   Költségvetés-tervezési munkafolyamat – rendelje hozzá a Pénzügyi osztály kapcsán az Automatikus munkafolyamat-jóváhagyást
-   A költségvetés-tervezési szakasz szabályai és sablonjai lehetőségnél, minden egyes munkafolyamat Költségvetés-tervezési szakasz kapcsán válassza ki, hogy engedélyezi-e a Sorok hozzáadása és Sorok módosítása lehetőséget, illetve hogy mi legyen az alapértelmezett Elrendezés

*Megjegyzés: Létrehozhat további dokumentumelrendezéseket is, és azokat, az Alternatív elrendezések gomb segítségével hozzárendelheti a rendelkezésre álló költségvetés-tervezési munkafolyamat szakaszhoz.* 

[![Alternatív elrendezések](./media/screenshot27.png)](./media/screenshot27.png) 

6.2. Válassza a Műveletek &gt; Aktiválás lehetőséget a jelen költségvetés-tervezési munkafolyamat aktiválásához. 

[![Aktiválás](./media/screenshot28.png)](./media/screenshot28.png)

## <a name="exercise-2-process-simulation"></a>2. sz. feladat: Folyamat-szimuláció

### <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>7. lépés: Kezdeti adatok létrehozása a költségvetési tervhez a Főkönyvből
7.1. Lépjen a következőhöz: Költségvetés készítése &gt; Időszakos &gt; Költségvetési terv létrehozása Főkönyvből. Töltse ki az időszaki folyamat paramétereit, majd kattintson a Létrehozás gombra. 

7.2. A Létrehozás folyamat során elkészített költségvetési terv megkereséshez lépjen a Költségvetés készítése &gt; Költségvetési tervek lehetőséghez. 

[![Költségvetési terv](./media/screenshot30.png)](./media/screenshot30.png) 

7.3. A Dokumentumszám hivatkozásra kattintva nyissa meg a dokumentum részleteit. Megjelenik a jelen oktatóanyag során létrehozott elrendezés szerinti költségvetési terv. 

[![Költségvetési terv megjelenítése](./media/screenshot31.png)](./media/screenshot31.png)

### <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>8. lépés: Tárgyévi költségvetés létrehozása az előző évi tényadatok alapján
Felosztási módszerek a költségvetési tervben történő felhasználásával egyszerűen átmásolhatja a költségvetési tervhez használandó információkat az egyik változatból a másikba/ azokat eloszthatja egy adott időszakra/ feloszthatja dimenziókhoz. A felosztások segítségével hozzuk létre a tárgyévi költségvetést az előző év tényadatokból. 

8.1. Válassza ki a költségvetés-tervezési dokumentumrács összes sorát, majd kattintson a Költségvetés felosztása elemre. 

[![Minden sor](./media/screenshot32.png)](./media/screenshot32.png) 

8.2. Jelölje ki a felosztási módot, az időszaki kulcsot, a forrás- és célforgatókönyveket, és kattintson a Hozzárendelés elemre. 

[![Felosztás](./media/screenshot33.png)](./media/screenshot33.png)

A rendszer átmásolja az előző évi tényleges összegeket a tárgyévi költségvetésbe, és – az Értékesítési görbe időszaki kulcs segítségével – felosztja azt az adott időszakokra. 

[![Értékesítési görbe](./media/screenshot34.png)](./media/screenshot34.png)

### <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>9. lépés: Módosítsa a költségvetés-tervezési dokumentumot az Excel segítségével, majd véglegesítse a dokumentumot
9.1. A dokumentum tartalmának Excelben való megnyitásához kattintson a Munkalap gombra.

9.2. Az Excel-munkafüzet megnyitása után módosítsa a költségvetési terv dokumentumának számadatait, majd kattintson a Közzététel gombra.

9.3. Visszatérés a költségvetési terv dokumentumhoz. Kattintson a Munkafolyamat &gt; Elküldés elemre a dokumentum automatikus jóváhagyásához.

[![Automatikus jóváhagyás](./media/screenshot37.png)](./media/screenshot37.png) 

A munkafolyamat befejezését követően a jóváhagyott költségvetés-tervezési dokumentum állapota Jóváhagyottra változik. [![Engedélyezve](./media/screenshot38.png)](./media/screenshot38.png)

## <a name="appendix"></a>Melléklet

### <a name="auto-approve-workflow-configuration"></a>Munkafolyamat-konfiguráció automatikus jóváhagyása

A. Költségvetés- &gt; Beállítás &gt; Költségvetés-tervezés &gt; Költségvetési munkafolyamatok. Új munkafolyamat létrehozása a sablon költségvetés-tervezési munkafolyamataival:

[![Új munkafolyamat létrehozása](./media/screenshot39.png)](./media/screenshot39.png)

A munkafolyamat csak egy feladatot fog tartalmazni – Költségvetési terv szakaszváltása. 

[![Költségvetési terv szakaszváltása](./media/screenshot40.png)](./media/screenshot40.png) 

Mentse és aktiválja a munkafolyamatot. 

B. Lépjen a következőhöz: Költségvetés-készítés &gt; Beállítás &gt; Költségvetés-tervezés &gt; Költségvetés-tervezési konfiguráció. A Szakaszok lapon hozzon létre 2 szakaszt – Kezdeti és Elküldve. 

[![Kezdeti és Elküldve](./media/screenshot41.png)](./media/screenshot41.png)

C. Lépjen a következőhöz: Költségvetés-készítés &gt; Beállítás &gt; Költségvetés-tervezés &gt; Költségvetés-tervezési konfiguráció. A Munkafolyamat szakaszai lapon társítsa az A. lépésben létrehozott Automatikus – jóváhagyást a Kezdeti és Elküldve szakaszhoz.

[![Költségvetés és költségvetés-tervezés](./media/screenshot42.png)](./media/screenshot42.png)  



