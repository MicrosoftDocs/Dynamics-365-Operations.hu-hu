---
title: Költségvetés áttekintése
description: Majdnem minden vállalatnak, amely használja a Pénzügy funkciót a Microsoft Dynamics 365 Finance rendszerben, képesnek kell lennie előirányzatot és tényleges adatokat összehasonlító jelentések készítésére. Ez a cikk ismerteti a minimális konfigurációt, amely költségvetések létrehozásához vagy külső programból történő betöltéséhez szükséges a Finance and Operations rendszerben.
author: ShylaThompson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 60113
ms.assetid: 28a9793e-d376-47af-a345-69046bad17df
ms.search.region: global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 36144474defc4849a112a180247f37796de00a27
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443989"
---
# <a name="budgeting-overview"></a>Költségvetés készítésének áttekintése

[!include [banner](../includes/banner.md)]

Majdnem minden vállalatnak, amely használja a Pénzügy funkciót a Microsoft Dynamics 365 Finance rendszerben, képesnek kell lennie előirányzatot és tényleges adatokat összehasonlító jelentések készítésére. Ez a cikk ismerteti a minimális konfigurációt, amely költségvetések létrehozásához vagy külső programból történő betöltéséhez szükséges a Finance and Operations rendszerben.

<a name="overview"></a>Áttekintés
--------

A jogi személy számára jóváhagyott költségvetés egy dokumentumban van vezetve, *költségvetésjegyzék bejegyzés* név alatt. A költségvetésjegyzék-bejegyzési dokumentumok sorai *költségvetési számlabejegyzésekként* ismertek, és pénzügyi dimenziókról tartalmaznak információkat, dátumokat és összegeket az elfogadott költségvetésből. A költségvetésjegyzék bejegyzési dokumentum integrálva van az alapvető pénzügyi dokumentumokba és lekérdezési oldalakba, ahol a főkönyv tényleges összege a költségvetés összegeivel van összehasonlítva. 

Többféle módszer létezik a költségvetésjegyzék-bejegyzések létrehozásához:

-   Manuálisan adja meg a dokumentum adatait a **Költségvetésjegyzék bejegyzés** oldalon.
-   Használja a Microsoft Excel sablont amelyet a **Megnyitás Excel-fájlban** gomb megnyomásával nyithat meg a **Költségvetésjegyzék-bejegyzések** oldalról.
-   Használja a **Költségvetési számlabejegyzések** adatentitást az Adatkezelés lehetőségben költségvetésjegyzék bejegyzések importálásához. Fontolja meg a módszer használatát és a **Halmazalapú** **feldolgozás** paraméter bekapcsolását, amikor sok költségvetésitételjegyzék-bejegyzést kell importálni a rendszerbe.
-   Ha a vállalat Költségvetési tervezés funkciót használ a költségvetési adatok előkészítéséhez, akkor használhatja a **Költségjegyzék bejegyzés generálása** időszakos folyamatot.

A költségvetésitételjegyzék-bejegyzés akkor tekinthető befejezettnek, ha a költségvetési egyenleg frissült. A **Költségvetésitételjegyzék-bejegyzések** oldalon kattintson a **Költségvetési egyenlegek frissítése** lehetőségekre a kiválasztott egy vagy több költségvetésitételjegyzék-bejegyzésnél. Miután frissítette a költségvetési egyenleget a költségvetésjegyzék állapota **Kész** értékre módosul. A kész költségvetésjegyzék bejegyzés nem nyitható meg újraszerkesztésre. Emiatt ha módosítani kell a költségvetési adatokat, akkor új költségvetésjegyzék bejegyzést kell létrehozni a kész költségvetésjegyzék bejegyzésben lévő adatok javítása helyett.

## <a name="configuration"></a>Konfiguráció
Költségvetés konfiguráláskor kezdjen a **Költségvetési paraméterek** oldalon. Ezen az oldalon meg kell adnia a költségvetési naplót, a költségvetésjegyzék bejegyzések sorszámát és az alapértelmezett működést a munkaterületeken.

Ezután ha vannak olyan irányelvek amelyek meghatározzák a költségvetésjegyzék bejegyzéseit a költségvetés típusa alapján (például átvitelek vagy jóváhagyások) akkor létre kell hozni egy költségvetésjegyzék bejegyzés munkafolyamatot a **Költségvetési munkafolyamatok** oldalon. Ha vannak olyan esetek, ahol az átvitelek engedélyezettek lehetnek munkafolyamat jóváhagyás nélkül, akkor megadhat költségvetéstranszfer szabályokat ezen esetek támogatásához. 

A **Költségvetési dimenziók** oldalon válassza ki a pénzügyi dimenziókat amelyeket költségvetéshez kíván használni a számlatükörben használt dimenziók alapján. Választhat, hogy az összes pénzügyi dimenziót vagy csak egy részüket választja költségvetés-tervezéshez.

Adja meg a *költségvetési modellt*, amelyik megfelel az összes vagy néhány költségvetésnek. Használhat egyetlen költségvetési modellt az összes költségvetésjegyzék bejegyzéshez. Másik lehetőségként létrehozhat elkülönített modelleket amelyek a költségvetés típusán, a földrajzi elhelyezkedésen vagy valamilyen egyéb költségvetéstípuson alapulnak. 

> [!NOTE] 
> Ha költségvetés-ellenőrzést használ, akkor csak egy költségvetési modellt társíthat egy specifikus költségvetésiciklus-időtartammal. 

Hozzon létre *költségvetési kódokat* amelyek azonosítják a költségvetési tranzakciókat a rekordban vagy bármilyen kapcsolódó munkafolyamatban. A költségvetési kódok az alábbi költségvetéstípusokat támogatják:

