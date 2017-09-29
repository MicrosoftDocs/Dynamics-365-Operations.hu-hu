--- 
title: "Tárgyieszköz-csoportok beállítása"
description: "Ez az eljárás bemutatja, hogy hogyan tud új tárgyieszköz-csoportot hozni létre."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c44ce1219c0fc860d621aa32c8eec7c5d640fa03
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-fixed-asset-groups"></a><span data-ttu-id="0a216-103">Tárgyieszköz-csoportok beállítása</span><span class="sxs-lookup"><span data-stu-id="0a216-103">Set up fixed asset groups</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0a216-104">Ez az eljárás bemutatja, hogy hogyan tud új tárgyieszköz-csoportot hozni létre.</span><span class="sxs-lookup"><span data-stu-id="0a216-104">This procedure shows how to create a new fixed asset group.</span></span> <span data-ttu-id="0a216-105">Ez a Könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="0a216-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="0a216-106">Ugorjon a Tárgyi eszközök > Beállítás > Tárgyieszköz-csoportok pontra.</span><span class="sxs-lookup"><span data-stu-id="0a216-106">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="0a216-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0a216-107">Click New.</span></span>
3. <span data-ttu-id="0a216-108">Írjon be egy értéket a Tárgyieszköz-csoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0a216-108">In the Fixed asset group field, type a value.</span></span>
4. <span data-ttu-id="0a216-109">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0a216-109">In the Name field, type a value.</span></span>
    * <span data-ttu-id="0a216-110">A Tárgyieszköz-csoportra érvényes automatikus számozás, illetve a Számsorozatkód felülírja a Tárgyieszköz-paraméterek beállításait.</span><span class="sxs-lookup"><span data-stu-id="0a216-110">Autonumber fixed assets and Number sequence code on the Fixed asset group will override the settings on the Fixed assets parameters.</span></span> <span data-ttu-id="0a216-111">Itt tudja megadni, hogy a jelen tárgyieszköz-csoportba tartozó eszközök számozása a többi csoporttól eltérő legyen.</span><span class="sxs-lookup"><span data-stu-id="0a216-111">You can change it here if the assets in this fixed asset group will have different numbering from other groups.</span></span>  
5. <span data-ttu-id="0a216-112">Kattintson a Könyvek elemre.</span><span class="sxs-lookup"><span data-stu-id="0a216-112">Click Books.</span></span>
6. <span data-ttu-id="0a216-113">A Könyv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0a216-113">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="0a216-114">Az Értékcsökkenés kiszámítása mező értéke Igen, a társított eszközkönyv tehát bekerül az értékcsökkenési javaslatokba.</span><span class="sxs-lookup"><span data-stu-id="0a216-114">The Calculate depreciation field is set to Yes, so the asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="0a216-115">Ha az Értékcsökkenés kiszámítása mező értéke Nem, akkor az eszköz kapcsán nem automatikus az értékcsökkenés alkalmazása.</span><span class="sxs-lookup"><span data-stu-id="0a216-115">If Calculate depreciation is set to No, the asset will not be automatically depreciated.</span></span>  
7. <span data-ttu-id="0a216-116">Adja meg években az eszköz Élettartamát.</span><span class="sxs-lookup"><span data-stu-id="0a216-116">Set the Service life of the asset, in years.</span></span>
    * <span data-ttu-id="0a216-117">Figyelje meg, hogy az Értékcsökkenési időszakok mező értéke az Élettartam beállítását követően kerül kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="0a216-117">Note that the Depreciation periods field value is calculated after setting the Service life.</span></span>  
8. <span data-ttu-id="0a216-118">Válassza ki valamelyik lehetőséget az Értékcsökkenési szabály mezőben.</span><span class="sxs-lookup"><span data-stu-id="0a216-118">In the Depreciation convention field, select an option.</span></span>
9. <span data-ttu-id="0a216-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0a216-119">Close the page.</span></span>


