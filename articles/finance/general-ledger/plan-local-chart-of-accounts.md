---
title: Helyi számlatükör tervezése
description: Ez a témakör segítséget nyújt a számlatükre tervezéséhez, ha követelményei vannak a szervezete törvényi/helyi követelményei kapcsán.
author: veneva
ms.date: 10/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts, LedgerConsolidateAccountGroup, MainAccountConsolidateAccount, DimensionDetails, MainAccountDetails
ROBOTS: ''
audience: Application User
ms.devlang: ''
ms.reviewer: roschlom
ms.tgt_pltfrm: ''
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.search.industry: ''
ms.author: veneva
ms.search.validFrom: 10/07/2021
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a99e4ef3355188f574930c1d885e53fcb3134ad1
ms.sourcegitcommit: c4500b626667185643b3a2e7fc3a004d42198d07
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2021
ms.locfileid: "7725175"
---
# <a name="plan-your-local-chart-of-accounts"></a>Helyi számlatükör tervezése

[!include [banner](../includes/banner.md)]

Ez a témakör segítséget nyújt a számlatükre tervezéséhez, ha a szervezet olyan jogi személyeket is tartalmaz, amelyek meg kell feleljenek a vállalkozás szemben elvárt helyi követelményeknek. Ez a témakör a következő kifejezések alapján írja le a számlatükröket:

- **Globális** – A szervezet globálisan használt számlatükre. A legtöbb esetben ebbe a számlatükörbe konszolidál.
- **Helyi** – Egy számlatükör, amely egy adott ország vagy régió területén jogi személynél használ.
- **Megosztott** – Olyan számlatükör, amely egynél több jogi személy számára használható. A globális számlatükör és a helyi számlatükör is megosztott lehet.

Több számlatükröt is létrehozhat és megoszthat. Egy megosztott számlatükröt egynél több jogi személy is használhat, de minden egyes jogi személyhez csak egy számlatükröt lehet hozzárendelni. A jogi személy által használt számlatükör a **Főkönyv** oldalon van definiálva.

A számlatükör megtervezésekor számos szervezet egy globális számlatükör használatára törekszik. A megosztott számlatükör képeség lehetővé teszi globális számlatükör létrehozását. Előnyös lehet egyetlen számlatükröt létrehozni és használni. Például egyszerűbb a szabályozás és az ellenőrzés, a karbantartás és a jelentéskészítés.

A legtöbb szervezet előnyben részesít egy globális számlatükröket, és ez a legegyszerűbben megvalósítható típus. Egyes jogi személyek azonban a következő okokból igényelnek helyi számlatükröket:

- Helyi jogszabályi követelmények
- A helyi könyvelési szabványok követelményei
- Iparági követelmények
- Vállalatspecifikus jelentési és elemzési követelmények

Ha a szervezet megköveteli, hogy egy jogi személy helyi számlatükröt használjon, két lehetőség áll rendelkezésre ennek bevezetéséhez:

- A globális számlatükör hozzárendelése és a helyi követelmények teljesítéséhez egyéb módszerek meghatározása.
- Rendeljen a jogi személyhez egy helyi számlatükröt, és határozza meg a globális számlatükörrel a kapcsolatokat.

Az alkalmazott megoldást a szervezeti struktúra és a jelentési struktúra határozza meg.

[![Diagram, amely mutatja, hogyan határozza meg a szervezeti struktúra, hogy globális vagy helyi számlatükör legyen-e használva.](./media/local-chart-of-accounts-diagram.png)](./media/local-chart-of-accounts-diagram.png)

Ha a globális számlatükör hozzá van rendelve a jogi személyhez, a következő lehetőségek állnak rendelkezésre a helyi jelentési követelményeknek való megfeleléshez:

- Helyi konszolidálás végzése.
- Pénzügyi dimenzió használata a helyi számlatükör nyomon követésére.
- Helyi főszámlák létrehozása a globális számlatükörben.
- Külső leképezés készítése a helyi számlatükörhöz.

Ha a helyi számlatükör hozzá van rendelve a jogi személyhez, csak a következő lehetőség áll rendelkezésre a globális konszolidácó követelményeknek való megfeleléshez.

## <a name="global-chart-of-accounts-assigned-to-a-legal-entity"></a>Jogi személyhez rendelt globális számlatükör

