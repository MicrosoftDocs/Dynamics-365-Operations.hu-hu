---
title: Egy munkafolyamat munkatételeinek delegálása
description: Ha azt tervezi, hogy távol lesz a munkahelyétől, vagy valamilyen más okból nem tud elvégezni egy adott munkaelemet, a munkaelemeket más felhasználóknak delegálhatja, illetve hozzárendelheti a felhasználókhoz.
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f85a1318822ceaf829134bf2eb3581e350d5bea4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "346249"
---
# <a name="delegate-work-items-in-a-workflow"></a>Egy munkafolyamat munkatételeinek delegálása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ha azt tervezi, hogy távol lesz a munkahelyétől, vagy valamilyen más okból nem tud elvégezni egy adott munkaelemet, a munkaelemeket más felhasználóknak delegálhatja, illetve hozzárendelheti a felhasználókhoz. Az eljárás segítségével beállíthatja a rendszert arra, hogy automatikusan delegálja az Ön munkaelemeit egy másik felhasználónak.



Ez az eljárás az USMF bemutatócéget használja.


## <a name="set-up-automatic-delegation"></a>Automatikus delegálás beállítása
1. Ugrás a Közös > Beállítás > Felhasználói beállítások elemre.
2. Kattintson a Munkafolyamat fülre.
    * Győződjön meg arról, hogy a Delegálás terület ki legyen bontva.    Annak a konfigurálásához, hogy a rendszer automatikusan delegálja az Ön munkaelemeit más felhasználóknak, delegálási szabályok kell létrehoznia, amelyek megadják, hogy mikor kell bizonyos típusú munkatételeket delegálni. Delegálási szabály létrehozásához kövesse az alábbi lépéseket.  
3. Kattintson a Hozzáadás gombra.
4. A Hatókör mezőben válasszon egy lehetőséget.
    * Mind – Az Önhöz rendelt összes munkaelem delegálása.    Modul – Csak azoknak a munkaelemeknek a delegálása, amelyek adott típusú munkafolyamathoz kapcsolódnak. Ha ezt a lehetőséget választja, a Név mezőben ki kell választania a munkafolyamat típusát.    Munkafolyamat – Csak azoknak a munkaelemeknek a delegálása, amelyek adott munkafolyamathoz kapcsolódnak. Ha ezt a lehetőséget választja, a Név mezőben ki kell választania a munkafolyamatot.  
5. A Delegálás mezőben jelölje ki azt a felhasználót, akihez a munkatételeket delegálni szeretné.
    * A Kezdő dátum/idő és a Záró dátum/idő mezők használatával adja meg, mikor szeretné, hogy automatikusan megtörténjen a munkatételek delegálása.  
6. A Kezdő dátum/idő mezőben adjon meg egy dátumot és időpontot.
7. A Záró dátum/idő mezőben adjon meg egy dátumot és időpontot.
8. A delegálási szabály aktiválásához jelölje be az Engedélyezett jelölőnégyzetet.
    * Ha hatókörként a modult választotta, ki kell választania a modult a Név mezőben.    Ha hatókörként a munkafolyamatot választotta, ki kell választania a konkrét munkafolyamatot a Név mezőben.  
9. A Megjegyzés mezőben adjon meg egy megjegyzést, amely leírja, miért delegálja a munkatételeket.

