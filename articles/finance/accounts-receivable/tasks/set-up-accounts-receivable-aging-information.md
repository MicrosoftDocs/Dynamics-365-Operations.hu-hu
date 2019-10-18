---
title: Kinnlevőségek korosítási adatainak beállítás és létrehozása
description: Az útmutató segít a korosítási időszak definíciójának, vevői egyenlegek korosításának beállításában és az egyenlegek megtekintésében a Gyűjtések oldal Korosított egyenleg listájában.
author: mikefalkner
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 77b5dd5feb16cc3bd6d64b6520cc47087c5b5224
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188648"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a>Kinnlevőségek korosítási adatainak beállítás és létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Az útmutató segít a korosítási időszak definíciójának, vevői egyenlegek korosításának beállításában és az egyenlegek megtekintésében a Gyűjtések oldal Korosított egyenleg listájában. Ez a felvétel az USMF bemutatócéget használja.


## <a name="create-an-aging-period-definition"></a>Korosítási időszak definícióinak létrehozása.
1. Ugorjon a **Navigációs ablaktábla > Modulok > Követelések és beszedések > Beállítás > Korosítási időszak definíciói** lehetőségre.
2. Kattintson az **Új** elemre.
3. Írjon be egy értéket a **Korosítási időszak definíciója** mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
5. Új korosítási időszak beszúrásához kattintson a **Hozzáadás alá** hivatkozásra.
6. Az **Időszak** mezőben adja meg a leírást a korosodási jelentések megjelenítéséhez.
7. Az **Egység** mezőben adjon meg egy számot.
8. Válasszon ki egy lehetőséget az **Intervallum** mezőben. A Főkönyvi időszak megegyezik a főkönyvi naptári időszakkal. Napok, hetek, hónapok, negyedévek és évek határozzák meg a dátumtartományok típusának méretét. A Korlátlan lehetőség kiválasztja az összes tranzakció előtti vagy utáni periódust, attól függően, hogy ez az első vagy az utolsó periódus.  
9. Válasszon ki egy lehetőséget a **Korosítás jelölője** mezőben.
10. A rács tetején válassza ki a periódust. Frissítse a leírást a korosítási időszak definíciójában a legrégebbi periódus leírásához
11. Az **Időszak** mezőben adja meg a korosítási időszak új leírását.
12. Zárja be a lapot.

## <a name="age-the-balances"></a>Korosítsa az egyenlegeket
1. Ugorjon a **Követelések és beszedések > Időszakos feladatok > Vevői egyenlegek korosítása** elemre.
2. A **Korosítási időszak definíciója** mezőben válassza ki a létrehozott korosítási időszak definícióját.
    + Egy aktív pillanatképet rendelhet minden egyes korosítási időszak definíciójához.  
    + Alapértelmezés szerint az összes vevő feldolgozásra kerül. Ezzel a választással egyéni gyűjtéseket számolhat vevőgyűjtőhöz.  
    + Válassza ki a dátumot a tranzakcióból, amelyet a korosításhoz fog használni.  
    + Korosítás "kezdete" dátum kiválasztása. Az alapértelmezett érték a mai nap, de ez módosítható a Kiválasztott dátum értékére, ilyenkor tetszés szerinti dátumot adhat meg. Kötegfolyamathoz használja a mai dátumot.  
3. Bővítse ki a **Vállalati** tartományt. Kiválaszthatja a vállalatokat, amelyek bekerülnek pillanatképbe. A jelenlegi vállalat van kiválasztva az alapértelmezett beállítások szerint.
4. A pillanatkép elkészítéséhez kattintson az **Ok** gombra. Eltart egy ideig, várjon, amíg a csúszka eltűnik, nézze meg érkezett-e üzenet az üzenetközpontba.

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a>A Gyűjtések oldalon a Korosított egyenlegek lista egyenlegeinek megtekintése
1. Ugorjon a **Hitelezés és beszedés > Beszedés > Korosított egyenlegek** elemre. A lista oldal a vevő egyenlegeit mutatja. A korosítási ikon a legrégebbi tranzakció korosítási időszakát jelzi.  
2. Válasszon egy egyenleggel rendelkező vevőt.
3. Bontsa ki a **Korosítás adatterületet** a korosított egyenleg megtekintéséhez. A korosítási időszak definíciója az adatterülethez a paraméterek között meghatározott alapértelmezett korosítási időszak definíciójából származik. A Gyűjtés menü segítségével megváltoztathatja.  

