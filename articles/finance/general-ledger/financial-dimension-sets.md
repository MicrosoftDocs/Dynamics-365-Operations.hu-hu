---
title: Pénzügyi dimenziókészletek
description: Ez a témakör a pénzügyi dimenziókészleteket írja le, és a használatuk optimalizálásához nyújt tippeket.
author: yukonpeegs
manager: AnnBe
ms.date: 03/23/2021
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b719d8eb868cb1722b470be4443d01181078ce21
ms.sourcegitcommit: 97ada5d52ed1829dcf030dad254096cd8df25da8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/06/2021
ms.locfileid: "5864412"
---
# <a name="financial-dimension-sets"></a><span data-ttu-id="d39ac-103">Pénzügyi dimenziókészletek</span><span class="sxs-lookup"><span data-stu-id="d39ac-103">Financial dimension sets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d39ac-104">Ez a témakör a pénzügyi dimenziókészleteket írja le, és a használatuk optimalizálásához nyújt tippeket.</span><span class="sxs-lookup"><span data-stu-id="d39ac-104">This topic describes financial dimension sets and provides some tips for optimizing their use.</span></span>

<span data-ttu-id="d39ac-105">A dimenziókészlet a pénzügyi dimenziók rendezett listája, amely a főkönyvi adatok felhasználó által definiált módon való összesítéséhez használható.</span><span class="sxs-lookup"><span data-stu-id="d39ac-105">A dimension set is an ordered list of financial dimensions that can be used to summarize General ledger data in a user-defined way.</span></span> <span data-ttu-id="d39ac-106">A dimenziókészletek elsődleges használata a főkönyvi kivonat meghatározása.</span><span class="sxs-lookup"><span data-stu-id="d39ac-106">A primary use of dimension sets is to define a trial balance.</span></span>

<span data-ttu-id="d39ac-107">Az egyetlen normál dimenziókészlet az a dimenziókészlet, amely csak a fő számlát tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="d39ac-107">The only standard dimension set is the dimension set that contains only the main account.</span></span>

<span data-ttu-id="d39ac-108">A **Pénzügyi dimenziókészletek** lap a pénzügyi dimenziókészletek létrehozására és kezelésére használható.</span><span class="sxs-lookup"><span data-stu-id="d39ac-108">You use the **Financial dimension sets** page to create and manage financial dimension sets.</span></span>

## <a name="dimension-set-balances"></a><span data-ttu-id="d39ac-109">Dimenziókészlet-egyenlegek</span><span class="sxs-lookup"><span data-stu-id="d39ac-109">Dimension set balances</span></span>

<span data-ttu-id="d39ac-110">A dimenziókészleteknek egyenlege lehet a pénzügyi dimenziók alapján.</span><span class="sxs-lookup"><span data-stu-id="d39ac-110">A dimension set can have balances that are based on its financial dimensions.</span></span> <span data-ttu-id="d39ac-111">Az egyenlegek a főkönyvben léteznek, és a dimenziókészlet-definíción alapulnak.</span><span class="sxs-lookup"><span data-stu-id="d39ac-111">The balances exist in General ledger and are based on the dimension set definition.</span></span> <span data-ttu-id="d39ac-112">Az egyenlegek a főkönyvi adatokból vannak összegezve, ami javítja a beolvasási teljesítményüket (például főkönyvi kivonat létrehozása során).</span><span class="sxs-lookup"><span data-stu-id="d39ac-112">The balances are summarized from the General ledger data to help improve performance when they are retrieved (for example, when a trial balance is generated).</span></span>

## <a name="create-balances"></a><span data-ttu-id="d39ac-113">Egyenlegek létrehozása</span><span class="sxs-lookup"><span data-stu-id="d39ac-113">Create balances</span></span>

<span data-ttu-id="d39ac-114">Az **Egyenlegek létrehozása** gombbal inicializálhatja egy olyan dimenziókészlet egyenlegét, amely jelenleg nem rendelkezik egyenlegekkel.</span><span class="sxs-lookup"><span data-stu-id="d39ac-114">Use the **Create balances** button to initialize the balances for a dimension set that doesn't currently have balances.</span></span>

> [!NOTE]
> <span data-ttu-id="d39ac-115">Javasoljuk, hogy korlátozza az egyenleggel rendelkezik dimenziókészletek számát, mivel az egyenlegek frissítése minden főkönyvi feladási tevékenységet befolyásol.</span><span class="sxs-lookup"><span data-stu-id="d39ac-115">We recommend that you limit the number of dimension sets that have balances, because balance updates affect all General ledger posting activities.</span></span>

## <a name="update-balances"></a><span data-ttu-id="d39ac-116">Egyenlegek módosítása</span><span class="sxs-lookup"><span data-stu-id="d39ac-116">Update balances</span></span>

