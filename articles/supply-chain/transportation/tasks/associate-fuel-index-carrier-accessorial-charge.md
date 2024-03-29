---
title: Üzemanyag-mutató társítása egy szállítóhoz kiegészítő díjként
description: Ez az útmutató bemutatja, hogyan lehet létrehozni egy kiegészítő szolgáltatás társítást, szállítmányozó kiegészítő szolgáltatási díjat, kiegészítő alapszolgáltatást üzemanyag-pótdíjhoz, és társítani egy szállítmányozó üzemanyag-mutatót egy szállítmányozóhoz.
author: Weijiesa
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d2df77fe94156e2b60b77fa1c995ea10eab048a0
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8670552"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a>Üzemanyag-mutató társítása egy szállítóhoz kiegészítő díjként

[!include [banner](../../includes/banner.md)]

Ez az útmutató bemutatja, hogyan lehet létrehozni egy kiegészítő szolgáltatás társítást, szállítmányozó kiegészítő szolgáltatási díjat, kiegészítő alapszolgáltatást üzemanyag-pótdíjhoz, és társítani egy szállítmányozó üzemanyag-mutatót egy szállítmányozóhoz. Az útmutató futtatása előtt létre kell hoznia egy szállítmányozó üzemanyag-mutatót. A „Szállítmányozói üzemanyag-mutató létrehozása” útmutatót használhatja ehhez. Általában a logisztikai vezető végzi el ezeket a beállítási feladatokat. Az eljárás létrehozásához az USMF bemutatóadatokat használtuk.


## <a name="create-an-accessorial-master"></a>Kiegészítő szolgáltatások alapadatainak létrehozása
1. Lépjen a Szállításkezelés > Beállítás > Minősítés > Kiegészítő alapszolgáltatások pontra.
2. Kattintson az Új lehetőségre.
3. A Kiegészítő alapszolgáltatások mezőbe írjon be egy értéket.
4. Írjon be egy értéket a Név mezőbe.
5. Kattintson a Mentés gombra.

## <a name="create-a-carrier-accessorial-charge"></a>Szállítmányozó kiegészítő költség létrehozása
1. Lépjen a Szállításkezelés > Beállítás > Minősítés > Szállítmányozó kiegészítő szolgáltatásának díjai pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Szállítmányozó kiegészítő szolgáltatása azonosító mezőbe.
4. A Szállítmányozó mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Ebben a példában válassza a teherautós szállítmányozót.  
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. A Szállítmányozói szolgáltatás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. A Kiegészítő alapszolgáltatás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
10. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Ebben a példában válassza ki az újonnan létrehozott Kiegészítő alapszolgáltatást.  
11. Kattintson a Mentés gombra.

## <a name="create-an-accessorial-assignment"></a>Kiegészítő szolgáltatási megbízás létrehozása
1. Kattintson a Kiegészítő szolgáltatások lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
4. Bontsa ki a Feltételek részt.
    * A feltételek között választhat úgy, hogy mindig az üzemanyag-pótdíjat alkalmazza, vagy ebben a példában válassza ki, hogy csak bizonyos régión belül legyen alkalmazva.  
5. Írjon be egy értéket a Kezdő irányítószám mezőbe.
6. Írjon be egy értéket a Záró irányítószám mezőbe.
7. Bontsa ki a Számítás részt.
    * A számítás szakaszban megadhatja az üzemanyag-pótdíj számítását. Ez a számítás a Kiegészítő szolgáltatás egységtől függ, amelyet a számítás alapjaként kiválasztott.  
8. A Kiegészítő díj típusa mezőben válassza ki az „Üzemanyag-pótdíj” lehetőséget.
9. A Kiegészítő szolgáltatás egysége mezőben válassza ki a „Futásteljesítmény” lehetőséget.
10. A Régió mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
11. A listában kattintson a kijelölt sorban lévő hivatkozásra.
12. Kattintson a Mentés gombra.

## <a name="update-the-carrier-rating-profile"></a>Szállítmányozó minősítési profiljának frissítése
1. Ugorjon a Szállításkezelés > Beállítás > Szállítmányozók > Szállítmányozók lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. Bontsa ki a Díjazási profilok részt.
4. Kattintson a Szerkesztés lehetőségre.
5. A Szállítmányozói üzemanyag-mutató mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. Kattintson a Mentés gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]