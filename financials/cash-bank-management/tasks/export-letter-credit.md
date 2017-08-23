--- 
title: "Akkreditív exportálása"
description: "Ez az eljárás bemutatja az Akkreditív exportálása folyamatot."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 55f62b501b545db54d717d8c66d09ec831cb286f
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="export-a-letter-of-credit"></a>Akkreditív exportálása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja az Akkreditív exportálása folyamatot.

Az akkreditív egy bank által kiállított megállapodás, amelyben a bank vállalja a kifizetés teljesítését a vevő részéről, amennyiben a vevő és eladó közti megállapodás feltételei fennállnak.



Ez előtt az eljárás előtt futtassa le a „Bank hitelek beállítása és profilok feladása”, valamint az „Akkreditív_Banki hitelmegállapodás létrehozása” eljárásokat. Az eljárás sikeres futtatásához ki kell választani a USMF bemutatócéget.




## <a name="create-sales-order-for-export-letter-of-credit"></a>Értékesítési rendelés létrehozása Exportakkreditívhez
1. Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.
2. Kattintson az Új lehetőségre.
3. A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A kívánt rekord megkeresése és kijelölése a listán
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Bontsa ki vagy csukja össze az Általános szakaszt.
7. A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Válassza ki azt a Helyet, ahol a kibocsátandó cikk raktározódik.  
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Válassza ki azt a Raktárt, ahol a kibocsátandó cikk raktározódik.  
10. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Megjegyzés: A Banki okmány típusa mezőnél az „Akkreditív” lehetőségnek kell kiválasztva lennie.  
11. A Banki okmány típusa mezőben válassza ki az „Akkreditív” lehetőséget.
12. Bontsa ki vagy csukja össze a Szállítás szakaszt.
    * Válassza ki: Szállítási dátum ellenőrzése = Nincs.  
13. Adjon meg egy dátumot a Kért átvételi dátum mezőben.
14. Kattintson az OK gombra.
15. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Válassza ki a Kiadásra/Eladásra szánt cikket.  
16. Keresse meg és jelölje ki a kívánt rekordot a listán.
17. A listában kattintson a kijelölt sorban lévő hivatkozásra.
18. Adjon meg egy számot az Egységár mezőben.
19. Bontsa ki vagy csukja össze a Soradatok szakaszt.
20. Kattintson a Kiszállítás fülre.
21. Adjon meg egy dátumot a Kért szállítási dátum mezőben.
22. Adjon meg egy dátumot a Visszaigazolt szállítási dátum mezőben.
23. A Művelet panelen kattintson a Kezelés elemre.
24. Kattintson az Akkreditív lehetőségre.
25. A Banki okmány száma mezőben adjon meg egy értéket.
26. Az Lejárati dátum mezőben adjon meg egy dátumot és időpontot.
27. Bontsa ki vagy csukja össze a Bank részletei szakaszt.
28. A Kibocsátó bank mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
29. A listában kattintson a kijelölt sorban lévő hivatkozásra.
30. Az Értesítő bank mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
31. A kívánt rekord megkeresése és kijelölése a listán
32. A listában kattintson a kijelölt sorban lévő hivatkozásra.
33. Kattintson az Értékesítési rendelés szállítmányainak beolvasása lehetőségre.
34. Kattintson a Banki okmány kiadása lehetőségre.
35. Zárja be a lapot.

## <a name="post-packing-slip"></a>Szállítólevél feladása
1. A Művelet panelen kattintson a Kitárolás és csomagolás elemre.
2. Kattintson A szállítólevél feladása lehetőségre.
3. Bontsa ki vagy csukja össze a Paraméterek szakaszt.
4. A Mennyiség mezőben válassza a „Mind” lehetőséget.
5. Bontsa ki vagy csukja össze a Beállítás szakaszt.
6. Adjon meg egy dátumot a Szállítólevél dátuma mezőben.
7. Válassza ki a Szállítmányszámot.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Kattintson az OK gombra.
10. Kattintson az OK gombra.

## <a name="post-sales-invoice"></a>Értékesítési számla feladása
1. A Művelet panelen kattintson a Számla lehetőségre.
2. Kattintson a Számla lehetőségre.
3. Bontsa ki vagy csukja össze az Áttekintés szakaszt.
4. Válassza ki a Szállítmányszámot.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Bontsa ki vagy csukja össze a Beállítás szakaszt.
7. A Számla dátuma mezőben adjon meg egy dátumot.
8. Kattintson az OK gombra.
9. Kattintson az OK gombra.

## <a name="shipment-document-submitted-status"></a>Szállítási dokumentum benyújtott állapota
1. A Művelet panelen kattintson a Kezelés elemre.
2. Kattintson az Akkreditív lehetőségre.
3. Bontsa ki vagy csukja össze a Sorok szakaszt.
    * Megjegyzés: A „Benyújtott dokumentum” mező beállítása „Igen” kell, hogy legyen.  

## <a name="verify-export-letter-of-credit"></a>Exportakkreditív ellenőrzése
1. Ugorjon a Készpénz- és bankkezelés > Akkreditívek > Exportakkreditív és importbeszedvény pontra.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Győződjön meg róla, hogy az Exportakkreditív esetében a Szállítmány állapota „Számlázva”.  

## <a name="customer-payment"></a>Vevői kifizetés
1. Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési napló pontra.
2. Kattintson az Új lehetőségre.
3. A listában jelölje meg a kiválasztott sort.
4. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Kattintson a Sorok pontra.
7. Adja meg a dátumot a Dátum mezőben.
8. A Számla mezőben adja meg a kívánt értékeket.
9. Kattintson a kiegyenlítésre.
10. Jelölje be az Összegek fejlécén lévő jelölőnégyzetet.
    * Megjegyzés: Állítsa a Megtekintés mezőt erre: „Akkreditív”.  
11. Keresse meg és jelölje ki a kívánt rekordot a listán.
12. Jelölje be a Jelölés jelölőnégyzetet, vagy törölje a jelet.
13. Kattintson az OK gombra.
14. Kattintson a Fizetések fülre.
    * Ellenőrizze a Banki okmány száma és a Szállítmányszám beállítások részleteit  
15. Kattintson a Feladás lehetőségre.

## <a name="verify-export-letter-of-credit-after-payment"></a>Exportakkreditív ellenőrzése kifizetés után
1. Ugorjon a Készpénz- és bankkezelés > Akkreditívek > Exportakkreditív és importbeszedvény pontra.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Győződjön meg arról, hogy a Szállítmány állapota = Kifizetés megérkezett és az Egyenleg összege = 0,00.  


