---
title: "Termelési paraméterek a Gyártásvégrehajtásban"
description: "Ez a témakör a Gyártásvégrehajtás modul termelési paramétereinek beállításával kapcsolatos információkat tartalmazza."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Manufacturing
ms.author: johanhoffmann
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: c8868c1b09b28f8098dfd7a4983c8bf0cce51a0c
ms.contentlocale: hu-hu
ms.lasthandoff: 06/20/2017

---

# <a name="production-parameters-in-manufacturing-execution"></a>Termelési paraméterek a Gyártásvégrehajtásban

[!include[banner](../includes/banner.md)]

Ez a témakör a Gyártásvégrehajtás modul termelési paramétereinek beállításával kapcsolatos információkat tartalmazza.

A **Gyártásvégrehajtás** modul elsősorban gyártó vállalatok általi használatra készült. Termelési feladatok vagy projektek időpontjának és cikkfelhasználásának regisztrálására használható. A Gyártásvégrehajtás modul feladatregisztrálásra történő használatának megkezdése előtt be kell állítania a különböző termelési paramétereket, amelyek meghatározzák, mikor és hogyan történik a regisztrációk feladása a termelési folyamat során. A termelési paraméterek beállításai befolyásolják a készletkezelést, a termelésirányítást és a költségszámítást.

Alaposan fontolja meg a **Termelési rendelés alapértékei** oldal beállításait, mielőtt a dolgozók elkezdenek regisztrációkat tenni a termelési feladatokba. Kattintson a **Gyártásvezérlés** &gt; **Beállítás** &gt; **Gyártásvégrehajtás** &gt; **Termelési rendelés alapértékei** pontra. Ha a vállalat a többhelyes funkciót használja, érdemes a gyártási rendeléseknél mindegyik helyhez más termelési paramétert beállítani. A **Termelés** modullal való integráció paraméterei a **Termelési paraméterek** lap következő fülein állíthatók be:

- **Általános** – Általános paraméterbeállítások a termelési feladatokhoz a Gyártásvégrehajtás modulban.
- **Indítás** – A termelési műveletek indításakor használt paraméterek.
- **Műveletek** – A termelési feladatokra alkalmazott paraméterek és a termelési folyamat során végzett műveletek visszajelzései.
- **Jelentés befejezettként** – A cikkek készként jelentésekor használt paraméterek egy termelési rendelés utolsó műveletekor.
- **Mennyiség ellenőrzése** – A termelési rendelések kezdő és visszajelzési mennyiségeinek ellenőrzésekor használt paraméterek.

## <a name="types-of-production-jobs"></a>A termelési feladatok típusai
A **Műveletek** lapon azokat a termelési feladattípusokat választjuk ki, amelyek a **Feladatregisztráció** oldalon regisztrációt igényelnek.

Általában a dolgozók beállítási feladatokon és feldolgozási feladatokon regisztrálnak. Azonban ha feladatütemezést alkalmaznak, kiválaszthat további feladattípusokat, amelyeken a dolgozóknak regisztrálniuk kell a termelési rendelések feldolgozása során. Például előírhatja szállítási feladatok történő regisztrációt.

> [!IMPORTANT]
> Győződjön meg arról, hogy minden fontos feladattípust kiválasszon. Ellenkező esetben feladatok lehet, hogy nem lesznek elérhetők a regisztrációhoz a **Regisztráció** oldalon. A kiválasztott beállításoknak meg kell egyeznie a **Feladatkezelés** oszlop **Beállítás** lapján az **Útvonalcsoportok** lap beállításaival (**Gyártásvezérlés** &gt; **Beállítás** &gt; **Útvonalak** &gt; **Útvonalcsoportok**).

Ha a **Feladatkezelés** ki van választva az útvonalcsoport egy meghatározott feladattípusánál, akkor ez a feladattípus a termelési rendelésen készként lesz jelentve, amikor a feladatot készként jelentik a Gyártásvégrehajtásban. Ha minden feladattípus, amelyhez a **Feladatkezelés** ki van jelölve, készként lett jelentve egy művelet esetén, a Gyártásvégrehajtás modul is készként jelenti a műveletet.

> [!NOTE]
> Egyes feladattípusok saját kezűleg is készként jelenthetők a termelési naplókon keresztül. Ebben az esetben válassza a **Feladatkezelés** lehetőséget a feladattípushoz, de ne válassza ki a feladattípus regisztrációját a **Műveletek** lapon a **Termelési paraméterek** lapon a Gyártásvégrehajtásban.

