---
title: Tárgyi eszköz létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet új tárgyieszköz-rekordot létrehozni a tárgyi eszköz lista lapjáról.
author: moaamer
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
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 481bdb55b813dad5366f382ae35d8345b0e67d9f
ms.sourcegitcommit: a9efbd69f2670fd6ba0ad0babf304fc206d01249
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2020
ms.locfileid: "4444206"
---
# <a name="create-a-fixed-asset"></a><span data-ttu-id="7a51f-103">Tárgyi eszköz létrehozása</span><span class="sxs-lookup"><span data-stu-id="7a51f-103">Create a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7a51f-104">Ez a témakör azt mutatja be, hogyan lehet új tárgyieszköz-rekordot létrehozni a **Tárgyi eszköz** lista lapjáról.</span><span class="sxs-lookup"><span data-stu-id="7a51f-104">This topic explains how to create a new fixed asset record from the **Fixed asset** list page.</span></span>

<span data-ttu-id="7a51f-105">A rendszer hozzárendeli az eszköz számát a tárgyieszköz-csoporthoz rendelt számsorozat alapján.</span><span class="sxs-lookup"><span data-stu-id="7a51f-105">The system assigns the asset number, based on the number sequence that is assigned to the fixed asset group.</span></span> <span data-ttu-id="7a51f-106">Ha a tárgyi eszköz sablonnal importál eszközöket a Microsoft Excel-bővítmény segítségével, vagy ha másik importálási feladatot alkalmaz, a rendszer automatikusan létrehozza a tárgyieszköz-rekordokat, és növeli a tárgyi eszköz számát.</span><span class="sxs-lookup"><span data-stu-id="7a51f-106">If you use the fixed asset template to import assets via the Microsoft Excel add-in, or if you use another import job, the system automatically creates fixed asset records and increments the asset number.</span></span>

<span data-ttu-id="7a51f-107">Eszközrekord kézi létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7a51f-107">To manually create an asset record, follow these steps.</span></span>

1. <span data-ttu-id="7a51f-108">Ugorjon a **Navigációs ablaktábla \> Modulok \> Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** elemre.</span><span class="sxs-lookup"><span data-stu-id="7a51f-108">Go to **Navigation pane \> Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="7a51f-109">A **műveleti ablaktáblán** kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="7a51f-109">On the **Action pane**, select **New**.</span></span>
3. <span data-ttu-id="7a51f-110">A **Tárgyieszköz-csoport** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7a51f-110">In **the Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="7a51f-111">A **Szám** mező alapértelmezett értéket vesz fel, ha engedélyezte **Tárgyi eszközök automatikus számozása funkciót** a **Tárgyi eszközök paramétereinél** és a **Tárgyieszköz-csoportban**.</span><span class="sxs-lookup"><span data-stu-id="7a51f-111">The **Number** field will default if you have enabled **Autonumber fixed assets functionality** in the **Fixed assets parameters** and the **Fixed asset group**.</span></span> <span data-ttu-id="7a51f-112">Ha nem, akkor meg kell adni egy egyedi számot a tárgyi eszköz azonosítására.</span><span class="sxs-lookup"><span data-stu-id="7a51f-112">If not, you must enter a unique number to identify the fixed asset.</span></span>
4. <span data-ttu-id="7a51f-113">A **Név** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7a51f-113">In the **Name** field, enter a value.</span></span> <span data-ttu-id="7a51f-114">Adja meg a kiegészítő információkat amelyek szükségesek a vállalata számára ezzel az eszközzel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="7a51f-114">Enter the additional information that your business needs for this asset.</span></span>
5. <span data-ttu-id="7a51f-115">A **Művelet panelen** kattintson a **Könyvek** elemre.</span><span class="sxs-lookup"><span data-stu-id="7a51f-115">On the **Action pane**, select **Books**.</span></span>
6. <span data-ttu-id="7a51f-116">Adja meg a dátumot a **Beszerzési dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="7a51f-116">In the **Acquisition date** field, enter a date.</span></span>
7. <span data-ttu-id="7a51f-117">Adjon meg egy számot a **Beszerzési ár** mezőben.</span><span class="sxs-lookup"><span data-stu-id="7a51f-117">In the **Acquisition price** field, enter a number.</span></span>

    - <span data-ttu-id="7a51f-118">Adja meg a kiegészítő információkat, amelyek szükségesek a vállalata számára ezzel a könyvvel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="7a51f-118">Enter the additional information that your business needs for this book.</span></span>
    - <span data-ttu-id="7a51f-119">Adja meg a kiegészítő információkat, amelyek szükségesek a vállalata számára a fennmaradó könyvekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="7a51f-119">Enter the additional information that your business needs for the remaining books.</span></span>

