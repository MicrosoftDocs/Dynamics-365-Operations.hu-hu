---
title: "Vállalatközi számlázás"
description: "Ebben a cikkben tudnivalók és példák találhatóak a Microsoft Dynamics 365 for Operations rendszer projektjeire vonatkozó vállalatközi számlázásról."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 94153
ms.assetid: 33e98da7-01c1-4369-923d-aa1c8326cb80
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 8a606f81e6e66390bf0add3deeeb032ab4cbd90b
ms.lasthandoff: 03/31/2017


---

# <a name="intercompany-invoicing"></a>Vállalatközi számlázás

[!include[banner](../includes/banner.md)]


Ebben a cikkben tudnivalók és példák találhatóak a Microsoft Dynamics 365 for Operations rendszer projektjeire vonatkozó vállalatközi számlázásról.

Előfordulhat, hogy a szervezete több osztállyal, leányvállalattal és egyéb jogi személyekkel rendelkezik, amelyek az adott projektekhez egymás között is átadnak termékeket és szolgáltatásokat. *Kölcsönadó jogi személy* a neve azon jogi személynek, aki szolgáltatást vagy terméket nyújt, és *kölcsönbe vevő jogi személy* a neve azon jogi személynek, aki átveszi a szolgáltatást vagy terméket. 

Az alábbi ábrán egy tipikus forgatókönyv látható, amelyen két jogi személy, SI FR (a kölcsönbe vevő jogi személy) és az SI USA (a kölcsönadó jogi személy)forrásokat oszt meg A vevő számára történő projekt szállításához. Ebben az esetben az SI FR-vel kötnek szerződést az A vevő számára történő munka szállítására. 

[![Vállalatközi számlázási példa](./media/interco.invoicing-01.jpg)](./media/interco.invoicing-01.jpg) 

A cél a Költségkontroll, az árbevétel elszámolást, az adók, és transzferárak rugalmasabbá és hatékonyabbá váljanak a vállalatközi projekttranzakciókra vonatkozóan. Ezen túlmenően a következő lehetőségeket nyújtják:

-   Hozzon létre vevői számlát egy projekthez a kölcsönbe vevő jogi profilban a vállalatközi időnyilvántartások, költségek, és szállítói számlák segítségével a kölcsönadó jogi személy profilban.
-   A adószámítások és a közvetett költségek támogatása.
-   A kölcsönadó jogi személy bevétel-könyvelésének elhalasztása, amikor a kölcsönbe vevő jogi személynek fel kell ismernie a költséget.
-   A kölcsönadó jogi személy befejezetlen termelés (WIP) bevételének elhatárolása.
-   Azon transzferárak beállítása, amelyek különböző árképzési modelleken alapulhatnak. Íme néhány példa:
    -   **Mennyiség** – Az az összeg, amelyet az **Árképzés** mezőben a tényleges költség a mennyiség vagy az egység szerint.
    -   **Költségek összege** – A tranzakciónkénti eladási ár/költség plusz a költségek ára, amelyet az **Árképzés** mezőben ad meg.
    -   **Költségszázalék** – A transzferár a tranzakciónkénti eladási ár/költség, amelyet az **Árképzés** mezőben megadott költségszázalékkal szorozzák meg.
    -   **Az eladási ár százaléka** – A kölcsönadó jogi személynek átadott eladási ár százaléka.
    -   **Az eladási ár alatti összeg** – A kölcsönbe vevő jogi személy visszatartja az összeget az eladási áraktól a kölcsönadó jogi személy számára történő átvitel előtt.
    -   **Hozzájárulási arány** – Az **Árképzés** mezőben megadott szám a hozzájárulási arány, amelyet az eladási ár százalékaként fejeznek ki.

## <a name="example-1-set-up-parameters-for-intercompany-invoicing"></a>1. Példa: A vállalatközi számlázásra vonatkozó paraméterek beállítása
Ebben a példában az USSI a kölcsönadó jogi személy, és az erőforrásai azon kölcsönbe vevő jogi személy idő jelentése, amelyhez a végső vevővel kötött szerződést tartozik. Az Órák és kiadások, az USSI alkalmazottak jelentését tartalmazhatja a projekt számlázása, amely FRSI-t hoz létre. Ezen kívül van a tranzakcióknak egy harmadik forrása is, amely a kölcsönadó jogi személytől származik (ebben a példában USSI), amikor az biztosítja a megosztott szállítók szolgáltatásait (például FRSI) és azokat a költségeket továbbítja a projektek számára a leányvállalatokon belül. Az összes megfelelő számladokumentum és adó számítását a Dynamics 365 for Operations rendszer végzi el. 

