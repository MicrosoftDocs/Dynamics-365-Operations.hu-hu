---
title: Új raktárelrendezés létrehozása
description: Ez a témakör leírja, hogyan állíthat be információkat a raktárban lévő hellyekkel kapcsolatban.
author: perlynne
manager: tfehr
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f07fee1787cc2719bafbe2bb6d54849edda14018
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000034"
---
# <a name="create-a-new-warehouse-layout"></a>Új raktárelrendezés létrehozása

[!include [banner](../../includes/banner.md)]

Ez a témakör leírja, hogyan állíthat be információkat a raktárban lévő hellyekkel kapcsolatban. Ez csak a Készletkezelő modulban az „alapvető raktározás” használatával létrehozott raktárakra érvényes, a Raktárkezelési rendszerben létrehozottakra nem. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.


## <a name="set-the-default-location-capacity"></a>Az alapértelmezett hely kapacitás-beállítása
1. A Navigációs ablaktáblában válassza a **Modulok > Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterek** lehetőséget.
2. Válassza ki a **Helyek** lapot.
3. Adjon meg egy számot a **Szokásos szélesség** mezőben.
4. Adjon meg egy számot a **Szokásos mélység** mezőben.
5. Adjon meg egy számot a **Szokásos magasság** mezőben.
6. Válassza a **Mentés** lehetőséget.
7. Zárja be a lapot.

## <a name="define-the-location-name-format"></a>Adja meg a hely nevének formátumát.
1. A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Beállítás > Készlet részletezése > Raktárak** részre.
2. Válassza az **Új** lehetőséget.
3. Érték beírása a **Raktár** mezőbe.
4. Írjon be egy értéket a **Név** mezőbe.
5. A **Hely** mező keresőjében válassza ki a kívánt rekordot.
6. A **Helynevek** szakasz bővítésének átváltása. A fejezetben leírt lehetőségek helynevek alapértelmezett formátumát adják meg. Ebben a példában megadjuk a folyosószámot, az állvány számát, illetve a polcszámot.  
7. A **Folyosó figyelembevétele** beállítása legyen **Igen**.
8. Az **Állvány figyelembevétele** beállítása legyen **Igen**. 
9. A **Formátum** mezőbe írjon be egy értéket az állványhoz.
10. A **Polc figyelembevétele** beállítása legyen **Igen**.
11. A **Formátum** mezőbe írjon be egy értéket a polchoz.

## <a name="define-warehouse-locations"></a>Raktár-helyek meghatározása
1. A Műveleti ablaktáblán válassza a **Raktár** elemet.
2. Válassza a **Hely varázsló** elemet.
3. Válassza a **Következő** lehetőséget.
4. A **Kiszállítási területek** beállítás kijelölésének törlése
5. Az **Ömlesztett tárolóhelyek** beállítás kijelölésének törlése
6. Válassza a **Tovább** lehetőséget, amíg ki nem választhatja a **Befejezés** lehetőséget.
7. Zárja be a lapot.
8. Frissítse a lapot..

