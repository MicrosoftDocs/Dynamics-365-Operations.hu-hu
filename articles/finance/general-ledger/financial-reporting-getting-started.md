---
title: Pénzügyi jelentéskészítés – áttekintés
description: Ez a témakör azt ismerteti, hol érheti el a Microsoft Dynamics 365 Finance pénzügyi jelentéseit, és hogyan használhatja a pénzügyi jelentési képességeket.
author: aprilolson
ms.date: 07/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1fbdab1f4f81bbdb8b0b5cb3e6a5237196d7dc76
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983977"
---
# <a name="get-started-with-financial-reporting"></a>Első lépések a Pénzügyi jelentéskészítéssel 

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hol érheti el a Pénzügyi jelentéseket, és hogyan használhatja a pénzügyi jelentési szolgáltatásokat. Emellett az elérhető alapértelmezett pénzügyi jelentések leírását is tartalmazza.

## <a name="accessing-financial-reporting"></a>Pénzügyi jelentéskészítés elérése

A **Pénzügyi jelentéskészítés** menüt a következő helyen találhatja meg:

- **Főkönyv** &gt; **Lekérdezések és jelentések**
- **Költségvetés készítése** &gt; **Lekérdezések és jelentések** &gt; **Alapvető költségvetés-tervezés**
- **Költségvetés készítése** &gt; **Lekérdezések és jelentések** &gt; **Költségvetés-tervezés**
- **Költségvetés készítése** &gt; **Lekérdezések és jelentések** &gt; **Költségvetés-ellenőrzés**
- Konszolidációk

Ha pénzügyi jelentést szeretne létrehozni és generálni egy jogi személy számára, be kell állítania a következő adatokat az adott jogi személyhez:

- Pénzügyi naptár
- Ledger
- Számlatükör
- Pénznem
- Tranzakció feladása legalább egy számlára
- A MainAccount a **Financial Reporting beállítása** lehetőség (**Főkönyv > Főkönyv beállítása > Financial Reporting beállítása**) **Kijelölve** oszlopában van felsorolva.

## <a name="granting-security-access-to-financial-reporting"></a>Biztonsági hozzáférés biztosítása a Financial Reporting szolgáltatáshoz

A pénzügyi jelentéskészítő funkciók azon felhasználók számára érhetők el, amelyek megfelelő jogosultságokkal és kiadott feladatokkal rendelkeznek a biztonsági szerepkörüknek megfelelően. Az alábbi szakaszok tartalmazzák ezen jogosultságok és feladatkörök listáját, valamint a kapcsolódó szerepköröket.

### <a name="duties"></a>Feladatkör

| Adó címke                            | Leírás                                                             | AOT neve                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Pénzügyi jelentések biztonságának karbantartása | Pénzügyi jelentések biztonságának karbantartása és felügyeleti feladatok végrehajtása. | PénzügyiJelentésekBiztonságánakKarbantartása |
| Pénzügyi jelentések karbantartása            | Pénzügyi jelentések tervezése és karbantartása.                                  | PénzügyiJelentésekKarbantartása         |
| Pénzügyi jelentések létrehozása            | Pénzügyi jelentések létrehozása és frissítése.                                 | PénzügyiJelentésekLétrehozása         |
| Pénzügyi teljesítmény ellenőrzése          | Pénzügyi teljesítmény ellenőrzése és elemzése.                               | PénzügyiJelentésekTeljEllenőrzése       |

### <a name="privileges"></a>Jogosultságok

| Jogosultság címkéje                       | Leírás                                                             | AOT neve                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Pénzügyi jelentések biztonságának karbantartása | Pénzügyi jelentések biztonságának karbantartása és felügyeleti feladatok végrehajtása. | FinancialReportsSecuritySystemMaintain |
| Pénzügyi jelentések karbantartása            | Pénzügyi jelentések tervezése és karbantartása.                                  | PénzügyiJelentésekKarbantartása  |
| Pénzügyi jelentések létrehozása            | Pénzügyi jelentések létrehozása és frissítése.                                 | PénzügyiJelentésekLétrehozása  |
| Pénzügyi jelentések megtekintése                | Pénzügyi jelentések megtekintése.                                                 | PénzügyiJelentésekMegtekintése             |

### <a name="roles"></a>Szerepkörök

