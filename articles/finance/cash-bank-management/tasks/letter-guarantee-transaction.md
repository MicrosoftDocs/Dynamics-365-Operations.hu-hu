---
title: Garancialevél-tranzakció
description: Ez az eljárás végigvezeti a Garancialevélhez kapcsolódó folyamaton.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 30e21c11b067f6def127f3eab026d7255ab1ca29
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779934"
---
# <a name="letter-of-guarantee-transaction"></a>Garancialevél-tranzakció

[!include [banner](../../includes/banner.md)]

Ez az eljárás végigvezeti a Garancialevélhez kapcsolódó folyamaton.



A következő feladatoknak kell készen lenniük az eljárás végrehajtása előtt:

- A garancialevélre vonatkozóan állítsa be a banki hiteleket és a feladási profilokat.

- Hozzon létre egy banki hitelmegállapodást a garancialevélhez.



Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-sales-order-with-letter-of-guarantee"></a>Értékesítési rendelés létrehozása garancialevéllel
1. Menjen a Kinnlevőségek **> az > rendeléshez**.
2. Kattintson az **Új** elemre.
3. A **Vevőszámla** mezőben adjon meg vagy válasszon ki egy értéket.
4. Bontsa ki az Általános szakaszt.
5. A **Hely** mezőben adjon meg vagy válasszon ki egy értéket.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. A **Raktár** mezőben adjon meg vagy válasszon ki egy értéket.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. A Banki **bizonylat típusa mezőben** válassza ki a **garancialevelet**.
10. Kattintson az **OK** gombra.
11. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.
12. Adjon meg egy számot az **Egységár** mezőben.
13. Bontsa ki a Soradatok szakaszt.
14. Kattintson a Kiszállítás lapra.
    * Megjegyzés: A Szállítási dátum ellenőrzése lehetőségnél a „Nincs” lehetőséget válassza  
15. Adjon meg **egy** dátumot a Kért szállítási dátum mezőben.
16. A Visszaigazolt **szállítási dátum mezőbe** írjon be egy dátumot.

## <a name="process-letter-of-guarantee_request"></a>Garancialevél-kérelem feldolgozása
1. A munkaablakban kattintson a Kezelés **gombra**.
2. Kattintson **a Garancialevél gombra**.
3. Kattintson a műveletpanelen a **garancialevélre**.
4. Kattintson a **Kérelem** gombra a legördülő párbeszédpanel megnyitásához.
5. A Típus **mezőben** adjon meg vagy válasszon ki egy értéket.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. Adjon meg egy számot az **Érték** mezőben.
8. A Lejárati **dátum mezőbe** írja be a dátumot és az időpontot.
9. Kattintson az **OK** gombra.
10. Zárja be a lapot.

## <a name="process-letter-of-guarantee_submit-to-bank"></a>Garancialevél feldolgozása Elküldés a banknak
1. Menjen a Készpénz- **és bankkezelés > garancialevelek > garancialevelekért.**
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. Kattintson a **Küldés a bankba** gombra a drop párbeszédpanel megnyitásához.
4. A **Bankszámlák** mezőben adjon meg vagy válasszon ki egy értéket.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Kattintson az **OK** gombra.

## <a name="process-letter-of-guarantee_receive-from-bank"></a>Garancialevél feldolgozása Fogadás a banktól
1. Kattintson a **Fogadás a banktól** gombra a drop párbeszédpanel megnyitásához.
2. **A Bank száma mezőbe** írjon be egy értéket.
    * Ellenőrizze az értékeket a kiszámított Árrés **és** **Költség mezőben**.  
3. Kattintson az **OK** gombra.
4. Bontsa ki a Műveletek szakaszt.
    * Ellenőrizze a „Fogadás a banktól” bejegyzést.  
5. Kattintson ide a Napló kötegszám **mezőjében található hivatkozáshoz**.
6. Kattintson a **Sorok** pontra.
    * Ellenőrizze a naplóbejegyzések feladását.  
7. Zárja be a lapot.

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a>Garancialevél feldolgozása Átadás a kedvezményezettnek
1. Menjen a Kinnlevőségek **> az > rendeléshez**.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.
3. A munkaablakban kattintson a Kezelés **gombra**.
4. Kattintson **a Garancialevél gombra**.
5. Kattintson a műveletpanelen a **garancialevélre**.
6. Kattintson **a Kedvezményezettnek gombra a** legördülő párbeszédpanel megnyitásához.
7. Kattintson az **OK** gombra.
8. Menjen a Készpénz- **és bankkezelés > garancialevelek > garancialevelekért.**
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
10. Kattintson **a Kedvezményezettnek gombra a** legördülő párbeszédpanel megnyitásához.
11. Kattintson az **OK** gombra.
12. Bontsa ki a Műveletek szakaszt.
    * Érvényesítse a „Kedvezményezettnek való átadás” bejegyzést.  

## <a name="process-letter-of-guarantee_increase-value"></a>Garancialevél feldolgozása Értéknövelés
1. Menjen a Kinnlevőségek **> az > rendeléshez**.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.
3. A munkaablakban kattintson a Kezelés **gombra**.
4. Kattintson **a Garancialevél gombra**.
5. Kattintson a műveletpanelen a **garancialevélre**.
6. Kattintson az Érték **növelése gombra** a legördülő párbeszédpanel megnyitásához.
7. Adjon meg **egy számot** az Érték hozzáadása mezőben.
8. Kattintson az **OK** gombra.
9. Menjen a Készpénz- **és bankkezelés > garancialevelek > garancialevelekért.**
10. Keresse meg és jelölje ki a kívánt rekordot a listán.
11. Kattintson az Érték **növelése gombra** a legördülő párbeszédpanel megnyitásához.
12. Kattintson az **OK** gombra.
13. Bontsa ki a Műveletek szakaszt.
    * Ellenőrizze az „Érték növelése” bejegyzést.  
14. Keresse meg és jelölje ki a kívánt rekordot a listán.
15. Kattintson ide a Napló kötegszám **mezőjében található hivatkozáshoz**.
16. Kattintson a **Sorok** pontra.
    * Érvényesítse a feladott naplóbejegyzéseket.  

## <a name="process-letter-of-guarantee_liquidate"></a>Garancialevél feldolgozása Likvidálás
1. Menjen a Kinnlevőségek **> az > rendeléshez**.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.
3. A munkaablakban kattintson a Kezelés **gombra**.
4. Kattintson **a Garancialevél gombra**.
5. Kattintson a műveletpanelen a **garancialevélre**.
6. Kattintson **a Felszámolás** gombra a legördülő párbeszédpanel megnyitásához.
7. Kattintson az **OK** gombra.
8. Menjen a Készpénz- **és bankkezelés > garancialevelek > garancialevelekért.**
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
10. Kattintson **a Felszámolás** gombra a legördülő párbeszédpanel megnyitásához.
11. Kattintson az **OK** gombra.
12. Bontsa ki a Műveletek szakaszt.
    * Érvényesítse a „Likvidálás” bejegyzéseket.  
13. Keresse meg és jelölje ki a kívánt rekordot a listán.
14. Kattintson ide a Napló kötegszám **mezőjében található hivatkozáshoz**.
15. Kattintson a **Sorok** pontra.
    * Érvényesítse a feladott naplóbejegyzéseket.  
16. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
