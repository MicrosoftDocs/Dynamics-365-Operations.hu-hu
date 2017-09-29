--- 
title: "E-mail sablonok kezelése"
description: "Átvihet információkat szervezete adatbázisából az új dokumentum könyvjelzőihez, és felhasználhatja azokat a pályázókkal és jelöltekkel történő hatékony kommunikációt segítő sablonokban."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1eeaf1675b6653ab2c8c04d05ec1bff3cd0bb18d
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="manage-email-templates"></a><span data-ttu-id="daf2f-103">E-mail sablonok kezelése</span><span class="sxs-lookup"><span data-stu-id="daf2f-103">Manage email templates</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="daf2f-104">Átvihet információkat szervezete adatbázisából az új dokumentum könyvjelzőihez, és felhasználhatja azokat a pályázókkal és jelöltekkel történő hatékony kommunikációt segítő sablonokban.</span><span class="sxs-lookup"><span data-stu-id="daf2f-104">You can transfer information from your organization’s database to the bookmarks in a new document and use it in templates that help you communicate efficiently with applicants and candidates.</span></span> <span data-ttu-id="daf2f-105">Ehhez létrehoz egy sablont, amely szabványos szöveget és néhány könyvjelzőt tartalmaz, ahová a rendszeradatokat be lehet szúrni.</span><span class="sxs-lookup"><span data-stu-id="daf2f-105">To do this, you create a template that contains standard text and some bookmarks where the system data should be inserted.</span></span> <span data-ttu-id="daf2f-106">Például beszúrhatja a pályázó címét és kapcsolattartási adatait egy Microsoft Word dokumentumba, amelyet a pályázóval folytatott kommunikáció során használhat.</span><span class="sxs-lookup"><span data-stu-id="daf2f-106">For example, you can insert address and contact information for an applicant into a Microsoft Word document that you can use when communicating with that applicant.</span></span> <span data-ttu-id="daf2f-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="daf2f-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="select-which-bookmarks-to-use-in-your-email-templates"></a><span data-ttu-id="daf2f-108">Megfelelő könyvjelzők kiválasztása az e-mail sablonokhoz</span><span class="sxs-lookup"><span data-stu-id="daf2f-108">Select which bookmarks to use in your email templates</span></span>
1. <span data-ttu-id="daf2f-109">Ugorjon a Pályázat könyvjelzőkre.</span><span class="sxs-lookup"><span data-stu-id="daf2f-109">Go to Application bookmarks.</span></span>
2. <span data-ttu-id="daf2f-110">A listában keresse meg és válassza ki a kívánt kapcsolattartási műveletet.</span><span class="sxs-lookup"><span data-stu-id="daf2f-110">In the list, find and select the desired correspondence action.</span></span>
3. <span data-ttu-id="daf2f-111">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="daf2f-111">Click Edit.</span></span>
4. <span data-ttu-id="daf2f-112">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="daf2f-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="daf2f-113">Válassza ki az e-mail sablonban használni kívánt mezőket a kiválasztott Kapcsolattartási művelethez, és mozgassa őket a Könyvjelzők mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="daf2f-113">Select the fields you would like to be able to use in an email template for the selected Correspondence action and move them to the Bookmark fields.</span></span>  
5. <span data-ttu-id="daf2f-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="daf2f-114">Close the page.</span></span>

## <a name="create-an-email-template"></a><span data-ttu-id="daf2f-115">E-mail sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="daf2f-115">Create an email template</span></span>
1. <span data-ttu-id="daf2f-116">Ugorjon az Emberi erőforrások > Toborzás > Kommunikáció > Pályázati e-mail-sablonok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="daf2f-116">Go to Human resources > Recruitment > Communication > Application e-mail templates.</span></span>
2. <span data-ttu-id="daf2f-117">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="daf2f-117">Click New.</span></span>
3. <span data-ttu-id="daf2f-118">A Kapcsolattartási művelet mezőben válassza ki az „Interjú” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="daf2f-118">In the Correspondence action field, select 'Interview'.</span></span>
    * <span data-ttu-id="daf2f-119">Válassza ki a kapcsolattartási műveletet, amely tartalmazza az adott típusú e-mailes kommunikációhoz szükséges könyvjelzőket.</span><span class="sxs-lookup"><span data-stu-id="daf2f-119">Select the correspondence action that contains the bookmarks to use for this type of email communication.</span></span>  
4. <span data-ttu-id="daf2f-120">Írjon be egy értéket az E-mail sablon mezőbe.</span><span class="sxs-lookup"><span data-stu-id="daf2f-120">In the E-mail template field, type a value.</span></span>
5. <span data-ttu-id="daf2f-121">Írjon be egy értéket a Tárgy mezőbe.</span><span class="sxs-lookup"><span data-stu-id="daf2f-121">In the Subject field, type a value.</span></span>
6. <span data-ttu-id="daf2f-122">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="daf2f-122">In the Text field, type a value.</span></span>
7. <span data-ttu-id="daf2f-123">A listában keresse meg és válassza ki a kívánt könyvjelző mezőt.</span><span class="sxs-lookup"><span data-stu-id="daf2f-123">In the list, find and select the desired bookmark field.</span></span>
8. <span data-ttu-id="daf2f-124">Folytassa az e-mail üzenet gépelését, és ahol szükséges, szúrja be a könyvjelző mezőket.</span><span class="sxs-lookup"><span data-stu-id="daf2f-124">Continue typing your email message, inserting the bookmark fields where you need them.</span></span>
    * <span data-ttu-id="daf2f-125">Folytassa az e-mail üzenet gépelését, és ahol szükséges, szúrja be a könyvjelző mezőket.</span><span class="sxs-lookup"><span data-stu-id="daf2f-125">Continue typing your email message inserting the bookmark fields where desired.</span></span>  
9. <span data-ttu-id="daf2f-126">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="daf2f-126">Click Save.</span></span>


