---
title: Vállalatközi köteg- és sorozatszámok
description: Ez a témakör bemutatja, hogy mi történik, amikor kötegszámokat és sorozatszámokat regisztrál a vállalatközi rendelésekhez
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4da936263bb57c24eeb7021ac61b3945bb2777fb
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548320"
---
# <a name="intercompany-batch-and-serial-numbers"></a>Vállalatközi köteg- és sorozatszámok

[!include [banner](../../includes/banner.md)]

Azoknál a vállalatoknál, amelyek sorozatszámokat és/vagy kötegszámokat használnak a cikkek nyomonkövetésére, a kivett cikkek sorozatszámait/kötegszámait is követni kell. A vállalatközi szolgáltatásokkal automatikussá tehető a sorozatszámok és kötegszámok vállalatok közötti továbbítása. Ha egy vállalatközi értékesítési rendelésen rögzíti a cikkek kötegszámokat és sorozatszámát, akkor be lehet állítani, hogy a program automatikusan továbbítsa a ezeket a vállalatközi beszerzési rendelésre és az eredeti értékesítési rendelésre. A megfelelő paramétereket az értékesítési rendelés **Vállalatközi** oldalon kell beállítani:

- Ha a **Köteg száma** mezőt választja, az **Értékesítési rendelés irányelvei** akkor a vállalatközi értékesítési rendelés csomagjegyzékének feladása során a kötegszám kerül a vállalatközi beszerzési rendelés készlettranzakcióiba.
- Ha a **Sorozatszám** mezőt választja, akkor a vállalatközi értékesítési rendelés csomagjegyzékének feladása során a sorozatszám kerül a vállalatközi beszerzési rendelés készlettranzakcióiba.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
