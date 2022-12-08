---
title: Akkreditív importálása
description: Ez az eljárás bemutatja egy akkreditív importálásának folyamatát.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, BankLCImport,  PurchEditLines, VendEditInvoice, SrsReportViewerForm, LedgerJournalTable, LedgerJournalTransVendPaym, VendOpenTrans, SysQueryForm, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 95a79b3c391c15099aee0a8d34419e1cf48fafbc
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2022
ms.locfileid: "9803991"
---
# <a name="import-letter-of-credit"></a>Akkreditív importálása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja egy akkreditív importálásának folyamatát. Az eljárás végrehajtása előtt be kell állítani a következőket: banki hitelek, feladási profilok, egy banki hitelmegállapodás és szállító banki adatai.

Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-a-purchase-order-with-letter-of-credit"></a>Beszerzési rendelés létrehozása akkreditívvel
1. Menjen a Kötelezettségek **> beszerzési > valamennyi beszerzési rendeléshez**.
2. Kattintson az **Új** elemre.
3. A **Szállítószámla** mezőben adjon meg vagy válasszon ki egy értéket.
4. A kívánt rekord megkeresése és kijelölése a listán
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Bontsa ki az **Általános** szakaszt.
7. A **Hely** mezőben adjon meg vagy válasszon ki egy értéket.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. A **Raktár** mezőben adjon meg vagy válasszon ki egy értéket.
10. A listában kattintson a kijelölt sorban lévő hivatkozásra.
11. Adja meg a dátumot a **Könyvelés dátuma** mezőben.
12. Adjon meg egy dátumot a **Kiszállítási dátum** mezőben.

>[!Note] 
>A **Banki bizonylat típusa mezőnek** akkreditűnek **kell lennie**.  

13. Kattintson az **OK** gombra.
14. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.
15. Keresse meg és jelölje ki a kívánt rekordot a listán.
16. A listában kattintson a kijelölt sorban lévő hivatkozásra.
17. Bontsa ki a **Sorrészletek** szakaszt.
18. Kattintson a Szállítás **fülre** .
19. Adjon meg egy dátumot a **Kiszállítási dátum** mezőben.
20. Adjon meg egy dátumot a **Visszaigazolt szállítási dátum** mezőben.
21. Adjon meg egy számot az **Egységár** mezőben.
    * Adja meg az Akkreditív adatait.  
22. A munkaablakban kattintson a Kezelés **gombra**.
23. Kattintson az akkreditó **vagy importbeszedve gombra**.
24. Az Alkalmazás **dátuma mezőben** adja meg a dátumot és az időpontot.
    * Ellenőrizze, hogy **a Bankszámla** mezőben az alapértelmezett aktív bankszámla van-e, amely az alkalmazás dátumán alapul.  
25. A Banki **bizonylat száma mezőbe** írjon be egy értéket.
26. A Kézhezvétel **dátuma mezőbe** írja be a dátumot és az időpontot.
27. Bontsa ki **a Banki bizonylat szakaszt** .
28. A Lejárati **dátum mezőbe** írja be a dátumot és az időpontot.
29. Bontsa ki **a Bank részletei szakaszt** .
30. Az Advising **bank mezőben** adjon meg vagy válasszon ki egy értéket.
31. A listában kattintson a kijelölt sorban lévő hivatkozásra.
32. Kattintson a **Mentés** gombra.
33. Kattintson a **Beszerzési rendelés szállítmányok beolvasása elemre**.
34. Zárja be a lapot.
35. A Művelet panelen kattintson a **Beszerzés** elemre.
36. Kattintson a **Megerősítés** gombra.
37. A munkaablakban kattintson a Kezelés **gombra**.
38. Kattintson az akkreditó **vagy importbeszedve gombra**.
39. Kattintson a **Folyamat** gombra.
40. Kattintson a **Megerősítés** gombra.
    * Győződjön meg róla, hogy a Hitel egyenlege levonja a beszerzési rendelés összegét. Ebben a példában a Beszerzési összeg = 500,00, a Hitelmegállapodás határértéke = 10000,00, tehát a Hitel egyenlege = 9500,00.  
41. Zárja be a lapot.
42. Adjon meg egy számot az **Egységár** mezőben.
43. Kattintson a **Mentés** gombra.
44. A Művelet panelen kattintson a **Beszerzés** elemre.
45. Kattintson a **Megerősítés** gombra.
    * Az akkreditó módosítása az egységár változásának következtében.  
46. A munkaablakban kattintson a Kezelés **gombra**.
47. Kattintson az akkreditó **vagy importbeszedve gombra**.
    * Az Akkreditív módosítása Beszerzési árban bekövetkező változás miatt.  
48. Kattintson a **Folyamat** gombra.
49. Kattintson a Módosítás **gombra**.
50. Kattintson az Eltávolítás **gombra**.
51. Kattintson az **Igen** gombra.
52. Kattintson a **Beszerzési rendelés szállítmányok beolvasása elemre**.
53. Kattintson a **Folyamat** gombra.
54. Kattintson a **Megerősítés** gombra.
    * Győződjön meg róla, hogy a Hitel egyenlege levonja a beszerzési rendelés összegét. Ebben a példában a szerkesztett Beszerzési összeg = 600,00, a Hitelmegállapodás határértéke = 10000,00, tehát a Hitel egyenlege = 9400,00.  
