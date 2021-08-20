---
title: Lízingnaplónevek beállítása
description: Ez a témakör a lízingnapló-nevek meghatározását ismerteti. A lízingnapló nevei határozzák meg azokat a naplókat, amelyekre az Eszközlízingből származó tételeket könyveli.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7caabeaf92bbce63cc30b2fb76111b33455af1910c2ea822453c550c61e02dd9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740884"
---
# <a name="set-up-lease-journal-names"></a>Lízingnaplónevek beállítása

[!include [banner](../includes/banner.md)]

A lízingnapló nevei határozzák meg azokat a naplókat, amelyekre az Eszközlízing-tranzakciókból származó tételeket könyveli. Csak az **Eszközlízing** naplótípushoz rendelt naplónevek jelennek meg az **Eszközlízing-paraméterek** lap **Kezdeti elszámolás** és **Havi naplónév** mezőiben. A **Számlanapló neve** mezőhöz csak a **szállítói számla rögzítése** naplótípus rendelhető hozzá.

A lízingnapló-nevek konfigurálásához kövesse az alábbi lépéseket.

1. Nyissa meg az **Eszközlízing \> Beállítás \> Eszközlízing paraméterei** lehetőséget.
2. Az **Általános** fül **Kezdeti elszámolás naplónév** mezőjében válasszon ki egy naplót. A program minden kezdeti elszámolási naplótételt erre a naplónévre ad fel.
3. A **Számlanapló neve** mezőben válassza ki a napló nevét. Ha a **Szállítónak fizetés** lehetőség beállítás **Igen** értékre van állítva a lízingkönyvhöz, akkor a lízing- és költségfizetési számlákat a rendszer erre a naplónévre adja fel.
4. A **Lízingnapló neve** mezőben válassza ki a napló nevét. Minden értékcsökkenési, kamat- és rövid távú átsorolási tétel erre a naplónévre lesz feladva. Ha a **Szállítónak fizetés** lehetőség beállítás **Nem** értékre van állítva a lízingkönyvhöz, akkor a lízingfizetések és költségfizetési bejegyzéseket a rendszer erre a naplónévre adja fel.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
