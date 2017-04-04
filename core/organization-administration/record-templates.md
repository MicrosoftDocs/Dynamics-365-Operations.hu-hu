---
title: "Rekordsablonok létrehozása"
description: "Ez a cikk bevezetőként szolgál a rekordsablonok koncepciójába és bemutatja, hogyan alkalmazhatóak új, információ megosztására alkalmas rekordok létrehozására."
author: pvillads
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 209e4fb346b8c5a02390996cb1fc8fdbd41ba241
ms.lasthandoff: 03/31/2017


---

# <a name="create-record-templates"></a>Rekordsablonok létrehozása

Ez a cikk bevezetőként szolgál a rekordsablonok koncepciójába és bemutatja, hogyan alkalmazhatóak új, információ megosztására alkalmas rekordok létrehozására.

Rekordsablonok segítségével több gyorsan Microsoft Dynamics 365 műveletek bejegyzéseket hoz létre. Rekordsablonok csak néhány Microsoft Dynamics 365 műveletekhez a bejegyzéstípusokhoz hozhat létre. Például paszta elképzelni egy autó bérleti üzleti található San Francisco Autókölcsönzési információk írunk. Mivel a legtöbb ügyfél valószínűleg San Franciscóból és környékéről származik majd, jó lenne automatikusan kitölteni az **Állam**, **Ország** és **Város** értékeket a bérleti képernyőn. **Megjegyzés:** műveletek, amelyekhez a hozzáférést a sablonok csak Dynamics 365 területeinek alkalmazhat. Azonban minden sabloncím látható, amikor új rekordot hoz létre, és más felhasználók számára is, ha az összes felhasználó számára rendelkezésre álló sablonokat hoz létre. Ezt mindenképpen figyelembe kell venni a sablonok elnevezésekor. Ha például bizalmasan kell kezelni, hogy a vállalat egyes alkalmazottai jutalékalapú fizetést kapnak, akkor kerülni kell az olyan elnevezéseket, amelyekben a jutalék szó szerepel. Ha egy adott képernyőhöz egy vagy több olyan sablon áll rendelkezésre, melyekhez Ön hozzáfér, és egy új rekordot próbál létrehozni a képernyőn, akkor megjelenik az **Egy sablon kiválasztása...** oldal. Amikor kiválasztja a sablont a listából, a kiválasztott sablon alapján létrejön egy alapértelmezett adatokat tartalmazó új rekord. Ha nem szeretné sablonok használatához válasszon új rekordok létrehozásakor a **ne kérdezzen újra** jelölőnégyzet be a **kiválasztása** oldalon. A sablon kiválasztása párbeszédpanel ismételt megjelenítéséhez kattintson a jobb gombbal minden olyan bejegyzést, kattintson a **rekordadatok**, majd **Sablonkiválasztás megjelenítése**.


