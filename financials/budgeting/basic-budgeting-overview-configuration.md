---
title: "Költségvetés áttekintése"
description: "Majdnem minden vállalat Pénzügy funkciót használja a Microsoft Dynamics 365 műveletekre kell-költségvetés-tényleges jelentéseket készíthet. Ez a cikk ismerteti a minimális konfiguráció szükséges műveletek Dynamics 365 költségvetések létrehozása vagy egy külső programból betölthetők."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 60113
ms.assetid: 28a9793e-d376-47af-a345-69046bad17df
ms.search.region: global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a639e509cf6a3d2f1b850f27481d7b95546522b8
ms.openlocfilehash: b62e14f7c91692ae97bb332b38b0deeb328cc1bd
ms.lasthandoff: 03/31/2017


---

# <a name="budgeting-overview"></a>Költségvetés áttekintése

Majdnem minden vállalat Pénzügy funkciót használja a Microsoft Dynamics 365 műveletekre kell-költségvetés-tényleges jelentéseket készíthet. Ez a cikk ismerteti a minimális konfiguráció szükséges műveletek Dynamics 365 költségvetések létrehozása vagy egy külső programból betölthetők.

<a name="overview"></a>Áttekintés
--------

A jogi személy számára jóváhagyott költségvetés egy dokumentumban van vezetve, *költségvetésjegyzék bejegyzés* név alatt. Jegyzék egy költségvetési tétel bizonylat sora nevezik *költségvetési számlára* tételeket, és a pénzügyi dimenzió-információt, dátumok és a jóváhagyott költségvetési összegeket tartalmaznak. A költségvetési tételjegyzék beléptetési okmányon az alapvető pénzügyi kimutatások és lekérdezési oldalak ahol összehasonlításra kerül tényleges összegek főkönyvi költségvetési összegek integrálva van. 

Több módon Dynamics 365 műveletek költségvetési tételjegyzék-bejegyzések létrehozása:

-   Manuálisan adja meg a dokumentum adatait a **Költségvetésjegyzék bejegyzés** oldalon.
-   Használja a Microsoft Excel sablont amelyet a **Megnyitás Excel fájlban** gomb megnyomásával nyithat meg a **Költségvetésjegyzék bejegyzések** oldalról.
-   Használja a **Költségvetési számlabejegyzések** adatentitást az Adatkezelés lehetőségben költségvetésjegyzék bejegyzések importálásához. Érdemes ezzel a módszerrel, és bekapcsolja a **beállítása alapján** ** feldolgozása ** paramétert, ha sok költségvetési tételek a rendszerbe importálni kell.
-   Ha a vállalat Költségvetési tervezés funkciót használ a költségvetési adatok előkészítéséhez, akkor használhatja a **Költségjegyzék bejegyzés generálása** időszakos folyamatot.

A költségvetési nyilvántartási bejegyzés számít fejeződik be, amikor a költségvetési egyenlegek frissítve lett. A a **költségvetési tételjegyzék-bejegyzések** lap **költségvetési egyenlegek frissítése** a kijelölt költségvetés-regisztrálás tételt vagy tételeket több. Miután frissítette a költségvetési egyenleget a költségvetésjegyzék állapota **Kész** értékre módosul. A kész költségvetésjegyzék bejegyzés nem nyitható meg újraszerkesztésre. Emiatt ha módosítani kell a költségvetési adatokat, akkor új költségvetésjegyzék bejegyzést kell létrehozni a kész költségvetésjegyzék bejegyzésben lévő adatok javítása helyett.

## <a name="configuration"></a>Konfiguráció
Költségvetés konfiguráláskor kezdjen a **Költségvetési paraméterek** oldalon. Ezen az oldalon meg kell adnia a költségvetési naplót, a költségvetésjegyzék bejegyzések sorszámát és az alapértelmezett működést a munkaterületeken.

Ezután ha vannak olyan irányelvek amelyek meghatározzák a költségvetésjegyzék bejegyzéseit a költségvetés típusa alapján (például átvitelek vagy jóváhagyások) akkor létre kell hozni egy költségvetésjegyzék bejegyzés munkafolyamatot a **Költségvetési munkafolyamatok** oldalon. Ha vannak olyan esetek, ahol az átvitelek engedélyezettek lehetnek munkafolyamat jóváhagyás nélkül, akkor megadhat költségvetéstranszfer szabályokat ezen esetek támogatásához. 

A **Költségvetési dimenziók** oldalon válassza ki a pénzügyi dimenziókat amelyeket költségvetéshez kíván használni a számlatükörben használt dimenziók alapján. Választhat, hogy az összes pénzügyi dimenziót vagy csak egy részüket választja költségvetés-tervezéshez.

