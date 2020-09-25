---
title: Költségellenőrzési munkaterület
description: Ez a témakör a Költségellenőrzés munkaterületről nyújt tájékoztatást. Ez a munkaterület központi pont, ahol a menedzserek, akik felelősek egy költségobjektum vagy egy költségobjektum-készlet egy dimenzióban vagy dimenziókon belüli vezérléséért, hozzáférhetnek a jelentésekhez.
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostControlWorkspaceConfiguration, CAMCostControlWorkspace, CAMCostControlWorkspaceConfigurationPerUser
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e94a8a5ecdc636e73755460a89b08f7271cd3ae1
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759520"
---
# <a name="cost-control-workspace"></a>Költségellenőrzési munkaterület 

[!include [banner](../includes/banner.md)]

A **Költségkontroll** munkaterület központi pont, ahol a menedzserek, akik felelősek egy költségobjektum vagy egy költségobjektum-készlet egy dimenzióban vagy dimenziókon (pl. költségközpontok és termékcsoportok) belüli vezérléséért, hozzáférhetnek a jelentésekhez. A munkaterületen lévő jelentéseket teljes mértékben költségkönyvelők kezelik, így a jelentéskészítéshez használt elrendezés és adatok konzisztensek lehetnek az egész szervezeten belül.

## <a name="cost-control-workspace-configuration"></a>Költségellenőrzési munkaterület konfigurációja

A költségkönyvelők meghatározhatnak annyi jelentéskonfigurációt, amennyire szükségük van a kívánt adatösszetételhez vagy elrendezéshez. A jelentés konfigurációja hat szakaszból áll, amelyek mindegyike hozzájárul a célzott adatösszetétel vagy az elrendezés kiválasztásához.

A Költségkontroll munkaterület konfigurálásához kattintson a következőkre: **Költségkönyvelés** \> **Beállítás** \> **Költségellenőrzési munkaterület konfigurációja**.

### <a name="general"></a>Általános

Az **Általános** gyorslapon egyedi jelentéselrendezés hozható létre. A jelentés neve olyan egyedi azonosító lesz, amelyet a felhasználók képesek felismerni a rendszer **Költségkontroll** munkaterületén. Megadhatja azt is, hogy a jelentés megosztott kell-e hogy legyen, vagy a költségkönyvelők belső jelentése.

| Mező       | Leírás |
|-------------|-------------|
| Név        | Az elrendezés egyedi neve. |
| Leírás | Adja meg a részletes leírást. |
| Közzétett   | A mező **Igen** értékének beállítása esetén a felhasználó, akihez a következő szerepkörök valamelyikét rendelték, láthatja a jelentést a **Költségkontroll** munkaterületen:<ul><li>Költségkönyvelés-kezelő</li><li>Költségkönyvelő munkatárs</li><li>Költségkönyvelő adminisztrátor</li><li>Költségobjektum-ellenőr</li></ul>A mező **Nem** értékének beállítása esetén csak azok a felhasználók, akihez a következő szerepkörök valamelyikét rendelték, láthatják a jelentést a **Költségkontroll** munkaterületen:<ul><li>Költségkönyvelés-kezelő</li><li>Költségkönyvelő munkatárs</li><li>Költségkönyvelő adminisztrátor</li></ul> |

### <a name="data-filtering"></a>Adatszűrés

Az **Adatszűrés** gyorslapon meghatározhatja a jelentés adatbeli alapjait. A jelentésben szereplő felhasználók a forrásadatok feldolgozása után láthatják a jelentésben szereplő értékeket.

| Mező                                                             | Leírás |
|-------------------------------------------------------------------|-------------|
| Költségkönyvelési főkönyv                                            | A **Költségkönyvelési főkönyv**, amely a jelentés alapjául szolgál. Az érték a **Költség-ellenőrzőegység** mezőből származik. |
| Költség-ellenőrzőegység                                                 | A kiválasztott érték határozza meg a költségszámítási könyvelést és a költségelemeket, amelyekre ez a jelentés alapul. |
| Statisztikai dimenzióhierarchia, költségösszetevődimenzió-hierarchia | A **Költségellenőrzés** munkaterületen konfigurációs rekord nem pénzbeli vagy monetáris értékeit is is lehet jelenteni, de nem ugyanaz az elrendezés. Válasszon ki egy értéket a **elem dimenzióhierarchia költség** mezőben monetáris értékek jelentéséhez. Válasszon ki egy értéket a **Statisztikai dimenzióhierarchia költség** mezőben nem monetáris értékek jelentéséhez. A kiválasztott dimenzióhierarchia-rekord határozza meg a jelentési és összesítési szintek szerkezetét.<blockquote>[!NOTE]<br>A nem monetáris és pénzbeli értékek egymás melletti megtekintéséhez exportálhat adatokat Microsoft Excel programba és a Microsoft Power BI tartalomcsomagba.</blockquote> |
| Költségobjektum dimenzióhierarchia                                   | Válassza ki a költségobjektum-dimenziók hierarchiáját, amely megfelel a jelentésben megadott célnak. |
| Költségvetés eredeti verziója                                           | Válassza ki a költségkeret-azonosítót, amely az eredeti költségkeretként jelenik meg a jelentés összefüggésében. |
| Költségvetés felülvizsgált verziója                                            | Válassza ki a költségkeret-azonosítót, amely a jelentés összefüggésében módosított költségvetésként működik. |

