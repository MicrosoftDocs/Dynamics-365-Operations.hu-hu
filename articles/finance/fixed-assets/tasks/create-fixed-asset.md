---
title: Tárgyi eszköz létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet új tárgyieszköz-rekordot létrehozni a tárgyi eszköz lista lapjáról.
author: saraschi2
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b7d65a047251fa036242fb456725bc8cba957b9
ms.sourcegitcommit: 51e626675b0130fa32a84ce2d9119b68ea928018
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4000243"
---
# <a name="create-a-fixed-asset"></a><span data-ttu-id="84cef-103">Tárgyi eszköz létrehozása</span><span class="sxs-lookup"><span data-stu-id="84cef-103">Create a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="84cef-104">Ez a témakör azt mutatja be, hogyan lehet új tárgyieszköz-rekordot létrehozni a **Tárgyi eszköz** lista lapjáról.</span><span class="sxs-lookup"><span data-stu-id="84cef-104">This topic explains how to create a new fixed asset record from the **Fixed asset** list page.</span></span>

<span data-ttu-id="84cef-105">A rendszer hozzárendeli az eszköz számát a tárgyieszköz-csoporthoz rendelt számsorozat alapján.</span><span class="sxs-lookup"><span data-stu-id="84cef-105">The system assigns the asset number, based on the number sequence that is assigned to the fixed asset group.</span></span> <span data-ttu-id="84cef-106">Ha a tárgyi eszköz sablonnal importál eszközöket a Microsoft Excel-bővítmény segítségével, vagy ha másik importálási feladatot alkalmaz, a rendszer automatikusan létrehozza a tárgyieszköz-rekordokat, és növeli a tárgyi eszköz számát.</span><span class="sxs-lookup"><span data-stu-id="84cef-106">If you use the fixed asset template to import assets via the Microsoft Excel add-in, or if you use another import job, the system automatically creates fixed asset records and increments the asset number.</span></span>

<span data-ttu-id="84cef-107">Eszközrekord kézi létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="84cef-107">To manually create an asset record, follow these steps.</span></span>

1. <span data-ttu-id="84cef-108">Ugorjon a **Navigációs ablaktábla \> Modulok \> Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** elemre.</span><span class="sxs-lookup"><span data-stu-id="84cef-108">Go to **Navigation pane \> Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="84cef-109">A **műveleti ablaktáblán** kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="84cef-109">On the **Action pane** , select **New**.</span></span>
3. <span data-ttu-id="84cef-110">A **Tárgyieszköz-csoport** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="84cef-110">In **the Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="84cef-111">A **Szám** mező alapértelmezett értéket vesz fel, ha engedélyezte **Tárgyi eszközök automatikus számozása funkciót** a **Tárgyi eszközök paramétereinél** és a **Tárgyieszköz-csoportban**.</span><span class="sxs-lookup"><span data-stu-id="84cef-111">The **Number** field will default if you have enabled **Autonumber fixed assets functionality** in the **Fixed assets parameters** and the **Fixed asset group**.</span></span> <span data-ttu-id="84cef-112">Ha nem, akkor meg kell adni egy egyedi számot a tárgyi eszköz azonosítására.</span><span class="sxs-lookup"><span data-stu-id="84cef-112">If not, you must enter a unique number to identify the fixed asset.</span></span>
4. <span data-ttu-id="84cef-113">A **Név** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="84cef-113">In the **Name** field, enter a value.</span></span> <span data-ttu-id="84cef-114">Adja meg a kiegészítő információkat amelyek szükségesek a vállalata számára ezzel az eszközzel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="84cef-114">Enter the additional information that your business needs for this asset.</span></span>
5. <span data-ttu-id="84cef-115">A **Művelet panelen** kattintson a **Könyvek** elemre.</span><span class="sxs-lookup"><span data-stu-id="84cef-115">On the **Action pane** , select **Books**.</span></span>
6. <span data-ttu-id="84cef-116">Adja meg a dátumot a **Beszerzési dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="84cef-116">In the **Acquisition date** field, enter a date.</span></span>
7. <span data-ttu-id="84cef-117">Adjon meg egy számot a **Beszerzési ár** mezőben.</span><span class="sxs-lookup"><span data-stu-id="84cef-117">In the **Acquisition price** field, enter a number.</span></span>

    - <span data-ttu-id="84cef-118">Adja meg a kiegészítő információkat, amelyek szükségesek a vállalata számára ezzel a könyvvel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="84cef-118">Enter the additional information that your business needs for this book.</span></span>
    - <span data-ttu-id="84cef-119">Adja meg a kiegészítő információkat, amelyek szükségesek a vállalata számára a fennmaradó könyvekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="84cef-119">Enter the additional information that your business needs for the remaining books.</span></span>

8. <span data-ttu-id="84cef-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="84cef-120">Close the page.</span></span>

<span data-ttu-id="84cef-121">A tárgyi eszközök importálása az Excel-bővítmény segítségével vagy az **adatkezelés** munkaterületről származó importálási feladat futtatásával is történhet .</span><span class="sxs-lookup"><span data-stu-id="84cef-121">You can also import fixed assets by using the Excel add-in or by running an import job from the **Data management** workspace.</span></span> <span data-ttu-id="84cef-122">Az importálás futtatása előtt írja be a sablonban a kötelező mezők értékeit.</span><span class="sxs-lookup"><span data-stu-id="84cef-122">Before you run the import, enter the values for required fields in the template.</span></span>

<span data-ttu-id="84cef-123">Ha nem definiálta a tárgyi eszköz számát az Excel-bővítmény sablonjában vagy az adatkezelés modulban, akkor a rendszer minden importált eszközhöz létrehoz egy tárgyi eszköz számát, és automatikusan megnöveli a számsorozatot mindegyikhez.</span><span class="sxs-lookup"><span data-stu-id="84cef-123">If you didn't define the fixed asset number in the template of the Excel add-in, or in Data management, the system creates a fixed asset number for each imported asset and automatically increments the number sequence for each.</span></span> <span data-ttu-id="84cef-124">Ha viszont eszközöket importál, és a sablonban adja meg a tárgyi eszköz számát, a rendszer **nem** növeli automatikusan a számsorozatot.</span><span class="sxs-lookup"><span data-stu-id="84cef-124">However, if you import assets and define asset numbers in the template, the system does **not** automatically increment the number sequence.</span></span> <span data-ttu-id="84cef-125">Ebben az esetben előfordulhat, hogy a rendszergazdának manuálisan frissíteni kell a számsorozatot.</span><span class="sxs-lookup"><span data-stu-id="84cef-125">In this case, an admin might have to manually update the number sequence.</span></span> <span data-ttu-id="84cef-126">Ha a tárgyi eszköz számát az Excel-bővítmény sablonjában definiálta, akkor a rendszer a meghatározott tárgyi eszköz számát használja, és növeli a számsorozatot.</span><span class="sxs-lookup"><span data-stu-id="84cef-126">If you defined the fixed asset number in the template of the Excel add-in, the system uses the defined fixed asset number and increments the number sequence.</span></span>