Ha a globális számlatükröt egy jogi személyhez kell rendelnie, négy lehetőség áll rendelkezésre a rendszer konfigurálásához, a korábban leírtak szerint. A négy lehetőség közül mindegyiknél egyetlen számlatükör van konfigurálva, és egy jogi személyhez csatolva a **Főkönyv** lapon. Ezután minden egyes beállítás más megközelítést alkalmaz a honosítási követelmények követelményeinek megfelelése érdekében. A következő szakaszok a rendszer honosítási követelményeinek konfigurálási lépéseit ismertetik. Ezenkívül leírják az egyes lehetőségek előnyeit és hátrányait is.

### <a name="do-local-consolidation"></a>Helyi konszolidálás végzése

A helyi konszolidáció az ajánlott megközelítés a helyi számlatükörre vonatkozó követelmények teljesítéséhez, az erre a célra kialakított rendszerfunkciókat kihasználva.

#### <a name="set-up-consolidation-for-a-local-chart-of-accounts"></a>Konszolidáció beállítása helyi számlatükörhöz

1. Egyetlen globális számlatükör létrehozása, amely tartalmazza az összes szükséges fő számlát.
2. Minden jogi személynél rendelje hozzá a globális számlatükröt a **Főkönyv** oldalon.
3. Hozzon létre egy konszolidációs jogi személyt minden szükséges honosításhoz.
4. Tegye a következők egyikét:

    - Ha csak egy honosítás szükséges, állítsa be a konszolidációs számlát a **Fő számla** lapon, vagy használja a **Konszolidációs csoportok** és a **További konszolidációs számlák** lapot.
    - Ha egynél több honosítás szükséges, vagy ha mind a számlaszám, mind a számlanév megköveteli a fordítást, a **Konszolidációs csoportok** és a **További konszolidációs számlák** lapokon lehet érvényesíteni a honosítási követelményeket.

5. Futtassa a konszolidációs folyamatot, hogy átalakítsa azt az értéket a forrás jogi személyből, amely a globális számlatükröt használja a konszolidációs vállalathoz , amely a helyi számlatükröt használja.

#### <a name="advantages"></a>Előnyök

- Ez a megközelítés egységes munkamódszert biztosít a szervezeten belül.
- A helyi beosztásnak egy fordítása van.
- Ez a megközelítés mind a fő számla azonosítójának, mind az egyes fő számlák neveinek fordítását támogatja.
- Támogatja a többszörös honosításokat.

#### <a name="disadvantages"></a>Hátrányok

- Létrejön egy további konszolidációs vállalat.
- Elvégzésre kerül egy további konszolidációs folyamat.
- Ez a megközelítés csak a konszolidációs folyamat befejezése után tud jelentést készítni a honosított diagramról.

### <a name="use-a-financial-dimension-to-track-the-local-chart-of-accounts"></a>Pénzügyi dimenzió használata a helyi számlatükör nyomon követésére

Ez a megközelítés egy pénzügyi dimenziót használ, ahol a pénzügyi dimenzióértékek a honosításhoz szükséges helyi fő számlákat képviselik. Jól működik, ha csak egy honosítás szükséges. Ugyanakkor a további honosítások és pénzügyi dimenziók hozzáadása során a rendszer kevésbé használhatóvá válik.

#### <a name="set-up-a-financial-dimension-for-a-local-chart-of-accounts"></a>Pénzügyi dimenzió beállítása helyi számlatükörhöz

1. Egyetlen globális számlatükör létrehozása, amely tartalmazza az összes szükséges fő számlát.
2. Minden jogi személynél rendelje hozzá a globális számlatükröt a **Főkönyv** oldalon.
3. Hozzon létre egy pénzügyi dimenziót, amely képviseli helyi számlatükröt.
4. Hozzon létre egy pénzügyidimenzió-értékeket, amely képviselik helyi számlatükör fő számláit.
5. A számlastruktúrát frissítse úgy, hogy tartalmazza a "helyi számlatükör" pénzügyi dimenziót.
6. Győződjön meg róla, hogy a "helyi számlatükör" pénzügyi dimenziónak mindig legyen értéke, és nem enged meg üres értéket. Célszerű származtatott dimenziókat vagy rögzített dimenziókat használni.
7. Hozzon létre egy pénzügyi dimenziókészletet, ahol a "helyi számlatükör" pénzügyi dimenzió az első kijelölt pénzügyi dimenzió. A pénzügyi dimenziókészlet a főkönyvi kivonat generálása során használható.

