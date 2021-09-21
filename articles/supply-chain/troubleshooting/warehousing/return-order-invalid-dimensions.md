---
title: Nem hozható létre rakománysor, mert érvénytelen készletdimenziók vannak.
description: Visszárurendelés raktárba való kiadásakor hibát jelezhet az érvénytelen készletdimenziókkal kapcsolatban. Távolítsa el ezeket a rendeléssorból.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac58
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3cb728f6a989cdac63c91d49baaea094bace59e4
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476568"
---
# <a name="cant-create-load-line-for-return-sales-order-due-to-invalid-inventory-dimensions"></a>Nem hozható létre rakománysor értékesítési visszárurendeléshez, mert érvénytelen készletdimenziók vannak.

## <a name="symptoms"></a>Tünetek

A következő hibaüzenet jelenhet meg, amikor értékesítési visszárurendelést próbál kiadni a raktárba:

> Nem hozhat létre terheléssort ehhez a rendelési sorhoz, mert érvénytelen készletdimenziókat tartalmaz. Nem hivatkozhat olyan készletdimenziókra, amelyek a helydimenzió alatt találhatók a foglalási hierarchiában. Távolítsa el az érvénytelen dimenziókat a rendelési sorból.

## <a name="resolution"></a>Megoldás

Sajnos a termék nem támogatja a terhelés feldolgozását az értékesítési visszárufolyamatnál. Ezért a visszáruértékesítési rendelést nem adhatja ki a raktárba.

A rendeléstranzakciókon nem hivatkozhat olyan készletdimenziókra, amelyek a **Helydimenzió** alatt találhatók a foglalási hierarchiában. Az a megoldás, hogy távolítsa el az érvénytelen dimenziókat a rendelési sorból.
