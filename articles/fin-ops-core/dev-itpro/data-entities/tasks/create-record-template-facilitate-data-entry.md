---
title: Adatbevitel megkönnyítése érdekében rekordsablon létrehozása
description: Ez a témakör bemutatja, hogyan hozható létre rekordsablon azért, hogy a gyakran használt mezőértékeket ne kelljen minden új rekordhoz explicit módon megadni.
author: margoc
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, SysRecordInfo, SysRecordTemplatePromptOnCreate
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f6a2eec8d730cb4c63c854433cf6160c475ce660
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753964"
---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="f5ecf-103">Adatbevitel megkönnyítése érdekében rekordsablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="f5ecf-103">Create a record template to facilitate data entry</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f5ecf-104">Ez a témakör bemutatja, hogyan hozható létre rekordsablon azért, hogy a gyakran használt mezőértékeket ne kelljen minden új rekordhoz explicit módon megadni.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-104">This topic demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="f5ecf-105">Ezzel az eljárással létrehoz egy új rekordot az új laptopokhoz, amelyeket fel kell venni a tárgyi eszközök közé.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-105">In this procedure, you'll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="f5ecf-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="f5ecf-107">A navigációs ablaktáblán ugorjon a **Modulok > Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök** elemre.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="f5ecf-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-108">Select **New**.</span></span>
3. <span data-ttu-id="f5ecf-109">A **Tárgyieszköz-csoport** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-109">In the **Fixed asset group** field, enter or select a value.</span></span>
4. <span data-ttu-id="f5ecf-110">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-110">In the **Name** field, type a value.</span></span> <span data-ttu-id="f5ecf-111">Adja meg például a következőt: **Vállalati vezetői laptop**.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-111">For example, enter **Corporate lead laptop**.</span></span>  
5. <span data-ttu-id="f5ecf-112">Írjon be egy értéket a **Keresési név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-112">In the **Search name** field, type a value.</span></span> <span data-ttu-id="f5ecf-113">Adja meg például a következőt: **laptop**.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-113">For example, enter **laptop**.</span></span>  
6. <span data-ttu-id="f5ecf-114">Bontsa ki a **Technikai információ** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-114">Expand the **Technical information** section.</span></span>
7. <span data-ttu-id="f5ecf-115">Írja be a kívánt értékeket a **Gyártmány**, **Modell** és **Modell év** mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-115">In the **Make**, **Model**, and **Model year** fields, type values.</span></span>
8. <span data-ttu-id="f5ecf-116">A műveleti ablaktáblán válassza ki a **Beállítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-116">On the Action Pane, select **Options**.</span></span>
9. <span data-ttu-id="f5ecf-117">Válassza ki a **Rekordinfó** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-117">Select **Record info**.</span></span>
10. <span data-ttu-id="f5ecf-118">Válassza ki a **Felhasználósablon** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-118">Select **User template**.</span></span>
11. <span data-ttu-id="f5ecf-119">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-119">In the **Name** field, type a value.</span></span>
12. <span data-ttu-id="f5ecf-120">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-120">In the **Description** field, type a value.</span></span>
13. <span data-ttu-id="f5ecf-121">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-121">Select **OK**.</span></span>
14. <span data-ttu-id="f5ecf-122">Válassza **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f5ecf-122">Select **Close**.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]