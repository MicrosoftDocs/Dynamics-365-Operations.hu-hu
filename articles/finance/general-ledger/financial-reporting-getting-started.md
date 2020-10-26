---
title: Pénzügyi jelentéskészítés – áttekintés
description: Ez a témakör azt ismerteti, hol érheti el a Microsoft Dynamics 365 Finance pénzügyi jelentéseit, és hogyan használhatja a pénzügyi jelentési képességeket.
author: aprilolson
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 363ce16b31a199e519c969746c4f10430d9d7497
ms.sourcegitcommit: 165e082e59ab783995c16fd70943584bc3ba3455
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/06/2020
ms.locfileid: "3967258"
---
# <a name="get-started-with-financial-reporting"></a>Financial Reporting – első lépések 

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hol érheti el a pénzügyi jelentéseket, és hogyan használhatja a pénzügyi jelentési szolgáltatásokat. Emellett az elérhető alapértelmezett pénzügyi jelentések leírását is tartalmazza.

<a name="accessing-financial-reporting"></a>Pénzügyi jelentéskészítés elérése
-----------------------------

A **Pénzügyi jelentéskészítés** menüt a következő helyen találhatja meg:

-   **Főkönyv** &gt; **Lekérdezések és jelentések**
-   **Költségvetés készítése** &gt; **Lekérdezések és jelentések** &gt; **Alapvető költségvetés-tervezés**
-   **Költségvetés készítése** &gt; **Lekérdezések és jelentések** &gt; **Költségvetés-tervezés**
-   **Költségvetés készítése** &gt; **Lekérdezések és jelentések** &gt; **Költségvetés-ellenőrzés**
-   Konszolidációk

Ha pénzügyi jelentést szeretne létrehozni és generálni egy jogi személy számára, be kell állítania a következő adatokat az adott jogi személyhez:

-   Pénzügyi naptár
-   Ledger
-   Számlatükör
-   Pénznem

## <a name="granting-security-access-to-financial-reporting"></a>Biztonsági hozzáférés biztosítása a Financial Reporting szolgáltatáshoz
A pénzügyi jelentéskészítő funkciók azon felhasználók számára érhetők el, amelyek megfelelő jogosultságokkal és kiadott feladatokkal rendelkeznek a biztonsági szerepkörüknek megfelelően. Az alábbi szakaszok tartalmazzák ezen jogosultságok és feladatkörök listáját, valamint a kapcsolódó szerepköröket.

### <a name="duties"></a>Feladatkör

| Adó címke                            | Leírás                                                             | AOT neve                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Pénzügyi jelentések biztonságának karbantartása | Pénzügyi jelentések biztonságának karbantartása és adminisztratív feladatok végrehajtása. | PénzügyiJelentésekBiztonságánakKarbantartása |
| Pénzügyi jelentések karbantartása            | Pénzügyi jelentések tervezése és karbantartása.                                  | PénzügyiJelentésekKarbantartása         |
| Pénzügyi jelentések létrehozása            | Pénzügyi jelentések létrehozása és frissítése.                                 | PénzügyiJelentésekLétrehozása         |
| Pénzügyi teljesítmény ellenőrzése          | Pénzügyi teljesítmény ellenőrzése és elemzése.                               | PénzügyiJelentésekTeljEllenőrzése       |

### <a name="privileges"></a>Jogosultságok

| Jogosultság címkéje                       | Leírás                                                             | AOT neve                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Pénzügyi jelentések biztonságának karbantartása | Pénzügyi jelentések biztonságának karbantartása és adminisztratív feladatok végrehajtása. | FinancialReportsSecuritySystemMaintain |
| Pénzügyi jelentések karbantartása            | Pénzügyi jelentések tervezése és karbantartása.                                  | PénzügyiJelentésekKarbantartása  |
| Pénzügyi jelentések létrehozása            | Pénzügyi jelentések létrehozása és frissítése.                                 | PénzügyiJelentésekLétrehozása  |
| Pénzügyi jelentések megtekintése                | Pénzügyi jelentések megtekintése.                                                 | PénzügyiJelentésekMegtekintése             |

### <a name="roles"></a>Szerepkörök

