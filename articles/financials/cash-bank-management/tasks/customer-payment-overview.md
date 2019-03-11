---
title: Vevői kifizetések áttekintése
description: Ez a feladat-útmutató végigvezeti a vevői kifizetések megadásánál használt különböző módszereken.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, CustPaymEntry, CustTableLookup, LedgerJournalTransCustPaym, CustOpenTrans, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6e82be0d68165f62bbdc72a70b0675c7418b14ae
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "317407"
---
# <a name="customer-payment-overview"></a>Vevői kifizetések áttekintése

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat-útmutató végigvezeti a vevői kifizetések megadásánál használt különböző módszereken. Ez a feladat az USMF bemutatócéget használja.

1. Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési napló pontra.
2. Kattintson az Új lehetőségre.
3. Válassza ki azt a kifizetési naplót, amelybe a vevői kifizetéseket menti.
4. Válassza ki a naplót, vagy manuálisan adja meg.
5. Kattintson a Vevői kifizetések megadása lehetőségre.
    * A vevői kifizetések megadása egyszerre csak egy vevői kifizetés rögzítésére szolgál. A kifizetési adatok megadása a felső részen történik, majd megjelölheti az összes, a kifizetés révén kifizetett számlát ugyanazon az oldalon.  
6. Adja meg az ügyfelet, akitől a kifizetést kapta.
    * Ha nem ismeri a vevőt, de tudja, hogy melyik tranzakció lett kifizetve, a Tranzakció mező segítségével adja meg a kifizetést. A Tranzakció mezőben adja meg, vagy válassza ki a számlát. A tranzakció kiválasztása után a vevő automatikusan alapértelmezés szerinti lesz.  
7. A Fizetési hivatkozás mezőben adja meg a fizetési hivatkozást.
    * A kifizetési hivatkozás a vevő csekkszáma vagy a vevő elektronikus kifizetésére való hivatkozás lehet. A kifizetési hivatkozás csak akkor szükséges, ha bejelöli azt, hogy a kifizetés egy letéti jegyen is szerepeljen.  
8. Válassza ki, hogy a kifizetés letéti jegyen fog-e szerepelni. 
9. Írja be a vevőkifizetések összegét.
    * A kifizetett összeg nem lesz az alapértelmezett. Azt manuálisan kell megadni.  
10. Jelölje be a vevő által kifizetett számlákat.
    * Ha a kifizetés előleg, nem kötelező a számlákat kiegyenlítésre megjelölni. A kifizetés anélkül is menthető és feladható. A számla kiegyenlítése egy későbbi időpontban is történhet.  
11. Írja be a kijelölt számlára kiegyenlítendő kifizetés összegét. 
    * Ez a mező használható, amikor a kifizetés részfizetésre szolgál. Ha nem ír be egy összeget, a kiegyenlítendő összeg automatikusan meghatározásra kerül.  
12. Kattintson a Mentés naplóba gombra.
    * A kifizetés naplóba mentése előtt győződjön meg arról, hogy meg van-e adva az ellenszámla. A Mentés naplóba funkció használatakor elmenti a kifizetést, és áthelyezi azt a naplóba. Ezután folytathatja a következő kifizetés rögzítésével.  
13. Zárja be a lapot.
14. Kattintson a Sorok pontra.
    * Sorok megnyitásakor megjelennek a Vevői kifizetések lapon rögzített és a naplóba mentett kifizetések. Ezen a lapon új vevői kifizetéseket is megadhat, vagy szerkesztheti a meglévő vevői kifizetéseket is feladás előtt.  
15. Az Új gombra kattintva hozzon létre egy másik kifizetést. 
16. Válassza ki az ügyfelet, akitől a kifizetést kapta.
    * Ha nem ismeri a vevőt, de ismeri a kifizetéssel kifizetett számlát, a Számla mező segítségével manuálisan adja meg vagy válassza ki a számlát. A vevő az alapértelmezett lesz a számla kiválasztása után.  
17. Kattintson a Tranzakciók kiegyenlítése gombra a kifizetett számlák megjelöléséhez.
    * Ekkor nem kell semmilyen számlát kiegyenlíteni. Ha ez egy előleg, vagy ha nem tudja, hogy milyen számla lett kifizetve, megadhatja és feladhatja a kifizetést. A kifizetés egy későbbi időpontban is kiegyenlíthető egy számlára.  
18. Jelölje be a kifizetés révén kifizetett számlákat. 
19. Írja be a számlára kiegyenlítendő kifizetés összegét.
20. Kattintson az OK gombra.
21. A Fizetési hivatkozás mezőben adja meg a fizetési hivatkozást. gombra.
    * A kifizetési hivatkozás csak akkor szükséges, ha bejelöli azt, hogy a kifizetés egy letéti jegyen is szerepeljen.  
22. Adja fel a vevői kifizetéseket. 

