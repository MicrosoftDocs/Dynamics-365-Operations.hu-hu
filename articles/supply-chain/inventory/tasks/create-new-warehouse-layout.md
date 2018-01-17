---
title: "Új raktárelrendezés létrehozása"
description: "Ez az eljárás bemutatja, hogyan adjon meg adatokat a raktár helyeivel kapcsolatban."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 253440d81edd6f71b52ae349398e3c6a895bf05c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-new-warehouse-layout"></a>Új raktárelrendezés létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan adjon meg adatokat a raktár helyeivel kapcsolatban. Ez csak a Készletkezelő modulban az „alapvető raktározás” használatával létrehozott raktárakra érvényes, a Raktárkezelési rendszerben létrehozottakra nem. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.


## <a name="set-the-default-location-capacity"></a>Az alapértelmezett hely kapacitás-beállítása
1. Ugrás a Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterek lehetőségre.
2. Kattintson a Helyek fülre.
3. Adjon meg egy számot a Szokásos szélesség mezőben.
4. Adjon meg egy számot a Szokásos mélység mezőben.
5. Adjon meg egy számot a Szokásos magasság mezőben.
6. Kattintson a Mentés gombra.
7. Zárja be a lapot.

## <a name="define-the-location-name-format"></a>Adja meg a hely nevének formátumát.
1. Ugrás a következő lehetőségre: Készletgazdálkodás > Beállítás > Készlet részletezése > Raktárak.
2. Kattintson az Új lehetőségre.
3. Érték beírása a Raktár mezőbe.
4. Írjon be egy értéket a Név mezőbe.
5. A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. A Helynevek szakasz bővítésének átváltása.
    * A fejezetben leírt lehetőségek helynevek alapértelmezett formátumát adják meg. Ebben a példában megadjuk a folyosószámot, az állvány számát, illetve a polcszámot.  
8. A folyosó figyelembevételével beállítása: Igen.
9. Az állvány figyelembevételével beállítása: Igen.
10. A Formátum mezőbe írjon be egy értéket az állványhoz.
    * Példa: -##  
11. A polc figyelembevételével beállítása: Igen.
12. A Formátum mezőbe írjon be egy értéket a polchoz.
    * Példa: -##  

## <a name="define-warehouse-locations"></a>Raktár-helyek meghatározása
1. A Műveleti panelen kattintson a Raktár elemre.
2. Kattintás a Hely varázslóra.
3. Kattintson a Tovább gombra.
4. A Kiszállítási területek beállítás kijelölésének törlése
5. Az Ömlesztett tárolóhelyek beállítás kijelölésének törlése
6. Kattintson a Tovább gombra.
7. Kattintson a Tovább gombra.
8. Kattintson a Tovább gombra.
9. Kattintson a Tovább gombra.
10. Kattintson a Tovább gombra.
11. Kattintson a Tovább gombra.
12. Kattintson a Tovább gombra.
    * Ne feledje, hogy a lapon látható fizikai dimenziók azok, melyeket Ön a folyamat kezdetekor állít be.  
13. Kattintson a Tovább gombra.
14. Kattintson a Finish gombra.
15. Zárja be a lapot.
16. Frissítse a lapot..

