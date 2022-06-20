---
title: Jelentések és dokumentumok összegformátumának megjelenítésének módosítása
description: Ez a cikk azt is bemutatja, hogyan lehet frissíteni az összegek megjelenítését a jelentésekben és más dokumentumokban, amelyek Finnországra, Lettországra, Litvániára, Lengyelországra, Csehországra, Magyarországra és Oroszországra vonatkozó jelentésekben és dokumentumokban jelennek meg.
author: anasyash
ms.date: 01/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Currency
audience: Application User
ms.reviewer: kfend
ms.custom: 264254
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e985ffc156caa86da3a3e8c36122e4f73278ca7f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907710"
---
# <a name="update-how-amounts-are-displayed-on-reports-and-documents"></a>Jelentések és dokumentumok összegformátumának megjelenítésének módosítása

[!include [banner](../includes/banner.md)]

Ez a cikk azt is bemutatja, hogyan lehet frissíteni az összegek megjelenítését a jelentésekben és más dokumentumokban, amelyek Finnországra, Lettországra, Litvániára, Lengyelországra, Csehországra, Magyarországra és Oroszországra vonatkozó jelentésekben és dokumentumokban jelennek meg.

Az Észtország, Lettország, Litvánia, Lengyelország, Csehország, Magyarország és Oroszország területén működő jogi személyeknél beállítható teljes név és rövid név a valutaegységekhez és alegységekhez. Ezek a nevek használhatók annak átalakításához, hogy hogyan hogyan jelennek meg az összegek a dokumentumokban és jelentésekben. Például: az **LTL 100.20** összeg megjeleníthető úgy, hogy **100 Litas 20 Centas**.

## <a name="set-up-full-and-short-names-for-currency-units-and-subunits"></a>Pénzegységek és részegységek teljes és rövid nevének beállítása
Pénzegységek teljes és rövid nevének és nyelvek részegységeinek beállításához kövesse az alábbi lépéseket:

1. Nyissa meg a **Pénznemek** oldalt.
2. Válassza ki a pénznemet.
3. A Műveleti ablaktáblán válassza a **Ragozás** elemet.
4. Egy nyelvhez teljes név és rövid név hozzáadásához kattintson a **Új** elemre, és adjon meg adatokat a következő mezőkbe.

   |             Mező                                                           |                        Leírás                                                                                                                                                                                                                                                |
   |------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                       <strong>Nyelv</strong>                        |                                                                                                               Adja meg az aktuális szöveg nyelvét.                                                                                                                |
   |    <strong>Egyes szám alanyeset (Egységek mezőcsoport neve)</strong>    |                                                                                       Adja meg a pénznem egyes számú formáját. Például a Litas egyes számának formája Litas.                                                                                       |
   |     <strong>Többes szám alanyeset (Egységek mezőcsoport neve)</strong>     | Adja meg a pénznem többes számú formáját. Például írja be azt, hogy Litai. <strong>Megjegyzés:</strong>: az <strong>Egyes szám birtokos eset</strong> és a <strong>Többes szám birtokos eset</strong> mezők a <strong>Nyelv</strong> mezőben kiválasztott nyelv alapján állnak rendelkezésre. |
   | <strong>Egyes szám alanyeset mező (Részek mezőcsoport neve)</strong> |                                                                                                        Adja meg a pénznem alegységének egyes számú formáját.                                                                                                         |
   |     <strong>Többes szám alanyeset (Részek mezőcsoport neve)</strong>     |                                                                                                         Adja meg a pénznem alegységének többes számú formáját.                                                                                                          |
   |    <strong>Egységek rövidített neve (Mezőcsoport rövid neve)</strong>    |                                                                                         Adja meg a pénznem azonosítására szolgáló ISO-kódot. Például a litván litas azonosítására az LTL karaktersort adja meg.                                                                                         |
   |   <strong>Részek rövidített neve (Mezőcsoport rövid neve)</strong>    |                                                                                               Adja meg a pénznem alegységének megnevezését. Például írja be azt, hogy Centas.                                                                                               |
   |       <strong>„És” kapcsolat az egységek és részek között</strong>       |                                     Jelölje be a pénzegységek és egységrészek közötti „és” kapcsolat kinyomtatásához. A 100,20 LTL összeg például így „100 litas és 20 centas” formában jelenik meg a számlákon és jelentéseken.                                      |
   |       <strong>Nem</strong>       |  Válassza ki a **Férfi**, **Nő** vagy **Semleges** értéket. Ez a paraméter befolyásolhatja annak az összegnek a szövegét, amely a készpénzes rendelésen szereplő helyi nyelvű szövegében látható. Amikor **például** **az euró pénznemre vonatkozó nemet nezóként** adja meg, az 1,01 eurós összeg cseh nyelven, jedno euro 01 centként íródott a *készpénzutelékre*.  |

5. Válassza a **Mentés** lehetőséget.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
