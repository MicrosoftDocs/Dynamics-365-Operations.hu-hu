---
title: Hitelkezelési információk hozzáadása ügyfelek számára
description: Ez a témakör azt mutatja be, hogyan lehet hozzáadni az ügyfelekhez a hitelkezelési adatokat.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: a04180a5dbec1e08d0149beeed0495a0d13af76c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971728"
---
# <a name="add-credit-management-information-for-customers"></a>Hitelkezelési információk hozzáadása ügyfelek számára

[!include [banner](../includes/banner.md)]

Miután beállította a hitelkezelést vezérlő paramétereit, további részleteket adhat meg mindegyik ügyfélhez. Ezek a részletek vezérlik a hitelkezelési folyamatokat, és további információkat is tartalmaznak, amelyek segítik az beszedési csoport tagjainak az ügyfelek kezelésében.

## <a name="customer-information"></a>Vevő adatai

Az ügyfelek adatait a **Hitel és beszedések** gyorslapon, az **Összes ügyfél** oldalon adhatja hozzá (**Kinnlevőségek \> Ügyfelek \> Összes ügyfél**).

1. A **Korlátlan hitelkeret** beállítását állítsa **Igen** értékre, ha az ügyfelet nem korlátozhatják a hitelkerettesztek.
2. A **Kizárás hitelkezelésből** beállítást állítsa **Igen** értékre, ha az ügyfelet ki szeretné zárni bármely műveletből, amely általában a hitelkezelési folyamatok során bekövetkezik.
3. Válassza ki az ügyfélhez a hitelkezelési csoportot.
4. Ha az ügyfél pénznemében szeretné kiszámítani a hitelkeretet, a **Hitelkeret az ügyfél pénznemében** mezőben adja meg az ügyfél hitelkeretét. A rendszer a vállalat pénznemében vett hitelkeretet átváltja a Hitelkezelési paraméterekben kiválasztott hitelkeret-árfolyamtípus által meghatározott árfolyammal.
5. A **Legutóbbi értékelés dátuma** mezőben adja meg a dátumot, amikor az ügyfél hitelkeretét egy hitelvezető utoljára értékelte.
6. A **Következő ütemezett értékelés dátuma** mezőben adja meg a dátumot, amikorra az ügyfél következő hitelbírálata és frissítése ütemezve van.
7. A **Jogosult hitelkeret** mezőben adja meg az ügyfélhez rendelhető legmagasabb hitelkeretet, az ügyfél hiteltörténetének felülvizsgálata alapján. A jogosult hitelkeret eltérheti a **Hitel és beszedések** gyorslapon látható hitelkerettől.
8. A **Jogosult hitelkeret pénzneme** mezőbe írja be a jogosult hitelkeret pénznemét.
9. A **Jogosult hitelkeret dátuma** mezőbe írja be a dátumot, amikor a jogosult hitelkeretet létrehozták.
10. A **Hitelszámla állapota** mezőbe adja meg az ügyfél hitelszámlájának állapotát.
11. Az **Állapot oka** mezőbe írja be a számla állapotához társított okot.
12. Az **Intézettel** beállítást állítsa **Igen** értékre, amellyel jelezheti, hogy az ügyfél jelenleg hozzá van rendelve egy hitelintézethez. Ez az érték csak tájékoztatásra szolgál. Ez a művelet nem használható hitelkezelési folyamatokban.
13. A **Tulajdonnal rendelkezik** beállítást állítsa **Igen** értékre, ha jelezni szeretné, hogy a vállalat tulajdonnal rendelkezik. Ez az érték csak tájékoztatásra szolgál. Ez a művelet nem használható bármely hitelkezelési folyamatban.
14. Az **Üzleti tevékenység kezdő dátuma** mezőbe adja meg a dátumot, amikor az ügyfél üzleti tevékenységbe kezdett. Ez az információ a kockázati pontszámok létrehozásakor használatos.
15. Az **Ügyfélkapcsolat kezdete** mezőben adja meg a dátumot, amikor az ügyfél számára az első tranzakciókat feldolgozták. Ez az információ a kockázati pontszámok létrehozásakor használatos.
16. Adjon meg megjegyzéseket, amelyeket a hitelcsoport az ügyfél hitelképességének további értékelésére használhat.

Ne feledje, hogy az **Ügyfél** oldalon látható információk egy részét egy másik folyamat hozza létre:

- A **Hitelkeret lejárati dátuma** mezőben a hitelkeret lejáratának dátuma látható. Ha nem állítja be ezt a mezőt, az ügyfél hitelkerete nem jár le.
- A **Hitelkeret dátuma** mezőben a hitelkeret létrehozásának dátuma látható. A mező minden alkalommal frissül, ha a hitelkeretet módosítják.
- Az ideiglenes hitelkeretek felülírják az ügyfél hitelkeretét egy adott időszakra. Ezeket használja a rendszer a hitelkeret helyett a teljes hitelkeret kiszámítására. Ez az információ csak akkor jelenik meg, ha van aktív hitelkeret. Az ideiglenes hitelkereteket hitelkeret-kiigazításokkal adhat meg.
- A **biztosítás és garanciák** mező a biztosítás és a garanciák teljes értékét jeleníti meg, amely növelheti a vevő hitelkeretét.
- A **teljes hitelkeret** mező az ügyfél végleges hitelkeretét jeleníti meg. A hitelkeret teljes összege tartalmaz biztosítást és garanciákat, valamint ideiglenes hitelkeretet.

