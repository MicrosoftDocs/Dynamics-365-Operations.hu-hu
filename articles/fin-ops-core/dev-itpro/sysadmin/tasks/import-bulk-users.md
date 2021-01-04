---
title: Felhasználók importálása az Azure Active Directory-szolgáltatásból
description: Ezzel az eljárással a rendszergazdák manuálisan importálhatnak felhasználókat nagy számú felhasználót importálhatnak az Azure Active Directory rendszerből.
author: peakerbl
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b6666310309817ff30ccb3902721880b829ee0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679814"
---
# <a name="import-users-from-azure-active-directory"></a><span data-ttu-id="39cf9-103">Felhasználók importálása az Azure Active Directory-szolgáltatásból</span><span class="sxs-lookup"><span data-stu-id="39cf9-103">Import users from Azure Active Directory</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a><span data-ttu-id="39cf9-104">Kiválasztott felhasználók importálása</span><span class="sxs-lookup"><span data-stu-id="39cf9-104">Import select users</span></span>

<span data-ttu-id="39cf9-105">Ezzel az eljárással a rendszergazdák kiválasztott felhasználókat importáljanak az Azure Active Directory (Azure AD) rendszerből.</span><span class="sxs-lookup"><span data-stu-id="39cf9-105">This procedure can be used by system administrators to import select users from Azure Active Directory (Azure AD).</span></span>

1. <span data-ttu-id="39cf9-106">A rendszer az aktuális munkamenet vállalatát importálja alapértelmezett vállalatként.</span><span class="sxs-lookup"><span data-stu-id="39cf9-106">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="39cf9-107">A felhasználók importálása előtt módosítsa az aktuális vállalatot, ha az szükséges.</span><span class="sxs-lookup"><span data-stu-id="39cf9-107">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="39cf9-108">Ugrás a **Rendszerfelügyelet > Felhasználók > Felhasználók** elemre.</span><span class="sxs-lookup"><span data-stu-id="39cf9-108">Go to **System administration > Users > User** s.</span></span>
3. <span data-ttu-id="39cf9-109">Kattintson a **Felhasználók importálása** elemre.</span><span class="sxs-lookup"><span data-stu-id="39cf9-109">Click **Import users**.</span></span>
4. <span data-ttu-id="39cf9-110">Jelölje ki az importálandó felhasználókat, és válassza a **Felhasználók importálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39cf9-110">Select the users that should be imported and select **Import users**.</span></span>

<span data-ttu-id="39cf9-111">Az importálás befejezése után szerepköröket kell hozzárendelni a felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="39cf9-111">After import is completed it will be required to assign roles to users.</span></span>

## <a name="import-users-in-bulk"></a><span data-ttu-id="39cf9-112">Felhasználók tömeges importálása</span><span class="sxs-lookup"><span data-stu-id="39cf9-112">Import users in bulk</span></span>

<span data-ttu-id="39cf9-113">Ezzel az eljárással a rendszergazdák nagy számú felhasználót importálhatnak az Azure Active Directory rendszerből.</span><span class="sxs-lookup"><span data-stu-id="39cf9-113">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>
<span data-ttu-id="39cf9-114">Ne feledje, hogy a Kötegelt importálás beállítás használatakor nem lehet felhasználókat kijelölni.</span><span class="sxs-lookup"><span data-stu-id="39cf9-114">Note that it is not possible to select users when using the Batch import option.</span></span>

## <a name="run-the-import-as-a-batch-job"></a><span data-ttu-id="39cf9-115">Az importálás futtatása kötegelt feladatként</span><span class="sxs-lookup"><span data-stu-id="39cf9-115">Run the import as a batch job</span></span>
1. <span data-ttu-id="39cf9-116">A rendszer az aktuális munkamenet vállalatát importálja alapértelmezett vállalatként.</span><span class="sxs-lookup"><span data-stu-id="39cf9-116">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="39cf9-117">A felhasználók importálása előtt módosítsa az aktuális vállalatot, ha az szükséges.</span><span class="sxs-lookup"><span data-stu-id="39cf9-117">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="39cf9-118">Ugrás a **Rendszerfelügyelet > Felhasználók > Felhasználók** elemre.</span><span class="sxs-lookup"><span data-stu-id="39cf9-118">Go to **System administration > Users > Users**.</span></span>
3. <span data-ttu-id="39cf9-119">Kattintson a **Kötegelt importálás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39cf9-119">Click **Batch import**.</span></span>
4. <span data-ttu-id="39cf9-120">Bontsa ki a **Futtatás a háttérben** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="39cf9-120">Expand the **Run in the background** section.</span></span>
4. <span data-ttu-id="39cf9-121">Válassza az **Igen** lehetőséget a **Kötegelt feldolgozás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="39cf9-121">Select \*\*Yes in the **Batch processing** field.</span></span>
6. <span data-ttu-id="39cf9-122">A **Kötegcsoport** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="39cf9-122">In the **Batch group** field, enter or select a value.</span></span> <span data-ttu-id="39cf9-123">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="39cf9-123">This is an optional step.</span></span>  
7. <span data-ttu-id="39cf9-124">Válassza ki az **Igen** lehetőséget a **Személyes** mezőben.</span><span class="sxs-lookup"><span data-stu-id="39cf9-124">Select **Yes** in the **Private** field.</span></span> <span data-ttu-id="39cf9-125">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="39cf9-125">This is an optional step.</span></span>  
8. <span data-ttu-id="39cf9-126">Válassza az **Igen** lehetőséget a **Kritikus feladat** mezőben.</span><span class="sxs-lookup"><span data-stu-id="39cf9-126">Select **Yes** in the **Critical job** field.</span></span> <span data-ttu-id="39cf9-127">b Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="39cf9-127">bThis is an optional step.</span></span>  
9. <span data-ttu-id="39cf9-128">Válasszon ki egy lehetőséget a \*\*Figyelési kategória mezőben.</span><span class="sxs-lookup"><span data-stu-id="39cf9-128">In the \*\*Monitoring category field, select an option.</span></span>
10. <span data-ttu-id="39cf9-129">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="39cf9-129">Click **OK**.</span></span>

<span data-ttu-id="39cf9-130">Az importálás befejezése után szerepköröket kell hozzárendelni a felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="39cf9-130">After import is completed, it will be required to assign roles to users.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="39cf9-131">Futtatás védőfalkörnyezetben</span><span class="sxs-lookup"><span data-stu-id="39cf9-131">Run in a sandbox environment</span></span>
1. <span data-ttu-id="39cf9-132">Válassza a **Kötegelt importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39cf9-132">Select **Batch import**.</span></span>
2. <span data-ttu-id="39cf9-133">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39cf9-133">Select **OK**.</span></span>
