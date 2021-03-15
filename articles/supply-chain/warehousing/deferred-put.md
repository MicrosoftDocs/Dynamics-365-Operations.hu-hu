---
title: Raktári munka halasztott feldolgozása
description: Ez a témakör azt a funkcionalitást ismerteti, amely lehetővé teszi a raktári munkakelések késleltetett feldolgozását a Dynamics 365 Supply Chain Management programban.
author: josaw1
manager: tfehr
ms.date: 11/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-6-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c85dd895e18805da2d1daf5f90f64db82bdc0116
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973785"
---
# <a name="deferred-processing-of-warehouse-work"></a>Raktári munka halasztott feldolgozása

[!include [banner](../includes/banner.md)]

Ez a témakör azt a funkcionalitást ismerteti, amely lehetővé teszi a késleltetett feldolgozást raktári munkákhoz a Dynamics 365 Supply Chain Management programban.

A halasztott feldolgozási funkciók esetében a raktári dolgozók továbbra is más munkát folytatnak, mialatt a betárolási művelet a háttérben lesz feldolgozva. A halasztott feldolgozás akkor hasznos, ha több munkasort kell feldolgozni, és a dolgozó lehetővé tudja tenni a munka aszinkron feldolgozását. Akkor is hasznos, ha a kiszolgálón előfordulhat a feldolgozási idő megnövekedése alkalomszerűen vagy nem tervezetten, és a megnövekedett feldolgozási idő hatással lehet a felhasználó termelékenységére.