#### <a name="advantages"></a>Előnyök

- A globális és a helyi számlatükrök fő számlái is léteznek a pénzügyi dimenziók szintjén. A fő számla globális, a pénzügyi dimenzió értéke pedig helyi.
- Ez a megközelítés valós idejű jelentést és nézeteket biztosít mind a globális pénzügyi helyzetről, mind a helyi pénzügyi helyzetről.

#### <a name="disadvantages"></a>Hátrányok

- Ha a főkönyvi paraméterekben az **Összesítő számlához használt értékek** mezőben a **Könyvelési felosztások** érték van beállítva, akkor a kinnlevőségek és a kötelezettségek összesítő számlájához hibásan lesznek használva azok a pénzügyi dimenziók, amelyek a költség/eszköz/bevétel fő számláját képviselik. Azt ajánljuk, hogy a mezőt inkább forrásdokumentumként állítsa be, hogy a helyes pénzügyidimenzió-értékeket használja a program.
- Ha sok helyi számlatükör szükséges, és mindegyikhez egy pénzügyi dimenzió van használva, akkor a pénzügyi dimenzióértékek listája hosszú és nehézkes lehet a használata.
- Ha több helyi számlatükröt kell adni, és ezek egy-egy külön pénzügyi dimenzióval vannak képviselve vannak, akkor a rendszer használhatóságát és teljesítményét befolyásolhatja a pénzügyi dimenziók és a pénzügyi dimenziókészletek hozzáadásakor.
- Javasoljuk, hogy alaposan mérlegelje a szükséges pénzügyi dimenziók számát, az egyes dimenziókban megadott értékek számát és a pénzügyidimenzió-készletek számát, mivel ezek a tényezők hatással lehetnek a rendszer teljesítményére.

### <a name="create-local-main-accounts-in-the-global-chart-of-accounts"></a>Helyi főszámlák létrehozása a globális számlatükörben

*Amiről a másolásszerkesztő kérdezett:* Ebben a megközelítésben a globális számlatükör helyi fő számlái tartalmazzák a fő számlákat a helyi számlatükörben a globális számlatükörben.

*Eredeti verzió*: A globális számlatükör megközelítésben a helyi főszámlákhoz az, hogy a helyi számlatükör főszámlák részei a globális számlatükörnek.

*Ezt kellene mondania*: Ebben a megközelítésben a helyi számlatükör helyi fő számlái szerepelnek a globális számlatükörben.


#### <a name="set-up-local-main-accounts-in-the-global-chart-of-accounts"></a>Helyi főszámlák beállítása a globális számlatükörben

1. Egyetlen számlatükröt hozzon létre, amely mind a globális számlatükör, mind a helyi számlatükör fő számláit tartalmazza.
2. Minden jogi személynél rendelje hozzá a számlatükröt a **Főkönyv** oldalon.
3. Az azonos célt képviselő fő számlák összegzése céljából a számlatükre összegző számlákat hozhat létre a számlatükrökhöz.
4. Hozzon létre jogiszemély-felülbírálásokat minden helyi számlához, hogy megakadályozza más jogi személyek tranzakcióit, amelyekhez nem készült a helyi számla.
5. Hozzon létre jogi személy-felülbírálásokat minden globális számlához, hogy megakadályozza a tranzakciókat a honosítási jogi személyekből.

#### <a name="advantages"></a>Előnyök

- A globális pénzügyi helyzet és a helyi pénzügyi helyzet valós idejű nézete elérhető a rendszer bizonyos jelentéseiben és bizonyos nézetekben a rendszerben, például a mérleg pénzügyi jelentésében. Az összegző számla **Időszak** gombjával is elérhető.
- Nincs további szegmens a főkönyvi számlán.

#### <a name="disadvantages"></a>Hátrányok

- Az összegző számla használata és láthatósága korlátozott. Például az összegző számlák nem láthatók a **Főkönyvi kivonat** listaoldalon.
- A karbantartáshoz további munka szükséges.
- A pénzügyi jelentések létrehozása további manuális munkát igényel.

### <a name="do-external-mapping-to-the-local-chart-of-accounts"></a>Külső leképezés készítése a helyi számlatükörhöz

