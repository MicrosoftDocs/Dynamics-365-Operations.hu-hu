--- 
title: "Kinnlevőségek korosítási adatainak beállítás és létrehozása"
description: "Az útmutató segít a korosítási időszak definíciójának, vevői egyenlegek korosításának beállításában és az egyenlegek megtekintésében a Gyűjtések oldal Korosított egyenleg listájában."
author: mikefalkner
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
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ed23bcfed4e256ecc16264a181161c7119cd9bb3
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a>Kinnlevőségek korosítási adatainak beállítás és létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Az útmutató segít a korosítási időszak definíciójának, vevői egyenlegek korosításának beállításában és az egyenlegek megtekintésében a Gyűjtések oldal Korosított egyenleg listájában. Ez a felvétel az USMF bemutatócéget használja.


## <a name="create-an-aging-period-definition"></a>Korosítási időszak definícióinak létrehozása.
1. Ugorjon a Követel és beszedések > Beállítás > Korosítási időszak definíciók pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Korosítási időszak meghatározása mezőbe.
4. Írjon egy értéket a „Leírás” mezőbe.
5. Új korosítási időszak beszúrásához kattintson a Hozzáadás hivatkozásra.
6. A Periódus mezőbe írja be a leírást a korosodási jelentések megjelenítéséhez.
7. Az Egység mezőben adjon meg egy számot.
8. Egy lehetőség kiválasztása a Intervallum mezőben.
    * A Főkönyvi időszak megegyezik a főkönyvi naptári időszakkal. Napok, hetek, hónapok, negyedévek és évek határozzák meg a dátumtartományok típusának méretét. A Korlátlan lehetőség kiválasztja az összes tranzakció előtti vagy utáni periódust, attól függően, hogy ez az első vagy az utolsó periódus.  
9. Egy lehetőség kiválasztása a Korosítás jelölője mezőben.
10. A rács tetején válassza ki a periódust. Frissítse a leírást a korosítási időszak definíciójában a legrégebbi periódus leírásához
11. A Periódus mezőbe írja be a korosítási időszak új leírását.
12. Zárja be a lapot.

## <a name="age-the-balances"></a>Korosítsa az egyenlegeket
1. Ugorjon a Követelések és beszedések > Időszakos feladatok > Vevői egyenlegek korosítása pontra.
2. A Korosítási időszak definíciója mezőben válassza ki a létrehozott korosítási időszak definícióját.
    * Egy aktív pillanatképet rendelhet minden egyes korosítási időszak definíciójához.  
    * Alapértelmezés szerint az összes vevő feldolgozásra kerül. Ezzel a választással egyéni gyűjtéseket számolhat vevőgyűjtőhöz.  
    * Válassza ki a dátumot a tranzakcióból, amelyet a korosításhoz fog használni.  
    * Korosítás "kezdete" dátum kiválasztása. Az alapértelmezett érték a mai nap, de ez módosítható a Kiválasztott dátum értékére, ilyenkor tetszés szerinti dátumot adhat meg. Kötegfolyamathoz használja a mai dátumot.  
3. Bővítse ki a vállalati tartományt. Kiválaszthatja a vállalatokat, amelyek bekerülnek pillanatképbe. A jelenlegi vállalat van kiválasztva az alapértelmezett beállítások szerint.
4. A pillanatkép elkészítéséhez kattintson az Ok gombra. Eltart egy ideig, várjon, amíg a csúszka eltűnik, nézze meg érkezett-e üzenet az üzenetközpontba.

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a>A Gyűjtések oldalon a Korosított egyenlegek lista egyenlegeinek megtekintése
1. Ugorjon a Hitelezés és beszedés > Beszedés > Korosított egyenlegek pontra.
    * A lista oldal a vevő egyenlegeit mutatja. A korosítási ikon a legrégebbi tranzakció korosítási időszakát jelzi.  
2. Válasszon egy egyenleggel rendelkező vevőt.
3. Bontsa ki a Korosítás adatterületet a korosított egyenleg megtekintéséhez.
    * A korosítási időszak definíciója az adatterülethez a paraméterek között meghatározott alapértelmezett korosítási időszak definíciójából származik. A Gyűjtés menü segítségével megváltoztathatja.  


