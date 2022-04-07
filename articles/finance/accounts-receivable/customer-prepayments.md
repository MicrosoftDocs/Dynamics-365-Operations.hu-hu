---
title: Vevői előlegek
description: Ez a témakör elmagyarázza, hogyan lehet beállítani és feldolgozni az ügyfelek előlegeit (más néven vevői letéteket).
author: twheeloc
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ba462dc2b5fe326db14dfb3c92f986478d31791
ms.sourcegitcommit: 3cb1f49a02e4a849fc34ffeb81fe507f0608b35e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464876"
---
# <a name="customer-prepayments"></a>Vevői előlegek

[!include [banner](../includes/banner.md)]

A vevői előlegeket akkor használjuk, amikor egy ügyféltől befizetést kap, de nincs olyan számla, amellyel szemben a fizetés kiegyenlíthető. Az ilyen típusú kifizetéseket ügyfélletétnek is nevezik.

Az ügyfél előlegek beállításának és feldolgozásának folyamata a következő alapvető lépésekből áll.

1. Hozzon létre egy vevőfeladási profilt az előlegekhez.
2. Állítsa be a **Feladási profil az előlegnapló-bizonylathoz** paramétert.
3. Hozzon létre egy vevői fizetési naplót, és jelölje be az **Előlegnapló-bizonylat** jelölőnégyzetet minden sorban.
4. A vevői kifizetési napló feladása.
5. A számla kiállítása után egyenlítse ki vele az előleget a **Nyitott tranzakciók rendezése** lapon.

## <a name="create-a-customer-posting-profile-for-prepayments"></a>Hozzon létre egy vevőfeladási profilt az előlegekhez

Általában, ha az áruk vagy szolgáltatások kiszállítása előtt, vagy a számla rendszerében számla kiállítása előtt fogad az ügyfelektől származó előlegeket vagy letéteket, akkor a készpénzt kötelezettségként kívánja rögzíteni, nem pedig eszközként a számlatükörben. Ugyanakkor ezen összegek főkönyvben való rögzítésére vonatkozó követelmények azonban országtól vagy régiótól függően eltérőek lehetnek. Ezért mindenképpen egyeztessen a könyvelőivel az alkalmazandó helyi szabályozásokról.

Általánosságban elmondható, hogy az előrefizetésre használható feladási profil létrehozásának folyamata megegyezik az egyéb feladási profilok létrehozásának folyamatával. Az elsődleges különbség az **Összegzett számla** mezőben kiválasztott fő fiók. A további információkat lásd: [Vevői feladási profilok](customer-posting-profiles.md).

## <a name="define-parameters-for-customer-prepayments"></a>Vevői előlegek paramétereinek meghatározása

Két fő kintlévőség-paramétert kell figyelembe vennie, amikor konfigurálja a rendszert az ügyfelek előlegeihez. Tegye a következőket a paraméterek konfigurálásához.

1. Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.
2. Nem kötelező: A **Főkönyv és áfa** lapon, a **Fizetés** gyorslapon lapon állítsa be az **Áfa az előlegnapló-bizonylaton** beállítást **Igen** értékre.
3. A **Feladási profil az előlegnapló-bizonylathoz** mezőben válassza ki azt az ügyfél-feladási profilt, amelyet az ügyfélelőlegek közzétételekor használni szeretne.
4. Zárja be a lapot.

## <a name="create-customer-prepayment-vouchers"></a>Vevői előlegbizonylatok létrehozása

Amikor létrehozza az ügyfél fizetési naplót, minden előleghez be kell állítania az **Előlegnapló-bizonylat** lehetőséget **Igen** értékre a **Vevő kifizetési naplója** oldalon. Vevői előleg létrehozásához tegye a következőket.

1. Válassza a **Kinnlevőségek \> Kifizetések \> Kifizetési napló** lehetőséget.
2. Válassza az **Új** lehetőséget egy napló létrehozásához.
3. A **Név** mezőben válassza ki a használandó napló nevét.

    > [!IMPORTANT]
    > Ha az előző eljárásban az **Áfa az előlegnapló-bizonylaton** lehetőséget **Igen** értékre állította be, akkor ki kell választania egy naplónevet, ahol az **Összeg tartalmazza az áfát** paraméter ki van választva. 

4. Opcionális: A **Leírás** mezőbe írja be a részletes leírást.
5. **Sorok** kiválasztása.
6. Ha üres sor nem létezik, válassza az **Új** lehetőséget egy sor létrehozásához.
7. A **Dátum** mezőben adja meg azt a dátumot, amikor az előleget könyvelni kell.
8. A **Számla** mezőben válassza ki a vevőt az előleghez.
9. Opcionális: A **Leírás** mezőbe írja be a tranzakció részletes leírását.
10. A **Jóváírás** mezőbe írja be az előleg összegét.
11. Az **Ellenszámla** mezőben válassza ki a fizetés ellenszámláját. Válassza például azt a bankot vagy főszámlát, a amelyre a fizetést könyvelni szeretné.
12. A **Fizetési mód** mezőben válassza ki az ügyfél fizetési módját.
13. A **Fizetés** lapon állítsa be az **Előlegnapló bizonylat** opciót **Igen** értékre.
14. Ismételje meg a 7-13. lépést minden további előleghez, amelyet könyvelni szeretne.
15. Válassza a **Közzététel** lehetőséget a napló véglegesítéséhez.

## <a name="settle-prepayments-with-invoices"></a>Előlegek kiegyenlítés számlákkal

Az **Vevői kifizetések** munkaterületén egyszerűen megtalálhatja és kiegyenlítheti a még nem teljesen kiegyenlített kifizetéseket.

1. A **Kezdőlap** irányítópulton válassza ki a **Vevői kifizetések** csempét.
2. A **Vevői tranzakciók** részben, a **Nem kiegyenlített kifizetések** lapon keresse meg és válassza ki a kiegyenlítendő kifizetést.
3. Válassza a **Tranzakcióinak kiegyenlítése** lehetőséget.
4. Jelölje be a kiegyenlített számlához a **Jelölés** jelölőnégyzetet.
5. Válassza a **Feladás** parancsot.

A nyitott tranzakciók kiegyenlítéséről további információt a [Kiegyenlítés áttekintése](/dynamics365/finance/cash-bank-management/settlement-overview) részben talál.
