---
title: Beszerzési szerződés létrehozása
description: Ez a témakör végigvezeti a beszerzési szerződés létrehozásán.
author: mkirknel
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1edfd4e56910376d0596eec5eff2af888f7dc98d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429461"
---
# <a name="create-a-purchase-agreement"></a>Beszerzési szerződés létrehozása

[!include [banner](../../includes/banner.md)]

Ez a témakör végigvezeti a beszerzési szerződés létrehozásán. Ez általában egy beszerzési vezető által történik. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja. A kezdés előtt létre kell hozni a beszerzési szerződés osztályozásait. Miután létrehozta a megállapodást, használhatja, amikor létrehoz egy beszerzési rendelést, és ez bemásolja a beszerzési szerződés feltételeit a megállapodás által érintett rendelés fejlécébe és soraiba.


## <a name="create-a-new-purchase-agreement"></a>Új beszerzési szerződés létrehozása
1. Ugorjon a **Navigációs ablaktábla > Modulok > Beszerzés és forrás > Beszerzési szerződések > Beszerzési szerződések** elemre.
2. Kattintson az **Új** elemre.
3. A **Szállítói számla** mezőben válassza ki a legördülő menüt, majd a kívánt rekord sorát.
4. A **Beszerzési szerződés osztályozása** mezőben válassza ki a legördülő menüt, majd a kívánt rekord sorát.
5. Bontsa ki az **Általános** gyorslapot.
6. Adjon meg egy dátumot a **Lejárati dátum** mezőben.

    - Ez a lejárati dátum lesz az alapértelmezés az összes kötelezettségvállalási sorban, és meghatározza, mennyi ideig érvényesek a kötelezettségek.  

7. A **Dokumentum címe** mezőbe írja be a beszerzési szerződés nevét.

    - Hagyja az **Alapértelmezett kötelezettségvállalás** mezőt **Termékmennyiségi kötelezettség** értéken (vagy módosítsa erre, ha nem ez az értéke).  
    - Az alapértelmezett kötelezettségvállalási érték határozza meg a megállapodási sorokban látható opciókat. Ha új kötelezettségtípusra van szüksége a megállapodási sorok létrehozásakor, módosítsa az alapértelmezett kötelezettséget a fejlécben. A kötelezettségvállalásoknak 4 típusa van: **Termékmennyiségi kötelezettség** – egy adott mennyiségű termékre; **Termék értékére vonatkozó kötelezettség** – termékösszeg adott pénznemben; **Termék kategóriaértékére vonatkozó kötelezettség** – egy beszerzési kategóriában lévő konkrét összeg devizában, ahol az összeg katalóguscikkre vagy a katalóguson kívüli cikkre vonatkozhat; **Értékre vonatkozó kötelezettség** – adott pénznemben lévő összegre, amely bármely termékre vagy beszerzési kategóriára vonatkozhat.  

8. Válassza ki az **OK** lehetőséget.

## <a name="add-a-commitment"></a>Kötelezettség hozzáadása
1. Válassza a **Sor hozzáadása** lehetőséget.
2. A **Cikkszám** mezőben válassza ki a kívánt rekordot a legördülő menüből.
3. Adjon meg egy számot a **Mennyiség** mezőben. Ez az a teljes mennyiség, amelyeket a megállapodás szerint beszerez a szállítótól.  
4. Adjon meg egy számot az **Egységár** mezőben.
5. Bontsa ki a **Sorrészletek** szakaszt.
6. Állítsa a **Maximális kényszerítése** opciót **Igen**-re. A **Maximum betartatása** beállítás korlátozza a kötelezettségvállalás használatát. Csak a **Mennyiség** mezőben megadott mennyiséget vásárolhatja meg az adott sorhoz.  

## <a name="add-header-conditions"></a>Fejlécben megadott feltételek hozzáadása
1. A műveleti ablaktáblán válassza ki a **Beállítások** elemet.
2. Válassza ki a **Nézetváltás** lehetőséget.
3. Válassza ki a **Fejlécnézet** elemet.
4. Bontsa ki a **Feltételek** szakaszt.
5. A **Fizetési mód** mezőben válassza ki a kívánt rekordot a legördülő menüből. Alapértelmezés szerint a szállítói számla fizetési feltételei láthatók itt.  
6. A **Szállítási mód** mezőben válassza ki a kívánt rekordot a legördülő menüből.
7. A **Szállítási feltételek** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.

## <a name="confirm-and-activate-the-agreement"></a>Erősítse meg és aktiválja a megállapodást
1. A Művelet panelen kattintson a **Beszerzési szerződés** elemre.
2. Válassza ki a **Visszaigazolás** lehetőséget. Állítsa a **Szerződés megjelölése érvényesként** beállítást **Igen** értékre.  
3. Válassza ki az **OK** lehetőséget.
4. A Művelet panelen kattintson a **Beszerzési szerződés** elemre.
5. Válassza a **Beszerzésiszerződés-visszaigazolások** elemet. Az **Előnézet/nyomtatás** beállítás lehetővé teszi a beszerzési szerződéshez dokumentum létrehozását, amelyet kinyomtathat vagy elküldhet a szállítónak. Ha később frissítési a szerződést, és ismételten megerősíti, mindkét verzió megjelenik itt.  
6. Zárja be a lapot.

