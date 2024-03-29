---
title: Csererendelés létrehozása egy cikkre vonatkozóan
description: A cserecikkrendeléseket általában a visszajuttatott termék kivizsgálása után hozzák létre.
author: josaw1
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnReplaceItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14751fb0e0632ca986d6eddf55c93d44fbd68276
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015464"
---
# <a name="create-an-item-replacement-order"></a>Csererendelés létrehozása egy cikkre vonatkozóan 

[!include [banner](../includes/banner.md)]


A cserecikkrendeléseket általában a visszajuttatott termék kivizsgálása után hozzák létre. Előfordulhat azonban, hogy a cikket még a visszajuttatás előtt ki kell cserélni, vagy az eredeti cikket egyáltalán nem juttatják vissza, ezért ilyenkor a cserecikkrendelést közvetlenül a visszárurendelés után létre lehet hozni.

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a>Csererendelés létrehozása visszáru beérkezése után

1.  Kattintson az **Értékesítés és marketing parancsra** \> **, ha minden visszárurendelést** \> **visszahoz**.

2.  Hozzon létre új visszárurendelést, vagy a **Visszárurendelések - RMA-szám: %1, %2** képernyő megnyitásához válasszon ki a listáról egy visszárurendelést.

3.  Kattintson a **Visszárusor** lehetőségre, majd válassza ki a **Helyettesítő cikk** opciót.

4.  Jelölje ki a cikket, amellyel cseréli a visszáruzott cikket. Adja meg a cikk adatait, majd kattintson az **Alkalmaz** gombra.

5.  A visszárurendelés szállítólevelének létrehozásához kattintson a **Visszárurendelés szállítólevele** elemre. A kijelölt cserecikkhez értékesítési rendelés jön létre.
    
    A rendszer a cserecikk értékesítési rendelésének létrejötte után automatikusan keresést végez az értékesítési szerződések között, és ha van megfelelő értékesítési szerződés, akkor azt alkalmazza az értékesítési rendelésen.

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a>Csererendelés létrehozása visszáruzott cikkhez annak beérkezése előtt 

1.  Kattintson az **Értékesítés és marketing parancsra** \> **, ha minden visszárurendelést** \> **visszahoz**.

2.  Hozzon létre új visszárurendelést, vagy a **Visszárurendelések - RMA-szám: %1, %2** képernyő megnyitásához válasszon ki a listáról egy visszárurendelést.

3.  A visszaküldött cikkre vonatkozó értékesítési rendelés azonosításához kattintson az **Értékesítési rendelés megkeresése** elemre. Töltse ki az **Értékesítési rendelés megkeresése** képernyőt, majd kattintson az **OK** gombra a képernyő bezárásához és a **Visszárurendelések - RMA-szám: %1, %2** képernyőre való visszatéréshez. A visszárucikkhez tartozó értékesítésirendelés-sor a visszárurendelésbe másolódik.

4.  Az **Értékesítési rendelés** képernyő megnyitásához kattintson a **Csererendelés** elemre.

5.  Jelölje be a **Visszárurendelés-sorok másolása** jelölőnégyzetet, hogy az értékesítési rendelésbe másolja a **Visszárurendelések - RMA-szám: %1, %2** képernyőn kijelölt visszárurendelés adatait.

6.  Szükség esetén adja meg és módosítsa az adatokat.
    
    Amennyiben a 3. lépésben azonosította az értékesítési rendelést, valamint ha a visszaküldött cikkre vonatkozó értékesítésirendelés-sor értékesítési szerződéshez kapcsolódik, a csererendelésre vonatkozó értékesítési szerződés azonosítója automatikusan megjelenik az **Értékesítési szerződés azonosítója** mezőben.

7.  Kattintson az **OK** gombra az **Értékesítési rendelés létrehozása** képernyő bezárásához és az **Értékesítési rendelés** képernyő megnyitásához, ahol folytathatja az új értékesítési rendelés adatainak megadását. Az alkalmazandó visszárurendelés-sorok az új értékesítési rendelésbe másolódnak. 
    
    Ha az értékesítési szerződés azonosítója automatikusan megjelent az **Értékesítési szerződés azonosítója** mezőben, akkor az értékesítési szerződés össze van kapcsolva a cikk csererendelésére vonatkozó értékesítési rendelés fejlécével. Ha az értékesítési szerződésben még nem teljesített kötelezettség szerepel, és az értékesítési rendelés még az értékesítési szerződés lejárata előtt létrejön, az értékesítési szerződés és az értékesítési rendelési sor között kapcsolat jön létre. Így az új értékesítésirendelés-sorba belemásolódnak az értékesítési szerződés adatai, például a cikk ára. 
  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]