### <a name="assign-calculation-records"></a>Számítási rekordok hozzárendelése

A többletkalkuláció több számítási lépést hajt végre a forrásadatokon, például a költségviselkedés szerinti osztályozáson, a költségelosztáson és a költségfelosztáson. Az ugyanazon fiskális időszakra többszörös járulékosköltség-számítás is végezhető, ha hiányzó forrásadatokat fedeznek fel, vagy a szabályokat frissíteni kell. Minden járulékosköltség-számítás egyedi azonosítóval kerül mentésre. A költségkönyvelő kiválaszthatja a speciális költségszámítási azonosítót. A jelentés felhasználói, például a vezetők, láthatják az általános számítás eredményeit a **Költségkontroll** munkaterületen.

| Mező                  | Leírás |
|------------------------|-------------|
| Pénzügyi naptári időszak | Válassza ki a fiskális naptári időszakot, hogy hozzárendeljen egy általánosköltség-számítási azonosítót.<blockquote>[!NOTE]<br>A mezőben felsorolt pénzügyi időszakok a költségszámla főkönyvvel kapcsolatos pénzügyi naptártól származnak.</blockquote> |
| Aktuális verzió         | Jelölje ki a megfelelő általánosköltség-számítási azonosítót. |
| Költségvetés-változat         | Jelölje ki a megfelelő általánosköltség-számítási azonosítót. |
| Felülvizsgált költségvetés-verzió | Jelölje ki a megfelelő általánosköltség-számítási azonosítót. |

### <a name="fiscal-periods-per-column"></a>Pénzügyi időszakok oszloponként

Az **Pénzügyi időszakok oszloponként** gyorslapon a Költségkönyvelő eldönti, hogy melyik időszakok jelenjenek meg a jelentés elrendezésében.

A kiválasztott oszlopban szereplő értékeket meg kell szorozni a kijelölt értékekkel a **Pénzügyi időszakok oszloponként** gyorslapon.

| Mező                | Leírás |
|----------------------|-------------|
| Aktuális időszak       | Az aktuális pénzügyi időszak egyenlege jelenik meg.<blockquote>[!NOTE]<br>Alapértelmezés szerint az aktuális időszak a munkamenet dátuma határozza meg. Az a **Költségellenőrzés** munkaterületén kiválasztható egy adott pénzügyi időszakban. A kiválasztott érték majd jelent az aktuális időszakra.</blockquote> |
| Előző időszak      | Az előző pénzügyi időszak egyenlege jelenik meg. A konvertálás az alábbi képlet alapján történik:<br>Aktuális pénzügyi időszak – 1<blockquote>[!NOTE]<br>Alapértelmezés szerint az előző időszakot a munkamenet dátuma határozza meg. A **Költségellenőrzés** munkaterületén kiválasztható egy adott pénzügyi időszak jelenlegi időszakként. Az **Előző időszak** ezután a megadottak szerint lesz újraszámítva.</blockquote> |
| Folyó év mai napig         | A folyó év mai napig jelenik meg. A konvertálás az alábbi képlet alapján történik:<br>YearToDate (Folyó pénzügyi időszak)<blockquote>[!NOTE]<br>Alapértelmezés szerint az aktuális időszak a munkamenet dátuma határozza meg. Az a **Költségellenőrzés** munkaterületén kiválasztható egy adott pénzügyi időszakban. A kiválasztott érték az aktuális időszakra vonatkozik, és a **Folyó év mai napig** értéke ennek megfelelően frissül.</blockquote> |
| Folyó év mai napig átlaga | A folyó év mai napig jelenik meg az átlag. A konvertálás az alábbi képlet alapján történik:<br>(YearToDate [Az aktuális pénzügyi időszak]) ÷ (Count [Az aktuális pénzügyi időszak])<p><strong>Példa</strong></p><ul><li>**Statisztikai dimenziótag:** Teljes munkaidős alkalmazottak</li><li>**Aktuális dátum:** 3-21-2017</li><li>**Időszak:** Pénzügyi időszak 1, Pénzügyi időszak 2, Pénzügyi időszak 3</li><li>**Nagyság:** 10, 10, 12</li></ul>Ebben az esetben **Folyó év mai dátum átlagos** (10 + 10 + 12) ÷ 3 = 10.67<p>A **Folyó év mai dátum átlagos** érték költség elem dimenzió tagok és a statisztikai dimenzió tagok alapján számítható.</p><blockquote>[!NOTE]<br>Alapértelmezés szerint az aktuális időszak a munkamenet dátuma határozza meg. Az a **Költségellenőrzés** munkaterületén kiválasztható egy adott pénzügyi időszakban. A kiválasztott érték az aktuális időszakra vonatkozik, és a **Folyó év mai napig** és **Folyó év mai napig átlag** értéke ennek megfelelően frissül.</blockquote> |

