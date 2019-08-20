---
title: Adatbevitel megkönnyítése érdekében rekordsablon létrehozása
description: Ez az eljárás bemutatja, hogyan hozható létre rekordsablon azért, hogy a gyakran használt mezőértékeket ne kelljen minden új rekordhoz explicit módon megadni.
author: margoc
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 3b2ba56b6146f2495fb6a53c3cef9f549b1ad837
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848207"
---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="df5e3-103">Adatbevitel megkönnyítése érdekében rekordsablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="df5e3-103">Create a record template to facilitate data entry</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="df5e3-104">Ez az eljárás bemutatja, hogyan hozható létre rekordsablon azért, hogy a gyakran használt mezőértékeket ne kelljen minden új rekordhoz explicit módon megadni.</span><span class="sxs-lookup"><span data-stu-id="df5e3-104">This procedure demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="df5e3-105">Ezzel a műveletsorral létrehoz egy új rekordot az új laptokhoz, amelyeket fel kell venni a tárgyi eszközök közé.</span><span class="sxs-lookup"><span data-stu-id="df5e3-105">In this procedure, you’ll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="df5e3-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="df5e3-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="df5e3-107">Nyissa meg a következőt: Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök.</span><span class="sxs-lookup"><span data-stu-id="df5e3-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="df5e3-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="df5e3-108">Click New.</span></span>
3. <span data-ttu-id="df5e3-109">A Tárgyieszköz-csoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="df5e3-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="df5e3-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="df5e3-110">In the Name field, type a value.</span></span>
    * <span data-ttu-id="df5e3-111">Adja meg például a következőt: „Vállalati vezetői laptop”.</span><span class="sxs-lookup"><span data-stu-id="df5e3-111">For example, enter 'Corporate lead laptop'.</span></span>  
5. <span data-ttu-id="df5e3-112">Írjon be egy értéket a Keresési név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="df5e3-112">In the Search name field, type a value.</span></span>
    * <span data-ttu-id="df5e3-113">Adja meg például a következőt: „laptop”.</span><span class="sxs-lookup"><span data-stu-id="df5e3-113">For example, enter 'laptop.'</span></span>  
6. <span data-ttu-id="df5e3-114">Bontsa ki a Technikai információ szakaszt.</span><span class="sxs-lookup"><span data-stu-id="df5e3-114">Expand the Technical information section.</span></span>
7. <span data-ttu-id="df5e3-115">A Gyártmány mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="df5e3-115">In the Make field, type a value.</span></span>
8. <span data-ttu-id="df5e3-116">A Modell mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="df5e3-116">In the Model field, type a value.</span></span>
9. <span data-ttu-id="df5e3-117">A Modellév mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="df5e3-117">In the Model year field, type a value.</span></span>
10. <span data-ttu-id="df5e3-118">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="df5e3-118">On the Action Pane, click Options.</span></span>
11. <span data-ttu-id="df5e3-119">Kattintson a Rekord adatai lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="df5e3-119">Click Record info.</span></span>
12. <span data-ttu-id="df5e3-120">Kattintson a Felhasználói sablon lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="df5e3-120">Click User template.</span></span>
13. <span data-ttu-id="df5e3-121">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="df5e3-121">In the Name field, type a value.</span></span>
    * <span data-ttu-id="df5e3-122">Adja meg például a következőt: „Vállalati laptop”.</span><span class="sxs-lookup"><span data-stu-id="df5e3-122">For example, enter 'Corporate laptop.'</span></span>  
14. <span data-ttu-id="df5e3-123">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="df5e3-123">In the Description field, type a value.</span></span>
    * <span data-ttu-id="df5e3-124">Adja meg például a következőt: „Vállalati laptop”.</span><span class="sxs-lookup"><span data-stu-id="df5e3-124">For example, enter 'Corporate laptop'.</span></span>  
15. <span data-ttu-id="df5e3-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="df5e3-125">Click OK.</span></span>
16. <span data-ttu-id="df5e3-126">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="df5e3-126">Click Close.</span></span>

