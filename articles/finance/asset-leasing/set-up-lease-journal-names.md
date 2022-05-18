---
title: Lízingnaplónevek beállítása
description: Ez a témakör a lízingnapló-nevek meghatározását ismerteti. A lízingnapló nevei határozzák meg azokat a naplókat, amelyekre az Eszközlízingből származó tételeket könyveli.
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 07b59d56fcb876f73369d0ceaa5ccd8226e58cf9
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725429"
---
# <a name="set-up-lease-journal-names"></a>Lízingnaplónevek beállítása

[!include [banner](../includes/banner.md)]


A lízingnapló nevei határozzák meg azokat a naplókat, amelyekre az Eszközlízing-tranzakciókból származó tételeket könyveli. Csak az **Eszközlízing** naplótípushoz rendelt naplónevek jelennek meg az **Eszközlízing-paraméterek** lap **Kezdeti elszámolás** és **Havi naplónév** mezőiben. A **Számlanapló neve** mezőhöz csak a **szállítói számla rögzítése** naplótípus rendelhető hozzá.

A rendszer bizonyos pénzügyi mezőket zárolja a szerkesztéstől, hogy megakadályozza a tranzakciók és az ütemtervek közötti eltéréseket. Néhány zárolt mező: **Számla**, **Összegek**, **Pénzügyi dimenziók**, **Pénznem** és **Tranzakciótípus**. Ezenkívül nem lesz lehetősége naplóbejegyzési sorokat hozzáadni vagy törölni az eszközlízing naplóbejegyzésekben, mivel ez eltéréseket okozhat az ütemezések és a tranzakciók között.


A bérletnaplók nevének beállítását a következő lépések szerint kell végrehajtani.

1. Nyissa meg az **Eszközlízing \> Beállítás \> Eszközlízing paraméterei** lehetőséget.
2. Az **Általános** fül **Kezdeti elszámolás naplónév** mezőjében válasszon ki egy naplót. A program minden kezdeti elszámolási naplótételt erre a naplónévre ad fel.
3. A **Számlanapló neve** mezőben válassza ki a napló nevét. Ha a **Szállítónak fizetés** lehetőség beállítás **Igen** értékre van állítva a lízingkönyvhöz, akkor a lízing- és költségfizetési számlákat a rendszer erre a naplónévre adja fel.
4. A **Lízingnapló neve** mezőben válassza ki a napló nevét. Minden értékcsökkenési, kamat- és rövid távú átsorolási tétel erre a naplónévre lesz feladva. Ha a **Szállítónak fizetés** lehetőség beállítás **Nem** értékre van állítva a lízingkönyvhöz, akkor a lízingfizetések és költségfizetési bejegyzéseket a rendszer erre a naplónévre adja fel.
5. Válasszon ki egy **naplót a Bérlése módosítási** napló neve mezőben. Ebbe a naplónévbe bérlet-helyesbítési, felmondási és értékvesztési tranzakciókat ad fel a program. A kiválasztott naplónévhez nem lehet munkafolyamat vagy jóváhagyás hozzárendelve. Ha nincs meghatározva a bérleti módosítási napló neve, akkor a bérleti díj módosítása, **a felmondási és értékvesztési tranzakciók a Bérleti napló neve mezőben kiválasztott naplónévre lesznek feladva**. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