Ebben a példában az FRSI lehetőségnek kell az USSI jogi személy vevőjének lennie és az USSI lehetőségnek az FRSI jogi személy szállítójának kell lennie. Ezt követően beállíthat egy vállalatközi kapcsolatot a két jogi személy között. A következő eljárás bemutatja,hogy hogyan állíthatja be úgy a paramétereket, hogy mindkét jogi személy szerepeljen a vállalatközi számlázásban.

1.  Az FRSI beállítása az USSI jogi személy vevőjeként és az USSI beállítása az FRSI jogi személy szállítójaként. A feladathoz szükséges lépésekhez három belépési pont van.
    | Lépés | Belépési pont                                                                       | Leírás   |
    |------|-----------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | A:    | Az USSI-ben kattintson a **Kinnlevőségek** &gt; **Vevők** &gt; **Összes vevő** pontra. | Hozzon létre egy új ügyfélbejegyzést az FRSI lehetőségre vonatkozóan, és válassza ki a vevőcsoportot.                                                                                                                                                                                                                           |
    | milliárd    | Az FRSI-ben kattintson a **Kötelezettségek** &gt; **Szállítók** &gt; **Összes szállító** pontra.        | Új szállítói rekord létrehozása az USSI lehetőségre vonatkozóan, és a szállítói csoport kiválasztása.                                                                                                                                                                                                                               |
    | K    | Az FRSI lehetőségben nyissa meg az imént létrehozott szállítói rekordot.                            | A Műveleti ablaktáblán a **Általános** lapon a **Beállítás** csoportban kattintson a **Vállalatközi** lehetőségre. A **Vállalatközi** lapon a **Kereskedelmi kapcsolat** lapon állítsa az **Aktív** csúszkát **Igen** lehetőségre. A **Vevő vállalat** mezőben jelölje ki azt az ügyfélbejegyzést, amelyet az A. lépésben hozott létre. |

2.  Kattintson a **Projektvezetés és könyvelés** &gt; **Beállítás** &gt; **Projektvezetés és könyvelés paraméterei** lehetőségre, ezt követően kattintson a **Vállalatközi** lapra. A paraméterek beállításának módja attól függ, hogy Ön a kölcsönbe vevő jogi személy vagy a kölcsönadó jogi személy szerepkörével rendelkezik.
    -   Ha a kölcsönbe vevő jogi személy, akkor válassza ki azt a beszerzési kategóriát, amelyet azon szállítói számlák egyeztetésére használnak, amelyek automatikusan létrejöttek.
    -   Ha Ön a hitelező jogi személy az összes kölcsönbe vevő jogi személyre vonatkozóan, válassza ki az alapértelmezett projekt kategóriát minden egyes tranzakció típusra vonatkozóan. Az adó konfigurációjára a projekt kategóriákat használják, ha a vállalatközi tranzakciókban kiszámlázott kategóriák csak a kölcsönbe vevő jogi személy lehetőségben léteznek. Választhatja a bevétel elhalasztását a vállalatközi tranzakciókra vonatkozóan. Ezt a könyvelést akkor hajtják végre, amikor a tranzakciókat feladták, és ezt követően sztornírozták a vállalatközi számla feladásakor.

3.  Kattintson a **Projektvezetés és könyvelés** &gt; **Beállítás** &gt; **Árak** &gt; **Transzferár** lehetőségre.
4.  Jelölje be a pénznem, a tranzakció típus és az átviteli ármodell lehetőséget. A számlában használt pénznem az a pénznem, amelyet konfiguráltak a vevői rekordban a kölcsönbe vevő jogi személyre vonatkozóan a kölcsönadó jogi személy lehetőségben. A pénznem az átadási ár táblában szereplő tételeket megfeleltetésére szolgál.
5.  Kattintson a **Főkönyv** &gt; **Feladás beállítása** &gt; **Vállalatközi könyvelés** elemre, és állítsa be az USSI és FRSI kapcsolatát.

## <a name="example-2-create-and-post-an-intercompany-timesheet"></a>2. példa: Egy vállalatközi idő-nyilvántartás létrehozása és feladása
Az USSI, a kölcsönadó jogi személy, akinek létre kell hozni és fel kell adni az FRSI kölcsönbe vevő jogi személytől származó projektre vonatkozó idő-nyilvántartást. A feladathoz szükséges lépésekhez két belépési pont van.

| Lépés | Belépési pont                                                                       | Leírás                                                                                                                                                                                       |
|------|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A:    | **Projekt management és számlázás** &gt; **Időnyilvántartások** &gt; **Összes időnyilvántartás** | Új időnyilvántartás létrehozása. Az idő-nyilvántartási sorban, a **Jogi személy** mezőben válassza az **FRSI** lehetőséget. A **Projekt azonosító** mezőben, jelölje ki az FRSI projektet. Adja meg a hét egyes napjain teljesített munkaórák számát. |
| milliárd    | **Idő-nyilvántIartás** oldal                                                                | A munkafolyamat futtatása után adja fel az Időnyilvántartást és jegyezze fel a bizonylat számát.                                                                                                               |

