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
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71e1657d738f691644b6d9cc4d34f812b853934e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978863"
---
# <a name="customer-payment-overview"></a>Vevői kifizetések áttekintése

[!include [banner](../../includes/banner.md)]

Ez a feladat-útmutató végigvezeti a vevői kifizetések megadásánál használt különböző módszereken. Ez a feladat az USMF bemutatócéget használja.

1. Válassza a **Navigációs ablaktábla >Modulok > Kinnlévőségek > Kifizetések > Kifizetési napló** elemet.
2. Kattintson az **Új** elemre.
3. Válassza ki azt a kifizetési naplót, amelybe a vevői kifizetéseket menti.
4. Válassza ki a naplót, vagy manuálisan adja meg.
5. A **Művelet panelen** kattintson a **Vevői fizetések megadása** elemre. A vevői kifizetések megadása egyszerre csak egy vevői kifizetés rögzítésére szolgál. A kifizetési adatok megadása a felső részen történik, majd megjelölheti az összes, a kifizetés révén kifizetett számlát ugyanazon az oldalon.  
6. Adja meg az ügyfelet, akitől a kifizetést kapta. Ha nem ismeri a vevőt, de tudja, hogy melyik tranzakció lett kifizetve, a Tranzakció mező segítségével adja meg a kifizetést. A Tranzakció mezőben adja meg, vagy válassza ki a számlát. A tranzakció kiválasztása után a vevő automatikusan alapértelmezés szerinti lesz.
7. A **Fizetési hivatkozás mezőben** adja meg a fizetési hivatkozást. A kifizetési hivatkozás a vevő csekkszáma vagy a vevő elektronikus kifizetésére való hivatkozás lehet. A kifizetési hivatkozás csak akkor szükséges, ha bejelöli azt, hogy a kifizetés egy letéti jegyen is szerepeljen.  
8. A **Kifizetési jegyzék** mezőben válassza ki, hogy a kifizetés letéti jegyen fog-e szerepelni. 
9. Az **Összeg** mezőbe írja be a vevői fizetés összegét. A kifizetett összeg nem lesz az alapértelmezett. Azt manuálisan kell megadni. 
10. Jelölje be a vevő által kifizetett számlákat. Ha a kifizetés előleg, nem kötelező a számlákat kiegyenlítésre megjelölni. A kifizetés anélkül is menthető és feladható. A számla kiegyenlítése egy későbbi időpontban is történhet.
11. Írja be a kijelölt számlára kiegyenlítendő kifizetés összegét. Ez a mező használható, amikor a kifizetés részfizetésre szolgál. Ha nem ír be egy összeget, a kiegyenlítendő összeg automatikusan meghatározásra kerül.
12. Kattintson a **Mentés naplóba** gombra. A kifizetés naplóba mentése előtt győződjön meg arról, hogy meg van-e adva az ellenszámla. A **Mentés naplóba** funkció használatakor elmenti a kifizetést, és áthelyezi azt a naplóba. Ezután folytathatja a következő kifizetés rögzítésével.
13. Zárja be a lapot.
14. A **Művelet panelen** kattintson a Sorok elemre. Sorok megnyitásakor megjelennek a **Vevői kifizetések lapon rögzítése** lapon és a naplóba mentett kifizetések. Ezen a lapon új vevői kifizetéseket is megadhat, vagy szerkesztheti a meglévő vevői kifizetéseket is feladás előtt.
15. Az **Új** gombra kattintva hozzon létre egy másik kifizetést. 
16. Válassza ki az ügyfelet, akitől a kifizetést kapta. Ha nem ismeri a vevőt, de ismeri a kifizetéssel kifizetett számlát, a Számla mező segítségével manuálisan adja meg vagy válassza ki a számlát. A vevő az alapértelmezett lesz a számla kiválasztása után.  
17. Kattintson a **Tranzakciók kiegyenlítése** gombra a kifizetett számlák megjelöléséhez. Nem kell semmilyen számlát kiegyenlíteni. Ha ez egy előleg, vagy ha nem tudja, hogy milyen számla lett kifizetve, megadhatja és feladhatja a kifizetést. A kifizetés egy későbbi időpontban is kiegyenlíthető egy számlára.  
18. Jelölje be a kifizetés révén kifizetett számlákat. 
19. Az **Összeg** mezőben írja be a számlára kiegyenlítendő kifizetés összegét.
20. Kattintson az **OK** gombra.
21. A **Fizetési hivatkozás mezőben** adja meg a fizetési hivatkozást. A kifizetési hivatkozás csak akkor szükséges, ha bejelöli azt, hogy a kifizetés egy letéti jegyen is szerepeljen.  
22. A vállalatközi vevői számlák feladásához a **Művelet panelen** kattintson a **Feladás** gombra. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]