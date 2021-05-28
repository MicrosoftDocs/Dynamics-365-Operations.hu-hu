---
title: A helyprofil nem engedélyezi a negatív készletet, de negatív aktuális készlet engedélyezett
description: A helyprofilhoz a Negatív készlet engedélyezése beállítása Nem, de a rendszer így is engedélyezi a negatív aktuális készletet.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 356d2dd7853bf93250e14eb9bd28a8a145794584
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026573"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a><span data-ttu-id="3cab1-103">A helyprofil nem engedélyezi a negatív készletet, de negatív aktuális készlet engedélyezett</span><span class="sxs-lookup"><span data-stu-id="3cab1-103">Location profile disallows negative inventory, but negative on-hand inventory is permitted</span></span>

<span data-ttu-id="3cab1-104">Tudásbáziscikk száma: 4613622</span><span class="sxs-lookup"><span data-stu-id="3cab1-104">KB number: 4613622</span></span>

## <a name="symptoms"></a><span data-ttu-id="3cab1-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="3cab1-105">Symptoms</span></span>

<span data-ttu-id="3cab1-106">A helyprofilhoz a **Negatív készlet engedélyezése** beállítása *Nem*, de a rendszer így is engedélyezi a negatív aktuális készletet.</span><span class="sxs-lookup"><span data-stu-id="3cab1-106">The **Allow negative inventory** option for the location profile is set to *No*, but the system still allows negative on-hand inventory.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="3cab1-107">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="3cab1-107">Example scenario</span></span>

<span data-ttu-id="3cab1-108">Állami szabályozású tranzakciók esetében a veszteség könyveléséhez a rendszernek képesnek kell lennie negatív készlet rögzítésére.</span><span class="sxs-lookup"><span data-stu-id="3cab1-108">For government-regulated transactions, the system must be able to record negative inventory to book losses.</span></span> <span data-ttu-id="3cab1-109">Azt szeretné, hogy egy cikk negatív készletet mutathasson, de csak a megadott helyeken, például az önköltségi helyeken.</span><span class="sxs-lookup"><span data-stu-id="3cab1-109">You want an item to be able to show negative inventory, but only in designated locations, such as tanks.</span></span> <span data-ttu-id="3cab1-110">Ha viszont a cikkmodellcsoport lehetővé teszi a negatív készletet, akkor úgy találja, hogy nem számít, hogy a helyen be van-e állítva a negatív készlet engedélyezése.</span><span class="sxs-lookup"><span data-stu-id="3cab1-110">However, if the item model group allows negative inventory, you find that it doesn't matter whether the location is set to allow negative inventory.</span></span> <span data-ttu-id="3cab1-111">Ha a cikk úgy van beállítva, hogy a negatív készlet nem megengedett, akkor a helyprofil beállítása sem számít.</span><span class="sxs-lookup"><span data-stu-id="3cab1-111">If the item is set up so that negative inventory isn't allowed, it doesn't matter how the location profile is set up.</span></span>

## <a name="resolution"></a><span data-ttu-id="3cab1-112">Felbontás</span><span class="sxs-lookup"><span data-stu-id="3cab1-112">Resolution</span></span>

<span data-ttu-id="3cab1-113">A helyprofil **Negatív készlet engedélyezése** beállítása csak a raktári folyamatokra (például a kitárolásra) vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="3cab1-113">The **Allow negative inventory** setting from the location profile applies only to warehouse processes, such as picking.</span></span> <span data-ttu-id="3cab1-114">A negatív készletre engedélyezésére beállított cikkmodellcsoportok ugyanakkor a Készletkezelés és Raktárkezelés modul minden folyamatát érintik, és a helyprofil nem bírálja felül a beállítást.</span><span class="sxs-lookup"><span data-stu-id="3cab1-114">However, item model groups that are set to allow negative inventory affect all processes from the Inventory management and Warehouse management modules, and the location profile won't override the setting.</span></span>

<span data-ttu-id="3cab1-115">Szabályozhatja, hogy egy raktárnak megengedett-e a negatív készletet tárolni.</span><span class="sxs-lookup"><span data-stu-id="3cab1-115">You can control whether a warehouse is allowed to carry negative inventory.</span></span> <span data-ttu-id="3cab1-116">A cikkmodellcsoportokat állítsa be a negatív fizikai készlet letiltására, és csak a megfelelő raktárakhoz állítsa be a negatív készlet engedélyezését.</span><span class="sxs-lookup"><span data-stu-id="3cab1-116">Set your item model groups to disallow negative physical inventory, and set only the relevant warehouse to allow negative inventory.</span></span>
