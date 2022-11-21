---
title: Akkreditív exportálása
description: Ez az eljárás bemutatja az Akkreditív exportálása folyamatot.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, DefaultDashboard, SalesTableListPage, SalesCreateOrder, SalesTable, BankLCExport, SalesEditLines,  LedgerJournalTable, LedgerJournalTransCustPaym, CustOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cf06a73bf7665059658c7884a0b9f973929d647c
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779554"
---
# <a name="export-letter-of-credit"></a>Akkreditív exportálása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja az Akkreditív exportálása folyamatot.

Az akkreditív egy bank által kiállított megállapodás, amelyben a bank vállalja a kifizetés teljesítését a vevő részéről, amennyiben a vevő és eladó közti megállapodás feltételei fennállnak.



A Banki **létesítmények és feladási** **profilok beállítása eljárás, valamint az Credit_Create a** banki hitelmegállapodási eljárást megelőzően futó művelet futtatása. Az eljárás sikeres futtatásához ki kell választani a USMF bemutatócéget.


## <a name="create-sales-order-for-export-letter-of-credit"></a>Értékesítési rendelés létrehozása Exportakkreditívhez
1. Menjen a Kinnlevőségek **> az > rendeléshez**.
2. Kattintson az **Új** elemre.
3. A **Vevői számla** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A kívánt rekord megkeresése és kijelölése a listán
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Az Általános szakasz kibontása **vagy összecsukása**.
7. A **Telephely** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A kiadni **kívánt** cikk raktárának telephelye.  
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. A **Raktár** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A kiadni **kívánt** cikk raktárának kiválasztása.  
10. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Megjegyzés: A Banki **bizonylat típusa mezőt** az akkreditekkel **kell kiválasztani**.  
11. A Banki **bizonylat típusa mezőben** válassza ki az **akkreditlevelet**.
12. A Szállítás szakasz kibontása **vagy összecsukása**.
    * Válassza a Nincs **szállításidátum-ellenőrzés** = **lehetőséget**.  
13. Adjon meg **egy dátumot a** Kért kézhezvételi dátum mezőben.
14. Kattintson az **OK** gombra.
15. A **Cikkszám** mezőben kattintson a legördülő gombra a keresés megnyitásához.
    * Válassza ki a Kiadásra/Eladásra szánt cikket.  
16. Keresse meg és jelölje ki a kívánt rekordot a listán.
17. A listában kattintson a kijelölt sorban lévő hivatkozásra.
18. Adjon meg egy számot az **Egységár** mezőben.
19. Bontsa ki vagy csukja össze a **Soradatok** szakaszt.
20. Kattintson a Szállítás **fülre**.
21. Adjon meg **egy** dátumot a Kért szállítási dátum mezőben.
22. A Visszaigazolt **szállítási dátum mezőbe** írjon be egy dátumot.
23. A munkaablakban kattintson a Kezelés **gombra**.
24. Kattintson az **akkreditűre**.
25. A Banki **bizonylat száma mezőbe** írjon be egy értéket.
26. A Lejárati **dátum mezőbe** írja be a dátumot és az időpontot.
27. A Bank részletei szakasz kibontása **vagy összecsukása**.
28. A Kibocsátó **bank mezőben** kattintson a legördülő gombra a keresés megnyitásához.
29. A listában kattintson a kijelölt sorban lévő hivatkozásra.
30. Az Advising **bank mezőben** kattintson a legördülő gombra a keresés megnyitásához.
31. A kívánt rekord megkeresése és kijelölése a listán
32. A listában kattintson a kijelölt sorban lévő hivatkozásra.
33. Kattintson az **értékesítési rendelés szállítmányának beolvasása elemre**.
34. Kattintson a Banki **bizonylat kiállítása gombra**.
35. Zárja be a lapot.

## <a name="post-packing-slip"></a>Szállítólevél feladása
1. A műveleti ablaktáblán kattintson a **Választás** elemre, majd válassza ki a csomag elemet.
2. Kattintson a Szállítólevél **feladja parancsra**.
3. Bontsa ki vagy csukja össze a **Paraméterek** szakaszt.
4. A **Mennyiség** mezőben válassza a **Mind** lehetőséget.
5. A Beállítás szakasz kibontása **vagy összecsukása**.
6. Adjon meg **egy dátumot** a Csomagjegyzék dátuma mezőben.
7. Válassza ki a Szállítmányszámot.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Kattintson az **OK** gombra.
10. Kattintson az **OK** gombra.

## <a name="post-sales-invoice"></a>Értékesítési számla feladása
1. A Műveleti ablaktáblán kattintson a **Számla** elemre.
2. Kattintson a **Számla** pontra.
3. Az Áttekintés szakasz kibontása **vagy összecsukása**.
4. Válassza ki **a szállítmány számát**.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. A Beállítás szakasz kibontása **vagy összecsukása**.
7. Adjon meg egy dátumot a **Számla dátuma** mezőben.
8. Kattintson az **OK** gombra.
9. Kattintson az **OK** gombra.

## <a name="shipment-document-submitted-status"></a>Szállítási dokumentum benyújtott állapota
1. A munkaablakban kattintson a Kezelés **gombra**.
2. Kattintson az **akkreditűre**.
3. A Sorok szakasz kibontása **vagy összecsukása**.
    * Megjegyzés: Az **Elküldött dokumentum mezőt** Igen gombra kell **állítani**.  

## <a name="verify-export-letter-of-credit"></a>Exportakkreditív ellenőrzése
1. Menjen a Készpénz- **és bankkezelés > akkredit > és importbeszedvét exportálása esetén**.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Győződjön meg róla, hogy **az exportakkreditó** Szállítmány **állapota** **Számlázva**.  

## <a name="customer-payment"></a>Vevői kifizetés
1. Ugrás a Kinnlevőségek **> és > naplóhoz**.
2. Kattintson az **Új** elemre.
3. A listában jelölje meg a kiválasztott sort.
4. A **Név** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Kattintson a **Sorok** pontra.
7. Adja meg a dátumot a **Dátum** mezőben.
8. A **Számla** mezőben adja meg a kívánt értékeket.
9. Kattintson a Kiegyenlítés **gombra**.
10. Jelölje be az Összegek fejlécén lévő jelölőnégyzetet.
    * Megjegyzés: Állítsa a **Mező** megjelenítése mezőt **akkreditűre**.  
11. Keresse meg és jelölje ki a kívánt rekordot a listán.
12. Jelölje be a Jelölés jelölőnégyzetet, **vagy törölje** a jelet a jelölőnégyzetből.
13. Kattintson az **OK** gombra.
14. Kattintson a Kifizetés **fülre**.
    * A banki bizonylat számának és a szállítmányszám részleteinek ellenőrzése  
15. Kattintson a **Bejegyzés** lehetőségre.

## <a name="verify-export-letter-of-credit-after-payment"></a>Exportakkreditív ellenőrzése kifizetés után
1. Menjen a Készpénz- **és bankkezelés > akkredit > és importbeszedvét exportálása esetén**.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Győződjön meg róla, hogy **a Kifizetés állapota Beérkezett** = **·** **, az Egyenleg** = **összege pedig 0,00.**  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