| Jogosultság címkéje                       | Feladatkör                                  | Szerepkörök                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Pénzügyi jelentések biztonságának karbantartása | Pénzügyi jelentések biztonságának karbantartása | Biztonsági rendszergazda                                                          |
| Pénzügyi jelentések karbantartása            | Pénzügyi jelentések karbantartása            | Főkönyvelő, számviteli felügyelő, pénzügyi ellenőr, költségvetés-kezelő |
| Pénzügyi jelentések létrehozása            | Pénzügyi jelentések létrehozása            | Vezérigazgató, pénzügyi igazgató, könyvelő                                                            |
| Pénzügyi jelentések megtekintése                | Pénzügyi teljesítmény ellenőrzése          | Nincs hozzárendelve                                                                   |

Miután hozzáadtunk egy felhasználót vagy egy szerepkör módosult, a felhasználónak el kell tudni érnie a pénzügyi beszámolókat néhány percen belül. 

> [!NOTE]
> A sysadmin szerepkör hozzáadódik a pénzügyi beszámoló minden szerepköréhez.

## <a name="report-deletions-and-expirations"></a>Jelentés törlése és lejárata
A jelentést generáló felhasználók törölhetik saját jelentéseiket. A **Pénzügyi jelentések biztonságának karbantartása** feladattal rendelkező felhasználók törölhetik mások jelentéseit. 

A 10.0.8-as verzióban bevezettük a lejárati dátumok koncepcióját. Egy új kötelező funkciót engedélyezük az **Összes** oldalon a funkciókezelési munkaterületen. A **Pénzügyi jelentés megőrzésével kapcsolatos irányelvek** funkcióban a következő módosítások történtek:
* Az újonnan létrehozott jelentések automatikusan meg lesznek jelölve a létrehozásuktól számított 90 napos lejárati dátummal.
* A funkció telepítése előttről származó meglévő jelentések mindegyike 90 napos lejárati időszakot kap. A dátum egy rövid időre üresen jelenhet meg, amíg a pénzügyi jelentéskészítési szolgáltatás fut, a jelentés létrejön, és a szolgáltatás frissíti az üres lejárati dátummal rendelkező meglévő jelentéseket. 
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
| Részletes főkönyvi kivonat – Alapértelmezett                         | Egyenleginformációk megtekintése minden olyan számlához, amely hitel- vagy bankkártya egyenleggel rendelkezik, valamint ezen egyenlegek nettó értéke, a tranzakció dátumával, a bizonylattal és a napló leírással együtt.                                                                                                                                  |
| Negyedéves költségtrend három évre – Alapértelmezett             | Betekintést nyújt az elmúlt három év 12 negyedévének költségeibe.                                                                                                                                                                                                                                   |
| JE és TB pénzügyi feliratok áttekintése – Alapértelmezett            | Az eszköz, a kötelezettség, a tulajdonosi tőke, a bevétel, a kiadás, a nyereség vagy a veszteség pénzügyi feliratok egyenlegeinek és aktivitásának áttekintése.                                                                                                                                                                           |
| Bevétel-kimutatás – Alapértelmezett                                | A szervezet nyereségességének megtekintése az aktuális időszakra és a folyó év mai napjáig.                                                                                                                                                                                                                                   |
| Főkönyvi tranzakciók listája – Alapértelmezett                        | Az összes számla egyenlegének részletes adatainak megtekintése. Ez a jelentés a hitel- és bankkártyák egyenlegét mutatja a tranzakciók további adataival együtt, mint például a tranzakció időpontja, a napló száma, a bizonylat, a feladás típusa és a nyomkövetési szám.                                                                            |
| Mutatószámok – Alapértelmezett                                          | A szervezet éves fizetőképességének, nyereségességének és hatékonysági rátájának megtekintése.                                                                                                                                                                                                                           |
| 12 hónapos költségek – Alapértelmezett                       | Az elmúlt 12 hónap költségeinek megtekintése. Ez a 12 hónap több mint egy pénzügyi évre is kiterjedhet.                                                                                                                                                                                                       |
| Folyamatos negyedéves bevétel-kimutatás – Alapértelmezett               | A szervezet nyereségességének megtekintése negyedéves lebontásban az elmúlt évben, valamint a folyó évben az aktuális időpontig.                                                                                                                                                                                                                   |
| Mérleg egymás mellett – Alapértelmezett                      | A szervezet éves pénzügyi helyzetének megtekintése. Ez a jelentés az eszközöket és a kötelezettséget, valamint a részvényesek saját tőkéjét jeleníti meg egyidejűleg.                                                                                                                                                                                |
| Összegző főkönyvi kivonat – Alapértelmezett                          | Egyenleg-adatok megtekintése az összes számlához, amelyekhez nyitó és záró egyenleg tartozik, hitel- vagy bankkártya egyenleggel rendelkeznek nettó eltéréssel.                                                                                                                                                                  |
| Éves összegző főkönyvi kivonat – Alapértelmezett           | Az egyenleg-adatok megtekintése az összes olyan számlához, amelyekhez nyitó és záró egyenleg tartozik, hitel- vagy bankkártya egyenleggel rendelkeznek nettó eltéréssel.                                                                                                                           |
| Heti értékesítések és kedvezmények – Alapértelmezett                     | Betekintés a hónap egyes heteinek értékesítéseibe és kedvezményeibe. Ez a jelentés összesen négy hetet tartalmaz.                                                                                                                                                                                                              |
| Rendelkezésre álló költségvetési alapok - alapértelmezett                         | A felülvizsgált költségvetés, a tényleges kiadások, költségvetési foglalások és az összes számla rendelkezésére álló költségvetési források részletes összehasonlításának megtekintése                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Pénzügyi jelentés megnyitása
Amikor rákattint a **Pénzügyi jelentéskészítés** menüre, a vállalat alapértelmezett pénzügyi jelentéseinek listája jelenik meg. Ezután megnyithatja vagy módosíthatja a jelentést. Az alapértelmezett jelentés megnyitásához válassza ki a jelentés nevét. A jelentés első megnyitásakor automatikusan létrejön a jelentés az előző hónapra. Például, ha 2019 augusztusában nyit meg egy jelentést először, a jelentés a 2019. július 31-i dátumhoz jön létre. Egy jelentés megnyitása után elkezdheti annak böngészését bizonyos adatok utáni leásással, illetve módosíthatja a jelentés beállításait.

