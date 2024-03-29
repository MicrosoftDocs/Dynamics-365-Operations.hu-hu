---
title: Teljes költségfelosztási módszer
description: Ez a cikk bemutatja a teljes költségfelosztás (TCA) használatának irányelveit. A TCA egy számítási módszer, amely a köteghez tartozó fő receptúracikk és a receptúrában meghatározott társtermékek közötti költséget adja meg.
author: JennySong-SH
ms.date: 04/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConsistOf, PmfFormulaCoBy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 83852
ms.assetid: 7c14c3e5-9476-4a79-a210-e77fc91cc7fc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 213db8303c27934050f5b414a67f6e510486dc94
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862685"
---
# <a name="total-cost-allocation-method"></a>Teljes költségfelosztási módszer

[!include [banner](../includes/banner.md)]

Az összköltség felosztás (TCA) a kötegrendelés fő receptúrás cikkének az ára és a receptúrához meghatározott társtermékek árösszegei közötti költség kiszámításának a módszere. Ez a módszer dinamikus. A költséget a társtermékek és a receptúrás cikk számára befejezettnek jelentett mennyiségek súlyozott átlagaként számítja ki. TCA használata esetén nem szükséges minden kötegrendelés esetében áttekintenie a költségfelosztásokat. Amennyiben nem alkalmaz TCA-t, a receptúra számítás egy meglevő funkciót alkalmaz.

## <a name="using-tca-for-coproducts"></a>TCA alkalmazása társtermékekre
Íme néhány irányelv a TCA társtermékekre történő alkalmazása esetében:

-   Ha a **Teljes költségfelosztás** csúszkát **Igen** opcióra állítja a receptúra verziónál, a társtermékeknek kötelezően 0 (nulla) fölötti önköltségi árral kell rendelkezniük. Az érték visszakapcsolható az aktív költségverzióról az azonos oldalra vagy a receptúra első, nem webhely-specifikus webhelyére. A feltétel érvényesítése a receptúra elfogadásakor történik meg.

    -   Nem kell manuálisan megadnia a társtermékek költségelosztási százalékát. Ehelyett a rendszer automatikusan létrehozza a költségelosztási százalékot a társtermékek aktív költségárának átlagaként. 
    -   Nem kell megadnia a normál költséget az olyan nem szabványos költségelemekért, amelyek társtermékek. A rendszerben kétféle költségszámítási változat létezik: a normál költség és a tervezett költség 
    -   Ha egy elemet nem a normál költségbecslési módszer értékel, javasoljuk, hogy a tervezett költségváltozatban aktív költségárat használjon. Ezt az árat a költségbecsléshez, például az anyagjegyzék kiszámításához, a gyártási költségbecsléshez és a készletértékelési folyamatba tartozó tartalékárhoz használják. 

-   Ha az **Összköltségfelosztás** csúszkát **Igen** opcióra állítja a receptúra verzió számára, és a következő feltételek igazak, akkor **TCA** a költségfelosztás módszere és a költségfelosztás százaléka változatlan:
    -   Társtermékeket adott hozzá.
    -   A társtermékek költségfelosztására más módszert használt.
-   Ha az **Összköltségfelosztás** csúszkát **Nem** opcióra állítja a receptúra verzió számára, és a következő feltételek igazak, akkor **Manuálisra** módosult a költségfelosztás módszere és a költségfelosztás százaléka változatlan:
    -   Társtermékeket adott hozzá.
    -   A költségfelosztás százalékos értéke nagyobb, mint 0 (nulla).
-   Egy receptúraszámítás sikeres végrehajtása előtt meg kell becsülnie a költségfelosztás százalékait. Ezt a lépést elvégezheti manuálisan vagy a **Költség becslése** beállítás segítségével a **Társtermékek** lapon. **Megjegyzés:** a **Költség becslése** a beállítás csak akkor érhető el, ha a **Teljes költségfelosztás** csúszka értéke **Igen** a receptúraverzióhoz. Akkor tekintheti meg a várható felosztást, ha a készként jelentett kötegrendelés mennyiségei megegyeznek a receptúrán megjelenő mennyiségekkel.
-   Amikor egy kötegrendelést manuálisan hoznak létre vagy egy tervezett kötegrendelést megerősítenek, akkor a receptúraverzióhoz tartozó **Teljes költségfelosztás** csúszka értéke a kötegrendelésbe másolódik. Azonban ezt a beállítást megváltoztathatja a kötegrendelésben. Ha a **Teljes költségfelosztás** csúszka értéke **Nem** a receptúraverzióban, majd **Igen** értékre módosul a kötegrendelésben, akkor a költségfelosztás módszere minden olyan sorban, amelyben **Manuális** volt **TCA** értékre módosul. A **Nincs** értékű sorok költségfelosztása változatlan marad. Ha a **Teljes költségfelosztás** csúszka értéke **Igen** a receptúraverzióban, majd **Nem** értékre módosul a kötegrendelésben, akkor a költségfelosztás módszere minden **Termelés** típusú társterméknél **Manuális** értékre módosul. A költségfelosztás százalékos értékei változatlanok maradnak.
-   A **Társtermék költségfelosztási** oldal jeleníti meg a költségfelosztás számított százalékos értékét. Ezt a lapot megnyithatja a **Kötegrendelés** oldalról. Ez az információ akkor hasznos, amikor a jelentett termékek és mennyiségek eltérnek kötegrendelésben található ütemezett vagy elindított mennyiségektől. Amikor a költség elkészült ezek új, TCA-ból származó százalékos felosztások a **Társtermék költségfelosztása** oldalon jelennek meg.

## <a name="calculating-the-burden-for-byproducts"></a>A melléktermékek költségterhelésének számítása
A **Melléktermék költségfelosztása** mező a **Társtermékek** oldalon egy enumerátor mező, amely csak melléktermékekhez használatos. A társtermékekhez ezen mező értéke mindig **Nincs**. A mellékterméksoroknál ez a mező határozza meg a melléktermék költségösszegének a termelés teljes költségéhez való hozzáadásának módját. Az alábbi lehetőségek közül választhat:

-   **Nincs** – Nem adódik hozzá összeg a termelés teljes költségéhez ebből a mellékterméksorból.
-   **Százalék** – A költségösszeg a termelés során felhasznált nyersanyagok teljes költségének egy százalékaként van kiszámítva. A számításokhoz használt százalék van megadva a mezőben.
-   **Sorozatonként** – A költségösszeg a termelési rendelés szabványos kötegméretei utáni összegként van kiszámítva. Ez az összeg független a termelésben jelentett mennyiségtől. A számításokhoz használt összeg van megadva a mezőben.
-   **Mennyiség szerint** – A költségösszeg a termelésben lévő receptúracikk jelentett mennyisége szerinti összegként van kiszámítva. A számításokhoz használt összeg van megadva a mezőben.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]