## <a name="example-3-create-and-post-an-intercompany-vendor-invoice"></a>3. példa: Egy vállalatközi szállítói számla létrehozása és feladása
Az USSI, a kölcsönadó jogi személy, akinek létre kell hozni és fel kell adni az FRSI kölcsönbe vevő jogi személytől származó projektre vonatkozó vállalatközi szállítói számlát. A szállítói számla a kihelyezett munkát és azt a költséget jelöli, amelyet az USSI által kifizetett szállítók hajtottak végre. A feladathoz szükséges lépésekhez két belépési pont van.

| Lépés | Belépési pont                                                                                      | Leírás                                                                                                                                                                                                                                                                          |
|------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A:    | **Kötelezettségek** &gt; **Számlák** &gt; **Nyitott szállítói számlák** &gt; **Új szállítói számla** | Hozzon létre új szállítói számlát, és adja meg azokat a szolgáltatásokat, amelyeket az FRSI projekt nevében szereztek be.                                                                                                                                                                                  |
| milliárd    | A **Szállítói számla** oldal                                                                      | Adja meg azokat a sorokat, amelyek az FRSI nevében kihelyezett szolgáltatásokat jelenítik meg. A **Részletek sor** Gyorslapon, a számlázási sorra vonatkozó **Projekt** lapon a **Projektvállalat** mezőjében adja meg az **FRSI** lehetőséget. Adja meg a projektet és a megfelelő információkat. Ezt követően adja fel a szállítói számlát. |

## <a name="example-4-create-and-post-the-intercompany-invoice"></a>4. példa: A vállalatközi szállítói számla létrehozása és feladása
Az USSI, a kölcsönadó jogi személynek létre kell hozni és fel kell adni a vállalatközi számlát. A feladathoz szükséges lépésekhez két belépési pont van.

| Lépés | Belépési pont                                                                                             | Leírás                                                                                                                                      |
|------|---------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| A:    | **Projektvezetés és könyvelés** &gt; **Projektszámlák** &gt; **Vállalatközi vevői számla**  | Kattintson az **Új** lehetőségre a **A vállalatközi számla létrehozása** oldal megnyitásához.                                                                                  |
| milliárd    | **Projektvezetés és könyvelés** &gt; **Projektszámlák** &gt; **Vállalatközi vevői számlák** | **A vállalatközi számla létrehozása** lapon, adja meg a jogi személyt, adja meg azt a tranzakciót, amelyet tartalmaznia kell, majd kattintson a **Keresés** lehetőségre. |
| K    | **Projektvezetés és könyvelés** &gt; **Projektszámlák** &gt; **Vállalatközi vevői számlák** | Jelölje ki a tranzakciót a számlához, vagy kattintson az **Összes kijelölése** lehetőségre a lista összes tranzakciójának számlázásához, és kattintson az **OK** lehetőségre.                  |
| A    | A **Vállalatközi számla** lap                                                                       | A vállalatközi vevői számlajavaslat jelenik meg.                                                                                             |
| E:    | A **Vállalatközi számla** lap                                                                       | Kattintson a **Bejegyzés** lehetőségre.                                                                                                                                  |

## <a name="example-5-post-the-vendor-invoice-and-invoice-the-customer"></a>5. példa: A szállítói számla feladása és a vevő számlázása
A kölcsönadó jogi személy, az USSI feladja a vállalatközi vevői számlát, a függőben lévő szállítói számla egyeztetését az FRSI, a kölcsönbe vevő jogi személy lehetőségben hozzák létre. A szállítói számla könyvelése után az FRSI a projektet is számlázza az USSI által megadott órákra vonatkozóan. A feladathoz szükséges lépésekhez három belépési pont van.

| Lépés | Belépési pont                                                                                        | Leírás                                                                                                             |
|------|----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| A:    | **Kötelezettségek** &gt; **Számlák** &gt; **Függőben lévő szállítói számlák**                            | Tekintse át a számlát annak ellenőrzése érdekében, hogy az idő-nyilvántartás értékeket tartalmazza, és ezt követően adja fel a szállítói számlát.                  |
| milliárd    | **Projektvezetés és könyvelés** &gt; **Projektszámlák** &gt; **Projekt számlajavaslatai** | Új projektszámla létrehozása a projektre vonatkozóan és győzödjön meg arról, hogy a feladott óratranzakciók megjelennek.            |
| K    | A **Projektszámla** lap                                                                       | Válassza ki a projektszámlát, és kattintson a **Részletek megtekintése** az önköltségi és az eladási összeg ellenőrzéséhez. Ezt követően adja fel a számlát. |






