---
title: Nem hozható létre rakománysor, mert érvénytelen készletdimenziók vannak.
description: Visszárurendelés raktárba való kiadásakor hibát jelezhet az érvénytelen készletdimenziókkal kapcsolatban. Távolítsa el ezeket a rendeléssorból.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b02408b61b07b272a7e7d52004dc2492d60ef28c
ms.sourcegitcommit: 0d14c4a1e6cf533dd20463f1a84eae8f6d88f71b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119212"
---
# <a name="cant-create-load-line-for-return-sales-order-due-to-invalid-inventory-dimensions"></a>Nem hozható létre rakománysor értékesítési visszárurendeléshez, mert érvénytelen készletdimenziók vannak.

## <a name="symptoms"></a>Tünetek

A következő hibaüzenet jelenhet meg, amikor értékesítési visszárurendelést próbál kiadni a raktárba:

> Nem hozhat létre terheléssort ehhez a rendelési sorhoz, mert érvénytelen készletdimenziókat tartalmaz. Nem hivatkozhat olyan készletdimenziókra, amelyek a helydimenzió alatt találhatók a foglalási hierarchiában. Távolítsa el az érvénytelen dimenziókat a rendelési sorból.

## <a name="resolution"></a>Megoldás

Sajnos a termék nem támogatja a terhelés feldolgozását az értékesítési visszárufolyamatnál. Ezért a visszáruértékesítési rendelést nem adhatja ki a raktárba.

A rendeléstranzakciókon nem hivatkozhat olyan készletdimenziókra, amelyek a **Helydimenzió** alatt találhatók a foglalási hierarchiában. Az a megoldás, hogy távolítsa el az érvénytelen dimenziókat a rendelési sorból.