A háttérben történő feldolgozás a SysOperation keretrendszer használatával érhető el. A további tudnivalókat lásd: [A SysOperation keretrendszer áttekintése](https://docs.microsoft.com/dynamicsax-2012/developer/sysoperation-framework-overview).

## <a name="configuring-the-work-processing-policies"></a>A munkafeldolgozási irányelvek konfigurálása

A halasztott feldolgozás használatához a munkafeldolgozási irányelvet kell konfigurálnia és használnia.

A házirendek a **Munkafeldolgozási házirendek** lapon vannak konfigurálva. Az alábbi táblázat ismerteti az ezen az oldalon elérhető mezőket.

| Mező                           | Leírás |
|---------------------------------|-------------|
| Munkafeldolgozási irányelv neve     | A munkafeldolgozási irányelv neve. |
| Munkarendelés típusa                 | Az a munkarendelés típusa, amelyre az irányelv alkalmazva van. |
| Művelet                       | Az irányelv használatával feldolgozott művelet. |
| Munkafeldolgozási módszer          | A munkasor feldolgozásához használt módszer. Ha a metódus beállítása **Azonnali**, a működés hasonlít arra viselkedésre, amikor a sor feldolgozásához nem használnak munkafeldolgozási irányelvet. Ha a metódus **Halasztott** értékre van állítva, a rendszer a kötegkeretrendszert használó halasztott feldolgozást használja. |
| Halasztott feldolgozási küszöbérték   | A **0** (nulla) érték azt jelzi, hogy nincs küszöbérték. Ebben az esetben a halasztott feldolgozás lesz használva, ha használható. Ha a meghatározott küszöbérték kiszámítása a küszöbérték alatt van, az azonnali módszer lesz használva. Máskülönben a rendszer a Halasztott metódust használja, ha az használható. Az értékesítéssel és átadással kapcsolatos munkák esetében a küszöbérték számítása a munka során a hozzárendelt forrás terhelésisorok száma szerint történik. Feltöltési munka esetén a küszöb kiszámítása a munka során feltöltött munkasorok számának használatával történik. Ha például az eladásokhoz **5** értéket ad meg a küszöbértékhez a kisebb munkák, amelyeknek kevesebb, mint öt kezdeti forrássora van, nem fogják használni a halasztott feldolgozást, de a nagyobb munkák igen. A küszöbérték csak akkor érvényes, ha a munka feldolgozási módszere **Halasztott**. |
| Halasztott feldolgozási kötegcsoport |A feldolgozáshoz használt kötegcsoport. |

A halasztott betárazási feldolgozás a következő munkarendelési típusokat támogatja: értékesítési rendelés, átmozgatási rendelés kiadása és feltöltés.

## <a name="assigning-the-work-creation-policy"></a>A munkalétrehozási irányelv hozzárendelése

A munkalétrehozási házirend hozzárendelhető a raktárkezelési paraméterekhez. Az egyes raktárak szintjén is hozzárendelhető. Ha az irányelv egy raktárhoz van rendelve, akkor csak az adott raktárhoz létrehozott munkára alkalmazza a rendszer. Ha raktározási szinten nincs hozzárendelve irányelv, a rendszer a raktárkezelési paraméterekből származó irányelvet alkalmazza.

## <a name="viewing-the-deferred-put-processing-tasks"></a>A halasztott betárazási feldolgozási feladatok megtekintése

Az elhalasztott betárazási feldolgozási feladatokat a **Halasztott betárazási feldolgozási feladatok** lapon tekintheti meg.

Alapértelmezés szerint a **Befejezett** feladatok vannak megjelenítve.

| Mező            | Leírás |
|------------------|-------------|
| Állapot           | A feladat állapota. |
| Kötegelt feladat állapota | A kapcsolódó kötegelt feladat állapota. Ha a kötegelt feladatot feldolgozták, a kötegelőzmények tartalmazzák a naplót és a kötegelt feladattal kapcsolatos információkat. |

Itt látható a lehetséges állapotok magyarázata:

- **Várakozik** – A kapcsolódó kötegelt feladat feldolgozásra vár a kötegkiszolgálón.
- **Sikertelen** – A feldolgozás nem sikerült. A tevékenységet újból fel lehet dolgozni az **Elhalasztott betárazás feldolgozása** művelet segítségével, vagy megszakítható az **Elhalasztott betárazás visszavonása** művelet segítségével.
- **Befejezett** – A feladat befejeződött.

## <a name="impact-on-closed-work-dates"></a>A lezárt munkaidőpontokra gyakorolt hatás

A halasztott betárazási feldolgozás használatakor a rendszer a lezárt munkadátumot a halasztott betárazási tevékenységek létrehozásának dátumának/időpontjának. A rendszer a lezárt munkadátumot használja, mert ez a legjobb becslés a betárazási művelet befejezésére.

## <a name="reprocessing-a-failed-task"></a>Meghiúsult feladat újrafeldolgozása

Egy sikertelen feladat újbóli feldolgozásához jelölje ki azt az oldalon, majd válassza a **Késleltetett betárazás feldolgozása** lehetőséget. Az újrafeldolgozás megfelel annak a helyzetnek, amikor a felhasználó mobileszközről végez elraktározást, mintha az azonnali feldolgozásra lett volna beállítva.

## <a name="canceling-failed-tasks"></a>Sikertelen feladatok megszakítása

Csak a sikertelen feladatokat lehet megszakítani. Amikor egy feladatot megszakít, azt hozzárendelheti egy új felhasználóhoz. Másik megoldásként a feladat a munkát maradhat hozzárendelve ahhoz a felhasználóhoz, aki feldolgozta a munkát. A törlés megfelel annak a helyzetnek, amikor a munkát visszahozzák a mobileszközre, mintha az utolsó felvétel éppen befejeződött volna, és a munkát be kell tárazni. A felhasználó azonban meghatározhatja, hogy a munka „más”, mert csak egy elraktározási lépéssel rendelkezik, és a hely megfelel annak a helynek, amelyet a munkát végző első felhasználó a végleges elraktározásnak határozott meg.

A tevékenység megszakításakor a munkát már nem blokkolja a halasztott feldolgozási blokkolás ok. Újra feldolgozható ugyanazon mobileszköz használatával.

A feladatrekord a tevékenység megszakításakor törlődik.

## <a name="configuring-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>A mobileszköz menüjének beállítása a halasztott feldolgozási irányelv kihagyásához

Beállíthatja a mobileszköz menüjelemét úgy, hogy ne legyen használatban a halasztott feldolgozási irányelv. A munka ezután úgy lesz feldolgozva, mintha nem alkalmaznának halasztott feldolgozási irányelvet. Ez a funkció lehetővé teszi egy felettesnek egy adott menüpont használatát, amikor a betárazást nem használják. A konfiguráláshoz állítsa a **Halasztott feldolgozási irányelv** mezőt **Beállítások felülbírálása, és a betárazás szinkronizált feldolgozása** értékre. 

## <a name="restrictions-when-the-deferred-put-processing-isnt-applied"></a>Korlátozások, ha a halasztott betárazási feldolgozás nincs alkalmazva

Számos olyan forgatókönyv van, ahol a halasztott betárazási feldolgozás nem kerül alkalmazásra annak ellenére, hogy az irányelv konfigurálva van. Íme néhány példa:

- Manuális munkabefejezést használnak.
- A munkát automatikus befejezéssel végzik el.
- Auditsablonok használata.


## <a name="monitoring-the-deferred-processing-tasks-from-the-outbound-work-monitoring-workspace"></a>A halasztott feldolgozási feladatok figyelése egy Kimenő munkamegfigyelési munkaterületről

A **Kimenő munka megfigyelése** munkaterülethez két csempe tartozik, amelyek segítenek a halasztott feldolgozási feladatok figyelésében:

- **Sikertelen halasztott betárazási feldolgozási feladatok** – Ez a csempe a sikertelen feladatok számát mutatja. Ha vannak sikertelen tevékenységek, a raktárkezelőnek újra kell feldolgoznia vagy törölnie kell azokat, mert nem lesznek automatikusan újrafeldolgozva.
- **Várakozás halasztott fel feldolgozási feladatokra** – Ez a csempe azon feladatok számát jeleníti meg, amelyek több mint 10 percig **Várakozás** állapotban voltak. Ha a csempén egy szám látható, akkor az azt jelezheti, hogy a kötegfeldolgozás során hiba történt. A **Várakozó** feladatokat manuálisan is feldolgozhatja. Ha egy feladathoz tartozó kötegelt feladatot később dolgoznak fel, az egyszerűen meghiúsul mert már fel lett dolgozva. Nem lesz hatása.

## <a name="deleting-completed-tasks"></a>Befejezett feladatok törlése

A már befejezett, halasztott betárazási feldolgozási tevékenységeket törölheti, ehhez jelölje ki, és törölje azokat a lapon.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]