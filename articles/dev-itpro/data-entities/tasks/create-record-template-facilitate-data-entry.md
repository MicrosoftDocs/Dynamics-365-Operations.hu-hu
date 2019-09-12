---
title: Adatbevitel megkönnyítése érdekében rekordsablon létrehozása
description: Ez a témakör bemutatja, hogyan hozható létre rekordsablon azért, hogy a gyakran használt mezőértékeket ne kelljen minden új rekordhoz explicit módon megadni.
author: margoc
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, SysRecordInfo, SysRecordTemplatePromptOnCreate
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 08ee7d0f0ce7e92eaa85137dcd2761bfd702eb8c
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/08/2019
ms.locfileid: "1866928"
---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="9c29a-103">Adatbevitel megkönnyítése érdekében rekordsablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="9c29a-103">Create a record template to facilitate data entry</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9c29a-104">Ez a témakör bemutatja, hogyan hozható létre rekordsablon azért, hogy a gyakran használt mezőértékeket ne kelljen minden új rekordhoz explicit módon megadni.</span><span class="sxs-lookup"><span data-stu-id="9c29a-104">This topic demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="9c29a-105">Ezzel a műveletsorral létrehoz egy új rekordot az új laptokhoz, amelyeket fel kell venni a tárgyi eszközök közé.</span><span class="sxs-lookup"><span data-stu-id="9c29a-105">In this procedure, you’ll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="9c29a-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="9c29a-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="9c29a-107">A navigációs ablaktáblán ugorjon a **Modulok > Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök** elemre.</span><span class="sxs-lookup"><span data-stu-id="9c29a-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="9c29a-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9c29a-108">Select **New**.</span></span>
3. <span data-ttu-id="9c29a-109">A **Tárgyieszköz-csoport** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9c29a-109">In the **Fixed asset group** field, enter or select a value.</span></span>
4. <span data-ttu-id="9c29a-110">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9c29a-110">In the **Name** field, type a value.</span></span> <span data-ttu-id="9c29a-111">Adja meg például a következőt: **Vállalati vezetői laptop**.</span><span class="sxs-lookup"><span data-stu-id="9c29a-111">For example, enter **Corporate lead laptop**.</span></span>  
5. <span data-ttu-id="9c29a-112">Írjon be egy értéket a **Keresési név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9c29a-112">In the **Search name** field, type a value.</span></span> <span data-ttu-id="9c29a-113">Adja meg például a következőt: **laptop**.</span><span class="sxs-lookup"><span data-stu-id="9c29a-113">For example, enter **laptop**.</span></span>  
6. <span data-ttu-id="9c29a-114">Bontsa ki a **Technikai információ** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="9c29a-114">Expand the **Technical information** section.</span></span>
7. <span data-ttu-id="9c29a-115">Írja be a kívánt értékeket a **Gyártmány**, **Modell** és **Modell év** mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="9c29a-115">In the **Make**, **Model**, and **Model year** fields, type values.</span></span>
8. <span data-ttu-id="9c29a-116">A műveleti ablaktáblán válassza ki a **Beállítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="9c29a-116">On the Action Pane, select **Options**.</span></span>
9. <span data-ttu-id="9c29a-117">Válassza ki a **Rekordinfó** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9c29a-117">Select **Record info**.</span></span>
10. <span data-ttu-id="9c29a-118">Válassza ki a **Felhasználósablon** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9c29a-118">Select **User template**.</span></span>
11. <span data-ttu-id="9c29a-119">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9c29a-119">In the **Name** field, type a value.</span></span>
12. <span data-ttu-id="9c29a-120">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9c29a-120">In the **Description** field, type a value.</span></span>
13. <span data-ttu-id="9c29a-121">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9c29a-121">Select **OK**.</span></span>
14. <span data-ttu-id="9c29a-122">Válassza **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9c29a-122">Select **Close**.</span></span>