8. <span data-ttu-id="7a51f-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7a51f-120">Close the page.</span></span>

<span data-ttu-id="7a51f-121">A tárgyi eszközök importálása az Excel-bővítmény segítségével vagy az **adatkezelés** munkaterületről származó importálási feladat futtatásával is történhet .</span><span class="sxs-lookup"><span data-stu-id="7a51f-121">You can also import fixed assets by using the Excel add-in or by running an import job from the **Data management** workspace.</span></span> <span data-ttu-id="7a51f-122">Az importálás futtatása előtt írja be a sablonban a kötelező mezők értékeit.</span><span class="sxs-lookup"><span data-stu-id="7a51f-122">Before you run the import, enter the values for required fields in the template.</span></span>

<span data-ttu-id="7a51f-123">Ha nem definiálta a tárgyi eszköz számát az Excel-bővítmény sablonjában vagy az adatkezelés modulban, akkor a rendszer minden importált eszközhöz létrehoz egy tárgyi eszköz számát, és automatikusan megnöveli a számsorozatot mindegyikhez.</span><span class="sxs-lookup"><span data-stu-id="7a51f-123">If you didn't define the fixed asset number in the template of the Excel add-in, or in Data management, the system creates a fixed asset number for each imported asset and automatically increments the number sequence for each.</span></span> <span data-ttu-id="7a51f-124">Ha viszont eszközöket importál, és a sablonban adja meg a tárgyi eszköz számát, a rendszer **nem** növeli automatikusan a számsorozatot.</span><span class="sxs-lookup"><span data-stu-id="7a51f-124">However, if you import assets and define asset numbers in the template, the system does **not** automatically increment the number sequence.</span></span> <span data-ttu-id="7a51f-125">Ebben az esetben előfordulhat, hogy a rendszergazdának manuálisan frissíteni kell a számsorozatot.</span><span class="sxs-lookup"><span data-stu-id="7a51f-125">In this case, an admin might have to manually update the number sequence.</span></span> <span data-ttu-id="7a51f-126">Ha a tárgyi eszköz számát az Excel-bővítmény sablonjában definiálta, akkor a rendszer a meghatározott tárgyi eszköz számát használja, és növeli a számsorozatot.</span><span class="sxs-lookup"><span data-stu-id="7a51f-126">If you defined the fixed asset number in the template of the Excel add-in, the system uses the defined fixed asset number and increments the number sequence.</span></span>

> [!NOTE]                                                                                                         
> <span data-ttu-id="7a51f-127">Az értékcsökkenés feladása után az **Aktivált** és az **Értékcsökkenés futtatási dátum** mezők zárolva lesznek a **Könyv** oldalon.</span><span class="sxs-lookup"><span data-stu-id="7a51f-127">After posting the depreciation, the **Placed in service** and **Depreciation run date** fields will be locked on the **Book** page.</span></span> <span data-ttu-id="7a51f-128">Emellett egyik mező sem frissül az adatentitásból.</span><span class="sxs-lookup"><span data-stu-id="7a51f-128">Also, both neither field will be updated from the data entity.</span></span>

> [!WARNING]
> <span data-ttu-id="7a51f-129">A rögzített eszközrekord nem törlődik, ha a tranzakciókat a kapcsolódó könyvbe adták fel, vagy ha az újonnan létrehozott eszközt naplósorban adták meg, de nem adták fel.</span><span class="sxs-lookup"><span data-stu-id="7a51f-129">The fixed asset record won't be deleted if transactions were posted to the associated book, or if the newly created fixed asset is entered on a journal line but not posted.</span></span> 
