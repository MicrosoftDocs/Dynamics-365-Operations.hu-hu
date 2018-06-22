---
title: "Pénzügyi jelentéskészítés"
description: "Ez a témakör azt ismerteti, hol érheti el a Microsoft Dynamics 365 for Finance and Operations pénzügyi jelentéseit, és hogyan használhatja a pénzügyi jelentési szolgáltatásokat. Emellett az elérhető alapértelmezett pénzügyi jelentések leírását is tartalmazza."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 83648a93f367510d7b04bbd04a9f37689ecfaa59
ms.openlocfilehash: 613fcf941576b9fb05f5c059699e4cc9c4cabe3e
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2018

---

# <a name="financial-reporting"></a>Pénzügyi jelentéskészítés

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hol érheti el a Microsoft Dynamics 365 for Finance and Operations pénzügyi jelentéseit, és hogyan használhatja a pénzügyi jelentési szolgáltatásokat. Emellett az elérhető alapértelmezett pénzügyi jelentések leírását is tartalmazza.

<a name="accessing-financial-reporting"></a>Pénzügyi jelentéskészítés elérése
-----------------------------

A **Pénzügyi jelentéskészítés** menüt a következőképpen találhatja meg a Finance and Operations szoftverben:

-   **Főkönyv** &gt; **Lekérdezések és jelentések**
-   **Költségvetés készítése** &gt; **Lekérdezések és jelentések** &gt; **Alapvető költségvetés-tervezés**
-   **Költségvetés készítése** &gt; **Lekérdezések és jelentések** &gt; **Költségvetés-tervezés**
-   **Költségvetés készítése** &gt; **Lekérdezések és jelentések** &gt; **Költségvetés-ellenőrzés**
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
| Pénzügyi jelentések karbantartása            | Pénzügyi jelentések karbantartása            | Főkönyvelő, számviteli felügyelő, pénzügyi ellenőr, költségvetés-kezelő |
| Pénzügyi jelentések létrehozása            | Pénzügyi jelentések létrehozása            | Vezérigazgató, pénzügyi igazgató, könyvelő                                                            |
| Pénzügyi jelentések megtekintése                | Pénzügyi teljesítmény ellenőrzése          | Nincs hozzárendelve                                                                   |

Miután hozzáadtunk egy felhasználót vagy egy szerepkör módosult, a felhasználónak el kell tudni érnie a pénzügyi beszámolókat néhány percen belül. **Megjegyzés:** a sysadmin szerepkör hozzáadódik a pénzügyi beszámoló minden szerepköréhez.

## <a name="default-reports"></a>Alapértelmezett jelentések
A pénzügyi jelentések között 22 alapértelmezett pénzügyi jelentés található. Minden jelentés egy alapértelmezett számlakategóriát használ a Finance and Operations rendszerben. Használhatja ezeket a jelentéseket úgy, ahogy vannak, vagy kiindulópontként a pénzügyi beszámolók készítéséhez. A hagyományos pénzügyi kimutatások, például a Bevétel-kimutatás vagy a Mérlegkimutatás mellett az alapértelmezett jelentések között olyan jelentések is vannak, amelyek különböző pénzügyi kimutatásokat tartalmaznak, amelyeket létrehozhat. 

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
Amikor rákattint a **Pénzügyi jelentéskészítés** menüre, a vállalat alapértelmezett pénzügyi jelentéseinek listája jelenik meg. Ezután megnyithatja vagy módosíthatja a jelentést. Az alapértelmezett jelentés megnyitásához válassza ki a jelentés nevét. A jelentés első megnyitásakor automatikusan létrejön a jelentés az előző hónapra. Például, ha 2016 augusztusában nyit meg egy jelentést először, a jelentés a 2016. július 31-i dátumhoz jön létre. Egy jelentés megnyitása után elkezdheti annak böngészését bizonyos adatok utáni leásással, illetve módosíthatja a jelentés beállításait.

## <a name="creating-and-modifying-financial-reports"></a>Pénzügyi jelentések létrehozása és módosítása
A pénzügyi jelentések listából új jelentést hozhat létre, vagy módosíthat egy meglévő jelentést. Ha rendelkezik a megfelelő engedélyekkel, új pénzügyi jelentést hozhat létre az **Új** gombra kattintva a műveletpanelen. Letöltődik a készülékére egy jelentéstervező program. A jelentéstervező elindulása után új jelentést hozhat létre. Az új jelentés mentése után megjelenik a pénzügyi jelentések listájában. A listában csak a Finance and Operation rendszerben használt vállalatra vonatkozó jelentések jelennek meg. A pénzügyi jelentések a Finance and Operations rendszerben való létrehozásának és módosításának folyamatával kapcsolatos további tudnivalókért olvassa el ezeket a [blogbejegyzések](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/tag/learning/) a Dynamics pénzügyi beszámolók webnaplóból. **Megjegyzés:** A számítógépre, amelyre letölti a jelentéstervező klienst, telepítve kell lennie a Microsoft .NET Framework 4.6.2 verziójának. A Microsoft .NET Framework ezen verziója [innen](https://www.microsoft.com/en-us/download/details.aspx?id=53345) tölthető le és telepíthető. Chrome használata esetén, telepítenie kell a ClickOnce kiterjesztést a jelentéstervező kliens letöltéséhez. Ha a böngészőt incognito módban futtatja, győződjön meg arról, a ClickOnce kiterjesztés engedélyezve van-e az incognito módban. Módosíthatja is a jelentést, amely megjelenik a pénzügyi jelentések listájában. Ha be van jelölve a jelentés neve körüli terület, kattintson a **Szerkesztés** menüpontra a Műveleti ablaktáblán. A jelentéstervező program elindul.

## <a name="additional-resources"></a>További erőforrások
- [Pénzügyi jelentések megtekintése](view-financial-reports.md)
- [Dynamics Pénzügyi jelentések blog](http://blogs.msdn.com/b/dynamics_financial_reporting/)




