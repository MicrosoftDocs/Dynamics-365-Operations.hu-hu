--- 
title: "Tárgyi eszköz áthelyezése"
description: "Ez a feladat-útmutató valamelyik pénzügyi dimenziókészletből helyezi át az adott tárgyieszköz-könyvre vonatkozó pénzügyi információkat az új pénzügyi dimenziókészletbe."
author: saraschi2
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 3eb00df127ed87cadde2b0fc7001d80a7fcc6e43
ms.contentlocale: hu-hu
ms.lasthandoff: 09/11/2018

---
# <a name="transfer-a-fixed-asset"></a><span data-ttu-id="11391-103">Tárgyi eszköz áthelyezése</span><span class="sxs-lookup"><span data-stu-id="11391-103">Transfer a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="11391-104">Ez a feladat-útmutató valamelyik pénzügyi dimenziókészletből helyezi át az adott tárgyieszköz-könyvre vonatkozó pénzügyi információkat az új pénzügyi dimenziókészletbe.</span><span class="sxs-lookup"><span data-stu-id="11391-104">This task guide will transfer the financial information for a fixed asset book from one financial dimension set to a new financial dimension set.</span></span>  <span data-ttu-id="11391-105">Ez a Könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="11391-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="11391-106">Nyissa meg a következőt: Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök.</span><span class="sxs-lookup"><span data-stu-id="11391-106">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="11391-107">A listában keresse meg és válassza ki az áthelyezni kívánt tárgyi eszközt.</span><span class="sxs-lookup"><span data-stu-id="11391-107">In the list, find and select the fixed asset to transfer.</span></span>
3. <span data-ttu-id="11391-108">A Műveleti ablaktáblában kattintson a Tárgyi eszköz elemre.</span><span class="sxs-lookup"><span data-stu-id="11391-108">On the Action Pane, click Fixed asset.</span></span>
4. <span data-ttu-id="11391-109">Kattintson a Tárgyi eszközök áthelyezése elemre.</span><span class="sxs-lookup"><span data-stu-id="11391-109">Click Transfer fixed assets.</span></span>
5. <span data-ttu-id="11391-110">Adja meg a dátumot az Áthelyezés dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="11391-110">In the Transfer date field, enter a date.</span></span>
6. <span data-ttu-id="11391-111">Vigyen fel az áthelyezést bemutató megjegyzést.</span><span class="sxs-lookup"><span data-stu-id="11391-111">Enter comments to describe the transfer.</span></span>
    * <span data-ttu-id="11391-112">Ez a lista megjeleníti a tárgyi eszközhöz tartozó összes könyvet.</span><span class="sxs-lookup"><span data-stu-id="11391-112">This list shows all books for the fixed asset.</span></span>  
7. <span data-ttu-id="11391-113">Jelölje meg az új pénzügyi dimenziókészlethez áthelyezni kívánt könyveket.</span><span class="sxs-lookup"><span data-stu-id="11391-113">Mark the books you want to transfer to a new financial dimension set.</span></span>
    * <span data-ttu-id="11391-114">Ez a lista a kiválasztott könyv jelenlegi pénzügyi dimenzióértékeit jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="11391-114">This list shows the existing financial dimension values for the selected book.</span></span>  
    * <span data-ttu-id="11391-115">Válassza ki a pénzügyi dimenziót, amelyet frissíteni szeretne a kiválasztott tárgyieszköz-könyvhöz.</span><span class="sxs-lookup"><span data-stu-id="11391-115">Select the financial dimension you want to update for the selected fixed asset book.</span></span>  
8. <span data-ttu-id="11391-116">A Pénzügyi dimenzió mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="11391-116">In the Financial dimension field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="11391-117">Állítsa be a megfelelő pénzügyi dimenzióértéket.</span><span class="sxs-lookup"><span data-stu-id="11391-117">Set other financial dimension values as appropriate.</span></span>  
    * <span data-ttu-id="11391-118">Áthelyezés esetén minden pénzügyi dimenzióérték változik, függetlenül attól, hogy rögzített-e értéket, vagy sem.</span><span class="sxs-lookup"><span data-stu-id="11391-118">All financial dimension values change when a transfer occurs, whether a value has been entered or left blank.</span></span> <span data-ttu-id="11391-119">Ha például adott meg értéket az Üzleti egység kapcsán, de üresen hagyta a Költséghely és Részleg pénzügyi dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="11391-119">For example, if you entered a value for the BusinessUnit and left the CostCenter and Department financial dimensions blank.</span></span> <span data-ttu-id="11391-120">Amennyiben a számlastruktúrája lehetővé teszi a Költséghely és a Részleg mezők üresen hagyását, úgy az átmozgatás eredményeképpen minden értékmodell megkapja a költséghely új értékét, és üres értéket kap a Költséghely és a Részleg esetében.</span><span class="sxs-lookup"><span data-stu-id="11391-120">If your account structure allows blank values for CostCenter and Department, the transfer would result in each value model having the new value for BusinessUnit and a blank value for CostCenter and Department.</span></span>  
9. <span data-ttu-id="11391-121">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="11391-121">Click Update.</span></span>
    * <span data-ttu-id="11391-122">Az áthelyezés véglegesítése előtt lehetősége van a változtatások előzetes megtekintésére.</span><span class="sxs-lookup"><span data-stu-id="11391-122">You have the opportunity to preview the changes before finalizing the transfer.</span></span>  
    * <span data-ttu-id="11391-123">A tárgyieszköz-könyvek áthelyezése előtt tekintse át az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="11391-123">Review results before transferring the fixed asset books.</span></span>  
10. <span data-ttu-id="11391-124">Kattintson az Áthelyezés elemre.</span><span class="sxs-lookup"><span data-stu-id="11391-124">Click Transfer.</span></span>


