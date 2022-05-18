---
title: Garancialevél-tranzakció
description: Ez az eljárás végigvezeti a Garancialevélhez kapcsolódó folyamaton.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e025f0d0a89eb6c6ab024236400a7c65b108e6d5
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/06/2022
ms.locfileid: "8722746"
---
# <a name="letter-of-guarantee-transaction"></a>Garancialevél-tranzakció

[!include [banner](../../includes/banner.md)]

Ez az eljárás végigvezeti a Garancialevélhez kapcsolódó folyamaton.



A következő feladatoknak kell készen lenniük az eljárás végrehajtása előtt:

- A garancialevélre vonatkozóan állítsa be a banki hiteleket és a feladási profilokat.

- Hozzon létre egy banki hitelmegállapodást a garancialevélhez.



Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-sales-order-with-letter-of-guarantee"></a>Értékesítési rendelés létrehozása garancialevéllel
1. Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.
2. Kattintson az Új lehetőségre.
3. A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.
4. Bontsa ki az Általános szakaszt.
5. A Hely mezőben adjon meg vagy válasszon ki egy értéket.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. A Raktár mezőben adjon meg vagy válasszon ki egy értéket.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. A Banki bizonylat típusa mezőben válassza ki a „Garancialevél” lehetőséget.
10. Kattintson az OK gombra.
11. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
12. Adjon meg egy számot az Egységár mezőben.
13. Bontsa ki a Soradatok szakaszt.
14. Kattintson a Kiszállítás lapra.
    * Megjegyzés: A Szállítási dátum ellenőrzése lehetőségnél a „Nincs” lehetőséget válassza  
15. Adjon meg egy dátumot a Kért szállítási dátum mezőben.
16. Adjon meg egy dátumot a Visszaigazolt szállítási dátum mezőben.

## <a name="process-letter-of-guarantee_request"></a>Garancialevél-kérelem feldolgozása
1. A Művelet panelen kattintson a Kezelés elemre.
2. Kattintson a Garancialevél lehetőségre.
3. A Műveleti ablaktáblán kattintson a Garancialevél lehetőségre.
4. A Kérelem gombra kattintva megnyithatja a legördülő párbeszédablakot.
5. A Típus mezőben adjon meg vagy válasszon ki egy értéket.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. Adjon meg egy számot az Érték mezőben.
8. Az Lejárati dátum mezőben adjon meg egy dátumot és időpontot.
9. Kattintson az OK gombra.
10. Zárja be a lapot.

## <a name="process-letter-of-guarantee_submit-to-bank"></a>Garancialevél feldolgozása Elküldés a banknak
1. Ugrás a Készpénz- és bankkezelés > Garancialevelek > Garancialevelek lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. Kattintson a Feladás a bankhoz gombra a legördülő párbeszédablak megnyitásához.
4. A Bankszámlák mezőben adjon meg vagy válasszon ki egy értéket.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Kattintson az OK gombra.

## <a name="process-letter-of-guarantee_receive-from-bank"></a>Garancialevél feldolgozása Fogadás a banktól
1. A Banktól fogadott gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. A Banki szám mezőben adjon meg egy értéket.
    * Ellenőrizze a Nyereség és a Költség mezőkben szereplő kiszámított értékeket.  
3. Kattintson az OK gombra.
4. Bontsa ki a Műveletek szakaszt.
    * Ellenőrizze a „Fogadás a banktól” bejegyzést.  
5. Kattintson a Naplóköteg száma mezőben található hivatkozásra.
6. Kattintson a Sorok pontra.
    * Ellenőrizze a naplóbejegyzések feladását.  
7. Zárja be a lapot.

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a>Garancialevél feldolgozása Átadás a kedvezményezettnek
1. Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.
3. A Művelet panelen kattintson a Kezelés elemre.
4. Kattintson a Garancialevél lehetőségre.
5. A Műveleti ablaktáblán kattintson a Garancialevél lehetőségre.
6. Kattintson a Kedvezményezettnek átadás gombra a legördülő párbeszédablak megnyitásához.
7. Kattintson az OK gombra.
8. Ugrás a Készpénz- és bankkezelés > Garancialevelek > Garancialevelek lehetőségre.
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
10. Kattintson a Kedvezményezettnek átadás gombra a legördülő párbeszédablak megnyitásához.
11. Kattintson az OK gombra.
12. Bontsa ki a Műveletek szakaszt.
    * Érvényesítse a „Kedvezményezettnek való átadás” bejegyzést.  

## <a name="process-letter-of-guarantee_increase-value"></a>Garancialevél feldolgozása Értéknövelés
1. Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.
3. A Művelet panelen kattintson a Kezelés elemre.
4. Kattintson a Garancialevél lehetőségre.
5. A Műveleti ablaktáblán kattintson a Garancialevél lehetőségre.
6. Az Értéknövelés gombra kattintva megnyithatja a legördülő párbeszédablakot.
7. Adjon meg egy számot az Érték hozzáadása mezőben.
8. Kattintson az OK gombra.
9. Ugrás a Készpénz- és bankkezelés > Garancialevelek > Garancialevelek lehetőségre.
10. Keresse meg és jelölje ki a kívánt rekordot a listán.
11. Az Értéknövelés gombra kattintva megnyithatja a legördülő párbeszédablakot.
12. Kattintson az OK gombra.
13. Bontsa ki a Műveletek szakaszt.
    * Ellenőrizze az „Érték növelése” bejegyzést.  
14. Keresse meg és jelölje ki a kívánt rekordot a listán.
15. Kattintson a Naplóköteg száma mezőben található hivatkozásra.
16. Kattintson a Sorok pontra.
    * Érvényesítse a feladott naplóbejegyzéseket.  

## <a name="process-letter-of-guarantee_liquidate"></a>Garancialevél feldolgozása Likvidálás
1. Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.
3. A Művelet panelen kattintson a Kezelés elemre.
4. Kattintson a Garancialevél lehetőségre.
5. A Műveleti ablaktáblán kattintson a Garancialevél lehetőségre.
6. A Likvidálás gombra kattintva megnyithatja a legördülő párbeszédablakot.
7. Kattintson az OK gombra.
8. Ugrás a Készpénz- és bankkezelés > Garancialevelek > Garancialevelek lehetőségre.
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
10. A Likvidálás gombra kattintva megnyithatja a legördülő párbeszédablakot.
11. Kattintson az OK gombra.
12. Bontsa ki a Műveletek szakaszt.
    * Érvényesítse a „Likvidálás” bejegyzéseket.  
13. Keresse meg és jelölje ki a kívánt rekordot a listán.
14. Kattintson a Naplóköteg száma mezőben található hivatkozásra.
15. Kattintson a Sorok pontra.
    * Érvényesítse a feladott naplóbejegyzéseket.  
16. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