## <a name="creating-and-modifying-financial-reports"></a>Pénzügyi jelentések létrehozása és módosítása
A pénzügyi jelentések listából új jelentést hozhat létre, vagy módosíthat egy meglévő jelentést. Ha rendelkezik a megfelelő engedélyekkel, új pénzügyi jelentést hozhat létre az **Új** gombra kattintva a műveletpanelen. Letöltődik a készülékére egy jelentéstervező program. A jelentéstervező elindulása után új jelentést hozhat létre. Az új jelentés mentése után megjelenik a pénzügyi jelentések listájában. A listában csak a Dynamics 365 Finance rendszerben használt vállalatra vonatkozó jelentések jelennek meg. 

## <a name="reporting-tree-definitions"></a>Jelentési-fa definíciók 
A pénzügyi jelentések létrehozásához használt összetevők egyike a jelentések fastruktúrájának definíciója. Jelentési fa meghatározása segít a szervezeti szerkezet és hierarchia meghatározásában. Ez egy dimenziókon átnyúló hierarchia a pénzügyi adatok dimenzionális kapcsolatai alapján. Jelentési egység és összefoglaló szinten biztosít információt a fa minden eleméről.

Korlátlan számú jelentési fát hozhat létre, hogy szervezete adatait különböző módokon jeleníthesse meg. Az egyes jelentési fák az osztályok és az összesítő egységek bármilyen kombinációját tartalmazhatják, de egy jelentésdefiníciót egyszerre csak egy jelentési fával lehet összekapcsolni. 


## <a name="troubleshooting-issues-opening-report-designer"></a>A jelentéskészítő megnyitásakor jelentkező problémák elhárítása
A jelentéskészítő megnyitásakor problémák merülhetnek fel néhány gyakori probléma esetében. Ezek a problémák és a problémamegoldás lépései a következők:

1. probléma: A jelentéskészítő nem indult el az **új** vagy **szerkesztés** kiválasztása alkalmával.

