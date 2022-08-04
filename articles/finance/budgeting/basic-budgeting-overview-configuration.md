---
title: Költségvetés áttekintése
description: Szinte minden vállalatnak, amely a Microsoft Dynamics 365 Pénzügy pénzügyei funkciót használja, létre kell hoznia a költségvetés és a tényleges jelentéseket. Ez a cikk bemutatja a pénzügyi költségvetések és műveletek költségvetésének létrehozásához, illetve egy külső programból való betöltéséhez szükséges minimális konfigurációt.
author: panolte
ms.date: 04/29/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetParameters
audience: Application User
ms.reviewer: kfend
ms.custom:
- "60113"
- intro-internal
ms.assetid: 28a9793e-d376-47af-a345-69046bad17df
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 380afc399a050215bb2d7b1e5ddb20088226f654
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068960"
---
# <a name="budgeting-overview"></a>Költségvetés-készítés áttekintése

[!include [banner](../includes/banner.md)]

Szinte minden vállalatnak, amely a Microsoft Dynamics 365 Pénzügy pénzügyei funkciót használja, létre kell hoznia a költségvetés és a tényleges jelentéseket. Ez a cikk bemutatja a pénzügyi költségvetések és műveletek költségvetésének létrehozásához, illetve egy külső programból való betöltéséhez szükséges minimális konfigurációt.

## <a name="overview"></a>Áttekintés

A jogi személy számára jóváhagyott költségvetés egy dokumentumban van vezetve, *költségvetésjegyzék bejegyzés* név alatt. A költségvetésjegyzék-bejegyzési dokumentumok sorai *költségvetési számlabejegyzésekként* ismertek, és pénzügyi dimenziókról tartalmaznak információkat, dátumokat és összegeket az elfogadott költségvetésből. A költségvetésjegyzék bejegyzési dokumentum integrálva van az alapvető pénzügyi dokumentumokba és lekérdezési oldalakba, ahol a főkönyv tényleges összege a költségvetés összegeivel van összehasonlítva. 

Többféle módszer létezik a költségvetésjegyzék-bejegyzések létrehozásához:

-   Manuálisan adja meg a dokumentum adatait a **Költségvetésjegyzék bejegyzés** oldalon.
-   Használja a Microsoft Excel sablont amelyet a **Megnyitás Excel-fájlban** gomb megnyomásával nyithat meg a **Költségvetésjegyzék-bejegyzések** oldalról.
-   Használja a **Költségvetési számlabejegyzések** adatentitást az Adatkezelés lehetőségben költségvetésjegyzék bejegyzések importálásához. Akkor érdemes megfontolni ennek a módszernek a használatát és a **Készlet alapú feldolgozás** paraméter bekapcsolását, ha sok költségvetési számla bejegyzést kell importálnia a rendszerbe.
-   Ha a vállalat Költségvetési tervezés funkciót használ a költségvetési adatok előkészítéséhez, akkor használhatja a **Költségjegyzék bejegyzés generálása** időszakos folyamatot.

A költségvetésitételjegyzék-bejegyzés akkor tekinthető befejezettnek, ha a költségvetési egyenleg frissült. A **Költségvetésitételjegyzék-bejegyzések** oldalon kattintson a **Költségvetési egyenlegek frissítése** lehetőségekre a kiválasztott egy vagy több költségvetésitételjegyzék-bejegyzésnél. Miután frissítette a költségvetési egyenleget a költségvetésjegyzék állapota **Kész** értékre módosul. A kész költségvetésjegyzék bejegyzés nem nyitható meg újraszerkesztésre. Emiatt ha módosítani kell a költségvetési adatokat, akkor új költségvetésjegyzék bejegyzést kell létrehozni a kész költségvetésjegyzék bejegyzésben lévő adatok javítása helyett.

## <a name="configuration"></a>Konfiguráció
Költségvetés konfiguráláskor kezdjen a **Költségvetési paraméterek** oldalon. Ezen az oldalon meg kell adnia a költségvetési naplót, a költségvetésjegyzék bejegyzések sorszámát és az alapértelmezett működést a munkaterületeken.

Ezután ha vannak olyan irányelvek amelyek meghatározzák a költségvetésjegyzék bejegyzéseit a költségvetés típusa alapján (például átvitelek vagy jóváhagyások) akkor létre kell hozni egy költségvetésjegyzék bejegyzés munkafolyamatot a **Költségvetési munkafolyamatok** oldalon. Ha vannak olyan esetek, ahol az átvitelek engedélyezettek lehetnek munkafolyamat jóváhagyás nélkül, akkor megadhat költségvetéstranszfer szabályokat ezen esetek támogatásához. 

