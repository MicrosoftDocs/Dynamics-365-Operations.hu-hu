--- 
title: "Rendelések várakoztatásának kezelése"
description: "Ez az eljárás bemutatja, hogyan lehet a vevői értékesítési rendeléseket várakoztatásra tenni, hogyan dolgozhat a várakoztatott rendelések kifizetésével, és hogyan tudja a rendelésvárakoztatásokat eltávolítani."
author: omulvad
manager: AnnBe
ms.date: 01/09/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 6a9487567620b7b7d6d15015f7f0b7675e227c8a
ms.contentlocale: hu-hu
ms.lasthandoff: 07/28/2017

---
# <a name="manage-order-holds"></a>Rendelések várakoztatásának kezelése

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet a vevői értékesítési rendeléseket várakoztatásra tenni, hogyan dolgozhat a várakoztatott rendelések kifizetésével, és hogyan tudja a rendelésvárakoztatásokat eltávolítani. Egy megrendelés különféle okokból kerülhet várakoztatásra. Például előfordulhat, hogy egy megrendelés mindaddig várakoztatva van, amíg a vevő címe, vagy a fizetési mód ellenőrzésre nem kerül, vagy amíg a vezető ellenőrzi a vevő hitelkeretét. Amíg a rendelés várakoztatáson van, a raktár nem tudja feldolgozni szállításra. 

Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.


## <a name="set-up-order-holds"></a>Rendelésvárakoztatások beállítása
1. Ugorjon az Értékesítés és marketing > Beállítás > Értékesítési rendelések > Rendelésvárakoztatási kódok lehetőségre.
2. Kattintson az Új lehetőségre.
3. A Várakoztatási kód mezőbe írjon be egy értéket.
    * Írja be például azt, hogy Visszahívás.  
4. A Leírás mezőben adjon meg egy értéket.
    * Például, Rendelés visszatartva, vevői visszahívásra vár.  
    * Opcionálisan bejelölheti a Foglalások eltávolítása jelölőnégyzetet, ha el szeretné távolítani a rendelésből a fizikai foglalásokat a várakoztatási kód hozzáadásakor.  
5. Kattintson a Mentés gombra.

## <a name="place-order-on-hold"></a>Rendelés várakoztatásra állítása
1. Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.
2. Kattintson az Új lehetőségre.
3. A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.
4. Kattintson az OK gombra.
5. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
6. Adjon meg egy számot a Mennyiség mezőben.
7. A Művelet panelen kattintson az Értékesítési rendelés elemre.
8. Kattintson a Rendelésvárakoztatások lehetőségre.
9. Kattintson az Új lehetőségre.
10. A Várakoztatási kód mezőjében válassza ki a korábbi részfeladatban létrehozott kódot.
11. Kattintson a Mentés gombra.
12. Zárja be a lapot.
13. Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.
14. A listában jelölje meg a kiválasztott sort.
    * Az aktuálisan várakoztatásra állított rendeléseknél be van jelölve a „Nem feldolgozandó” és a „Várakoztatott” mező.    
15. A Művelet panelen kattintson a Kitárolás és csomagolás elemre.

## <a name="manage-order-holds"></a>Rendelések várakoztatásának kezelése
1. Ugorjon az Értékesítés és marketing > Értékesítési rendelések > Nyitott rendelések > Rendelésvárakoztatások elemre.
    * A Rendelésvárakoztatások oldal olyan munkaterületként működik, amely a jelenlegi és a feldolgozott várakoztatások áttekintését nyújtja, és ahol elvégezhető a várakoztatások és a társított értékesítési rendelések kezelése.      
2. A listában jelölje meg a kiválasztott sort.
3. Kattintson a Várakoztatás kivétele lehetőségre a Művelet panelen.
4. Kattintson a Kivétel elemre.
5. A listában szüntesse meg a kiválasztott sor megjelölését.
    * A Felelős mező most már megjeleníti a felhasználói azonosítót.   
6. Kattintson a Kivétel törlése elemre.
7. Kattintson a Várakoztatás megszüntetése lehetőségre a Művelet panelen.
    * Ha készen áll a várakoztatás eltávolítására és a rendelés feldolgozásának folytatására a teljesítés következő lépésével, törölnie kell a várakoztatást. Ha a rendelésen nem szükséges módosításokat végrehajtani, lefuttathatja a Várakoztatás megszüntetése műveletet. Ha azonban a várakoztatás törlésekor a rendelést frissíteni kell, a Törlés és módosítás műveletet használhatja.      
    * A Törlés és küldés művelet csak a Hívásközpont funkció használata esetén alkalmazható.  
8. Kattintson a Várakoztatások megszüntetése elemre.
    * Ezzel törölte a várakoztatást a rendelésből, és eltávolította az aktív várakoztatások listájáról. Minden várakoztatás megtekintéséhez, vagy egy részhalmazuk megtekintéséhez egy bizonyos állapot szerint, módosítsa a Megjelenítés mező értékét.     