* Az Internet Explorer szolgáltatásban válassza ki a **Beállítások** elemet, majd válassza az **Internetbeállítások** lehetőséget. Válassza a **Biztonság** fület. Válassza ki a megbízható helyeket, majd válassza ki a **Helyek** elemet. A **Webhely hozzáadása a zónához** részben adja meg: „\*\.dynamics.com” (idézőjelek nélkül), majd válassza a **Hozzáadás** lehetőséget. 
* Az Internet Explorer szolgáltatásban válassza ki a **Beállítások** elemet, majd válassza az **Internetbeállítások** lehetőséget. Válassza a **Biztonság** fület. Válassza ki a megbízható helyeket. A zóna Biztonsági szint feliratú területen módosítsa a beállítást **Közepesen alacsony** értékre.
* Tiltsa le az előugró ablakok blokkolását a böngészőjében.
* A Microsoft .NET-keretrendszer 4.6.2 vagy újabb telepítéséhez munkaállomások szükségesek. A Microsoft .NET Framework ezen verziója a [Microsoft letöltőközpontból](https://www.microsoft.com/download/details.aspx?id=53345) tölthető le és telepíthető.
* Ha a Chrome böngészőt használja a Microsoft Edge-hez, akkor telepítenie kell a ClickOnce kiterjesztést a jelentéstervező kliens letöltéséhez. Ha a böngészőt inkognitó módban futtatja, győződjön meg arról, a ClickOnce kiterjesztés engedélyezve van-e az inkognitó módban. 
     1. Új böngésző megnyitása a Microsoft Edge-ben.
     2. Adja az **edge://flags** parancsot, és válassza az **Enter** billentyűt.
     3. Keresse meg a **ClickOnce támogatás** beállítást, vagy használja ezt a közvetlen hivatkozást: **edge://flags/#edge-click-once** .
     4. A legördülő menü beállítását állítsa **Engedélyezett** értékre.
     5. Válassza a **Böngésző újraindítása** lehetőséget.

2. probléma: A felhasználó nincs hozzárendelve a Financial Reporting használatához szükséges engedélyekhez. 

* Ha ellenőrizni szeretné, hogy a felhasználó nem rendelkezik-e engedéllyel, válassza az **Igen** lehetőséget a következő hibán: "nem lehet csatlakozni a Financial Reporting kiszolgálóhoz. Válassza az Igen beállítást, ha folytatni szeretné, és adja meg másik kiszolgáló címét.” Válassza ki a **Kapcsolat ellenőrzése** lehetőséget. Ha nincs engedélye, akkor egy üzenet jelenik meg, amely azt mondja, "A csatlakozási kísérlet nem sikerült. A felhasználó nem rendelkezik a kiszolgálóhoz való kapcsolódáshoz szükséges jogosultsággal. Kérje a rendszergazda segítségét.”
* A szükséges engedélyek a következő táblázatban láthatók: [Biztonsági hozzáférés biztosítása a Financial Reporting szolgáltatáshoz](#granting-security-access-to-financial-reporting). A Financial Reporting biztonsága ezeken a jogosultságokon alapul. Nem férhet hozzá, hacsak ezeket a jogosultságokat (vagy egy másik biztonsági szerepkört, amely tartalmazza ezeket a jogosultságokat) Önhöz nem rendeli. 
* A **Vállalat felhasználói biztosítója a vállalatnak** integrációs feladat (amely szintén felelős és ismert a felhasználói integrációról) 5 perces időtartamokon fut. Előfordulhat, hogy akár 10 percig is eltarthat, amíg a Financial Reporting szolgáltatásban érvénybe lépnek a jogosultságok. 
  Ha egy másik felhasználó megnyithatja a Jelentéskészítőt, válassza az **Eszközök** elemet , majd kiválaszthatja az **integráció állapota** elemet. Győződjön meg róla, hogy az integrációs leképezés „Vállalat felhasználói biztosítója a vállalatnak” sikeresen lefutott, mert Önhöz hozzárendelték a Financial Reporting használati jogosultságát. 
* Előfordulhat, hogy egy másik hiba megakadályozta a **Dynamics felhasználó és Financial Reporting felhasználói integrációt** a befejezéstől. Vagy előfordulhat, hogy az adatpiac alaphelyzetbe állítása megtörtént, de még nem fejeződött be, vagy más rendszerhiba történt. Próbálja meg újra futtatni a folyamatot később. Ha a probléma továbbra is fennáll, forduljon a rendszergazdához.

3. probléma: Továbbléphet a ClickOnce-jelentéstervező bejelentkezési oldalán, de a Jelentéskészítőben nem hajtható végre a bejelentkezés. 

* A helyi számítógépen a bejelentkezési hitelesítő adatok megadásakor beállított idő csak a Financial Reporting kiszolgáló idejétől számított öt percen belül lehet. Ha több, mint öt perc eltérés van, akkor a rendszer nem engedélyezi a bejelentkezést. 
* Ebben az esetben azt javasoljuk, hogy a Windows automatikus beállításával engedélyezze a számítógép idejét. 

## <a name="additional-resources"></a>További erőforrások
- [Pénzügyi jelentések megtekintése](view-financial-reports.md)
- [Jelentési fa definíciója a pénzügyi jelentésekben](../../fin-ops-core/dev-itpro/analytics/financial-reporting-tree-definitions.md)