| Jogosultság címkéje                       | Kötelesség                                  | Szerepkörök                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Pénzügyi jelentések biztonságának karbantartása | Pénzügyi jelentések biztonságának karbantartása | Biztonsági rendszergazda                                                          |
| Pénzügyi jelentések karbantartása            | Pénzügyi jelentések karbantartása            | Főkönyvelő, számviteli felügyelő, pénzügyi ellenőr, költségvetés-kezelő |
| Pénzügyi jelentések létrehozása            | Pénzügyi jelentések létrehozása            | Vezérigazgató, pénzügyi igazgató, könyvelő                                                            |
| Pénzügyi jelentések megtekintése                | Pénzügyi teljesítmény ellenőrzése          | Nincs hozzárendelve                                                                   |

Miután hozzáadtak egy felhasználót vagy egy szerepkör módosult, a felhasználónak el kell tudni érnie a Financial Reporting szolgáltatást néhány percen belül. 

> [!NOTE]
> A sysadmin szerepkör hozzáadódik a pénzügyi beszámoló minden szerepköréhez.

## <a name="report-deletions-and-expirations"></a>Jelentés törlése és lejárata

A jelentést generáló felhasználók törölhetik saját jelentéseiket. A **Pénzügyi jelentések biztonságának karbantartása** feladattal rendelkező felhasználók törölhetik mások jelentéseit. 

A 10.0.8-as verzióban bevezettük a lejárati dátumok koncepcióját. Egy új kötelező funkciót engedélyezük az **Összes** oldalon a funkciókezelési munkaterületen. A **Pénzügyi jelentés megőrzésével kapcsolatos irányelvek** funkcióban a következő módosítások történtek:
* Az újonnan létrehozott jelentések automatikusan meg lesznek jelölve a létrehozásuktól számított 90 napos lejárati dátummal.
* A funkció telepítése előttről származó meglévő jelentések mindegyike 90 napos lejárati időszakot kap. A dátum egy rövid időre üresen jelenhet meg, amíg a Pénzügyi jelentéskészítési szolgáltatás fut, a jelentés létrejön, és a szolgáltatás frissíti az üres lejárati dátummal rendelkező meglévő jelentéseket. 
* Ehhez a funkcióhoz a **Pénzügyi jelentések biztonságának karbantartása** feladattal rendelkező felhasználók férhetnek hozzá. A **Pénzügyi jelentések lejáratának karbantartása** jogosultságot kapott, **Pénzügyi jelentések karbantartása** feladattal rendelkező felhasználók mindegyike szintén rendelkezik a lejárati idő módosításának képességével. Jelenleg két megőrzési lehetőség áll rendelkezésre: 

    * 90 napos lejárat.
    * Annak beállítása, hogy a jelentés soha ne járjon le.

Ha a lejárat (például 90 nap) ki van választva, akkor a mai naptól számított 90 napot alkalmaz. Jelentés létrehozásakor ez a viselkedés eltér az eredeti létrehozási dátumtól számított 90 nap beállítástól. 

A további lehetőségeket jövőbeli funkciók esetén figyelembe vesszük majd. A 90 nap lejárata lesz az alapértelmezett érték, és a megfelelő engedélyekkel rendelkező felhasználók felülírhatják az alapértelmezett beállítást a **Pénzügyi jelentések** listaoldalán.

## <a name="default-reports"></a>Alapértelmezett jelentések

A pénzügyi jelentések között 22 alapértelmezett pénzügyi jelentés található. Minden jelentés az alapértelmezett főszámla kategóriákat használja. Használhatja ezeket a jelentéseket úgy, ahogy vannak, vagy kiindulópontként a pénzügyi beszámolók készítéséhez. A hagyományos pénzügyi kimutatások, például a Bevétel-kimutatás vagy a Mérlegkimutatás mellett az alapértelmezett jelentések között olyan jelentések is vannak, amelyek különböző pénzügyi kimutatásokat tartalmaznak, amelyeket létrehozhat. 

<!--Each report in the following table links to an Office Mix presentation about the report.-->

