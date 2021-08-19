---
title: Termelési rendelés létrehozása
description: Ez az eljárás bemutatja, hogyan lehet termelési rendelést létrehozni.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdTable, ProdBOM, ProdRoute, ProdJournalCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dfdce6061c0490fa3069e3e97eba7513721884f180089ba2a2b5fa934f2518f7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746160"
---
# <a name="create-a-production-order"></a>Termelési rendelés létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet termelési rendelést létrehozni. Ez az eljárás az USMF bemutatócéget használja. Ez az első eljárás abból a hétből, amely bemutatja a termelési rendelés életciklusát.


## <a name="create-a-production-order"></a>Termelési rendelés létrehozása
1. Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.
2. Kattintson az Új termelési rendelés lehetőségre.
3. A Cikkszám mezőbe írja be az „D0001” értéket.
4. A Szállítás mezőben adja meg a szállítási dátumot.
    * A szállítási dátum azt jelzi, hogy a termelési rendelésnek mikor kell véget érnie, hogy időben lehessen szállítani. Ez a dátum az ütemezési folyamatban használható. Például a szállítási dátumtól visszafelé ütemezheti a rendelést.  
5. Állítsa a mennyiséget 20 értékre.
    * Megjegyzés: Az Anyagjegyzékszám mező automatikusan megjeleníti az aktív Anyagjegyzék számát az aktuális cikk esetében, de a termelési rendeléshez megváltoztathatja az Anyagjegyzéket az elfogadott Anyagjegyzék-verziók listájából egy aktív Anyagjegyzéket kiválasztva.    Megjegyzés: Az Útvonalszám mező automatikusan megjeleníti az aktív Útvonal számát az aktuális cikk esetében, de a termelési rendeléshez megváltoztathatja az Útvonalat az elfogadott Útvonal-verziók listájából egy aktív Útvonalat kiválasztva.  
6. Kattintson a Létrehozás lehetőségre.

## <a name="validate-the-production-order"></a>Validálja a termelési rendelést.
1. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * A termelési rendelés számához, amelyet az imént létrehozott, kattintson a hivatkozásra. Ezzel megnyitja a Részletek lapot a rendeléshez.  
2. Kattintson a Szerkesztés lehetőségre.
3. A Szállítás mezőben adja meg a szállítási dátumot.
    * Például megváltoztathatja a termelési rendelés szállítási dátumát.  
4. Kattintson a Mentés gombra.
5. Zárja be a lapot.

## <a name="update-the-bom"></a>AJ frissítése.
1. A Művelet panelen kattintson a Termelési rendelés elemre.
2. Kattintson az Anyagjegyzék elemre.
    * Nyissa meg az Anyagjegyzék lapot az Anyagjegyzék adatainak validálásához, amelyeket az alapértelmezett adatokból másolt át, mikor létrehozta a termelési rendelést. Ebben az eljárásban szükség lesz az Anyagjegyzék-mennyiség frissítésére.  
3. Kattintson a Szerkesztés lehetőségre.
4. Adjon meg egy számot a Mennyiség mezőben.
    * Az AJ-sor mennyiségének módosítása hatással van a termelési rendelés nyersanyag-felhasználásának költségbecslésére.  
5. Kattintson a Mentés gombra.
6. Zárja be a lapot.

## <a name="update-the-production-route"></a>Termelési útvonal módosítása.
1. A Művelet panelen kattintson a Termelési rendelés elemre.
2. Kattintson az Útvonalra.
    * Nyissa meg az Útvonal lapot a termelési útvonal adatainak validálásához, amelyeket az alapértelmezett adatokból másolt át, mikor létrehozta a termelési rendelést. Ebben az eljárásban frissítenie kell a mennyiséget a termelési útvonal egyik műveletéhez.  
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
4. Kattintson a Szerkesztés lehetőségre.
5. A Folyamat menny. mezőben adjon meg egy számot.
    * A feldolgozási idő módosítása hatással van a becsült útvonal-felhasználásra és a termelési rendelés költségére.  
6. Kattintson a Mentés gombra.
7. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]