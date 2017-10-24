--- 
title: "A szállítmányozók beállítása"
description: "Ez az eljárás bemutatja, hogyan lehet beállítani a szállítmányozót, és meghatározni a részleteket, mint például a szolgáltatás, a szállítási mód, a szállítási ajánlat, a szállítási megszorítások és a szállítási díj."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e27be049bebd63c9266029b8981874417a9f0a8c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-shipping-carriers"></a>A szállítmányozók beállítása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet beállítani a szállítmányozót, és meghatározni a részleteket, mint például a szolgáltatás, a szállítási mód, a szállítási ajánlat, a szállítási megszorítások és a szállítási díj. A szállítási koordinátor ezután hozzárendelheti a szállítmányozót egy bejövő vagy kimenő rakományhoz.


## <a name="create-a-new-shipping-carrier"></a>Új szállítmányozó létrehozása
1. Ugorjon a Szállításkezelés > Beállítás > Szállítmányozók > Szállítmányozók lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Szállítmányozók mezőbe.
4. Írjon be egy értéket a Név mezőbe.
5. A Mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>A szállítmányozóra vonatkozó általános információk kitöltése
1. Bontsa ki az Áttekintés részt.
2. Jelölje be a Szállítmányozó aktiválása jelölőnégyzetet, vagy törölje a kijelölést.
3. A Szállító mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Válassza ki a szállítmányozóhoz hozzárendelendő szállítókódot.  
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. A Szállítási ajánlat típusa mezőben válasszon ki egy lehetőséget.
    * Válassza ki a Kézi lehetőséget a Szállítási ajánlat oldal használatához, vagy válassza ki az EDI lehetőséget az ajánlat frissítéséhez az Electronic Data Interchange (EDI) szolgáltatással.  
7. Jelölje be a Szállítmányozóminősítés engedélyezése jelölőnégyzetet, vagy törölje a kijelölést.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>A szállítmányozó számára szükséges szolgáltatások létrehozása
1. Bontsa ki a Szolgáltatások részt.
2. Kattintson az Új lehetőségre.
3. A listában jelölje meg a kiválasztott sort.
4. Írjon be egy értéket a Szállítmányozói szolgáltatás mezőbe.
5. Írjon be egy értéket a Név mezőbe.
6. A Szállítási mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. Keresse meg és jelölje ki a kívánt rekordot a listán.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="set-up-the-address-for-the-carrier-optional"></a>A szállítmányozó címének beállítása (opcionális)
1. A Címek szakasz bővítésének átváltása.
2. Kattintson az Új lehetőségre.
3. A „Név vagy leírás” mezőbe írjon be egy értéket.
4. Az Ország/régió mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Az Irányítószámok záró értéke mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. A kívánt rekord megkeresése és kijelölése a listán
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Érték beírása az Utcanév mezőbe
10. Kattintson az OK gombra.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>A szállítmányozó díjazási profil beállítása.
1. Bontsa ki a Díjazási profilok részt.
2. Kattintson az Új lehetőségre.
3. A listában jelölje meg a kiválasztott sort.
4. Írjon egy értéket a Díjazási profil mezőbe.
5. Írjon be egy értéket a Név mezőbe.
6. A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. A kívánt rekord megkeresése és kijelölése a listán
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
10. A kívánt rekord megkeresése és kijelölése a listán
11. A listában kattintson a kijelölt sorban lévő hivatkozásra.
12. A Díjkalkulátor mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Válassza ki a szállítmányozóval kötött szerződésnek megfelelő díjkalkulátort.  
13. Keresse meg és jelölje ki a kívánt rekordot a listán.
14. A listában kattintson a kijelölt sorban lévő hivatkozásra.
15. A Díjjegyzék mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
16. A kívánt rekord megkeresése és kijelölése a listán
17. A listában kattintson a kijelölt sorban lévő hivatkozásra.
18. A Szállításiidő-kalkulátor mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
19. A listában kattintson a kijelölt sorban lévő hivatkozásra.
20. Kattintson a Mentés gombra.


