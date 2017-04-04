---
title: "Pénzügyi jelentéskészítés"
description: "Ez a témakör ismerteti a pénzügyi beszámolás a Microsoft Dynamics 365 műveletek eléréséhez hol és hogyan használja a pénzügyi jelentési szolgáltatások. Az alapértelmezett biztosított pénzügyi jelentések leírását tartalmazza."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d13747f17b5f382b3a530b1f166681eeec0b9d73
ms.lasthandoff: 03/31/2017


---

# <a name="financial-reporting"></a>Pénzügyi jelentéskészítés

Ez a témakör ismerteti a pénzügyi beszámolás a Microsoft Dynamics 365 műveletek eléréséhez hol és hogyan használja a pénzügyi jelentési szolgáltatások. Az alapértelmezett biztosított pénzügyi jelentések leírását tartalmazza.

<a name="accessing-financial-reporting"></a>Pénzügyi jelentéskészítés elérése
-----------------------------

Megtalálhatja a **pénzügyi beszámoló** 365 Dynamics a Műveletek menü a következő helyezi:

-   **Főkönyvi**&gt;**lekérdezések és jelentések**
-   **Költségvetés**&gt;**Inquires és a jelentések**&gt;**alapvető költségvetés-tervezés**
-   **Költségvetés**&gt;**lekérdezések és jelentések**&gt;**költségvetés-tervezés**
-   **Költségvetés**&gt;**lekérdezések és jelentések**&gt;**a költségvetés-ellenőrzés**
-   Konszolidációk

Ha pénzügyi jelentést szeretne létrehozni és generálni egy jogi személy számára, be kell állítania a következő adatokat az adott jogi személyhez:

-   Pénzügyi naptár
-   Főkönyv
-   Számlatükör
-   Pénznem

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
| Pénzügyi jelentések biztonságának karbantartása | Pénzügyi jelentések biztonságának karbantartása és adminisztratív feladatok végrehajtása. | PénzügyiJelentésekBiztonságánakKarbantartása |
| Pénzügyi jelentések karbantartása            | Pénzügyi jelentések tervezése és karbantartása.                                  | PénzügyiJelentésekKarbantartása  |
| Pénzügyi jelentések létrehozása            | Pénzügyi jelentések létrehozása és frissítése.                                 | PénzügyiJelentésekLétrehozása  |
| Pénzügyi jelentések megtekintése                | Pénzügyi jelentések megtekintése.                                                 | PénzügyiJelentésekMegtekintése             |

### <a name="roles"></a>Szerepkörök

| Jogosultság címkéje                       | Feladatkör                                  | Szerepkörök                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Pénzügyi jelentések biztonságának karbantartása | Pénzügyi jelentések biztonságának karbantartása | Biztonsági rendszergazda                                                          |
| Pénzügyi jelentések karbantartása            | Pénzügyi jelentések karbantartása            | Számviteli vezető felügyelő számviteli, pénzügyi ellenőr, Költségvetés-kezelő |
| Pénzügyi jelentések létrehozása            | Pénzügyi jelentések létrehozása            | Vezérigazgatói, pénzügyi igazgató, könyvelő                                                            |
| Pénzügyi jelentések megtekintése                | Pénzügyi teljesítmény ellenőrzése          | Nincs hozzárendelve                                                                   |

Miután hozzáadtunk egy felhasználót vagy egy szerepkör módosult, a felhasználónak el kell tudni érnie a pénzügyi beszámolókat néhány percen belül. **Megjegyzés:** a sysadmin szerepkör hozzáadódik a pénzügyi beszámoló minden szerepkör.

## <a name="default-reports"></a>Alapértelmezett jelentések
A pénzügyi jelentések között 22 alapértelmezett pénzügyi jelentés található. Minden jelentés használja az alapértelmezett fő számla kategóriák Dynamics 365 műveletekhez. Használhatja ezeket a jelentéseket úgy, ahogy vannak, vagy kiindulópontként a pénzügyi beszámolók készítéséhez. A hagyományos pénzügyi kimutatások, például a Bevétel-kimutatás vagy a Mérlegkimutatás mellett az alapértelmezett jelentések között olyan jelentések is vannak, amelyek különböző pénzügyi kimutatásokat tartalmaznak, amelyeket létrehozhat. Minden a jelentés jelentéssel kapcsolatban az alábbi táblázat hivatkozások bemutatók Office keverjük össze.

