---
title: Rendelkezésre álló készlet adatentitásainak kiterjesztése
description: A témakör egy példán keresztül mutatja be, hogyan adhatók bővített mezők az INVENTORSITEONHANDENTITY és az INVENTWAREHOUSEONHANDENTITY nézethez, hogy a rendelkezésre álló készlet adatentitásainak funkciói működjenek a bővítményekkel.
author: sherry-zheng
manager: tfehr
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 2e805b9379c73f7b7eb2820662fad70e28181ebf
ms.sourcegitcommit: f59df61799915f6a79aec7e3e8664c02df6597da
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/22/2021
ms.locfileid: "5043393"
---
# <a name="extend-inventory-on-hand-data-entities"></a><span data-ttu-id="97e6f-103">Rendelkezésre álló készlet adatentitásainak kiterjesztése</span><span class="sxs-lookup"><span data-stu-id="97e6f-103">Extend inventory on-hand data entities</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="97e6f-104">A Microsoft Dynamics 365 Supply Chain Management olyan [bővíthetőségi](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) funkciókat biztosít, amelyekkel [bővítményen keresztül mezőket adhat hozzá a táblákhoz](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md).</span><span class="sxs-lookup"><span data-stu-id="97e6f-104">Microsoft Dynamics 365 Supply Chain Management provides [extensibility](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) features that let you [add fields to tables through extension](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md).</span></span> <span data-ttu-id="97e6f-105">A témakör egy példán keresztül mutatja be, hogyan adhatók bővített mezők az `INVENTORSITEONHANDENTITY` és az `INVENTWAREHOUSEONHANDENTITY` nézethez, hogy a rendelkezésre álló készlet adatentitásainak funkciói működjenek a bővítményekkel.</span><span class="sxs-lookup"><span data-stu-id="97e6f-105">This topic provides an example that shows how to add extended fields to the `INVENTORSITEONHANDENTITY` and `INVENTWAREHOUSEONHANDENTITY` views, so that the capabilities of the inventory on-hand data entities can work with the extensions.</span></span> <span data-ttu-id="97e6f-106">További információ az adatentitásokról: [Adatkezelés – áttekintés](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span><span class="sxs-lookup"><span data-stu-id="97e6f-106">For more information about data entities, see [Data management overview](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="97e6f-107">Az alábbi listában a rendelkezésre álló készlet néhány adatentitása látható:</span><span class="sxs-lookup"><span data-stu-id="97e6f-107">Here is a list of some of the inventory on-hand data entities:</span></span>
>
> - <span data-ttu-id="97e6f-108">Aktuális készlet hely szerint</span><span class="sxs-lookup"><span data-stu-id="97e6f-108">Inventory on-hand by site</span></span>
> - <span data-ttu-id="97e6f-109">Aktuális készlet telephely szerint V2</span><span class="sxs-lookup"><span data-stu-id="97e6f-109">Inventory on-hand by site V2</span></span>
> - <span data-ttu-id="97e6f-110">Aktuális készlet raktár szerint</span><span class="sxs-lookup"><span data-stu-id="97e6f-110">Inventory on-hand by warehouse</span></span>
> - <span data-ttu-id="97e6f-111">Rendelkezésre álló készlet raktár szerint, v2</span><span class="sxs-lookup"><span data-stu-id="97e6f-111">Inventory on-hand by warehouse v2</span></span>

<span data-ttu-id="97e6f-112">Miután felvette a mezőket az `inventSiteOnHandView` nézet által használt táblákba, szinkronizálnia kell a motort, hogy a rendszer helyesen ismerje fel a kiterjesztéseket.</span><span class="sxs-lookup"><span data-stu-id="97e6f-112">After you add fields to tables that are used by the `inventSiteOnHandView` view, you must sync the engine so that the extensions are correctly recognized.</span></span>

1. <span data-ttu-id="97e6f-113">Bővítse az `InventSiteOnHandView` nézetet a bővítmény mező hozzáadásával.</span><span class="sxs-lookup"><span data-stu-id="97e6f-113">Extend the `InventSiteOnHandView` view by adding the extension field.</span></span>
1. <span data-ttu-id="97e6f-114">Bővítse az `InventSiteOnHandAggregatedView` nézetet a bővítmény mezőkkel.</span><span class="sxs-lookup"><span data-stu-id="97e6f-114">Extend the `InventSiteOnHandAggregatedView` view with the extension fields.</span></span>
1. <span data-ttu-id="97e6f-115">Bővítse az `InventSiteOnHandAggregatedViewBuilder` viewBuilder-osztályt a `getExtensionFields()` metódus módosításával.</span><span class="sxs-lookup"><span data-stu-id="97e6f-115">Extend the `InventSiteOnHandAggregatedViewBuilder` viewBuilder class by modifying the `getExtensionFields()` method.</span></span> <span data-ttu-id="97e6f-116">Ilyen módon a régi nézetmezőket új nézetmezőkre képezi le, amikor viewBuilder-szinkronizálás fut.</span><span class="sxs-lookup"><span data-stu-id="97e6f-116">In this way, you map old view fields to new view fields when viewBuilder synchronization is run.</span></span>

<span data-ttu-id="97e6f-117">A következő négy mezőt például hozzáadta az `InventTable` táblához a bővítményen keresztül:</span><span class="sxs-lookup"><span data-stu-id="97e6f-117">For example, you've added the following four fields to the `InventTable` table through extension:</span></span>

- <span data-ttu-id="97e6f-118">Egyéni mező, 1</span><span class="sxs-lookup"><span data-stu-id="97e6f-118">Custom field 1</span></span>
- <span data-ttu-id="97e6f-119">Egyéni mező, 2</span><span class="sxs-lookup"><span data-stu-id="97e6f-119">Custom field 2</span></span>
- <span data-ttu-id="97e6f-120">Egyéni mező, 3</span><span class="sxs-lookup"><span data-stu-id="97e6f-120">Custom field 3</span></span>
- <span data-ttu-id="97e6f-121">Egyéni mező, 4</span><span class="sxs-lookup"><span data-stu-id="97e6f-121">Custom field 4</span></span>

<span data-ttu-id="97e6f-122">Ilyen esetben a következő módon kell módosítania a `getExtensionFields()` módszert.</span><span class="sxs-lookup"><span data-stu-id="97e6f-122">In the case, you must modify the `getExtensionFields()` method in the following way.</span></span>

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

<span data-ttu-id="97e6f-123">Miután elvégezte ezeket a lépéseket, az új mezők hozzáadásával helyek szerint vagy a raktár adatentitásai szerint terjesztheti ki a rendelkezésre álló készletet.</span><span class="sxs-lookup"><span data-stu-id="97e6f-123">After you complete these steps, you can extend the inventory on-hand by site and inventory on-hand by warehouse data entities by adding the new fields.</span></span> <span data-ttu-id="97e6f-124">Ezzel a módszerrel gondoskodhat arról, hogy a rendszer felismerje a kiterjesztett mezőket, és befoglalja őket az adott adatentitásokat használó adatáttelepítés során.</span><span class="sxs-lookup"><span data-stu-id="97e6f-124">In this way, you ensure that the extended fields are recognized and included during data migration that uses those data entities.</span></span>
