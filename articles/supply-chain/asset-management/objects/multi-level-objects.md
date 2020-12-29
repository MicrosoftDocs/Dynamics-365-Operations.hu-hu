---
title: Többszintű eszközök
description: Ez a témakör a többszintű eszközök létrehozásának és törlésének módját ismerteti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b7609a85f0315ee5cb5fae62d151b271ef5febe
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429654"
---
# <a name="multi-level-assets"></a><span data-ttu-id="a2bef-103">Többszintű eszközök</span><span class="sxs-lookup"><span data-stu-id="a2bef-103">Multi-level assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="a2bef-104">Ez a témakör a többszintű eszközök létrehozásának és törlésének módját ismerteti.</span><span class="sxs-lookup"><span data-stu-id="a2bef-104">This topic explains how to create and delete multi-level assets.</span></span> <span data-ttu-id="a2bef-105">Az eszközöket és a kapcsolódó aleszközöket hierarchikus fastruktúrában lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="a2bef-105">You can create assets and related sub-assets in a hierarchical tree structure.</span></span> <span data-ttu-id="a2bef-106">Így megjelenítheti az eszközök közötti kapcsolatokat és függőségeket.</span><span class="sxs-lookup"><span data-stu-id="a2bef-106">In this way, you can show relations and dependencies among assets.</span></span> <span data-ttu-id="a2bef-107">A karbantartási munkákat a fastruktúra minden szintjéhez lehet kapcsolni.</span><span class="sxs-lookup"><span data-stu-id="a2bef-107">Maintenance jobs can be related to all levels of the tree structure.</span></span> <span data-ttu-id="a2bef-108">Statisztikákat egyéni szintekhez, vagy az összes aleszközszint összességéhez is létre lehet hozni.</span><span class="sxs-lookup"><span data-stu-id="a2bef-108">Statistics can also be created for an individual level or as a sum of all sub-asset levels.</span></span>

<span data-ttu-id="a2bef-109">Az **Összes eszköz** listoldalon (**Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz**) az **Eszköz** oszlopban megtlaálható az eszközök listája hierarchikus sorrendben.</span><span class="sxs-lookup"><span data-stu-id="a2bef-109">On the **All Assets** list page (**Asset management** \> **Common** \> **Assets** \> **All assets**), the **Asset** column lists assets in hierarchical order.</span></span> <span data-ttu-id="a2bef-110">A **Fölérendelt** oszlop a kapcsolódó fölérendelt elemet mutatja.</span><span class="sxs-lookup"><span data-stu-id="a2bef-110">The **Parent** column shows the related parent.</span></span> <span data-ttu-id="a2bef-111">Ezenkívül, ha már létrehoztak eszközöket és aleszközöket, akkor a **Kapcsolódó információk** ablaktábla **Eszközfa** szakaszában láthatók az eszközök fastruktúrában.</span><span class="sxs-lookup"><span data-stu-id="a2bef-111">Additionally, if assets and sub-assets have already been created, the **Asset tree** section in the **Related information** pane shows the assets in a tree structure.</span></span>

<span data-ttu-id="a2bef-112">Az eszközök létrehozásával kapcsolatos további tudnivalókért tekintse meg az [Eszköz létrehozása](../objects/create-an-object.md) részt.</span><span class="sxs-lookup"><span data-stu-id="a2bef-112">For information about how to create an asset, see [Create an asset](../objects/create-an-object.md).</span></span> <span data-ttu-id="a2bef-113">Aleszköz létrehozásához válassza ki a fölérendelt eszközt az **Általános** gyorslap **Fölérendelt** mezőjében.</span><span class="sxs-lookup"><span data-stu-id="a2bef-113">To create a sub-asset, select the parent asset in the **Parent** field on the **General** FastTab.</span></span>

## <a name="copy-an-asset-or-asset-structure"></a><span data-ttu-id="a2bef-114">Eszköz vagy eszközstruktúra másolása</span><span class="sxs-lookup"><span data-stu-id="a2bef-114">Copy an asset or asset structure</span></span>

<span data-ttu-id="a2bef-115">Ha a vállalatnál több hasonló eszközstruktúra is van, az Eszközkezelés Másolás funkciója segítségével gyorsan létrehozhatja azokat.</span><span class="sxs-lookup"><span data-stu-id="a2bef-115">If your company has several similar asset structures, you can use the Copy function in Asset Management to quickly create them.</span></span>