| Alapértelmezett jelentés                                                                                         | Leírás                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 12 hónapos egyoszlopos bevétel-kimutatás – Alapértelmezett | A szervezet nyereségességének megtekintése az elmúlt 12 hónapban egy oszlopban.                                                                                                                                                                                                                                      |
| 12 hónapos trend bevétel-kimutatás – Alapértelmezett                 | A szervezet nyereségességének megtekintése az elmúlt 12 hónapban egy oszlopban. Ez a 12 hónap több mint egy pénzügyi évre is kiterjedhet.                                                                                                                                                                                             |
| Kiadások és költségvetés – Alapértelmezett                                | Az összes számla eredeti költségvetési egyenlege részletes adatainak megtekintése, és összehasonlítása a módosított költségvetéssel, amelyben eltérő kiadások vannak.                                                                                                                                                                          |
| Könyvvizsgálati részletek – Alapértelmezett                                  | Az összes számla egyenlegének részletes adatainak megtekintése. Ez a jelentés a hitel- és bankkártya egyenlegeket mutatja a jelentési pénznemben és a helyi pénznemben a tranzakciók további adataival együtt, mint például a felhasználói azonosító, az utolsó módosítást végrehajtó felhasználó, az utolsó módosítás dátuma, és a napló azonosítója. |
| Vevői egyenleglista – Alapértelmezett                                   | Az összes számla egyenlegének részletes adatainak megtekintése. Ez a jelentés megjeleníti a nyitó és záró egyenlegeket, a hitel- és bankkártyák egyenlegeit az aktuális időszakra és a folyó év aktuális napjáig a tranzakciók további adataival együtt, mint például a bizonylat.                                                                    |
| Mérleg – Alapértelmezett                                   | A szervezet éves pénzügyi helyzetének megtekintése.                                                                                                                                                                                                                                                             |
| Mérleg és bevétel-kimutatás egymás mellett – Alapértelmezett | A vállalat éves pénzügyi helyzetének és nyereségességének megjelenítése egymás mellett.                                                                                                                                                                                                                              |
| Pénzforgalom – Alapértelmezett                                       | Betekintés a szervezet beérkező és kimenő készpénzfizetéseibe.                                                                                                                                                                                                                                   |
| Részletes JE és TB áttekintés – Alapértelmezett                      | Nyitó egyenleg és a tevékenységi információk megtekintése az összes fiókban.                                                                                                                                                                                                                                                      |
| [Részletes főkönyvi kivonat – Alapértelmezett](trial-balance-financial-reports.md)| Egyenleginformációk megtekintése minden olyan számlához, amely hitel- vagy bankkártya egyenleggel rendelkezik, valamint ezen egyenlegek nettó értéke, a tranzakció dátumával, a bizonylattal és a napló leírással együtt.                                                                                                                                  |
| Negyedéves költségtrend három évre – Alapértelmezett             | Betekintést nyújt az elmúlt három év 12 negyedévének költségeibe.                                                                                                                                                                                                                                   |
| JE és TB pénzügyi feliratok áttekintése – Alapértelmezett            | Az eszköz, a kötelezettség, a tulajdonosi tőke, a bevétel, a kiadás, a nyereség vagy a veszteség pénzügyi feliratok egyenlegeinek és aktivitásának áttekintése.                                                                                                                                                                           |
| [Bevétel-kimutatás – Alapértelmezett](income-statement-financial-report.md)| A szervezet nyereségességének megtekintése az aktuális időszakra és a folyó év mai napjáig.                                                                                                                                                                                                                                   |
| Főkönyvi tranzakciók listája – Alapértelmezett                        | Az összes számla egyenlegének részletes adatainak megtekintése. Ez a jelentés a hitel- és bankkártyák egyenlegét mutatja a tranzakciók további adataival együtt, mint például a tranzakció időpontja, a napló száma, a bizonylat, a feladás típusa és a nyomkövetési szám.                                                                            |
| Mutatószámok – Alapértelmezett                                          | A szervezet éves fizetőképességének, nyereségességének és hatékonysági rátájának megtekintése.                                                                                                                                                                                                                           |
| 12 hónapos költségek – Alapértelmezett                       | Az elmúlt 12 hónap költségeinek megtekintése. Ez a 12 hónap több mint egy pénzügyi évre is kiterjedhet.                                                                                                                                                                                                       |
| Folyamatos negyedéves bevétel-kimutatás – Alapértelmezett               | A szervezet nyereségességének megtekintése negyedéves lebontásban az elmúlt évben, valamint a folyó évben az aktuális időpontig.                                                                                                                                                                                                                   |
| Mérleg egymás mellett – Alapértelmezett                      | A szervezet éves pénzügyi helyzetének megtekintése. Ez a jelentés az eszközöket és a kötelezettséget, valamint a részvényesek saját tőkéjét jeleníti meg egyidejűleg.                                                                                                                                                                                |
| [Összegző főkönyvi kivonat – Alapértelmezett](trial-balance-financial-reports.md)| Egyenleg-adatok megtekintése az összes számlához, amelyekhez nyitó és záró egyenleg tartozik, hitel- vagy bankkártya egyenleggel rendelkeznek nettó eltéréssel.                                                                                                                                                                  |
| [Éves összegző főkönyvi kivonat – Alapértelmezett](trial-balance-financial-reports.md)| Az egyenleg-adatok megtekintése az összes olyan számlához, amelyekhez nyitó és záró egyenleg tartozik, hitel- vagy bankkártya egyenleggel rendelkeznek nettó eltéréssel.                                                                                                                           |
| Heti értékesítések és kedvezmények – Alapértelmezett                     | Betekintés a hónap egyes heteinek értékesítéseibe és kedvezményeibe. Ez a jelentés összesen négy hetet tartalmaz.                                                                                                                                                                                                              |
| Rendelkezésre álló költségvetési alapok - alapértelmezett                         | A felülvizsgált költségvetés, a tényleges kiadások, költségvetési foglalások és az összes számla rendelkezésére álló költségvetési források részletes összehasonlításának megtekintése                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Pénzügyi jelentés megnyitása