### <a name="columns-to-display-for-costs"></a>Megjelenítendő oszlopok költségekhez

A **Megjelenítendő oszlopok költségekhez** gyorslapon a Költségkönyvelő úgy dönt, hogy mely oszlopoknak kell tartalmaznia a jelentés elrendezését. Három kategóriába sorolhatók: a rögzített költség, változó költség és a költség nem besorolt.

| Mező                 | Leírás |
|-----------------------|-------------|
| Fix költség            | Ez oszloptípus költségét jeleníti meg a tárgyieszköz-alapján a kijelölt többletköltség-számítási azonosítója.<blockquote>[!NOTE]<br>Ennél az oszloptípusnál csak akkor, ha egy többletköltség-számítási azonosítója ki van jelölve a pénzügyi időszak egyenlegének jelennek meg.</blockquote> |
| Változó költség         | Ez az oszloptípus a változó költségét jeleníti meg a tárgyieszköz-alapján a kijelölt többletköltség-számítási azonosítója.<blockquote>[!NOTE]<br>Ennél az oszloptípusnál csak akkor, ha egy többletköltség-számítási azonosítója ki van jelölve a pénzügyi időszak egyenlegének jelennek meg.</blockquote> |
| Rögzített + változó költség | Ez az oszloptípus a rögzített és változó költségét jeleníti meg a tárgyieszköz-alapján a kijelölt többletköltség-számítási azonosítója.<blockquote>[!NOTE]<br>Ennél az oszloptípusnál csak akkor, ha egy többletköltség-számítási azonosítója ki van jelölve a pénzügyi időszak egyenlegének jelennek meg.</blockquote> |
| Teljes költség            | Ennél az oszloptípusnál az összes költség (nem besorolt költség, rögzített költség, valamint változó költség).<blockquote>[!NOTE]<br>Az oszloptípusát mindig mutatja az egyenleget.</blockquote> |
| Nem besorolt költség     | Ez az oszloptípus a nem minősített költségeket mutatja.<blockquote>[!NOTE]<br>Ez az oszlop arra szolgál, hogy ellenőrizze, hogy az összes költség helyesen lett-e besorolva az általános számítással, vagy hogy a költségviselkedési szabályokat be kell-e állítani.</blockquote> |

### <a name="columns-to-display-for-budgeted-costs"></a>Megjelenítendő oszlopok előirányzott költségekhez

A **Megjelenítendő oszlopok költségvetési költségekhez** gyorslapon a Költségkönyvelő úgy dönt, hogy mely oszlopoknak kell tartalmaznia a jelentés elrendezését. Az eredeti és a felülvizsgált költségvetéshez egyéni beállítások is kiválaszthatók.

> [!NOTE]
> Mivel az alábbi mezők ugyanúgy viselkednek az eredeti költségvetés és a felülvizsgált költségvetés esetében, csak egyszer magyarázzuk el.

| Mező                     | Leírás |
|---------------------------|-------------|
| Költségvetés                    | A költségvetési egyenlegek a kiválasztott oszlopok szerint jelennek meg.<blockquote>[!NOTE]<br>Az egyenlegek alapjául az **Adatok szűrése** gyorslapon kijelölt költségvetés-verziók szolgálnak.</blockquote> |
| Költségvetés eltérése           | A költségvetés és a tényleges adatok közötti különbség kiszámítása és megjelenítése. A konvertálás az alábbi képlet alapján történik:<br>Költségvetési egyenleg – a tényleges egyenlege |
| Költségvetés eltérése (%)      | A költségvetés és a tényleges adatok közötti különbség kiszámítása és megjelenítése százalékban. A konvertálás az alábbi képlet alapján történik:<br>(Költségvetési egyenleg – tényleges egyenleg) ÷ költségvetési egyenleg |
| Eltérés időszakának küszöbértéke | Küszöbérték beállítása monetáris összeg eltérésében a jelenlegi időszakban. Ha a küszöbértéket túllépték, a vonal pirosan kiemelve jelenik meg a **Költségkontroll** munkaterületen.<blockquote>[!NOTE]<br>Ez a mező csak a kiadásokat megjelenítő költségelemekre vonatkozik.</blockquote> |
| Eltérés évének küszöbértéke   | Küszöbérték beállítása monetáris összeg eltérésében az évre. Ha a küszöbértéket túllépték, a vonal pirosan kiemelve jelenik meg a **Költségkontroll** munkaterületen. |
| Eltérés küszöbértéke %      | Küszöbérték beállítása az eltéréshez. Ha a küszöbértéket túllépték, a vonal pirosan kiemelve jelenik meg a **Költségkontroll** munkaterületen.<blockquote>[!NOTE]<br>Az aktuális időszakra és évre azonos százalékos küszöbérték vonatkozik.</blockquote> |