<span data-ttu-id="d39ac-117">Az **Egyenlegek frissítése** gombra kattintva a legutóbbi főkönyvi feladási tevékenységet is beleveheti az egyenlegekbe.</span><span class="sxs-lookup"><span data-stu-id="d39ac-117">Use the **Update balances** button to include the latest General ledger posting activity in the balances.</span></span> <span data-ttu-id="d39ac-118">Az egyenlegfrissítések világos műveletek.</span><span class="sxs-lookup"><span data-stu-id="d39ac-118">Balance updates are light operations.</span></span> <span data-ttu-id="d39ac-119">Csak a legutóbbi frissítés óta történt főkönyvi feladási tevékenységet kell feldolgozniuk.</span><span class="sxs-lookup"><span data-stu-id="d39ac-119">They must process only the General ledger posting activity that has occurred since the last update.</span></span>

> [!NOTE]
> <span data-ttu-id="d39ac-120">A főkönyvi kivonatok megjelenítése frissítést kényszerít ki annak a biztosítására, hogy a megjelenített egyenlegek aktuálisak legyenek.</span><span class="sxs-lookup"><span data-stu-id="d39ac-120">Display of the trial balance forces an update, to ensure that the balances that are shown are current.</span></span> <span data-ttu-id="d39ac-121">Fontolja meg egy ismétlődő kötegelt feladat használatát, hogy gyorsan frissüljenek a leggyakrabban használt dimenziókészletek.</span><span class="sxs-lookup"><span data-stu-id="d39ac-121">Consider using a recurring batch job so that updates to your most frequently used dimension sets are quick.</span></span> <span data-ttu-id="d39ac-122">Ezzel a módszerrel minimálisra csökkentheti a főkönyvi kivonat felhasználók várakozási idejét.</span><span class="sxs-lookup"><span data-stu-id="d39ac-122">In this way, you help minimize the time that trial balance users must wait.</span></span>

## <a name="rebuild-balances"></a><span data-ttu-id="d39ac-123">Egyenlegek újbóli létrehozása</span><span class="sxs-lookup"><span data-stu-id="d39ac-123">Rebuild balances</span></span>

<span data-ttu-id="d39ac-124">Az **Egyenlegek újbóli létrehozása** gomb használatával az egyenlegeket a nulláról hozza újra létre.</span><span class="sxs-lookup"><span data-stu-id="d39ac-124">Use the **Rebuild balances** button to re-create the balances from scratch.</span></span> <span data-ttu-id="d39ac-125">Ily módon gondoskodhatja arról, hogy azok megegyeznek a főkönyvi adatokkal.</span><span class="sxs-lookup"><span data-stu-id="d39ac-125">In this way, you help ensure that they match the data in General ledger.</span></span> <span data-ttu-id="d39ac-126">Az egyenlegek újraépítése rengeteg számítás igényel, és általában nem szükséges.</span><span class="sxs-lookup"><span data-stu-id="d39ac-126">A rebuild of balances requires lots of processing and should not usually be required.</span></span>

> [!NOTE]
> <span data-ttu-id="d39ac-127">Ha olyan forgatókönyve van, amely rendszeresen megköveteli az egyenlegek újraépítését, akkor forduljon az ügyfélszolgálathoz.</span><span class="sxs-lookup"><span data-stu-id="d39ac-127">If you have a scenario that regularly requires a rebuild of balances, we recommend that you contact customer support.</span></span> <span data-ttu-id="d39ac-128">Az ügyféltámogatás segítségével meghatározható, hogy az egyenlegek miért nem egyeznek meg a főkönyvi adatokkal.</span><span class="sxs-lookup"><span data-stu-id="d39ac-128">Customer support can help you determine why balances don't match the data in General ledger.</span></span>

## <a name="clear-balances"></a><span data-ttu-id="d39ac-129">Egyenlegek rendezése</span><span class="sxs-lookup"><span data-stu-id="d39ac-129">Clear balances</span></span>

<span data-ttu-id="d39ac-130">Az **Egyenlegek törlése** gombbal eltávolíthatja az egyenlegeket, és leállíthatja a további frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="d39ac-130">Use the **Clear balances** button to remove the balances and stop any further updates.</span></span> <span data-ttu-id="d39ac-131">A dimenziókészlet már nem lesz hatással a főkönyvi feladási tevékenységekre.</span><span class="sxs-lookup"><span data-stu-id="d39ac-131">The dimension set will no longer have an impact on General ledger posting activities.</span></span>

<span data-ttu-id="d39ac-132">További információért lásd: [Pénzügyi dimenziók](financial-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="d39ac-132">For more information, see [Financial dimensions](financial-dimensions.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