Adja meg egy * költségvetési modell * egészét vagy egy részét a költségvetés, amely megfelel. Használhat egyetlen költségvetési modellt az összes költségvetésjegyzék bejegyzéshez. Másik lehetőségként létrehozhat elkülönített modelleket amelyek a költségvetés típusán, a földrajzi elhelyezkedésen vagy valamilyen egyéb költségvetéstípuson alapulnak. 

> [!NOTE] 
> Költségvetés-ellenőrzés használata esetén is társíthat egyetlen költségvetési modell egy adott költségvetési ciklus időtartama. 

Hozzon létre *költségvetési kódokat *amelyek azonosítják a költségvetési tranzakciókat a rekordban vagy bármilyen kapcsolódó munkafolyamatban. A költségvetési kódok az alábbi költségvetéstípusokat támogatják:

-   Eredeti költségvetés
-   Áthelyezés
-   Ellenőrzés
-   Kötelezettségvállalás
-   Előzetes kötelezettségvállalás
-   Áthozott költségvetés

A költségvetési kódok lehetővé teszik a jóváhagyott költségvetés könyvvizsgálati ellenőrzését a költségvetési cikluson keresztül. Ha egy munkafolyamat kapcsolódik a költségvetési kód, a munkafolyamat engedélyezve lesz a költségvetési kódot használó összes költségvetési nyilvántartási bejegyzések és érhető el a költségvetési nyilvántartási bejegyzés előtt el kell végezni a munkafolyamat-lépésekhez az **kész** szakasz.  

Tetszés szerint is beállíthat *költségvetés-átviteli szabályok*. Költségvetés-átviteli szabályok használatához jelölje be a **Költségvetés-átvitelekre vonatkozó szabályok használata** a a **költségvetési paraméterek** oldalon. Költségvetés-átviteli szabályok használatának idejét, ha egy felhasználó a dokumentum létrehozása a költségvetési kódot, amely segítségével a **Átvitel** írja be a költségvetési egyenlegek nem frissíthető, ha a költségvetés-átviteli szabályokat nem sikeres. Ha például meg lehetővé teheti a költségvetés-átvitel dokumentumok ahol a kiadási költségvetés át, a fő számlát, amelyre az értékesítés és Marketing részleg között, de megtilthatják, hogy a költségvetési átvitel alatt a szervezeti egységhez, vagy csak az adott típusú költségvetési számlabejegyzés adott munkafolyamat-jóváhagyás.

## <a name="using-workspaces-and-inquiry-pages-to-track-budget-vs-actuals"></a>Munkaterületek és a lekérdezési lapok segítségével nyomon követheti a költségvetés-tényleges
A költségvetés-kezelő tekintheti meg a költségvetés aktuális állapotát a **főkönyvi költségvetések és az előrejelzések** munkaterület. A **túllépő útiköltség költségvetési** és **a költségvetést bevétel** lapok biztosítja a gyors pénzügyi dimenziókombinációk Ha költségvetési tervek nem felelnek, vagy a program hamarosan eléri a küszöbértéket. A költségvetési küszöbértéket, és a Dimenziófókuszok kattintva a lapokon használt személyre szabható **konfigurálása a munkaterület**. Rákattinthat **egységvezetőket** ellenőrizhető, hogy az adott pénzügyi dimenziókombinációk ezen a lapon kiválasztott felelős dolgozók. Például ha látja, hogy a műveletek részleg a kiadási költségvetés lesz a költségvetési küszöbértéket meghaladó, egyszerűen található, és lépjen kapcsolatba a kiadás megvitatására üzemvezető részleg. 

> [!NOTE] 
> A **részleg vezetője** mezőjében a **szervezeti egységek** lap határozza meg, amely a menedzserek támogatja az adott pénzügyi dimenzió kombinációk. Kattintson a **bővebb** megnyitásához a lap alján a **Tényleges vs és költségvetés szerinti** lekérdezési lap további részletek a tényleges összegek és a költségvetési összegeket. 

A **tényleges és költségvetési érték összevetése** lekérdezési lap lehetővé teszi a költségvetés-tényleges összegek és részletesen. Válasszon ki egy sort a lekérdezési lapon, és kattintson a **időszaki egyenlegek** pénzügyi időszakok közötti terjednek költségvetés és a tényleges összegek megtekintéséhez. A **költségvetési számlabejegyzések** lap megjeleníti a részletező szeretné a költségvetési tételjegyzék-bejegyzések költségvetési összeg részletes adatait. A **általános naplóbejegyzések **lap megnyitása a főkönyvi tranzakciók szerepelnek a számított **tényleges** összege. 

A vállalat által használt költségvetés-tervezési funkció is létrehozása és alkalmazása *költségvetési előrejelzések alapján *a a **főkönyvi költségvetések és az előrejelzések** munkaterület.


