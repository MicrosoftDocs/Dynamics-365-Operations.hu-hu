---
title: E-mail-sablonok kezelése
description: Ez a cikk az e-mail-sablonok kezelését ismerteti.
author: andreabichsel
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMApplicationWordBookmark, HRMApplicationEmailTemplate
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0fac7a8332e21f0fa767d1926c63833ebd90c78c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563896"
---
# <a name="manage-email-templates"></a><span data-ttu-id="59525-103">E-mail-sablonok kezelése</span><span class="sxs-lookup"><span data-stu-id="59525-103">Manage email templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="59525-104">Átvihet információkat szervezete adatbázisából az új dokumentum könyvjelzőihez, és felhasználhatja azokat a pályázókkal és jelöltekkel történő hatékony kommunikációt segítő sablonokban.</span><span class="sxs-lookup"><span data-stu-id="59525-104">You can transfer information from your organization's database to the bookmarks in a new document and use it in templates that help you communicate efficiently with applicants and candidates.</span></span> <span data-ttu-id="59525-105">Ehhez létrehoz egy sablont, amely szabványos szöveget és néhány könyvjelzőt tartalmaz, ahová a rendszeradatokat be lehet szúrni.</span><span class="sxs-lookup"><span data-stu-id="59525-105">To do this, you create a template that contains standard text and some bookmarks where the system data should be inserted.</span></span> <span data-ttu-id="59525-106">Például beszúrhatja a pályázó címét és kapcsolattartási adatait egy Microsoft Word-dokumentumba, amelyet a pályázóval folytatott kommunikáció során használhat.</span><span class="sxs-lookup"><span data-stu-id="59525-106">For example, you can insert address and contact information for an applicant into a Microsoft Word document that you can use when communicating with that applicant.</span></span> <span data-ttu-id="59525-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="59525-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="select-which-bookmarks-to-use-in-your-email-templates"></a><span data-ttu-id="59525-108">Megfelelő könyvjelzők kiválasztása az e-mail sablonokhoz</span><span class="sxs-lookup"><span data-stu-id="59525-108">Select which bookmarks to use in your email templates</span></span>
1. <span data-ttu-id="59525-109">A navigációs ablakban lépjen a **Modulok > Emberi erőforrások > Munkaerő-felvétel > Kommunikáció > Pályázat könyvjelzői** részre.</span><span class="sxs-lookup"><span data-stu-id="59525-109">In the navigation pane, go to **Modules > Human Resources > Recruitment > Communication > Application bookmarks**.</span></span>
2. <span data-ttu-id="59525-110">A listában keresse meg és válassza ki a kívánt kapcsolattartási műveletet.</span><span class="sxs-lookup"><span data-stu-id="59525-110">In the list, find and select the desired correspondence action.</span></span>
3. <span data-ttu-id="59525-111">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="59525-111">Select **Edit**.</span></span>
4. <span data-ttu-id="59525-112">Válassza ki az e-mail sablonban használni kívánt mezőket a kiválasztott Kapcsolattartási művelethez, és mozgassa őket a Könyvjelzők mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="59525-112">Select the fields you would like to be able to use in an email template for the selected Correspondence action and move them to the Bookmark fields.</span></span>  
5. <span data-ttu-id="59525-113">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="59525-113">Close the page.</span></span>

## <a name="create-an-email-template"></a><span data-ttu-id="59525-114">E-mail sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="59525-114">Create an email template</span></span>
1. <span data-ttu-id="59525-115">A navigációs ablakban lépjen a **Modulok > Emberi erőforrások > Munkaerő-felvétel > Kommunikáció > Pályázat e-mail sablonjai** részre.</span><span class="sxs-lookup"><span data-stu-id="59525-115">In the navigation pane, go to **Modules > Human resources > Recruitment > Communication > Application e-mail templates**.</span></span>
2. <span data-ttu-id="59525-116">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59525-116">Select **New**.</span></span>
3. <span data-ttu-id="59525-117">A **Kapcsolattartási művelet** mezőben válassza az **Interjú** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59525-117">In the **Correspondence action** field, select **Interview**.</span></span> <span data-ttu-id="59525-118">Válassza ki a kapcsolattartási műveletet, amely tartalmazza az adott típusú e-mailes kommunikációhoz szükséges könyvjelzőket.</span><span class="sxs-lookup"><span data-stu-id="59525-118">Select the correspondence action that contains the bookmarks to use for this type of email communication.</span></span>  
4. <span data-ttu-id="59525-119">Az **E-mail-sablon** mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="59525-119">In the **E-mail template** field, type a value.</span></span>
5. <span data-ttu-id="59525-120">Írjon be egy értéket a **Tárgy** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="59525-120">In the **Subject** field, type a value.</span></span>
6. <span data-ttu-id="59525-121">Írjon be egy értéket a **Szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="59525-121">In the **Text** field, type a value.</span></span>
7. <span data-ttu-id="59525-122">A listában keresse meg és válassza ki a kívánt könyvjelző mezőt.</span><span class="sxs-lookup"><span data-stu-id="59525-122">In the list, find and select the desired bookmark field.</span></span>
8. <span data-ttu-id="59525-123">Folytassa az e-mail üzenet gépelését, és ahol szükséges, szúrja be a könyvjelző mezőket.</span><span class="sxs-lookup"><span data-stu-id="59525-123">Continue typing your email message, inserting the bookmark fields where you need them.</span></span>
9. <span data-ttu-id="59525-124">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59525-124">Select **Save**.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]