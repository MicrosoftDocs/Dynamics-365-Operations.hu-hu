---
title: Egy munkafolyamat munkatételeinek delegálása
description: Ha azt tervezi, hogy távol lesz a munkahelyétől, vagy valamilyen más okból nem tud elvégezni egy adott munkaelemet, a munkaelemeket más felhasználóknak delegálhatja, illetve hozzárendelheti a felhasználókhoz.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
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
ms.openlocfilehash: 44dc747543e32b54729d12c89a401b0187e25a61
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916415"
---
# <a name="delegate-work-items-in-a-workflow"></a>Egy munkafolyamat munkatételeinek delegálása

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a>Munkaelem delegálátsa manuálisan

Ha egyetlen munkaelemet szeretne delegálni, válassza a **Delegálás** beállítást a **Munkafolyamat** menüben, majd adja meg a delegálni kívánt felhasználót a megjegyzéssel együtt. Ez hozzárendeli a munkaelemet újra a felhasználóhoz, így végrehajthatja.

## <a name="automatically-delegate-work-items"></a>Munkaelem delegálása automatikusan

Ha úgy tervezi, hogy nem lesz az irodában vagy más okból nem lesz elérhető a munkaelemek feldolgozáshoz egy bizonyos ideig, automatikusan delegálhatja az új munkaelemeket más felhasználókhoz a **Felhasználói beállítások** oldal segítségével.

### <a name="set-up-automatic-delegation"></a>Automatikus delegálás beállítása
1. Ugrás a **Közös > Beállítás > Felhasználói beállítások** elemre.
2. Kattintson a **Munkafolyamat** fülre. Győződjön meg róla, hogy a Delegálások szakasz ki van bontva. Annak a konfigurálásához, hogy a rendszer automatikusan delegálja az Ön munkaelemeit más felhasználóknak, delegálási szabályok kell létrehoznia, amelyek megadják, hogy mikor kell bizonyos típusú munkatételeket delegálni. Delegálási szabály létrehozásához kövesse az alábbi lépéseket.  
3. Kattintson a **Hozzáadás** parancsra.
4. A **Hatókör** mezőben válasszon egy lehetőséget.
    - Mind – Az Önhöz rendelt összes munkaelem delegálása.
    - Modul – Csak azoknak a munkaelemeknek a delegálása, amelyek adott típusú munkafolyamathoz kapcsolódnak. Ha ezt a lehetőséget választja, a Név mezőben ki kell választania a munkafolyamat típusát.
    - Munkafolyamat – Csak azoknak a munkaelemeknek a delegálása, amelyek adott munkafolyamathoz kapcsolódnak. Ha ezt a lehetőséget választja, a Név mezőben ki kell választania a munkafolyamatot.  
5. A **Delegálás** mezőben jelölje ki azt a felhasználót, akihez a munkatételeket delegálni szeretné. A Kezdő dátum/idő és a Záró dátum/idő mezők használatával adja meg, mikor szeretné, hogy automatikusan megtörténjen a munkatételek delegálása.  
6. A **Kezdő dátum/idő** mezőben adjon meg egy dátumot és időpontot.
7. A **Záró dátum/idő** mezőben adjon meg egy dátumot és időpontot.
8. A delegálási szabály aktiválásához jelölje be az **Engedélyezett** jelölőnégyzetet. Ha hatókörként a **Modult** választotta, ki kell választania a modult a Név mezőben. Ha hatókörként a **Munkafolyamatot** választotta, ki kell választania a konkrét munkafolyamatot a Név mezőben.  
9. A **Megjegyzés** mezőben adjon meg egy megjegyzést, amely leírja, miért delegálja a munkatételeket.

