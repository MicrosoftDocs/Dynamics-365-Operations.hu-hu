---
title: A kifizetéseket a program automatikusan kiegyenlíti a rendelések számlázása vagy szállítása előtt
description: Ez a cikk olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha egy kifizetést közvetlenül a rendelés elküldése után egyenlít ki az Adyen portálon, annak ellenére, hogy az értékesítési rendelés számlázása vagy kiszállítása még nem történt meg.
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
ms.openlocfilehash: 6fdaf48600edc22b5423e0167177616758e2dc6e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282707"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a>A kifizetéseket a program automatikusan kiegyenlíti a rendelések számlázása vagy szállítása előtt

[!include [banner](../../includes/banner.md)]

Ez a cikk olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha egy kifizetést közvetlenül a rendelés elküldése után egyenlít ki az Adyen portálon, annak ellenére, hogy az értékesítési rendelés számlázása vagy kiszállítása még nem történt meg.

## <a name="description"></a>Leírás

Egy kifizetést közvetlenül a rendelés elrendelése után kiegyenlít az Adyen portálon annak ellenére, hogy az értékesítési rendelés számlázása vagy kiszállítása még nem történt meg.

## <a name="resolution"></a>Felbontás

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a>Manuális rögzítés konfigurálása az e-kereskedelmi kifizetésekhez az Adyen portálon

Kövesse az alábbi lépéseket a manuális rögzítés e-kereskedelmi kifizetésekhez történő konfigurálásához az Adyen portálon.

1. Jelentkezzen be az Adyen portálra.
1. A jobb felső sarokban válassza ki az e-kereskedelmi csatorna kereskedői számláját.
1. A felső navigációs sávon válassza a **Számla**, majd a **Beállítás** lehetőséget.
1. A **Rögzítés késleltetése** mezőben válassza a **kézi** lehetőséget.

    ![Az Adyen portál Rögzítés késleltetésének beállítása.](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a>További erőforrások

[Adyen fizetés rögzítése](https://docs.adyen.com/point-of-sale/capturing-payments)

[Dynamics 365 Payment Connector az Adyen szolgáltatáshoz](../dev-itpro/adyen-connector.md)

[Adyen fizetési összekötő a Dynamics 365 szolgáltatáshoz](https://docs.adyen.com/plugins/microsoft-dynamics)
