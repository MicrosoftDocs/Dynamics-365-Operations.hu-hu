---
title: A nem készletcikkek kivehetők
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha a vevők készleten lévő cikkeket adhatnak a bevásárlókocsijukhoz, és továbblépnek a pénztárhoz.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 3bc924e44077886b942e19b25a84f0f1d4298c13
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282734"
---
# <a name="items-without-inventory-can-be-checked-out"></a>A nem készletcikkek kivehetők

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha a vevők készleten lévő cikkeket adhatnak a bevásárlókocsijukhoz, és továbblépnek a pénztárhoz.

## <a name="description"></a>Leírás

A felhasználók akkor is hozzáadhatnak egy cikket a kosárhoz, ha az üzletben nincs aktuális készlet, majd továbbléphetnek a pénztár oldalra.

## <a name="resolution"></a>Felbontás

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a>A nincs készleten állapottal kapcsolatos hibák megjelenítése tulajdonság engedélyezése a Commerce webhelyszerkesztőben

Kövesse az alábbi lépéseket **A nincs készleten állapottal kapcsolatos hibák megjelenítése** tulajdonság Commerce webhelyszerkesztőben történő engedélyezéséhez.

1. Válassza ki azt a webhelyet, amelyen dolgozik.
1. A bal oldali navigációs részben válassza ki az **Oldalak** lehetőséget.
1. A megnyitáshoz válassza a **CartPage** lehetőséget.
1. Válassza ki az **1. bevásárlókocsi** lehetőséget, válassza a **Szerkesztés** lehetőséget, majd a tulajdonságok panelen jelölje be **A nincs készleten állapottal kapcsolatos hibák megjelenítése** jelölőnégyzetet.
1. Mentse és tegye közzé az oldalt.

## <a name="additional-resources"></a>További erőforrások

[Készletbeállítások alkalmazása](../inventory-settings.md)

[Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](../calculated-inventory-retail-channels.md)

[Készletpufferek és készletszintek konfigurálása](../inventory-buffers-levels.md)
