---
title: Eszköznézet
description: Ez a témakör az Eszközkezelés modul eszköznézetet ismerteti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTree, EntAssetFunctionalLocationTree
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0256cc86dc306c8addb37d2c8f335470b19177a
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019404"
---
# <a name="asset-view"></a><span data-ttu-id="6e96d-103">Eszköznézet</span><span class="sxs-lookup"><span data-stu-id="6e96d-103">Asset view</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="6e96d-104">Ez a témakör az Eszközkezelés modul eszköznézetet ismerteti.</span><span class="sxs-lookup"><span data-stu-id="6e96d-104">This topic describes the asset view in Asset Management.</span></span> <span data-ttu-id="6e96d-105">Az **Eszköznézet** oldal az aktív eszközöket és a munkavégzési helyeket fastruktúrában jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="6e96d-105">The **Asset view** page shows active assets and functional locations in a tree view.</span></span> <span data-ttu-id="6e96d-106">Ezért könnyen áttekintést kaphat az eszközök és munkavégzési helyek kapcsolatairól.</span><span class="sxs-lookup"><span data-stu-id="6e96d-106">Therefore, you can easily get an overview of asset relations to functional locations.</span></span> <span data-ttu-id="6e96d-107">Ezenkívül részletes információkat is megtekinhet a munkavégzési helyszínekről, az eszközökről és a kapcsolódó anyagjegyzékről.</span><span class="sxs-lookup"><span data-stu-id="6e96d-107">Additionally, you can view detailed information about functional locations, assets, and related bills of materials (BOMs).</span></span> <span data-ttu-id="6e96d-108">Ezenkívül gyorsan áttekintheti az eszközhöz kapcsolódó aktív karbantartási kéréseket és munkrendeléseket.</span><span class="sxs-lookup"><span data-stu-id="6e96d-108">You can also get a quick overview of active maintenance requests and work orders that are related to an asset.</span></span>

1. <span data-ttu-id="6e96d-109">Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Eszköznézet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6e96d-109">Select **Asset management** \> **Common** \> **Assets** \> **Asset view**.</span></span>
2. <span data-ttu-id="6e96d-110">A lapon megjelenő nézet megváltoztatásához jelöljön ki egy új értéket a **Nézet** mezőben.</span><span class="sxs-lookup"><span data-stu-id="6e96d-110">To change the view that is shown on the page, select a new value in the **View** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6e96d-111">Az **Eszköznézet** oldal megnyitásakor látható nézet az **Eszközkezelési paraméterek** oldal **Eszközök** lapjának **Nézet** mezőjében kiválasztott értéktől függ (**Eszközkezelés** \> **Beállítás** \> **Eszközkezelési paraméterek**).</span><span class="sxs-lookup"><span data-stu-id="6e96d-111">The default view that is shown when you open the **Asset view** page depends on the value that is selected in the **View** field on the **Assets** tab of the **Asset management parameters** page (**Asset management** \> **Setup** \> **Asset management parameters**).</span></span>

<span data-ttu-id="6e96d-112">A lap jobb oldalán a Gyorslapok a kijelölt nézet részleteit mutatják.</span><span class="sxs-lookup"><span data-stu-id="6e96d-112">On the right side of the page, FastTabs shows details of the selected view.</span></span>

<span data-ttu-id="6e96d-113">A fastruktúra felett megjelenő navigációs útvonal mutatja a fastruktúra aktuális kiválasztását.</span><span class="sxs-lookup"><span data-stu-id="6e96d-113">The breadcrumb trail that appears above the tree view shows the current selection in the tree view.</span></span> <span data-ttu-id="6e96d-114">Ez a navigációs útvonal a következő formátumot használja:</span><span class="sxs-lookup"><span data-stu-id="6e96d-114">This breadcrumb trail uses the following format:</span></span>

<span data-ttu-id="6e96d-115">Munkavégzési helyszín azonosítója / Munkavégzési helyszín azonosítja (ha egynél több munkavégzési helyszín létezik) \> Eszközazonosító / Eszközazonosító (ha egynél több eszköz van) – Cikkszám.</span><span class="sxs-lookup"><span data-stu-id="6e96d-115">Functional location ID / Functional location ID (if there is more than one functional location) \> Asset ID / Asset ID (if there is more than one asset) - Item number.</span></span>

<span data-ttu-id="6e96d-116">Ha a fanézetben kiválasztott egy eszközt, az **Aktív kérések** vagy az **Aktív munkarendelések** kiválasztásával megtekintheti az eszközhöz kapcsolódó karbantartási kéréseket vagy munkarendeléseket.</span><span class="sxs-lookup"><span data-stu-id="6e96d-116">If you've selected an asset in the tree view, you can select **Active requests** or **Active work orders** to view the maintenance requests or work orders that are related to the asset.</span></span> <span data-ttu-id="6e96d-117">A kapcsolódó nézet megnyitásához válassza a **Megnyitás** \> **Munkavégzési helyszín**, **Eszköz** vagy **Eszköz DBJ** pontot.</span><span class="sxs-lookup"><span data-stu-id="6e96d-117">You can also select **Open** \> **Functional location**, **Asset**, or **Asset BOM** to open the related view.</span></span>

<span data-ttu-id="6e96d-118">Az **Eszköz munkavégzési helyszínei** beállítás, amelyet a **Nézet** mezőből is kiválaszthat, bármely eszközkeresőben elérhető, ahol eszközt lehet választani.</span><span class="sxs-lookup"><span data-stu-id="6e96d-118">The **Asset functional locations** option that you can select in the **View** field is also available in any asset lookup where you can select an asset.</span></span> <span data-ttu-id="6e96d-119">A fastruktúra megjelenik az **Eszköznézet** lapon, például ahol [létrehoz egy eszközt](../objects/create-an-object.md), létrehoz egy karbantartási kérést vagy egy munkarendelést.</span><span class="sxs-lookup"><span data-stu-id="6e96d-119">The tree view is shown on an **Asset view** tab, for example, where you [create an asset](../objects/create-an-object.md), create a maintenance request, or create a work order.</span></span>
