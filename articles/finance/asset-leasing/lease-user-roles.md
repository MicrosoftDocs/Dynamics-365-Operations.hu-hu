---
title: Lízingfelhasználói szerepkörök hozzárendelése
description: Ez a témakör az Eszközlízinghez használt biztonsági szerepeket ismerteti. Azt is bemutatja, hogyan rendelhet hozzá felhasználókat ezekhez a szerepkörökhöz.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 16719576dde73f096c0102a89c43cbc75594cc80
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819842"
---
# <a name="assign-lease-user-roles"></a>Lízingfelhasználói szerepkörök hozzárendelése

[!include [banner](../includes/banner.md)]

Ez a témakör az Eszközlízinghez használt biztonsági szerepeket ismerteti. Azt is bemutatja, hogyan rendelhet hozzá felhasználókat ezekhez a szerepkörökhöz.

Három felhasználói szerepkör különbözteti meg a hozzáférést az Eszközlízingben. Az egyik szerepkör megfelelő a lízingek karbantartásához, a másik a lízingek megtekintéséhez, a harmadik pedig a lízingadminisztrátor feladatainak ellátásához. Minden szerepkör rendelkezik az összes lízinglapra vonatkozó speciális engedélyekkel, és mindegyik lehetővé teszi a felhasználók számára a lízingek megtekintését, létrehozását, szerkesztését vagy törlését a feladatköreiknek megfelelően.

| Szerep           | Leírás |
|----------------|-------------|
| Lízing karbantartása | A szerepkörben lévő felhasználók lízingeket adhatnak hozzá, szerkeszthetnek, törölhetnek és tekinthetnek meg. Ez a szerepkör olyan napi felhasználók számára készült, akiknek feladatai közé tartozik a havi naplóbejegyzések létrehozása és feladása, valamint új lízingek hozzáadása. Ez a szerepkör hozzáférést biztosít az összes eszközlízing-funkcióhoz. |
| Lízing megtekintése     | A szerepkörben lévő felhasználók csak lízingbejegyzéseket, -ütemezéseket tekinthetnek meg és jelentéseket futtathatnak. Nem hozhatnak létre új lízingeket, nem szerkeszthetik a meglévő lízingeket, és nem hozhatnak létre naplóbejegyzéseket a lízingekkel szemben. A szerepkör olyan felhasználók számára készült, akiknek csak meg kell tekinteniük a lízingeket, a lízingütemezéseket és a lízingekkel szemben előforduló tranzakciókat. |
| Lízingkönyvelő    | Ebben a szerepkörben lévő felhasználók csak új lízingeket hozhatnak létre. Nem szerkeszthetik és nem törölhetik a meglévő lízingeket, nem tekinthetik meg a lízingütemezéseket, illetve nem adhatnak fel lízingnapló-bejegyzéseket. Ez a szerepkör adatbeviteli kapacitással dolgozó felhasználók számára készült. |

Az alábbi lépésekkel rendelje hozzá a felhasználókat az Eszközlízingben használt szerepkörökhöz.

1. Menjen a **Rendszergazda \> Biztonság \> Felhasználók szerepkörökhöz való hozzárendelés**.
2. Válassza a **Lízing karbantartása**, **Lízingkönyvelő** vagy a **Lízing megtekintése** szerepkört, majd válassza a **Felhasználók manuális hozzárendelése/kizárása** lehetőséget.
3. Válassza ki a szerepkörhöz hozzárendelni kívánt felhasználót, majd válassza a **Hozzárendelés a szerepkörhöz** lehetőséget.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]