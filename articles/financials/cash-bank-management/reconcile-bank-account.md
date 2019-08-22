---
title: Bankszámla egyeztetése
description: Ez a témakör bemutatja, hogyan lehet egyeztetni egy bankszámlát.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e9a9d1c53a4b9e764c1592cca898cd6f3293594
ms.sourcegitcommit: 299e20b59ebefa584ed46a13da3f1a7ff709e43c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2019
ms.locfileid: "1863632"
---
# <a name="reconcile-a-bank-account"></a>Bankszámla egyeztetése

[!include[banner](../includes/banner.md)]

Amikor banki kivonatot kap, akkor javasolt, hogy rendszeres időközönként egyeztesse a jogi személy banki tranzakcióit a bank kivonaton szereplő tranzakciókkal.

Nem lehetséges a banki kivonat és a bankszámla egyeztetése, ha a kivonaton szereplő bármely csekk vagy letétijegy-kifizetés aktuális állapota **Visszavonásra vár**. Miután egy ellenőr felad vagy elutasít egy csekksztornírozást vagy egy letétijegy-kifizetés visszavonását, az állapot már nem **Visszavonásra vár**, így már egyeztetheti a bankszámlát.

1.  Menjen a **Készpénz és bankkezelés** \> **Bankszámlák** \> **Bankszámlák** menüpontra. Válassza ki a bankszámlát, amelyet a banki kivonattal egyeztetni szeretné, és válassza az **Egyeztetés** > **Számlaegyeztetés** lehetőséget.

2.  Adja meg az adatokat a **Bankszámlakivonat dátuma** és a **banki kivonat** mezőkben. A **Záróegyenleg** mezőben megadhatja a bankszámla egyenlegét, ahogy az megjelenik a banki kivonaton.

3.  A **Tranzakciók** lehetőség kiválasztásával megnyithatja a **Számlaegyeztetés** oldalon.

4.  A banki kivonaton szereplő mindegyik tranzakciónál jelölje be a **Törölve** jelölőnégyzetet, ha a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban szereplő összeg megfelel a bank kivonaton szereplő összegnek. Ezenkívül a **Banki tranzakció típusa** mező értékét is megadhatja vagy módosíthatja. Ez a mezőérték a banki tranzakciók statisztikája és egyes jelentések szempontjából fontos.
    

    > [!NOTE]
    > <P>Ne jelölje be a <STRONG>Törölve</STRONG> jelölőnégyzetet azoknál a tranzakcióknál, amelyek nem szerepelnek a banki kimutatáson. Ezek a tranzakciók továbbra is megjelennek ezen a képernyőn, amíg egy későbbi banki kivonattal meg nem történik az egyeztetésük.</P>
    > <P>A <STRONG>Törölve</STRONG> jelölőnégyzet nem érhető el, ha a tranzakció állapota <STRONG>Visszavonásra vár</STRONG>. A tranzakciók akkor rendelkezhetnek ilyen állapottal, ha a Finance and Operations modul beállításai megkövetelik, hogy a sztornírozásokat vagy visszavonásokat elküldjék ellenőrzésre a könyvelés előtt. Miután egy ellenőr könyveli vagy elutasítja a sztornírozást vagy a visszavonást, az állapot már nem <STRONG>Visszavonásra vár</STRONG>, így már egyeztetheti a bankszámlát a banki kivonattal.</P>

    
    Ha szeretné a banki kivonaton megjelenő csekkek egy adott intervallumához bejelölni a **Törölve**jelölőnégyzetet, akkor válassza a **Csekk intervallumának kijelölése** lehetőséget, majd adja meg az intervallumot.

5.  Ha a bankszámla-tranzakció összege nem felel meg a banki kivonaton szereplő tranzakció összegének, adja meg a helyesbítő összeget a **Helyesbítő összeg** mezőben.
    

    > [!NOTE]
    > <P>Ha a javítandó tranzakció pénzügyi időszaka már le van zárva, a <STRONG>Helyesbítő öszeg</STRONG> mező nem használható. Ehelyett hozzon létre egy sort, amelynek tranzakciós dátuma a helyesbítéshez használt nyitott pénzügyi időszakban van. Ebben az esetben az eredeti tranzakciónál használt pénzügyi dimenziókat és az fő ellenszámlát is fel kell venni.</P>



6.  Hozzon létre tranzakciókat az olyan bejegyzésekhez, amelyek szerepelnek a banki kivonaton, de nincsenek rögzítve a Finance and Operations rendszerben (például díjakhoz és kamathoz). Adja meg a **Banki tranzakciótípus** értékét és a megfelelő pénzügyi dimenziókat.

7.  Ahogyan a banki kivonaton szereplő tranzakciókat **Törölt** értékkel jelöli meg, a **Nem egyezetett** mezőben szereplő összeg (amelyet a rendszer a változtatásokkal párhuzamosan folyamatosan újraszámít) egyre közelebb kerül a nullához. Amikor eléri a nulla értéket, válassza a **Számla egyeztetése** lehetőséget az egyeztetés, illetve a létrehozott tranzakciók és javítások feladásához.
    
    Az egyeztetés feladása után a benne szereplő tranzakciókat már nem lehet módosítani vagy javítani, és nem jelennek meg a jövőbeli számlaegyeztetésben.

8.  A még nem egyeztetett banki tranzakciók megtekintéséhez használja a **Nem egyeztetett banki tranzakciók** jelentést. A bankszámlához tartozó banki kivonat megtekintéséhez használja a **Banki kivonat** jelentést.

# <a name="cancel-bank-statement-reconciliation"></a>Banki kivonat egyeztetésének megszakítása 

A banki kivonat egyeztetésének megszakítása funkció segítségével megszakíthatja a banki kivonat egyeztetését. A szolgáltatás használatához engedélyezze a **Banki kivonat egyeztetésének megszakítása** funkciót a **Funkciókezelés** munkaterületen. Engedélyeznie kell a **Banki kivonat szerkesztésének engedélyezése** paramétert is. Ehhez lépjen a **Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelés paraméterei > Banki egyeztetés** pontra.
 
A banki kivonat egyeztetései csak abban az időrendi sorrendben vonhatók vissza, amelyben bevitték őket. A banki kivonat egyeztetésének megszakításakor az új tranzakciókat és helyesbítéseket a program sztornírozza, és az összes többi tranzakciót nem egyeztetettként jelöli meg.
 
A banki kivonat egyeztetésének megszakításához válassza ki a banki kivonatot, és válassza a **Banki kivonat > Banki egyeztetés visszavonása** lehetőséget. A **Banki egyeztetés visszavonása** lapon adja meg az **Okkód**, az **Okhoz kapcsolódó megjegyzés**és a **Visszavonás dátuma** értékét. A visszavonás elindításához válassza az **OK** lehetőséget. Ne feledje, hogy a banki kivonat visszavonási dátuma nem lehet korábbi a banki kivonat dátumánál. A banki kivonat egyeztetésének visszavonása után a banki kivonat **Visszavonás dátuma** mezője frissül a megadott **Visszavonási dátum** értékével. Válassza a **Tranzakciók** gombot azoknak a tranzakcióknak a megtekintéséhez, amelyek egyeztetését visszavonta.
