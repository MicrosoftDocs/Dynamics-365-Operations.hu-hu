---
title: Rendelkezésre álló készlet adatentitásainak kiterjesztése
description: Ez a cikk egy olyan példát mutat be, amely bemutatja, hogyan lehet további mezőket hozzáadni az INVENTORSITEONHANDENTITY és az INVENTWARERAKTÁROZÁSONHANDENTITY nézethez, hogy az aktuális készleten lévő adatentitások lehetőségei együtt tudjanak működni a kiterjesztésekkel.
author: yufeihuang
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 352b466a185bcd0778ea17e598129864c1547987
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906037"
---
# <a name="extend-inventory-on-hand-data-entities"></a>Rendelkezésre álló készlet adatentitásainak kiterjesztése

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management olyan [bővíthetőségi](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) funkciókat biztosít, amelyekkel [bővítményen keresztül mezőket adhat hozzá a táblákhoz](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md). Ez a cikk egy `INVENTORSITEONHANDENTITY``INVENTWAREHOUSEONHANDENTITY` olyan példát mutat be, amely bemutatja, hogyan lehet további mezőket hozzáadni a nézetekhez, hogy az aktuális készleten lévő adatentitások lehetőségei együtt tudjanak működni a kiterjesztésekkel. További információ az adatentitásokról: [Adatkezelés – áttekintés](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

> [!NOTE]
> Az alábbi listában a rendelkezésre álló készlet néhány adatentitása látható:
>
> - Aktuális készlet hely szerint
> - Aktuális készlet telephely szerint V2
> - Aktuális készlet raktár szerint
> - Rendelkezésre álló készlet raktár szerint, v2

Miután felvette a mezőket az `inventSiteOnHandView` nézet által használt táblákba, szinkronizálnia kell a motort, hogy a rendszer helyesen ismerje fel a kiterjesztéseket.

1. Bővítse az `InventSiteOnHandView` nézetet a bővítmény mező hozzáadásával.
1. Bővítse az `InventSiteOnHandAggregatedView` nézetet a bővítmény mezőkkel.
1. Bővítse az `InventSiteOnHandAggregatedViewBuilder` viewBuilder-osztályt a `getExtensionFields()` metódus módosításával. Ilyen módon a régi nézetmezőket új nézetmezőkre képezi le, amikor viewBuilder-szinkronizálás fut.

A következő négy mezőt például hozzáadta az `InventTable` táblához a bővítményen keresztül:

- Egyéni mező, 1
- Egyéni mező, 2
- Egyéni mező, 3
- Egyéni mező, 4

Ilyen esetben a következő módon kell módosítania a `getExtensionFields()` módszert.

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

Miután elvégezte ezeket a lépéseket, az új mezők hozzáadásával helyek szerint vagy a raktár adatentitásai szerint terjesztheti ki a rendelkezésre álló készletet. Ezzel a módszerrel gondoskodhat arról, hogy a rendszer felismerje a kiterjesztett mezőket, és befoglalja őket az adott adatentitásokat használó adatáttelepítés során.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]