A **Költségvetési dimenziók** oldalon válassza ki a pénzügyi dimenziókat amelyeket költségvetéshez kíván használni a számlatükörben használt dimenziók alapján. Választhat, hogy az összes pénzügyi dimenziót vagy csak egy részüket választja költségvetés-tervezéshez.

Határozzon meg egy olyan *költségvetési modellt*, amely megfelel az összes vagy néhány költségvetésnek. Használhat egyetlen költségvetési modellt az összes költségvetésjegyzék bejegyzéshez. Másik lehetőségként létrehozhat elkülönített modelleket amelyek a költségvetés típusán, a földrajzi elhelyezkedésen vagy valamilyen egyéb költségvetéstípuson alapulnak. 

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

Microsoft Dynamics A 365 Pénzügy 10.0.7 verziójában (2020. január) bevezetett funkciók hozzáadják a költségvetési tételjegyzék-bejegyzések rugalmasságát és képességét. Ha engedélyezni kívánja ezeket a fejlesztéseket , nyissa meg a **Funkció-kezelési** munkaterületet, és válassza ki a **Költségvetési tételjegyzék-bejegyzések csak mennyiséghez** és/vagy **Költségvetési tételjegyzék-bejegyzések az összegtípus alapján**.

A **Költségvetési tételjegyzék-bejegyzések csak mennyiséghez** esetén csak mennyiségi értékkel adhatók fel olyan költségvetési tételjegyzék-bejegyzések. Például feladhat egy 32 és egy nulla árat tartalmazó költségvetési bejegyzést, ami nulla összeggel jár. Ezt a mennyiséget egy pénzügyi jelentés keretein belül használhatja, hogy meghatározza a mennyiségre jutó árat. Ne feledje, hogy a funkció részeként nem lettek frissítve a lekérdezések és a jelentések. Ez a funkció csak nulla összeg feladását teszi lehetővé.

A **Költségvetési tételjegyzék-bejegyzések az összegtípus alapján** lehetővé teszi au alapértelmezett összegtípus számára, hogy a költségregiszter bejegyzésben a kiadástól eltérő összegtípus legyen. A költségvetési tételjegyzék-bejegyzés sora most alapértelmezetten költségként jelenik meg, amikor a fő számla típusa költség; alapértelmezetten bevételként jelenik meg, ha a fő számla típusa bevétel; és az alapértelmezett költség lesz az összes többi számlatípus esetében.

## <a name="using-workspaces-and-inquiry-pages-to-track-budget-vs-actuals"></a>Munkaterületek és a lekérdezési lapok segítségével nyomon követheti a költségvetés-tényleges
A költségvetés-kezelő tekintheti meg a költségvetés aktuális állapotát a **főkönyvi költségvetések és az előrejelzések** munkaterület. A **túllépő útiköltség költségvetési** és **a költségvetést bevétel** lapok biztosítja a gyors pénzügyi dimenziókombinációk Ha költségvetési tervek nem felelnek, vagy a program hamarosan eléri a küszöbértéket. A költségvetési küszöbértéket, és a Dimenziófókuszok kattintva a lapokon használt személyre szabható **konfigurálása a munkaterület**. Rákattinthat **egységvezetőket** ellenőrizhető, hogy az adott pénzügyi dimenziókombinációk ezen a lapon kiválasztott felelős dolgozók. Például ha látja, hogy a műveletek részleg a kiadási költségvetés lesz a költségvetési küszöbértéket meghaladó, egyszerűen található, és lépjen kapcsolatba a kiadás megvitatására üzemvezető részleg. 

> [!NOTE] 
> A **Szervezeti egységek** lapon található **Részleg vezetője** mező határozza meg, hogy mely vezetők támogatják az adott pénzügyi dimenziókombinációkat. Kattintson a **bővebb** megnyitásához a lap alján a **Tényleges vs és költségvetés szerinti** lekérdezési lap további részletek a tényleges összegek és a költségvetési összegeket. 

A **tényleges és költségvetési érték összevetése** lekérdezési lap lehetővé teszi a költségvetés-tényleges összegek és részletesen. Válasszon ki egy sort a lekérdezési lapon, és kattintson a **időszaki egyenlegek** pénzügyi időszakok közötti terjednek költségvetés és a tényleges összegek megtekintéséhez. A **költségvetési számlabejegyzések** lap megjeleníti a részletező szeretné a költségvetési tételjegyzék-bejegyzések költségvetési összeg részletes adatait. A **általános naplóbejegyzések** lap megnyitása a főkönyvi tranzakciók szerepelnek a számított **tényleges** összege. 

A vállalat által használt költségvetés-tervezési funkció is létrehozása és alkalmazása *költségvetési előrejelzések alapján* a a **főkönyvi költségvetések és az előrejelzések** munkaterület.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]

