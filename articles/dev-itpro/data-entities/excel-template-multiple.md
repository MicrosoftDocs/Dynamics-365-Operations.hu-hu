---
title: "Adatok importálása több munkalapos Excel adatentitás-sablonokból"
description: "Ez a témakör leírja, hogyan importálhatók az adatok Excel adatentitás-sablonokkal a Microsoft Dynamics 365 Finance and Operations, Enterprise edition megoldásba."
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: 84b9e9128d7ea6cdf9949549f4ab7a1c6c01691b
ms.contentlocale: hu-hu
ms.lasthandoff: 12/14/2017

---

# <a name="excel-templates-with-multiple-worksheets"></a>Több munkalapos Excel-sablonok

Az adatkezelés a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition megoldásban támogatja a Microsoft Excel-alapú sablonokat az adatentitások esetében. Ezek a sablonok egy vagy több munkalapot is tartalmazhatnak. A több munkalapot tartalmazó sablonok gyakran használatosak olyan esetekben, amikor célszerű egyetlen fájlban kezelni az adatokat, és több entitásba importálni őket. Jó példát jelentenek erre a telephelyek és a raktárak.

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a>Fájl feltöltése egyszer, és a hozzárendelése az összes entitáshoz
Lássunk egy példát, amelyben egy Excel-fájl szerepel két munkalappal, amelyek a **Telephelyek** és **Raktárak** nevet viselik. Az adatimportálási projekt beállításához beállítjuk az első adatentitást, a **Telephelyeket**, majd feltöltjük a fájlt. A **Telephelyek** kiválasztható az ehhez az entitáshoz használandó munkalapként.

Ha a második entitást, a **Raktárakat** a **Fájl hozzáadása** képernyő elhagyása nélkül adjuk hozzá, a munkalap-keresés lehetővé teszi a **Raktárak** munkalap hozzáadását anélkül, hogy újra fel kellene tölteni a fájlt. Csak akkor kellene új fájlt feltölteni, ha a **Raktárak** adatai egy másik fájlban lennének.

![Több munkalap](./media/AddFileMultipleWorkSheets.png) 

## <a name="fix-worksheet-to-entity-mapping"></a>A munkalap és az entitás közötti megfeleltetés kijavítása

A munkalap és az adatentitás közötti megfeleltetés az importálási feladatban a rácsban javítható ki. A **Munkalap** rácsbeli oszlop mutatja a megfeleltetett fájlból származó a munkalapokat. A legördülő menüből választhat egy másik munkalapot. Ha a kiválasztott munkalap már hozzá van rendelve egy entitáshoz az adatprojektben, a rendszer megkérdezi, hogy jóváhagyja-e a módosítást. Azt ajánljuk, hogy a rácsban javítsa ki az összes megfeleltetést.

![Munkalap-megfeleltetés frissítése](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a>Ismételt hozzárendelés egy új fájlhoz

Azokban az esetekben, amikor ugyanannak a fájlnak egy új verzióját, vagy egy teljesen új fájlt kell feltölteni a meglévő entitásokhoz egy adatprojektben, a **Fájl hozzáadása** lehetőséget kell használni, és az entitásokat újra hozzá kell adni úgy, mintha első alkalommal adnák hozzá őket. A rendszer megerősíti, hogy felül kívánja-e írni a meglévő entitásokat a folytatás előtt az adatprojektben. Azok az entitások, amelyeket nem adtak hozzá újra (vagy nem írtak felül) továbbra is megtartják a korábbi hozzárendeléseket a korábbi fájlból.

## <a name="upload-a-file-using-run-project"></a>Fájl feltöltése a Projekt futtatása lehetőséggel

Egy importálási projekt végrehajtásához feltölthet egy Excel-fájlt a **Projekt futtatása** funkció használatával. Ügyelnie kell arra, hogy csak olyan fájlokat töltsön fel, amelyek ugyanazokat a munkalapokat tartalmazzák, mint a meglévő leképezések az adatentitásokhoz az adatprojektben. Ha egy munkalap nem található az újonnan feltöltött fájlban, a rendszer hibaüzenetet jelenít meg, és az importálás leáll. Ha egy entitás esetében módosítani kell a hozzárendelést a munkalaphoz, akkor az adatprojektben a hozzárendeléseket először frissíteni kell az adatprojektből, mielőtt a fájlt használná **Projekt futtatása** funkcióban.


