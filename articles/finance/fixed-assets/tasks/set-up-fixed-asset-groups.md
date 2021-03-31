---
title: Tárgyieszköz-csoportok beállítása
description: Ez a témakör bemutatja, hogyan tud új tárgyieszköz-csoportot létrehozni.
author: saraschi2
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee3cec5c6abf08c88a61af2ec4bde6a863de2f95
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224645"
---
# <a name="set-up-fixed-asset-groups"></a><span data-ttu-id="faf04-103">Tárgyieszköz-csoportok beállítása</span><span class="sxs-lookup"><span data-stu-id="faf04-103">Set up fixed asset groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="faf04-104">Ez a témakör bemutatja, hogyan tud új tárgyieszköz-csoportot létrehozni.</span><span class="sxs-lookup"><span data-stu-id="faf04-104">This topic explains how to create a new fixed asset group.</span></span> <span data-ttu-id="faf04-105">Ez a Könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="faf04-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="faf04-106">A Navigációs ablaktáblán ugorjon a **Modulok > Tárgyi eszközök > Beállítás > Tárgyieszköz-csoportok** elemre.</span><span class="sxs-lookup"><span data-stu-id="faf04-106">In the navigation pane, go to **Modules > Fixed assets > Setup > Fixed asset groups**.</span></span>
2. <span data-ttu-id="faf04-107">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="faf04-107">Select **New**.</span></span>
3. <span data-ttu-id="faf04-108">Írjon be egy értéket a **Tárgyieszköz-csoport** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="faf04-108">In the **Fixed asset group** field, type a value.</span></span>
4. <span data-ttu-id="faf04-109">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="faf04-109">In the **Name** field, type a value.</span></span> <span data-ttu-id="faf04-110">A **Tárgyieszköz-csoportra** érvényes automatikus számozás, illetve a Számsorozatkód felülírja a Tárgyieszköz-paraméterek beállításait.</span><span class="sxs-lookup"><span data-stu-id="faf04-110">Autonumber fixed assets and Number sequence code on the **Fixed asset** group will override the settings on the Fixed assets parameters.</span></span> <span data-ttu-id="faf04-111">Itt tudja megadni, hogy a jelen tárgyieszköz-csoportba tartozó eszközök számozása a többi csoporttól eltérő legyen.</span><span class="sxs-lookup"><span data-stu-id="faf04-111">You can change it here if the assets in this fixed asset group will have different numbering from other groups.</span></span>  
5. <span data-ttu-id="faf04-112">Válassza ki a **Könyvek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="faf04-112">Select **Books**.</span></span>
6. <span data-ttu-id="faf04-113">A **Könyv** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="faf04-113">In the **Book** field, enter or select a value.</span></span> <span data-ttu-id="faf04-114">Az **Értékcsökkenés kiszámítása** mező értéke **Igen**, a társított eszközkönyv tehát bekerül az értékcsökkenési javaslatokba.</span><span class="sxs-lookup"><span data-stu-id="faf04-114">The **Calculate depreciation** field is set to **Yes**, so the asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="faf04-115">Ha az **Értékcsökkenés kiszámítása** mező értéke **Nem**, akkor az eszköznél nem automatikus az értékcsökkenés alkalmazása.</span><span class="sxs-lookup"><span data-stu-id="faf04-115">If **Calculate depreciation** is set to **No**, the asset will not be automatically depreciated.</span></span>  
7. <span data-ttu-id="faf04-116">Adja meg években az eszköz Élettartamát.</span><span class="sxs-lookup"><span data-stu-id="faf04-116">Set the Service life of the asset, in years.</span></span> <span data-ttu-id="faf04-117">Figyelje meg, hogy az **Értékcsökkenési időszakok** mező értéke az Élettartam beállítását követően kerül kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="faf04-117">Note that the **Depreciation periods** field value is calculated after setting the Service life.</span></span>  
8. <span data-ttu-id="faf04-118">Válassza ki valamelyik lehetőséget az **Értékcsökkenési szabály** mezőben.</span><span class="sxs-lookup"><span data-stu-id="faf04-118">In the **Depreciation convention** field, select an option.</span></span>
9. <span data-ttu-id="faf04-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="faf04-119">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]