## <a name="temporary-credit-limits"></a>Ideiglenes hitelkeretek

Az ideiglenes hitelkeretek felülírják az ügyfél hitelkereteit egy megadott időszakra. Az ideiglenes hitelkereteket hitelkeret-kiigazítások használatával adhat meg. A hitelkeret-korrekciók segítségével a hitelvezetők frissíthetik egyetlen ügyfél, egy ügyfélécsoport vagy az összes ügyfél hitelkereteit és lejárati dátumait egy feladási folyamat során.

Hitelkeret-korrekciós bejegyzéseket a **Hitelkeret-korrekciók** oldalon hozhat létre (**Hitelkezelés \> Hitelkeret-korrekciók \> Hitelkeret-korrekciók**).

## <a name="create-insurance-policies-and-guarantees"></a>Biztosítási kötvények és garanciák létrehozása

Minden egyes ügyfélhez egy vagy több biztosítási kötvény és garancia hozható létre. Ezekkel utána kiszámíthatja a vállalat kitettségét abban az esetben, ha hitelt nyújt egy ügyfélnek. A biztosítási kötvények és a garanciák is szerepelhetnek az ügyfél hitelkeretében.

A biztosítási kötvényeket és a garanciákat az **Összes ügyfél** oldalon lehet létrehozni (**Kinnlevőségek \> Ügyfelek \> Összes ügyfél**). Válasszon ki egy vevőt, és ezt követően a műveleti ablak **Hitelkezelés** lapján válassza a **Biztosítások és garanciák** elemet.

> [!NOTE]
> A következő eljárásban a globális címjegyzékből válasszon ki egy biztosítót vagy egy kezest. Ezért az eljárás elkezdése előtt győződjön meg arról, hogy a biztosítók és a kezesek hozzá vannak rendelve a globális címjegyzékhez.

1. Írja be az **Azonosító** mezőbe a **garancia** vagy a **biztosítás** értéket.
2. A **Garancia/biztosítás típusa** mezőben válasszon ki egyet a korábban beállított garancia- vagy biztosítási típusok közül.
3. A **Biztosító/kezes** mezőben a globális címjegyzékből válasszon ki egy biztosítót vagy egy kezest. 
4. Ha az **Azonosító** mezőben a **Biztosítás** elemet választotta, az **Irányelv fedezeti típusa** mezőben válassza ki a korábban beállított fedezeti típusok egyikét. Nem választható ki irányelv fedezeti típusa garanciához.
5. Az **Azonosító** mezőbe írja be az irányelv azonosítóját. Ez az azonosító általában egy irányelv száma.
6. A **Hatályba lépés** mezőbe írja be a biztosítási kötvény vagy garancia kezdő dátumát.
7. A **Lejárat** mezőbe írja be a biztosítási kötvény vagy garancia lejárati dátumát.
8. Az **Érték** mezőbe írja be a biztosítási kötvény vagy garancia értékét. Ez az érték az irányelv teljes értéke.
9. A **Pénznem** mezőben válassza ki az irányelv értékének pénznemét. 
10. A **Hitelkeret frissítése** mezőben adjon meg egy százalékot **0** és **100** között. Ezt a százalékos értéket alkalmazza a rendszer az irányelv értékére, és az eredményként kapott összeggel növeli azt a hitelkeretet, amely a hitelkeret-számításokban szerepel. A kiszámított érték a **Teljes hitelkeret, biztosítás és garanciák** részben látható, az **Ügyfelek** oldal **Hitel és beszedések** gyorslapján.

    Egy példa:

    - A hitelkeret (A) 100 000.
    - Az irányelv értéke (B) 50 000.
    - A **Hitelkeret frissítése** százaléka (C) 50,00.
    
    Ebben az esetben a tényleges hitelkeret 125 000 (= A + \[B × C\]).

11. Jelölje be a **Kitettségben szerepel** jelölőnégyzetet, amellyel csökkentheti a hitelkeret-számításokban használt hitelkeretet az irányelv teljes értékével. Ha ez a jelölőnégyzet be van jelölve, akkor a **Hitelkeret frissítése** százalék megadásakor kiszámított értéket a rendszer nem használja a hitelkeret-számításokban.

    Egy példa:

    - A hitelkeret (A) 100 000.
    - Az irányelv értéke (B) 50 000.
    - A **Hitelkeret frissítése** százaléka (C) 50,00.

    Ebben az esetben a tényleges hitelkeret 125 000 (= A + \[B × C\]).
    
    Ha azonban bejelöli a **Kitettségben szerepel** jelölőnégyzetet, akkor a **Hitelkeret frissítése** 50 000-es értéke (=100 000 50%-a) törlődik, a kitettség értéke pedig 75 000 (= A + \[B × C\] – B).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]