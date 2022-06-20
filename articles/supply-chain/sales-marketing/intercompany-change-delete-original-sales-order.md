---
title: Eredeti vállalatközi értékesítési rendelés módosítása vagy törlése
description: Ez a témakör ismerteti az eredeti értékesítési rendelés funkció módosítását és törlését.
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 6ff7eeb00fec7c1b9fa1dc08fa231669f728ed3c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859077"
---
# <a name="change-or-delete-an-original-intercompany-sales-order"></a>Eredeti vállalatközi értékesítési rendelés módosítása vagy törlése

[!include [banner](../../includes/banner.md)]

Amikor módosít egy értékesítési rendelést a módosításokat a program automatikusan szinkronizálja a megfelelő vállalatközi beszerzési rendeléssel és a vállalatközi értékesítési rendeléssel is.

> [!NOTE]
> A módosítások nem vonatkoznak sem a külső szállítók beszerzési rendeléseire, sem a külső szállítók beszerzésirendelés-soraihoz kapcsolódó eredeti értékesítésirendelés-sorokra.

Az alábbi táblázat összefoglalja a végrehajtható módosításokat és a várható eredményeket.

| Művelet | Eredmény |
|---|---|
| Egy&nbsp;eredeti&nbsp;értékesítési&nbsp;rendelés&nbsp;törlése. | A program a kapcsolódó vállalatközi beszerzési rendelést és vállalatközi értékesítési rendelést szintén törli. Ha a rendelés állapota **Kitárolási lista** vagy későbbi a folyamatban, akkor az értékesítési rendelés nem törölhető. |
| Eredeti értékesítésirendelés-sor törlése. | A program a kapcsolódó vállalatközi beszerzésirendelés-sort és vállalatközi értékesítésirendelés-sort szintén törli. Ha a rendelés állapota **Kitárolási lista** vagy későbbi a folyamatban, akkor az értékesítésirendelés-sor nem törölhető. |
| Új értékesítési sor hozzáadása eredeti értékesítési rendeléshez. | Az új értékesítési sor a vállalatközi beszerzési rendelésben és a vállalatközi értékesítési rendelésben is létrejön. |
| Eredeti értékesítésirendelés-sor mennyiségének módosítása. | A program a vállalatközi beszerzésirendelés-sorral és a vállalatközi értékesítésirendelés-sorral is szinkronizálja a mennyiséget. A nettó összeg minden rendelésnél frissül. |
| Közvetlen kiszállítás tiltása eredeti értékesítési rendelésnél. | Az eredeti értékesítési rendelés **Közvetlen kiszállítás** mezője nem változtatható meg, ha a vállalatközi értékesítési rendelési sor állapota már legalább **Kitárolási lista**, **Kimeneti rendelés** vagy **Kitárolásilista-napló**. A vállalatközi beszerzési rendelés szállítási címe a normál szállítási címre (a beszerzési rendelés szokásos szállítási címére) módosul. Ezenkívül a vállalatközi beszerzési rendelés sorai a sorok normál szállítási címére módosulnak. A program mindkettőt szinkronizálja a vállalatközi értékesítési rendeléssel és a sorokkal. A szállítás típus az eredeti értékesítési rendelés minden sorában **Nincs** lesz, és a mező szinkronizálva lesz a vállalatközi beszerzésirendelés-sorokkal is. A külső szállítók beszerzési rendeléseit és a külső szállítók beszerzésirendelés-soraihoz kapcsolódó eredeti értékesítési sorokat a változások nem érintik. A program frissíti a vállalatközi beszerzési rendelés és a rendelés sorainak a szállítási dátumát – valamint a vállalatközi értékesítési rendelésben és a rendelés soraiban szereplő kért kézhezvételi dátumot/szállítási dátumot. |
| Közvetlen kiszállítás engedélyezése eredeti értékesítési rendelésnél. | Az eredeti értékesítési rendelés **Közvetlen kiszállítás** mezője nem módosítható ha a vállalatközi értékesítési rendelési sor állapota már legalább **Kitárolási lista**, **Kimeneti rendelés** vagy **Kitárolásilista-napló**. A program a vállalatközi beszerzési rendelés szállítási címét módosítja az eredeti értékesítési rendelés alapján, és szinkronizálja a vállalatközi értékesítési rendeléssel. A szállítás típus az eredeti értékesítési rendelés minden sorában **Közvetlen kiszállítás** lesz, és a mező szinkronizálva lesz a vállalatközi beszerzésirendelés-sorokkal is. Az egyes eredeti értékesítésirendelés-sorokat a program a vállalatközi beszerzésirendelés-sorokkal és a vállalatközi értékesítésirendelés-sorokkal is szinkronizálja. A program frissíti a vállalatközi beszerzési rendelés és a rendelés sorainak a szállítási dátumát – valamint a vállalatközi értékesítési rendelésben és a rendelés soraiban szereplő kért kézhezvételi dátumot/szállítási dátumot. |
| Megjegyzés együttes hozzáadása az eredeti értékesítési rendelés fejlécéhez és soraihoz. | A program átmásolja a megjegyzést a vállalatközi beszerzési rendelésbe és a vállalatközi értékesítési rendelésbe. |
| Megjegyzés módosítása vagy törlése. | Ha módosít vagy töröl egy megjegyzést, a megfelelő megjegyzés a vállalatközi beszerzési rendelésben és a vállalatközi értékesítési rendelésben is módosul vagy törlődik. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