Amikor rákattint a **Pénzügyi jelentéskészítés** menüre, a vállalat alapértelmezett pénzügyi jelentéseinek listája jelenik meg. Ezután megnyithatja vagy módosíthatja a jelentést. Az alapértelmezett jelentés megnyitásához válassza ki a jelentés nevét. A jelentés első megnyitásakor automatikusan létrejön a jelentés az előző hónapra. Például, ha 2019 augusztusában nyit meg egy jelentést először, a jelentés a 2019. július 31-i dátumhoz jön létre. Egy jelentés megnyitása után elkezdheti annak böngészését bizonyos adatok utáni leásással, illetve módosíthatja a jelentés beállításait.

## <a name="creating-and-modifying-financial-reports"></a>Pénzügyi jelentések létrehozása és módosítása

A pénzügyi jelentések listából új jelentést hozhat létre, vagy módosíthat egy meglévő jelentést. Ha rendelkezik a megfelelő engedélyekkel, új pénzügyi jelentést hozhat létre az **Új** gombra kattintva a műveletpanelen. Letöltődik a készülékére egy jelentéstervező program. A jelentéstervező elindulása után új jelentést hozhat létre. Az új jelentés mentése után megjelenik a pénzügyi jelentések listájában. A listában csak a Dynamics 365 Finance rendszerben használt vállalatra vonatkozó jelentések jelennek meg. 

## <a name="reporting-tree-definitions"></a>Jelentési-fa definíciók

A pénzügyi jelentések létrehozásához használt összetevők egyike a jelentések fastruktúrájának definíciója. Jelentési fa meghatározása segít a szervezeti szerkezet és hierarchia meghatározásában. Ez egy dimenziókon átnyúló hierarchia a pénzügyi adatok dimenzionális kapcsolatai alapján. Jelentési egység és összefoglaló szinten biztosít információt a fa minden eleméről.

Korlátlan számú jelentési fát hozhat létre, hogy szervezete adatait különböző módokon jeleníthesse meg. Az egyes jelentési fák az osztályok és az összesítő egységek bármilyen kombinációját tartalmazhatják, de egy jelentésdefiníciót egyszerre csak egy jelentési fával lehet összekapcsolni. 

## <a name="update-the-financial-reporting-version-through-slipstreaming"></a>A pénzügyi jelentés verziójának frissítése slipstreamingen keresztül

A Pénzügy és a Műveletek alkalmazás minden hónapban frissül. A Financial Reporting azonban nem feltétlenül frissülnek ebben az ütemben. Ezenkívül a vevőknek több lehetőség áll rendelkezésre arról, hogy mikor valósítják meg a Pénzügyi és üzemeltetési alkalmazások frissítéseit. A Financial Reporting frissítései automatikusan telepítve vannak. A Financial Reporting egy erre a célra kijelölt verziót használ fel, amely az ügyfél környezetében lesz betöltve, amikor szolgáltatásfrissítés történik, amikor a szolgáltatás leállítását kezdeményezik, vagy ha a vevő környezete Karbantartási módban van. Ennek a folyamatnak az neve *slipstreaming* vagy *valós frissítés* mivel minden ügyfél-implementáció a Financial Reporting ugyanazon verziójára van beállítva.

