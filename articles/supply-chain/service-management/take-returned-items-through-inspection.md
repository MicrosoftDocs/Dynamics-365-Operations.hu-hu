---
title: "A visszaadott cikkek vizsgálatának végigvitele"
description: "A visszaadott cikkek vizsgálatának végigvitele."
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: df209cfdbdef591e9f24161b3651316c43d69ee0
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---


# <a name="take-returned-items-through-inspection"></a>A visszaadott cikkek vizsgálatának végigvitele 

[!include [banner](../includes/banner.md)]


1.  Kattintson ide: **Készletkezelés** \> **Időszakos** \> **Minőségkezelés** \> **Karanténutasítások**.

2.  Keresse meg azt a rendeléssort, amely megfelel a vizsgált visszáru cikknek.

    > [!NOTE]
    > <P>Egy karanténutasítás csak egyetlen cikkszámhoz társítható. Ha 10 különböző cikkszámú cikk érkezik vissza egyetlen szállítmányban, és ezeket karanténba helyezik, akkor 10 külön karanténutasítást kell létrehozni.</P>

3.  A cikk vizsgálata után az **Intézkedési kód** mező beállításával jelezheti, hogy mit kell tenni a cikkel, és milyen kapcsolódó pénzügyi tranzakciókat kell kezelni, amik a következők lehetnek: a cikk visszavétele a készletbe és az ár visszatérítése, a cikk leselejtezése és cserecikk küldése a vevőnek, vagy a cikk visszaküldése a vevőnek, és a költségek kiszámlázása.
    
    > [!NOTE]
    > <P>Ha egy cikkszámkötegben több visszaadott cikk nem társítható ugyanahhoz az intézkedési kódhoz, akkor az egyes részkötegekre vonatkozó különböző intézkedési kódoknak megfelelően fel kell bontani a karanténutasítást (<STRONG>Funkciók</STRONG> &gt; <STRONG>Felosztás</STRONG>).</P>


4.  A kivizsgálás befejezése után a **Készként jelentés** lehetőségre kattintva kiadhatja a visszaadott cikkeket, és létrehozhat egy cikkérkezési naplóbejegyzést. A cikkeket fogadó személy vagy részleg ezután feldolgozza a készletbe visszahelyezendő cikkek naplóját.
    
    – vagy –
    
    Fejezze be a karanténutasítást, és helyezze vissza a cikkeket közvetlenül a készletbe a **Készlet** gomb valamelyik funkciójával.

5.  A módosítások mentéséhez zárja be a képernyőt.

## <a name="see-also"></a>Lásd még

[A visszaadott cikkek kivezetési módjának megadása](specify-how-to-dispose-of-returned-items.md)

  