-   Eredeti költségvetés
-   Áthelyezés
-   Ellenőrzés
-   Kötelezettségvállalás
-   Előzetes kötelezettségvállalás
-   Áthozott költségvetés

A költségvetési kódok lehetővé teszik a jóváhagyott költségvetés könyvvizsgálati ellenőrzését a költségvetési cikluson keresztül. Ha egy munkafolyamat egy költségvetési kódhoz van társítva, akkor a munkafolyamat engedélyezett minden költségvetésitételjegyzék-bejegyzéshez, amelyet a költségvetés használ, és a munkafolyamat lépéseit el kell végezni mielőtt a költségvetésitételjegyzék-bejegyzés **Kész** állapotú lehet.  

Továbbá tetszés szerint megadhat *költségvetés-átviteli szabályokat*. Költségvetés-átviteli szabályok használatához jelölje be a **Költségvetés-átvitelekre vonatkozó szabályok használata** elemet a **Költségvetési paraméterek** oldalon. Költségvetés-átviteli szabályok használatának idejét, ha egy felhasználó a dokumentum létrehozása a költségvetési kódot, amely segítségével a **Átvitel** írja be a költségvetési egyenlegek nem frissíthető, ha a költségvetés-átviteli szabályokat nem sikeres. Ha például meg lehetővé teheti a költségvetés-átvitel dokumentumok ahol a kiadási költségvetés át, a fő számlát, amelyre az értékesítés és Marketing részleg között, de megtilthatják, hogy a költségvetési átvitel alatt a szervezeti egységhez, vagy csak az adott típusú költségvetési számlabejegyzés adott munkafolyamat-jóváhagyás.

A Microsoft Dynamics 365 Finance 10.0.7 verzióban (2020 január) bevezetett funkció a költségvetési tételjegyzék-bejegyzések számára hozzáadott képességgel és rugalmassággal bővült. Ha engedélyezni kívánja ezeket a fejlesztéseket , nyissa meg a **Funkció-kezelési** munkaterületet, és válassza ki a **Költségvetési tételjegyzék-bejegyzések csak mennyiséghez** és/vagy **Költségvetési tételjegyzék-bejegyzések az összegtípus alapján**.

A **Költségvetési tételjegyzék-bejegyzések csak mennyiséghez** esetén csak mennyiségi értékkel adhatók fel olyan költségvetési tételjegyzék-bejegyzések. Például feladhat egy 32 és egy nulla árat tartalmazó költségvetési bejegyzést, ami nulla összeggel jár. Ezt a mennyiséget egy pénzügyi jelentés keretein belül használhatja, hogy meghatározza a mennyiségre jutó árat. Ne feledje, hogy a funkció részeként nem lettek frissítve a lekérdezések és a jelentések. Ez a funkció csak nulla összeg feladását teszi lehetővé.

A **Költségvetési tételjegyzék-bejegyzések az összegtípus alapján** lehetővé teszi au alapértelmezett összegtípus számára, hogy a költségregiszter bejegyzésben a kiadástól eltérő összegtípus legyen. A költségvetési tételjegyzék-bejegyzés sora most alapértelmezetten költségként jelenik meg, amikor a fő számla típusa költség; alapértelmezetten bevételként jelenik meg, ha a fő számla típusa költség; és az alapértelmezett költség lesz az összes többi számlatípus esetében.

## <a name="using-workspaces-and-inquiry-pages-to-track-budget-vs-actuals"></a>Munkaterületek és a lekérdezési lapok segítségével nyomon követheti a költségvetés-tényleges
A költségvetés-kezelő tekintheti meg a költségvetés aktuális állapotát a **főkönyvi költségvetések és az előrejelzések** munkaterület. A **túllépő útiköltség költségvetési** és **a költségvetést bevétel** lapok biztosítja a gyors pénzügyi dimenziókombinációk Ha költségvetési tervek nem felelnek, vagy a program hamarosan eléri a küszöbértéket. A költségvetési küszöbértéket, és a Dimenziófókuszok kattintva a lapokon használt személyre szabható **konfigurálása a munkaterület**. Rákattinthat **egységvezetőket** ellenőrizhető, hogy az adott pénzügyi dimenziókombinációk ezen a lapon kiválasztott felelős dolgozók. Például ha látja, hogy a műveletek részleg a kiadási költségvetés lesz a költségvetési küszöbértéket meghaladó, egyszerűen található, és lépjen kapcsolatba a kiadás megvitatására üzemvezető részleg. 

> [!NOTE] 
> A **Szervezeti egységek** lapon található **Részleg vezetője** mező határozza meg, hogy mely vezetők támogatják az adott pénzügyi dimenziókombinációkat. Kattintson a **bővebb** megnyitásához a lap alján a **Tényleges vs és költségvetés szerinti** lekérdezési lap további részletek a tényleges összegek és a költségvetési összegeket. 

A **tényleges és költségvetési érték összevetése** lekérdezési lap lehetővé teszi a költségvetés-tényleges összegek és részletesen. Válasszon ki egy sort a lekérdezési lapon, és kattintson a **időszaki egyenlegek** pénzügyi időszakok közötti terjednek költségvetés és a tényleges összegek megtekintéséhez. A **költségvetési számlabejegyzések** lap megjeleníti a részletező szeretné a költségvetési tételjegyzék-bejegyzések költségvetési összeg részletes adatait. A **általános naplóbejegyzések** lap megnyitása a főkönyvi tranzakciók szerepelnek a számított **tényleges** összege. 

A vállalat által használt költségvetés-tervezési funkció is létrehozása és alkalmazása *költségvetési előrejelzések alapján* a a **főkönyvi költségvetések és az előrejelzések** munkaterület.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]