55. Zárja be a lapot.

## <a name="post-packing-slip"></a>Szállítólevél feladása
1. A Művelet panelen kattintson a **Fogadás** elemre.
2. Kattintson a **Termékbevételezés** lehetőségre.
3. A PurchParmTable_Num **mezőbe** írjon be egy értéket.
    * Az akkreditóra **hivatkozva** létrehozott szállítmányszám kiválasztása.  
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Adjon meg **egy** dátumot a Termékbevételezés dátuma mezőben.
6. Kattintson az **OK** gombra.
7. Zárja be a lapot.
8. Zárja be a lapot.

## <a name="verify-import-letter-of-credit-status"></a>Ellenőrizze az Importakkreditív állapotát.
1. Menjen a Készpénz- **és bankkezelés > akkredit > importakkreditó és importbeszedvés importálása gombra.**
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Ellenőrizze az **Importakkreditó állapotát**.     
4. Zárja be a lapot.
5. Zárja be a lapot.

## <a name="post-purchase-invoice"></a>Beszerzési számla feladása
1. Menjen a Kötelezettségek **> beszerzési > valamennyi beszerzési rendeléshez**.
    * Válassza ki az akkreditívvel létrehozott beszerzési rendelést.  
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. A Műveleti ablaktáblán kattintson a **Számla** elemre.
5. Kattintson a **Számla** pontra.
6. Adjon meg egy értéket a **Szám** mezőben.
7. A Szállítmány **száma mezőben** adjon meg vagy válasszon ki egy értéket.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Adjon meg egy dátumot a **Számla dátuma** mezőben.
10. Kattintson az **Egyeztetési állapot frissítése** lehetőségre.
11. Kattintson a **Bejegyzés** lehetőségre.
12. Zárja be a lapot.
13. Zárja be a lapot.

## <a name="verify-import-letter-of-credit-status-and-printing"></a>Ellenőrizze az Importakkreditív állapotát és a nyomtatást

1. Menjen a Készpénz- **és bankkezelés > akkredit > importakkreditó és importbeszedvés importálása gombra.**
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Ellenőrizze az Importakkreditív2 állapotát.  
    * Ellenőrzés:  **Számlázott banki hitel részleteinek** = **szállítási**  állapota  
4. Kattintson a Nézet **gombra**.
5. Kattintson a Pályázat **nyomtatása gombra**.
6. Kattintson az **OK** gombra.
    * Győződjön meg róla, hogy az Akkreditívigénylés nyomtatása megtörténik.  
7. Zárja be a lapot.
8. Zárja be a lapot.
9. Zárja be a lapot.

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a>Az akreditívvel létrehozott beszerzési számlára vonatkozó Szállító kifizetési napló feladása
1. Ugorjon a **Kötelezettségek > Fizetési beállítás > Fizetési napló** pontra.
2. Kattintson az **Új** elemre.
3. A **Név** mezőben adjon meg vagy válasszon ki egy értéket.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Kattintson a **Sorok** pontra.
6. Adja meg a dátumot a **Dátum** mezőben.
7. A **Számla** mezőben adja meg a kívánt értékeket.
8. Kattintson a Tranzakciók **egyenlítésére**.
9. Bontsa ki **az Összegek szakaszt** .
10. Válasszon egy **beállítást a Show** mezőben.
    * Ellenőrizze, hogy **módosult-e a Banki bizonylat száma**  **és a** Szállítmányszám mező.  
11. Jelölje be a **Megjelölés** jelölőnégyzetet.
12. Kattintson az **OK** gombra.
13. Kattintson a Fizetések fülre.
    * Ellenőrizze, hogy **módosult-e a Banki bizonylat száma**  **és a** Szállítmányszám mező.  
14. Kattintson a **Bejegyzés** lehetőségre.
15. Zárja be a lapot.
16. Zárja be a lapot.

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a>Az Importakkreditív állapotának ellenőrzése a Számla kifizetése után
1. Menjen a Készpénz- **és bankkezelés > akkredit > importakkreditó és importbeszedvés importálása gombra.**
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Ellenőrizze az **Importakkreditó állapotát**.   
4. Zárja be a lapot.

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a>Banki hitelmegállapodás korlát és a terheléskihasználtsági jelentés ellenőrzése
1. Menjen a Készpénz- **és bankkezelés > lekérdezések és jelentések > akkre vonatkozó garancialevelekről > bank hitelekről és kihasználtságról szóló jelentésében**.
2. Bontsa ki a **Szerepeltetni kívánt rekordok** szakaszt.
3. Kattintson a **Szűrő** parancsra.
    * Definiálja **a Feltétel** mezőt a szükséges bankszámlával.  
4. A **Feltétel** mezőben adjon meg vagy válasszon ki egy értéket.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Kattintson az **OK** gombra.
7. Kattintson az **OK** gombra.
    * Ellenőrizze a tranzakciókat felsoroló jelentést.  
    * Győződjön meg róla, hogy a jelentés felsorolja a tranzakciókat a Banki okmány számával, a Hitelmegállapodás határértékével, a felhasznált összeggel és a hitel egyenlegének összegével együtt.  
8. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