Az egyes verziókban kiadott módosítások [A Dynamics 365 Finance újdonságai és módosításai](../../finance/get-started/whats-new-home-page.md) részben találhatók. A platformfrissítések és hibajavítások az egyes kiadásokhoz a lap alján, a "További erőforrások" szakaszban találhatók.

A kiválasztott slipstreamed verzió a termelésre kész Financial Reporting felülvizsgált és ellenőrzött verziója. Kompatibilis a Dynamics 365 Finance minden korábbi és későbbi verziójával. Például a Financial Reporting a legutóbbi 10.0.19-es builden lehet, miközben a vevő még mindig a 10.0.16-os alkalmazásverziót használja.

> [!NOTE]
> Az egyetlen körülmények, amikor a vevők egy korábbi verzióra (visszalépési esetbe) állhatnak át, ha a Microsoft egy probléma miatt leállít egy valós bevezetést. Amint elérhető egy javítás, automatikusan alkalmazva lesz.

Az integrált telepítési folyamat teljesen automatizált, és nem igényel semmilyen vevői műveletet. Három topológiák használnak fel integrált telepítést, mindegyik egy kissé másképpen:

- **Helyszíni** – A helyszíni telepítések nem támogatják az integrált és a valós frissítés telepítést.
- **Infrastruktúra szolgáltatásként (IaaS)** – Az integrált logika minden olyan művelet során alkalmazható, amely megpróbálja frissíteni a Financial Reporting alkalmazást. Tartalmazza a bináris frissítéseket és a bináris frissítéseket tartalmazó közvetítést.
- **Önkiszolgáló** – a Financial Reporting leállását igénylő bármely művelet az integrált logikát alkalmazza:

    - A bináris frissítéseket és a bináris frissítéseket tartalmazó közvetítéseket tartalmazza.
    - Javítás vagy más infrastruktúra-leállás
    - AOT-csomagtelepítések

## <a name="troubleshooting-issues-opening-report-designer"></a>A jelentéskészítő megnyitásakor jelentkező problémák elhárítása

A jelentéskészítő megnyitásakor problémák merülhetnek fel néhány gyakori probléma esetében. Ezek a problémák és a problémamegoldás lépései a következők:

1. probléma: A jelentéskészítő nem indult el az **új** vagy **szerkesztés** kiválasztása alkalmával.

