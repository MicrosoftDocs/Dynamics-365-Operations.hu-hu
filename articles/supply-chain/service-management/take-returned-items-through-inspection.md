---
title: A visszaadott cikkek vizsgálatának végigvitele
description: A visszaadott cikkek vizsgálatának végigvitele.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f30937eb44893a3cb3587d072b685a855b0ecd3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224906"
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

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]