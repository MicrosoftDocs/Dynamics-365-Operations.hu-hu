---
title: Új raktárelrendezés létrehozása
description: Ez a témakör a raktárak helyekkel kapcsolatos információinak beállítását ismerteti.
author: yufeihuang
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 143648e5317e6dce1b1a76a96d6069abe5d0e351
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859314"
---
# <a name="create-a-new-warehouse-layout"></a>Új raktárelrendezés létrehozása

[!include [banner](../../includes/banner.md)]

Ez a témakör a raktárak helyekkel kapcsolatos információinak beállítását ismerteti. Ez csak a Készletkezelő modulban az „alapvető raktározás” használatával létrehozott raktárakra érvényes, a Raktárkezelési rendszerben létrehozottakra nem. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.


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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]