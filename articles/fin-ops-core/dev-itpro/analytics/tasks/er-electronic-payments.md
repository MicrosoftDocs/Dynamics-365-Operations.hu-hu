---
title: ER – Hozzon létre elektronikus dokumentumokat a kifizetésekre vonatkozóan a formátumkonfiguráció segítségével
description: Ez a témakör azt ismerteti, hogyan lehet új elektronikus jelentési formátumkonfigurációt használni a kifizetések feldolgozásához használt elektronikus dokumentumok előállításához.
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
ms.openlocfilehash: b70b246e3618e8f083e5f6757ee8a97d8072a635
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290874"
---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a>ER – Hozzon létre elektronikus dokumentumokat a kifizetésekre vonatkozóan a formátumkonfiguráció segítségével

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként használhat egy új Elektronikus jelentés (ER) konfigurációt, az elektronikus fizetési dokumentum létrehozásához a kifizetések feldolgozására vonatkozóan. Ezeket a lépéseket a GBSI minta vállalatban hajthatja végre.

Ahhoz, hogy végrehajthassa ezeket a lépéseket, hajtsa végre a „Konfiguráció létrehozása a kifizetési dokumentum formátumával” eljárás lépéseit.


## <a name="change-the-configuration-of-the-electronic-payment-method"></a>Módosítsa az elektronikus fizetési mód konfigurációját
1. Ugorjon a Kötelezettségek > Kifizetés beállítása > Fizetési módok pontra.
2. Váltsa át a Fájlformátum szakaszt a kibontáshoz, ha szükséges.
3. Rekordok kereséséhez használja a gyorsszűrőt. Például végezzen szűrést az „Elektronikus” érték beírásával a Fizetési mód mezőben.
4. Kattintson a Szerkesztés lehetőségre.
5. Állítsa át az Általános elektronikus jelentéskészítés mezőt Igen értékre.
    * Válassza ki az Igen értéket az általános elektronikus jelentési minta használatba vételéhez a Kifizetési fájlok létrehozásához.  
6. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. Válassza ki a BACS (UK fiktív) formátumkonfigurációt.
8. Kattintson a Mentés gombra.
9. Zárja be a lapot.

## <a name="test-the-format-of-generated-payment-files"></a>Tesztelje a létrehozott fizetési fájlok formátumát
1. Ugorjon a Kötelezettségek > Fizetési beállítás > Fizetési napló pontra.
2. Kattintson az Új lehetőségre.
3. A listában jelölje meg a kiválasztott sort.
4. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Válassza ki a VendPay lehetőséget.  
6. Kattintson a Mentés gombra.
7. Kattintson a Sorok pontra.
8. A Vállalat mezőben írja be az „DEMF” értéket.
    * DEMF  
9. A Számla mezőben állítsa az értékeket „DE-01001”-re.
    * DE - 01001  
10. Írja be a „Fizetés” szöveget a Leírás mezőbe.
    * Fizetés  
11. Adjon meg egy számot a Tartozik mezőben.
    * 1000  
12. Kattintson a Fizetések fülre.
13. A Fizetési mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
14. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki az Elektronikus érték lehetőséget.  
15. A listában kattintson a kijelölt sorban lévő hivatkozásra.
16. Kattintson a Mentés gombra.
17. Kattintson a Kifizetések létrehozása elemre.
18. A Fizetési mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
19. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki az Elektronikus érték lehetőséget.  
20. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Válassza ki az Elektronikus érték lehetőséget.  
21. Írjon be egy értéket a Fájlnév mezőbe.
    * Például írja be a „Kifizetések” szöveget.  
22. A Bankszámla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
23. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Válassza ki a GBSI MŰV. értéket.  
24. Kattintson az OK gombra.
25. Kattintson az OK gombra.
    * Elemezze a létrehozott kifizetési fájlt az XML-formátumban. Hasonlítsa össze a tervezett dokumentumelrendezéssel és a meghatározott fizetési tranzakció attribútumokkal.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