## <a name="bom-consumption-and-picking-list-journals"></a>Anyagjegyzék-felhasználás és kitárolási listák naplói
Az anyagjegyzék (AJ) konzisztens beállítása azért fontos, mert segít a készletkezelés hatékony működésének biztosításában. Például ha az Anyagjegyzék-felhasználási paraméterek beállítása nem megfelelő a Gyártásvégrehajtás modulban, előfordulhat, hogy a rendszer kétszer vagy egyszer sem von le anyagokat a készletből.

A **Termelési paraméterek** lapon az automatikus Anyagjegyzék-felhasználás három szakaszból épül fel:

- A termelés megkezdésekor. Ezt a szakaszt az **Indítás** lapon állítsa be.
- A termelési folyamat során egy művelet befejezésekor. Ezt a szakaszt a **Műveletek** lapon állítsa be.
- Termelési rendelés készként történő jelentésekor. Ezt a szakaszt a **Jelentés készként** lapon állítsa be.

Minden szakaszban az **Automatikus anyagjegyzék-felhasználás** mezőben a termelési rendelés cikkeinek három kitárolási módja közül választhat:

- **Ürítési elv** – Ez a lehetőség a **Termelés** modul anyagjegyzékéhez meghatározott lehetőséggel együtt használatos. Kattintson a következő lehetőségre: **Gyártásvezérlés** &gt; **Közös** &gt; **Termelési rendelések** &gt; **Minden termelési rendelés**. A **Minden termelési rendelés** lapon kiválaszthat egy termelési rendelést a listában, majd a műveleti ablaktáblán kattintson az **Anyagjegyzék** lehetőségre. Az **Anyagjegyzék** lapon a **Beállítási** lap **Ürítési elv** mezőjében válasszon egyet a következő lehetőségek közül:

    - **Indítás**
    - **Befejezés**
    - **Manuális**
    - Üres (nincs megadva beállítás)
    - **Rendelkezésre áll a helyen**

    A Gyártásvégrehajtás modulban ha az **Ürítési elv** van kiválasztva az **Automatikus anyagjegyzék-felhasználás** mezőben az **Indítás** lapon, az anyagjegyzékben szereplő minden **Indítás** beállítású anyagot a rendszer levon a készletből a művelet megkezdésekor. A **Rendelkezésre áll a helyen** lehetőség a speciális raktárkezelési folyamatokkal kezelt termékek számára engedélyezett. Ha bejelöli az ürítési alapelvet, a rendszer kiürítése az anyagot a nyersanyag-kitárolás raktári munka befejezésekor. A rendszer akkor is kiüríti az anyagot, ha egy, a jelen ürítési elvet használó AJ-sort a rendszer kiadja a raktárnak, és az anyag elérhető a termelés bemeneti helyén.
    
    > [!NOTE]
    > Ha az **Ürítési elv** mező be van állítva az **Indítás** lapon a Gyártásvégrehajtásban, ugyanezt az elvet kell bejelölnie a **Műveletek** lapon vagy a **Jelentés készként** lapon. Ez a követelmény segít biztosítani, hogy a rendszer levonja az anyagokat azon anyagjegyzékek készletéből, amelyek a **Befejezés** ürítési elvet használják a termelési rendelésben. Ha ugyanez az ürítési elv nincs bejelölve a **Műveletek** fülön vagy a **Jelentés készként** lapon, előfordulhat, hogy a rendszer az anyagokat kétszer vonja le a készletből.
 
- **Mindig** – Ha bejelöli ezt a lehetőséget egy fokozathoz, a rendszer mindig levonja az anyagokat a készletból abban a szakaszban. Például a termelési anyagokat a termelési rendelés indításakor vonja le. Ez a beállítás megköveteli, hogy a **Soha** legyen bejelölve a **Műveletek** és a **Jelentés készként** lapokon. Ez a követelmény megakadályozza, hogy a rendszer kétszer vonja le a cikkeket a készletből.
- **Soha** – Ha egy fokozatban ezt a lehetőséget választja, az adott szakaszban nem történik az anyagjegyzék-felhasználás. Ha például a **Soha** lehetőséget választja mindhárom lapon (**Indítás**, **Műveletek** és **Jelentés készként**), az anyagokat manuálisan kell levonni a készletből.

> [!IMPORTANT]
> Alaposan fontolja meg a termelési paraméterek beállítását, és győződjön meg arról, hogy a **Termelési paraméterek** különböző lapjain beállított paraméterek ne mondjanak ellent egymásnak.

Az alábbi példák bemutatják a különféle anyagjegyzék felhasználási elveket támogató paramétereket. A paramétereket a **Termelési paraméterek** lapon lehet beállítani a Gyártásvégrehajtás modulban.

### <a name="example-1-backflushing-on-operations"></a>1. példa: Ürítés műveletek után