1. <span data-ttu-id="a2bef-116">Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2bef-116">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="a2bef-117">Az **Összes eszköz** listaoldalon válassza ki a másolni kívánt eszközt.</span><span class="sxs-lookup"><span data-stu-id="a2bef-117">On the **All assets** list page, select the asset to copy.</span></span> <span data-ttu-id="a2bef-118">Ha például a teljes eszközstruktúrát kívánja másolni (az aleszközöket is beleértve), válasszon ki egy fölérendelt eszközt.</span><span class="sxs-lookup"><span data-stu-id="a2bef-118">For example, if you want to copy the whole asset structure, including sub-assets, select a parent asset.</span></span>
3. <span data-ttu-id="a2bef-119">Válassza az **Eszköz másolása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2bef-119">Select **Copy asset**.</span></span> <span data-ttu-id="a2bef-120">A **Másolás forrása** szakasz **Eszköz** mezője a listaoldalon kiválasztott eszközre van állítva.</span><span class="sxs-lookup"><span data-stu-id="a2bef-120">In the **Copy from** section, the **Asset** field is set to the asset that you selected on the list page.</span></span>
4. <span data-ttu-id="a2bef-121">A **Másolás célja** szakasz **Eszköz mezőjében** adja meg az új eszköz nevét.</span><span class="sxs-lookup"><span data-stu-id="a2bef-121">In the **Copy to** section, in the **Asset** field, enter the name of the new asset.</span></span>
5. <span data-ttu-id="a2bef-122">Ha a létrehozott eszköz egy meglévő eszközstruktúrához kell, hogy tartozzon, akkor válasszon egy fölérendelt azonosítót a **fölérendelt eszköz** szakasz **Eszköz** mezőjében.</span><span class="sxs-lookup"><span data-stu-id="a2bef-122">If the asset that you're creating should be part of an existing asset structure, in the **Parent asset** section, in the **Asset** field, select a parent ID.</span></span>
6. <span data-ttu-id="a2bef-123">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2bef-123">Select **OK**.</span></span> <span data-ttu-id="a2bef-124">Az új eszközstruktúra megjelenik az **Összes eszköz** listaoldalon.</span><span class="sxs-lookup"><span data-stu-id="a2bef-124">The new asset structure is shown on the **All assets** list page.</span></span> <span data-ttu-id="a2bef-125">A másolt eszközhöz kapcsolódó összes eszközattribútum, karbantartási terv és karbantartási kör átkerül az új eszközre vagy eszközstruktúrára.</span><span class="sxs-lookup"><span data-stu-id="a2bef-125">All asset attributes, maintenance plans, and maintenance rounds that are related to the asset that you copied are transferred to the new asset or asset structure.</span></span>

<span data-ttu-id="a2bef-126">Eszközstruktúra másolásakor az új struktúrában szereplő aleszközök neve megegyezik a másolt aleszközök nevével.</span><span class="sxs-lookup"><span data-stu-id="a2bef-126">When you copy an asset structure, the sub-assets in the new structure have the same name as the sub-assets that you copied.</span></span> <span data-ttu-id="a2bef-127">A másolási eljárás befejezése után egyszerűen megváltoztathatja az eszköz nevét és egyéb beállításait.</span><span class="sxs-lookup"><span data-stu-id="a2bef-127">After the copy procedure is completed, you can easily change the name and other settings for an asset.</span></span> <span data-ttu-id="a2bef-128">Válassza ki az eszközt az **Összes eszköz** listaoldalon, majd kattintson a **szerkesztés** gombra.</span><span class="sxs-lookup"><span data-stu-id="a2bef-128">Select the asset on the **All assets** list page, and then select the **Edit** button.</span></span>

> [!NOTE]
> <span data-ttu-id="a2bef-129">Eszköz-vagy eszközstruktúra másolásakor az új eszközök életciklus-állapota visszaáll az eszközök kezdeti életciklus-állapotaként megadott tetszőleges állapotra.</span><span class="sxs-lookup"><span data-stu-id="a2bef-129">When you copy an asset or asset structure, the lifecycle state of the new assets is reset to whatever state you defined as the initial lifecycle state for assets.</span></span> <span data-ttu-id="a2bef-130">A munkavégzési helyszín visszaáll az alapértelmezett munkavégzési helyszínre.</span><span class="sxs-lookup"><span data-stu-id="a2bef-130">The functional location is reset to the default functional location.</span></span>

## <a name="delete-an-asset-or-asset-structure"></a><span data-ttu-id="a2bef-131">Eszköz vagy eszközstruktúra törlése</span><span class="sxs-lookup"><span data-stu-id="a2bef-131">Delete an asset or asset structure</span></span>

<span data-ttu-id="a2bef-132">Ha egy eszköz kapcsolódó aleszközökkel rendelkezik, akkor azt csak akkor törölheti, ha bármelyik eszközre nincs regisztrálva karbantartási kérés, munkarendelési feladat, hibaregisztrációk vagy állapotfelmérések.</span><span class="sxs-lookup"><span data-stu-id="a2bef-132">If an asset has related sub-assets, you can delete it only if no maintenance requests, work order jobs, fault registrations, or condition assessments are registered on any of the assets.</span></span>

1. <span data-ttu-id="a2bef-133">Az **Összes eszköz** listaoldalon válassza ki a törölni kívánt eszközt.</span><span class="sxs-lookup"><span data-stu-id="a2bef-133">On the **All assets** list page, select the asset to delete.</span></span>
2. <span data-ttu-id="a2bef-134">Válassza a **Törlés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2bef-134">Select **Delete**.</span></span>

> [!NOTE]
> <span data-ttu-id="a2bef-135">Ha ezzel az eljárással nem lehet törölni egy eszközt, egy másik módszer a törlés kezelésére, hogy egy eszközéletciklus-állapotot állítson be erre a célra.</span><span class="sxs-lookup"><span data-stu-id="a2bef-135">If you can't delete an asset by using this procedure, another way to handle deletion is to set up an asset lifecycle state for this purpose.</span></span> <span data-ttu-id="a2bef-136">Beállíthat például egy **Selejtezett** vagy **Törölt** életciklus-állapotot az **Eszköz életciklus-állapotai** oldalon.</span><span class="sxs-lookup"><span data-stu-id="a2bef-136">For example, you can set up a **Scrapped** or **Deleted** lifecycle state on the **Asset lifecycle states** page.</span></span>