A globális számlatükör azt feltételezi, hogy Ön a leképezéseket és honosításokat a rendszeren kívül kezeli. Ebben a megközelítésben egyetlen globális számlatükröt hoz létre a Microsoft Dynamics 365 Finance alkalmazásban és a rendszeren kívül kezeli a követelményeket.

#### <a name="set-up-external-mapping-to-a-local-chart-of-accounts"></a>Külső leképezés beállítása a helyi számlatükörhöz

1. Egyetlen globális számlatükör létrehozása, amely tartalmazza az összes szükséges fő számlát.
2. Minden jogi személynél rendelje hozzá a globális számlatükröt a **Főkönyv** oldalon.
3. A helyi számlatükörhöz a leképezést a Finance alkalmazáson kívül végzi.

#### <a name="advantages"></a>Előnyök

- Ez a megközelítés konzisztens munkamódszert biztosít a szervezeten belül.

#### <a name="disadvantages"></a>Hátrányok

- A helyi jelentés nem érhető el a rendszerből.
- Ez a megközelítés hibákra hajlamos pénzügyi jelentések létrehozásakor.

## <a name="local-chart-of-accounts-assigned-to-legal-entity"></a>Jogi személyhez rendelt helyi számlatükör

Ha a szervezet úgy dönt, hogy nem használ globális számlatükröt a jogi személyek között, akkor minden egyes egyedi helyi számlatükör számára külön számlatükör jön létre. Ekkor minden jogi személy a **Főkönyv** lapon a megfelelő számlatükhöz kapcsolódik.

### <a name="do-global-consolidation"></a>Globális konszolidálás végzése

Ebben a megközelítésben egy konszolidációs vállalat segítségével lehet egyesíteni és összesíteni az egyes forrásvállalatok egyenlegét a konszolidációs vállalat összesített globális számlatükrében. Ehhez a módszerhez szükség van a helyi számlatükör és a konszolidációs vállalat globális számlatükre megfeleltetésére.

#### <a name="set-up-global-consolidation"></a>Globális konszolidálás beállítása

1. Hozzon létre egy külön számlatükröt minden olyan jogi személyhez, amelynek más helyi számlatükre van. Ha bármelyik jogi személynek ugyanaz a helyi számlatükre, akkor csak egy helyi számlatükörre van szükség, és meg lehet osztani.
2. Minden jogi személynél rendelje hozzá a megfelelő számlatükröt a **Főkönyv** oldalon.
3. Nem kötelező: Hozzon létre számlatükröt minden konszolidációs vállalat globális számlatükre számára, amelynek más a globális számlatükre.
4. Hozzon létre egy konszolidációs jogi személyt minden szükséges konszolidációs szinthez, és rendelje hozzá a megfelelő számlatükröt a **Főkönyv** lapon.
5. Tegye a következők egyikét:

    - Ha csak egy konszolidáció szükséges, konfigurálja a konszolidációs számlát a **Fő számla** oldalon.
    - Ha egynél több konszolidáció szükséges, vagy ha mind a számlaszám, mind a számlanév megköveteli a fordítást, a **Konszolidációs csoportok** és a **További konszolidációs számlák** lapokon lehet érvényesíteni a globális számlatükrök követelményeit.

6. A konszolidációs folyamatot futtassa, és az egyenlegeket vigye át a helyi jogi személyekből a konszolidált jogi személybe. Ez a konszolidált jogi személy az 5. lépésben meghatározott konszolidációs számlákat használja.

#### <a name="advantages"></a>Előnyök

- A helyi könyvelési szabványok formátuma natívan van alkalmazva.
- Ez a megközelítés egyszerűbbé teszi a helyi pénzügyi csoport számára a munkát.

#### <a name="disadvantages"></a>Hátrányok

- Nem érhető el a globális pozíció valós idejű nézete.
- Előfordulhat, hogy a konszolidációs folyamat gyakrabban fut.

## <a name="additional-resources"></a>További erőforrások

- [Számlatükör tervezése](plan-chart-of-accounts.md)
- [Főkönyvek konfigurálása](configure-ledger.md)
- [A pénzügyi dimenziók és a feladás](Default-dimensions.md#balancing-dimension)
- [Pénzügyi dimenziókészletek](financial-dimension-sets.md)
- [Konszolidáció és megszüntetés áttekintése](../budgeting/consolidation-elimination-overview.md)
- [Konszolidációs csoportok és további konszolidációs számlák](../budgeting/consolidation-account-groups-consolidation-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