A következő beállításokat akkor használja, ha kitárolási listanaplókat és az AJ-cikkek felhasználását tartalmazó naplókat kell generálni, amikor a műveletben előállított cikkeket készként jelentik.

| Lap                | Mező                          | Beállítás                             |
|--------------------|--------------------------------|-------------------------------------|
| Eleje              | Módosítás kezdete - online           | **Állapot** vagy **Állapot + mennyiség** |
| Eleje              | Automatikus anyagjegyzék-felhasználás      | **Soha**                           |
| Operations         | Automatikus anyagjegyzék-felhasználás      | **Mindig**                          |
| Készként jelentés | Automatikus anyagjegyzék-felhasználás      | **Soha**                           |
| Készként jelentés | Módosítás befejezésének jelentése - online | **Állapot + mennyiség**               |

### <a name="example-2-backflushing-on-production"></a>2. példa: Ürítés termelés után

A következő beállításokat akkor használja, ha kitárolási listanaplókat és az AJ-cikkek felhasználását tartalmazó naplókat kell generálni, amikor a termelési rendelés cikkeit készként jelentik.

| Lap                | Mező                          | Beállítás                             |
|--------------------|--------------------------------|-------------------------------------|
| Eleje              | Módosítás kezdete - online           | **Állapot** vagy **Állapot + mennyiség** |
| Eleje              | Automatikus anyagjegyzék-felhasználás      | **Soha**                           |
| Operations         | Automatikus anyagjegyzék-felhasználás      | **Soha**                           |
| Készként jelentés | Automatikus anyagjegyzék-felhasználás      | **Mindig**                          |
| Készként jelentés | Módosítás befejezésének jelentése - online | **Állapot + mennyiség**               |

### <a name="example-3-flushing-principle"></a>3. példa: Ürítési elv

A következő beállításokat akkor használja, ha kitárolási listanaplókat és az AJ-cikkek felhasználását tartalmazó naplókat az AJ-cikkekre beállított ürítési elvnek megfelelően kell generálni.

| Lap                | Mező                          | Beállítás                |
|--------------------|--------------------------------|------------------------|
| Eleje              | Módosítás kezdete - online           | **Állapot + mennyiség**  |
| Eleje              | Automatikus anyagjegyzék-felhasználás      | **Ürítési elv** |
| Operations         | Automatikus anyagjegyzék-felhasználás      | **Ürítési elv** |
| Készként jelentés | Automatikus anyagjegyzék-felhasználás      | **Soha**              |
| Készként jelentés | Módosítás befejezésének jelentése - online | **Állapot + mennyiség**  |

### <a name="example-4-deduction-of-materials-during-startup-of-a-production-order"></a>4. példa: Anyagok levonása termelési rendelés indításakor

A következő beállításokat akkor használja, ha kitárolási listanaplókat és az AJ-cikkek felhasználását tartalmazó naplókat kell generálni a művelet indításakor.

| Lap                | Mező                          | Beállítás                             |
|--------------------|--------------------------------|-------------------------------------|
| Eleje              | Módosítás kezdete - online           | **Állapot + mennyiség**               |
| Eleje              | Automatikus anyagjegyzék-felhasználás      | **Mindig**                          |
| Operations         | Automatikus anyagjegyzék-felhasználás      | **Soha**                           |
| Készként jelentés | Automatikus anyagjegyzék-felhasználás      | **Soha**                           |
| Készként jelentés | Módosítás befejezésének jelentése - online | **Állapot** vagy **Állapot + mennyiség** |

Az ebben a részben korábban ismertetett kijelölések alapján a kitárolási listanaplók feladása a termelési rendelési folyamat különböző szakaszaiban történik:

- A művelet indításakor
- Amikor egy művelet mennyiségi visszajelzését jelentik
- Amikor egy termelési rendelés cikkeit készként jelentik

### <a name="example-5-manual-bom-consumption"></a>5. példa: Manuális anyagjegyzék-felhasználás

A következő beállításokat akkor használhatja, ha az anyagokat mindig manuálisan kell levonni a készletből. Ebben az esetben a kitárolási listanaplókat nem adják fel.

| Lap                | Mező                          | Beállítás    |
|--------------------|--------------------------------|------------|
| Eleje              | Módosítás kezdete - online           | **Állapot** |
| Eleje              | Automatikus anyagjegyzék-felhasználás      | **Soha**  |
| Operations         | Automatikus anyagjegyzék-felhasználás      | **Soha**  |
| Készként jelentés | Automatikus anyagjegyzék-felhasználás      | **Soha**  |
| Készként jelentés | Módosítás befejezésének jelentése - online | **Állapot** |