* Az Internet Explorer szolgáltatásban válassza ki a **Beállítások** elemet, majd válassza az **Internetbeállítások** lehetőséget. Válassza a **Biztonság** fület. Válassza ki a megbízható helyeket, majd válassza ki a **Helyek** elemet. A **Webhely hozzáadása a zónához** részben adja meg: „\*\.dynamics.com” (idézőjelek nélkül), majd válassza a **Hozzáadás** lehetőséget. 
* Az Internet Explorer szolgáltatásban válassza ki a **Beállítások** elemet, majd válassza az **Internetbeállítások** lehetőséget. Válassza a **Biztonság** fület. Válassza ki a megbízható helyeket. A zóna Biztonsági szint feliratú területen módosítsa a beállítást **Közepesen alacsony** értékre.
* Tiltsa le az előugró ablakok blokkolását a böngészőjében.
* A Microsoft .NET-keretrendszer 4.6.2 vagy újabb telepítéséhez munkaállomások szükségesek. A Microsoft .NET Framework ezen verziója a [Microsoft letöltőközpontból](https://www.microsoft.com/download/details.aspx?id=53345) tölthető le és telepíthető.
* Chrome böngésző használata esetén, telepítenie kell a ClickOnce kiterjesztést a jelentéstervező kliens letöltéséhez. Ha a Chrome böngészőt incognito módban futtatja, győződjön meg arról, a ClickOnce kiterjesztés engedélyezve van-e az incognito módban. A Chrome ClickOnce kiterjesztéssel kapcsolatos további tudnivalókat lásd: [Felhőtelepítések rendszerkövetelményei](../../fin-ops-core/fin-ops/get-started/system-requirements.md).
* Ha a Microsoft Edge-t Chrome böngészővel használja, akkor nem kell ClickOnce-kiterjesztést telepítenie az Edge Chromium számára. Azonban engedélyeznie kell a ClickOnce lehetőséget a jelentéstervező kliens letöltéséhez. Ha a böngészőt inkognitó módban futtatja, győződjön meg arról, a ClickOnce kiterjesztés engedélyezve van-e az inkognitó módban.

    1. Új böngésző megnyitása a Microsoft Edge-ben.
    2. Adja az **edge://flags** parancsot, és válassza az **Enter** billentyűt.
    3. Keresse meg a **ClickOnce támogatás** beállítást, vagy használja ezt a közvetlen hivatkozást: **edge://flags/#edge-click-once**.
    4. A legördülő menü beállítását állítsa **Engedélyezett** értékre.
    5. Válassza a **Böngésző újraindítása** lehetőséget.

2. probléma: A felhasználó nincs hozzárendelve a Financial reporting használatához szükséges engedélyekhez. 

* Ha ellenőrizni szeretné, hogy a felhasználó nem rendelkezik-e engedéllyel, válassza az **Igen** lehetőséget a következő hibán: „Nem lehet csatlakozni a Financial Reporting kiszolgálóhoz. Válassza az Igen beállítást, ha folytatni szeretné, és adja meg másik kiszolgáló címét.” Válassza ki a **Kapcsolat ellenőrzése** lehetőséget. Ha nincs engedélye, akkor egy üzenet jelenik meg, amely azt mondja, "A csatlakozási kísérlet nem sikerült. A felhasználó nem rendelkezik a kiszolgálóhoz való kapcsolódáshoz szükséges jogosultsággal. Kérje a rendszergazda segítségét.”
* A szükséges engedélyek a következő táblázatban láthatók: [Biztonsági hozzáférés biztosítása a Financial Reporting szolgáltatáshoz](#granting-security-access-to-financial-reporting). A Financial Reporting biztonsága ezeken a jogosultságokon alapul. Nem férhet hozzá, hacsak ezeket a jogosultságokat (vagy egy másik biztonsági szerepkört, amely tartalmazza ezeket a jogosultságokat) Önhöz nem rendeli. 
* A **Vállalat felhasználói biztosítója a vállalatnak** integrációs feladat (amely szintén felelős és ismert a felhasználói integrációról) 5 perces időtartamokon fut. Előfordulhat, hogy akár 10 percig is eltarthat, amíg a Financial reporting szolgáltatásban érvénybe lépnek a jogosultságok. 

    Ha egy másik felhasználó megnyithatja a Jelentéskészítőt, válassza az **Eszközök** elemet , majd kiválaszthatja az **integráció állapota** elemet. Győződjön meg róla, hogy az integrációs leképezés „Vállalat felhasználói biztosítója a vállalatnak” sikeresen lefutott, mert Önhöz hozzárendelték a Financial reporting használati jogosultságát. 

* Előfordulhat, hogy egy másik hiba megakadályozta a **Dynamics felhasználó és Financial reporting felhasználói integrációt** a befejezéstől. Vagy előfordulhat, hogy az adatpiac alaphelyzetbe állítása megtörtént, de még nem fejeződött be, vagy más rendszerhiba történt. Próbálja meg újra futtatni a folyamatot később. Ha a probléma továbbra is fennáll, forduljon a rendszergazdához.

3. probléma: Továbbléphet a **ClickOnce jelentéstervező** bejelentkezési oldalán, de a Jelentéskészítőben nem hajtható végre a bejelentkezés. 

* A helyi számítógépen a bejelentkezési hitelesítő adatok megadásakor beállított idő csak a Financial reporting kiszolgáló idejétől számított öt percen belül lehet. Ha több, mint öt perc eltérés van, akkor a rendszer nem engedélyezi a bejelentkezést. 
* Ha a számítógépen lévő idő eltér a Financial Reporting kiszolgálón lévő időtől, javasoljuk, hogy engedélyezze a számítógép idejének automatikus beállítására vonatkozó Windows opciót. 

## <a name="troubleshoot-report-designer-issues-with-event-viewer"></a>A jelentéskészítővel kapcsolatos problémák hibaelhárítása az eseménynaplóval

Az Eseménynapló segítségével elemezheti a Financial Reporting használata során felmerülő egyes problémákat. 

### <a name="what-happens-when-you-have-connections-issues-with-financial-reporting"></a>Mi történik, ha a Financial Reporting szolgáltatással kapcsolatos kapcsolati problémái vannak? 

Az alábbi lépésekkel hatékonyabbá teheti a Microsoft ügyfélszolgálatával folytatott beszélgetéseket, és gyorsabban kaphat megoldásokat. 
 
A következő lépésekben a Financial Reporting szolgáltatáshoz tartozó Eseménynapló üzenetei bekapcsolásának folyamatát ismertetjük. Az Eseménynapló által generált naplók segítenek az ügyfélszolgálati szakértőknek a kapcsolati probléma forrásának gyors azonosításában. A naplók másolatát küldje be a jegyével együtt, amikor kapcsolatba lép az ügyfélszolgálattal.


1. Másolja a RegisterETW.zip fájlt a kliens munkaállomásra (lehetőleg az Asztalra), és csomagolja ki a [RegisterETW.zip](https://dev.azure.com/msdyneng/e6f12261-a46a-4af1-ac0c-e22bc2c5a478/_apis/git/repositories/ff923027-67f0-43fb-b63c-6d6b6423840f/Items?path=%2F.attachments%2FRegisterETW-c1a35291-6aa6-4462-a2bc-4ba117fd5f8e.zip&download=false&resolveLfs=true&%24format=octetStream&api-version=5.0-preview.1&sanitize=true&versionDescriptor.version=wikiMaster) fájlt.
2. Győződjön meg róla, hogy a Windows Eseménynapló be van zárva.
3. Nyisson meg egy Administrator PowerShell parancssort, és lépjen abba a könyvtárba, ahol a RegisterETW.ps1 található.
4. Futtassa a következő parancsot: .\RegisterETW.ps1

    A sikeres kimenetet a PowerShellben a következő üzenet jelzi: **Befejezett RegisterETW parancsfájl**.

    Nyissa meg újra az eseménynaplót, és látni fogja ezeket a naplókat a **Microsoft > Dynamics** helyen:

    * MR-ügyfél
    * MR-DVT
    * MR-integráció
    * MR-naplózó
    * MR-jelentéskészítés
    * MR_SchedulerTasks
    * MR-Sql
    * MR-TraceManager

5. Reprodukálja a problémát a Report Designerben.
6. Exportálja az MR-Logger eseményeit az Eseménynapló segítségével.

## <a name="troubleshoot-issues-connecting-to-financial-reporting"></a>A Financial Reporting szolgáltatáshoz való csatlakozással kapcsolatos problémák elhárítása

Probléma: A következő hibaüzenetet kapja: „Nem sikerült csatlakozni a Financial Reporting kiszolgálóhoz”.

* Határozza meg, hogy a probléma a Chrome és az Edge internetes böngészőkben jelentkezik-e.
* Ha a probléma csak egy böngészőben jelentkezik, akkor ez lehet a ClickOnce problémája. 
* Amikor megkapja a kapcsolódási hibaüzenetet, válassza az **Ellenőrzés** lehetőséget a kapcsolat teszteléséhez, és nézze meg, milyen üzenet jelenik meg. 
* A probléma oka lehet, hogy egy másik felhasználónak nincs hozzáférése a Financial Reporting szolgáltatáshoz. Ha egy felhasználónak nincs hozzáférése, akkor egy üzenetet kap, amely szerint nincs jogosultsága.
* Ha a probléma több böngészőben is jelentkezik, győződjön meg arról, hogy a munkaállomáson az óra Automatikus értékre van állítva.
* Működjön együtt olyan felhasználóval, aki biztonsági rendszergazdai jogokkal rendelkezik a Dynamics 365 Finance alkalmazásban, és rendszergazdai jogosultsággal rendelkezik a hálózati tartományban, jelentkezzen be a munkaállomásra, és nézze meg, hogy tud-e csatlakozni. Ha tud csatlakozni, a probléma a hálózati engedélyekkel lehet összefüggésben.
* A munkaállomáson ideiglenesen tiltsa le a tűzfalat. Ha ezután képes csatlakozni a Report Designerhez, a probléma a tűzfallal van. Működjön együtt a szervezet informatikai osztályával a probléma megoldása érdekében.

## <a name="additional-resources"></a>További erőforrások

- [Pénzügyi jelentések megtekintése](view-financial-reports.md)
- [Jelentési fa definíciója a pénzügyi jelentésekben](../../fin-ops-core/dev-itpro/analytics/financial-reporting-tree-definitions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