| Alapértelmezett jelentés                                                                                         | Leírás                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [12 Month Rolling Single Column Income Statement – Default](https://mix.office.com/watch/76kc7bm3wnt1) | A szervezet nyereségességének megtekintése az elmúlt 12 hónapban egy oszlopban.                                                                                                                                                                                                                                      |
| [12 Month Trend Income Statement – Default](https://mix.office.com/watch/12brmfge5p8r)                 | A szervezet nyereségességének megtekintése az elmúlt 12 hónapban egy oszlopban. Ez a 12 hónap több mint egy pénzügyi évre is kiterjedhet.                                                                                                                                                                                             |
| [Actual vs Budget – Default](https://mix.office.com/watch/fi439lkwr0no)                                | Az összes számla eredeti költségvetési egyenlege részletes adatainak megtekintése, és összehasonlítása a módosított költségvetéssel, amelyben eltérő kiadások vannak.                                                                                                                                                                          |
| [Audit Details – Default](https://mix.office.com/watch/1i15nzd3nwkyh)                                  | Az összes számla egyenlegének részletes adatainak megtekintése. Ez a jelentés a hitel- és bankkártya egyenlegeket mutatja a jelentési pénznemben és a helyi pénznemben a tranzakciók további adataival együtt, mint például a felhasználói azonosító, az utolsó módosítást végrehajtó felhasználó, az utolsó módosítás dátuma, és a napló azonosítója. |
| [Balance List – Default](https://mix.office.com/watch/1kezwu2a10fq4)                                   | Az összes számla egyenlegének részletes adatainak megtekintése. Ez a jelentés megjeleníti a nyitó és záró egyenlegeket, a hitel- és bankkártyák egyenlegeit az aktuális időszakra és a folyó év aktuális napjáig a tranzakciók további adataival együtt, mint például a bizonylat.                                                                    |
| [Balance Sheet – Default](https://mix.office.com/watch/zkgq0u7visw9)                                   | A szervezet éves pénzügyi helyzetének megtekintése.                                                                                                                                                                                                                                                             |
| [Balance Sheet and Income Statement Side by Side - Default](https://mix.office.com/watch/zkgq0u7visw9) | A vállalat éves pénzügyi helyzetének és nyereségességének megjelenítése egymás mellett.                                                                                                                                                                                                                              |
| [Cash Flow – Default](https://mix.office.com/watch/jd3go9pz6390)                                       | Betekintés a szervezet beérkező és kimenő készpénzfizetéseibe.                                                                                                                                                                                                                                   |
| [Detailed JE and TB Review – Default](https://mix.office.com/watch/1sw9fmtwgjb1f)                      | Nyitó egyenleg és a tevékenységi információk megtekintése az összes fiókban.                                                                                                                                                                                                                                                      |
| [Detailed Trial Balance - Default](https://mix.office.com/watch/1ewwgbpv0iwrl)                         | Egyenleginformációk megtekintése minden olyan számlához, amely hitel- vagy bankkártya egyenleggel rendelkezik, valamint ezen egyenlegek nettó értéke, a tranzakció dátumával, a bizonylattal és a napló leírással együtt.                                                                                                                                  |
| [Expenses Three Year Quarterly Trend – Default](https://mix.office.com/watch/gwm4zu7tmtj8)             | Betekintést nyújt az elmúlt három év 12 negyedévének költségeibe.                                                                                                                                                                                                                                   |
| [Financial Captions JE and TB Review – Default](https://mix.office.com/watch/1sw9fmtwgjb1f)            | Az eszköz, a kötelezettség, a tulajdonosi tőke, a bevétel, a kiadás, a nyereség vagy a veszteség pénzügyi feliratok egyenlegeinek és aktivitásának áttekintése.                                                                                                                                                                           |
| [Income Statement – Default](https://mix.office.com/watch/sbuhgl5hzuhi)                                | A szervezet nyereségességének megtekintése az aktuális időszakra és a folyó év mai napjáig.                                                                                                                                                                                                                                   |
| [Ledger Transaction List – Default](https://mix.office.com/watch/19h9v2rmh48vy)                        | Az összes számla egyenlegének részletes adatainak megtekintése. Ez a jelentés a hitel- és bankkártyák egyenlegét mutatja a tranzakciók további adataival együtt, mint például a tranzakció időpontja, a napló száma, a bizonylat, a feladás típusa és a nyomkövetési szám.                                                                            |
| [Ratios – Default](https://mix.office.com/watch/b08hfc5h92me)                                          | A szervezet éves fizetőképességének, nyereségességének és hatékonysági rátájának megtekintése.                                                                                                                                                                                                                           |
| [Rolling 12 Month Expenses – Default](https://mix.office.com/watch/iywod5qmqhz7)                       | Az elmúlt 12 hónap költségeinek megtekintése. Ez a 12 hónap több mint egy pénzügyi évre is kiterjedhet.                                                                                                                                                                                                       |
| [Rolling Quarter Income Statement – Default](https://mix.office.com/watch/1k4yl6a6oyxqc)               | A szervezet nyereségessége megtekintése negyedéves alapon az elmúlt évben és az év elejétől.                                                                                                                                                                                                                   |
| [Side by Side Balance Sheet – Default](https://mix.office.com/watch/zkgq0u7visw9)                      | A szervezet éves pénzügyi helyzetének megtekintése. Ez a jelentés az eszközöket és a kötelezettséget, valamint a részvényesek saját tőkéjét jeleníti meg egyidejűleg.                                                                                                                                                                                |
| [Summary Trial Balance – Default](https://mix.office.com/watch/1ewwgbpv0iwrl)                          | Egyenleg-adatok megtekintése az összes számlához, amelyekhez nyitó és záró egyenleg tartozik, hitel- vagy bankkártya egyenleggel rendelkeznek nettó eltéréssel.                                                                                                                                                                  |
| [Summary Trial Balance Year Over Year – Default](https://mix.office.com/watch/1ewwgbpv0iwrl)           | Az aktuális év és az elmúlt év nyitó és záró, valamint a tartozik és követel egyenlegeinek és azok nettó különbség rendelkező fiókok egyenleg adatainak megtekintése.                                                                                                                           |
| [Weekly Sales and Discounts - Default](https://mix.office.com/watch/112ng0hy5de0j)                     | Betekintés a hónap egyes heteinek értékesítéseibe és kedvezményeibe. Ez a jelentés összesen négy hetet tartalmaz.                                                                                                                                                                                                              |
| [Rendelkezésre álló költségvetési források - alapértelmezett](https://mix.office.com/watch/15hcpezcbx7tv)                         | Felülvizsgált költségvetés, tényleges kiadások, költségvetési foglalások és fiókok rendelkezésre álló költségvetési források részletes összehasonlítása                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Pénzügyi jelentés megnyitása
Amikor rákattint a **Pénzügyi jelentéskészítés** menüre, a vállalat alapértelmezett pénzügyi jelentéseinek listája jelenik meg. Ezután megnyithatja vagy módosíthatja a jelentést. Az alapértelmezett jelentés megnyitásához válassza ki a jelentés nevét. A jelentés első megnyitásakor automatikusan létrejön a jelentés az előző hónapra. Például jelentést 2016 augusztus első alkalommal nyitja meg, ha a jelentés jön létre 2016. július 31. Egy jelentés megnyitása után elkezdheti annak böngészését bizonyos adatok utáni leásással, illetve módosíthatja a jelentés beállításait.

## <a name="creating-and-modifying-financial-reports"></a>Pénzügyi jelentések létrehozása és módosítása
A pénzügyi jelentések listából új jelentést hozhat létre, vagy módosíthat egy meglévő jelentést. Ha rendelkezik a megfelelő engedélyekkel, új pénzügyi jelentés gombra kattintva létrehozhat **új** meg a műveletpanelen. A jelentés Tervező program letöltődik az eszközre. A report designer indítása után majd az új jelentést hozhat létre. Az új jelentés mentése után megjelenik a pénzügyi jelentések listájában. A lista csak a vállalat műveletekhez használt 365 Dynamics létrehozott jelentéseket tartalmazza. Dynamics 365 műveletek pénzügyi jelentések létrehozása és módosítása a folyamattal kapcsolatos további tudnivalókért olvassa el ezeket [blogbejegyzések](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/tag/learning/) a pénzügyi Dynamics jelentése a blog. **Megjegyzés:** tölti le a jelentés Tervező-ügyfél verziója szükséges 4.6.2 a Microsoft .NET Framework telepítve van a számítógépen. Ezen verziója a Microsoft .NET Framework letöltött és telepített [Itt](https://www.microsoft.com/en-us/download/details.aspx?id=53345). Chrome használata, telepítenie kell a ClickOnce kiterjesztése annak érdekében, hogy töltse le a jelentést Tervező ügyfél. Incognito módban futtatja, győződjön meg arról, a ClickOnce kiterjesztés incognito mód engedélyezve van. Módosíthatja is a jelentést, amely megjelenik a pénzügyi jelentések listájában. Ha be van jelölve a jelentés neve körüli terület, kattintson a **Szerkesztés** menüpontra a Műveleti ablaktáblán. A jelentéstervező program elindul.

<a name="see-also"></a>Lásd még
--------

[View financial reports](view-financial-reports.md)

[Dynamics Pénzügyi jelentések blog](http://blogs.msdn.com/b/dynamics_financial_reporting/)