## <a name="cost-control-workspace"></a>Költségellenőrzési munkaterület

A **Költségkontroll** munkaterület webes jelentésként szolgál. Emiatt a költség tárgyának felelős vezetők kaphatnak hozzáférést leírtak szerint [objektum hozzáférési jogok megadása a költség-vezérlők](access-rights-cost-object-controller.md).

Például a vezetők számára rendelkezésre álló jelentések listájának megadott beállítás szabályozza a **közzétett** beállítás a **Költségellenőrzés munkaterület konfigurációk** oldalon.

![Egy jelentést, amely a felhasználók megtekinthetik a költség-ellenőrzés munkaterületen](./media/report-cost-control.png)

Vezető kiválaszthatja a megjelenítendő pénzügyi naptári időszakot. Alapértelmezés szerint az alapértelmezett aktuális időszak a munkamenet dátuma határozza meg.

A pénzügyi naptári időszak értékei határozzák meg a jelentés nevének és a pénzügyi naptár kiválasztott a költségkönyvelési Főkönyv, amely társítva van a jelentés neve a a **Költségellenőrzés munkaterület konfigurációk** oldalon.

A költségobjektum-méret hierarchiában a felhasználók kiválaszthatják azt az összesítési szintet, amelyen a mérlegeket meg kell jeleníteni. A hozzáférési szintű biztonság engedélyezésével szabályozhatja az engedélyeket, hogy a felhasználók csak azokat a hierarchiaszinteket választhassák ki, amelyekhez hozzájutottak. Ezért csak az összesített egyenlegeket láthatja, amelyekhez hozzáférést biztosított.

### <a name="add-or-remove-columns"></a>Oszlopok hozzáadása vagy eltávolítása

A felhasználók testre szabhatják a jelentésben szereplő oszlopokat, hogy megfeleljenek a követelményeknek.

### <a name="view-details"></a>Részletek megtekintése

A felhasználók a munkaterületen megjelenített egyenlegek mögötti részleteket is megjeleníthetik. Ha a felhasználók válassza ki a költség dimenzió hierarchia elemcsomóponthoz, és kattintson **részleteinek megtekintése**, a **részletei költség** párbeszédpanelen a csomópont részletes adatainak megjelenítése.

A rács minden költségelemet bemutat, amely összefügg a költségelem dimenzió hierarchia-csomópontjával és értékeivel. A rácsban megjelenő oszlopok megegyeznek a munkaterületi beállításokkal.

Két diagram mutatja a tényleges és költségvetési adatok összevetését és a költségvetési variancia összefoglalását időszakonként.

![Diagramok mutatják a tényleges és költségvetési adatok összevetését és a költségvetési variancia összefoglalását időszakonként.](./media/cost-element-details-operations.png)

A felhasználók a **Költségbejegyzések** elemre kattintva leáshatnak szükség szerint a bejegyzés részleteihez.

![Költségbejegyzések](./media/cost-entries.png)

Például a bérleti díj olyan kiadás, amelyet a költséghelyek között osztanak fel. A felhasználó, aki meg akarja érteni a bérleti költségét, amelyet a költségközpontjának meg kell tennie, lefújhat, hogy megnézze, hogy a bérleti díj kiszámításra került.

Ha a felhasználók a **Felosztás alapja** lehetőségre kattintanak a **Költségbejegyzések** oldalon, megjelenik egy párbeszédpanel. A felhasználók ezután hozzárendelhetik az allokációs bázist a szabályhoz és megtekinthetik az adott időszakra regisztrált megfelelő statisztikai intézkedéseket.

A következő példában az allokációs bázis a **Receptúrafelosztási alap** típusnál van, akkor megjelenik a receptúra. A receptúrában szereplő tényezők szerepelnek. Ezenkívül egy rács mutatja a költségobjektumonként elvégzett számítást.

![Számítás költségobjektumként](./media/cost-entries-allocation-base.png)

További erőforrások 

[Hozzáférési jogok meghatározása költségobjektum-ellenőrök számára](access-rights-cost-object-controller.md)


