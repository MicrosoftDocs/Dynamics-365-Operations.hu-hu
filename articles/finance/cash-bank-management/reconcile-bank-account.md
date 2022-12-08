---
title: Bankszámla egyeztetése
description: Ez a témakör azt ismerteti, hogyan lehet egyeztetni a bankszámlákat.
author: angelad116
ms.date: 11/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: angelading
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 12de50f26127c54c2f82ace43487de10e7125aea
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804210"
---
# <a name="reconcile-a-bank-account"></a>Bankszámla egyeztetése

[!include[banner](../includes/banner.md)]

Amikor banki kivonatot kap, akkor javasolt, hogy rendszeres időközönként egyeztesse a jogi személy banki tranzakcióit a bank kivonaton szereplő tranzakciókkal.

A banki kivonatok nem egyeztethetők egy bankszámlával, ha a **kivonaton szereplő bármelyik csekk vagy letétijegy-kifizetés állapota jelenleg Visszavonásra vár**. Miután egy ellenőr felad vagy elutasít egy csekksztornírozást vagy egy letétijegy-kifizetés visszavonását, az állapot már nem **Visszavonásra vár**, így már egyeztetheti a bankszámlát.

1. Menjen a **Készpénz és bankkezelés** \> **Bankszámlák** \> **Bankszámlák** menüpontra. Válassza ki a bankszámlát, amelyet a banki kivonattal egyeztetni szeretné, és válassza az **Egyeztetés** > **Számlaegyeztetés** lehetőséget.

2. Adja meg az adatokat a **Bankszámlakivonat dátuma** és a **banki kivonat** mezőkben. A **Záróegyenleg** mezőben megadhatja a bankszámla egyenlegét, ahogy az megjelenik a banki kivonaton.

3. A **Tranzakciók** lehetőség kiválasztásával megnyithatja a **Számlaegyeztetés** oldalon.

4. A banki kivonaton szereplő minden tranzakciónál jelölje be a Törölve jelölőnégyzetet, **ha** a Dynamics 365 Pénzügyben szereplő összeg megegyezik a banki kivonaton szereplő összeggel. Ezenkívül a **Banki tranzakció típusa** mező értékét is megadhatja vagy módosíthatja. Ez a mezőérték a banki tranzakciók statisztikája és egyes jelentések szempontjából fontos.
    

>[!NOTE]
>Ne jelölje be a **Törölve** jelölőnégyzetet az olyan tranzakcióknál, amelyek nem a banki kivonaton vannak. Ezek a tranzakciók továbbra is megjelennek ezen a képernyőn, amíg egy későbbi banki kivonattal meg nem történik az egyeztetésük.
>A **Törölve** jelölőnégyzet nem érhető el, ha a **tranzakció visszavonásra váró állapotú**. A tranzakciók akkor rendelkezhetnek ilyen állapottal, ha a Finance modul beállításai megkövetelik, hogy a sztornírozásokat vagy visszavonásokat elküldjék ellenőrzésre a könyvelés előtt. Miután egy ellenőr könyveli vagy elutasítja a sztornírozást vagy a visszavonást, az állapot már nem **Visszavonásra vár**, így már egyeztetheti a bankszámlát a banki kivonattal.


A Törölve **jelölőnégyzet** bejelölése esetén a banki kivonaton a csekkek egy része látható, **jelölje be a Csekkintervallum** jelölése jelölőnégyzetet, majd adja meg az intervallumot.

5.  Ha egy bankszámla-tranzakció összege nem egyezik meg a banki kivonaton lévő tranzakció összegével, **a** Korrekció összege mezőbe írja be a korrekció összegét.
    

> [!NOTE]
> Ha a javítható tranzakció pénzügyi időszaka le van zárva, **a** Javítás összege mező nem használható. Ehelyett hozzon létre egy sort, amelynek tranzakciós dátuma a helyesbítéshez használt nyitott pénzügyi időszakban van. Ebben az esetben az eredeti tranzakciónál használt pénzügyi dimenziókat és az fő ellenszámlát is fel kell venni.



6.  Hozzon létre tranzakciókat az olyan bejegyzésekhez, amelyek szerepelnek a banki kivonaton, de nincsenek rögzítve a Finance rendszerben (például díjakhoz és kamathoz). Adja meg a **Banki tranzakciótípus** értékét és a megfelelő pénzügyi dimenziókat.

7.  Ahogyan a banki kivonaton szereplő tranzakciókat **Törölt** értékkel jelöli meg, a **Nem egyezetett** mezőben szereplő összeg (amelyet a rendszer a változtatásokkal párhuzamosan folyamatosan újraszámít) egyre közelebb kerül a nullához. Amikor eléri a nulla értéket, válassza a **Számla egyeztetése** lehetőséget az egyeztetés, illetve a létrehozott tranzakciók és javítások feladásához.
    
    Az egyeztetés feladása után a benne szereplő tranzakciókat nem lehet módosítani vagy javítani, és a későbbi számlaegyeztetés során nem jelennek meg.

8.  A még nem egyeztetett banki tranzakciók megtekintéséhez használja a **Nem egyeztetett banki tranzakciók** jelentést. A bankszámlához tartozó banki kivonat megtekintéséhez használja a **Banki kivonat** jelentést.

## <a name="cancel-bank-statement-reconciliation"></a>Banki kivonat egyeztetésének megszakítása 

A **banki kivonat egyeztetésének megszakítása** funkcióval visszavonható a banki kivonat egyeztetése. A szolgáltatás használatához engedélyezze a **Banki kivonat egyeztetésének megszakítása** funkciót a **Funkciókezelés** munkaterületen. Engedélyeznie kell a **Banki kivonat szerkesztésének engedélyezése** paramétert is. Ehhez lépjen a **Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelés paraméterei > Banki egyeztetés** pontra.
 
A banki kivonat egyeztetései csak abban az időrendi sorrendben vonhatók vissza, amelyben bevitték őket. A banki kivonat egyeztetésének megszakításakor az új tranzakciókat és helyesbítéseket a program sztornírozza, és az összes többi tranzakciót nem egyeztetettként jelöli meg.
 
A banki kivonat egyeztetésének megszakításához válassza ki a banki kivonatot, és válassza a **Banki kivonat > Banki egyeztetés visszavonása** lehetőséget. A **Banki egyeztetés visszavonása** lapon adja meg az **Okkód**, az **Okhoz kapcsolódó megjegyzés** és a **Visszavonás dátuma** értékét. A visszavonás elindításához válassza az **OK** lehetőséget. Ne feledje, hogy a banki kivonat visszavonási dátuma nem lehet korábbi a banki kivonat dátumánál. A banki kivonat **egyeztetésének**  **érvénytelenítését követően a rendszer frissíti a banki kivonat Érvénytelenítési dátum mezőjét a megadott érvénytelenítési dátummal.**  Válassza a **Tranzakciók** gombot azoknak a tranzakcióknak a megtekintéséhez, amelyek egyeztetését visszavonta.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
