---
title: Felhasználók importálása az Azure Active Directory-szolgáltatásból
description: Ezzel az eljárással a rendszergazdák manuálisan importálhatnak felhasználókat nagy számú felhasználót importálhatnak az Azure Active Directory rendszerből.
author: peakerbl
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c2600ad8f441e6b73b143c27afa08ad0a5c2748
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5571005"
---
# <a name="import-users-from-azure-active-directory"></a><span data-ttu-id="4a546-103">Felhasználók importálása az Azure Active Directory-szolgáltatásból</span><span class="sxs-lookup"><span data-stu-id="4a546-103">Import users from Azure Active Directory</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a><span data-ttu-id="4a546-104">Kiválasztott felhasználók importálása</span><span class="sxs-lookup"><span data-stu-id="4a546-104">Import select users</span></span>

<span data-ttu-id="4a546-105">Ezzel az eljárással a rendszergazdák kiválasztott felhasználókat importáljanak az Azure Active Directory (Azure AD) rendszerből.</span><span class="sxs-lookup"><span data-stu-id="4a546-105">This procedure can be used by system administrators to import select users from Azure Active Directory (Azure AD).</span></span>

1. <span data-ttu-id="4a546-106">A rendszer az aktuális munkamenet vállalatát importálja alapértelmezett vállalatként.</span><span class="sxs-lookup"><span data-stu-id="4a546-106">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="4a546-107">A felhasználók importálása előtt módosítsa az aktuális vállalatot, ha az szükséges.</span><span class="sxs-lookup"><span data-stu-id="4a546-107">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="4a546-108">Ugrás a **Rendszerfelügyelet > Felhasználók > Felhasználók** elemre.</span><span class="sxs-lookup"><span data-stu-id="4a546-108">Go to **System administration > Users > User** s.</span></span>
3. <span data-ttu-id="4a546-109">Kattintson a **Felhasználók importálása** elemre.</span><span class="sxs-lookup"><span data-stu-id="4a546-109">Click **Import users**.</span></span>
4. <span data-ttu-id="4a546-110">Jelölje ki az importálandó felhasználókat, és válassza a **Felhasználók importálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4a546-110">Select the users that should be imported and select **Import users**.</span></span>

<span data-ttu-id="4a546-111">Az importálás befejezése után szerepköröket kell hozzárendelni a felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="4a546-111">After import is completed it will be required to assign roles to users.</span></span>

## <a name="import-users-in-bulk"></a><span data-ttu-id="4a546-112">Felhasználók tömeges importálása</span><span class="sxs-lookup"><span data-stu-id="4a546-112">Import users in bulk</span></span>

<span data-ttu-id="4a546-113">Ezzel az eljárással a rendszergazdák nagy számú felhasználót importálhatnak az Azure Active Directory rendszerből.</span><span class="sxs-lookup"><span data-stu-id="4a546-113">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>
<span data-ttu-id="4a546-114">Ne feledje, hogy a Kötegelt importálás beállítás használatakor nem lehet felhasználókat kijelölni.</span><span class="sxs-lookup"><span data-stu-id="4a546-114">Note that it is not possible to select users when using the Batch import option.</span></span>

## <a name="run-the-import-as-a-batch-job"></a><span data-ttu-id="4a546-115">Az importálás futtatása kötegelt feladatként</span><span class="sxs-lookup"><span data-stu-id="4a546-115">Run the import as a batch job</span></span>
1. <span data-ttu-id="4a546-116">A rendszer az aktuális munkamenet vállalatát importálja alapértelmezett vállalatként.</span><span class="sxs-lookup"><span data-stu-id="4a546-116">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="4a546-117">A felhasználók importálása előtt módosítsa az aktuális vállalatot, ha az szükséges.</span><span class="sxs-lookup"><span data-stu-id="4a546-117">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="4a546-118">Ugrás a **Rendszerfelügyelet > Felhasználók > Felhasználók** elemre.</span><span class="sxs-lookup"><span data-stu-id="4a546-118">Go to **System administration > Users > Users**.</span></span>
3. <span data-ttu-id="4a546-119">Kattintson a **Kötegelt importálás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4a546-119">Click **Batch import**.</span></span>
4. <span data-ttu-id="4a546-120">Bontsa ki a **Futtatás a háttérben** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4a546-120">Expand the **Run in the background** section.</span></span>
4. <span data-ttu-id="4a546-121">Válassza az **Igen** lehetőséget a **Kötegelt feldolgozás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4a546-121">Select **Yes** in the **Batch processing** field.</span></span>
6. <span data-ttu-id="4a546-122">A **Kötegcsoport** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4a546-122">In the **Batch group** field, enter or select a value.</span></span> <span data-ttu-id="4a546-123">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="4a546-123">This is an optional step.</span></span>  
7. <span data-ttu-id="4a546-124">Válassza ki az **Igen** lehetőséget a **Személyes** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4a546-124">Select **Yes** in the **Private** field.</span></span> <span data-ttu-id="4a546-125">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="4a546-125">This is an optional step.</span></span>  
8. <span data-ttu-id="4a546-126">Válassza az **Igen** lehetőséget a **Kritikus feladat** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4a546-126">Select **Yes** in the **Critical job** field.</span></span> <span data-ttu-id="4a546-127">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="4a546-127">This is an optional step.</span></span>  
9. <span data-ttu-id="4a546-128">Válasszon ki egy lehetőséget a **Figyelési kategória** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4a546-128">In the **Monitoring category** field, select an option.</span></span>
10. <span data-ttu-id="4a546-129">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="4a546-129">Click **OK**.</span></span>

<span data-ttu-id="4a546-130">Az importálás befejezése után szerepköröket kell hozzárendelni a felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="4a546-130">After import is completed, it will be required to assign roles to users.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="4a546-131">Futtatás védőfalkörnyezetben</span><span class="sxs-lookup"><span data-stu-id="4a546-131">Run in a sandbox environment</span></span>
1. <span data-ttu-id="4a546-132">Válassza a **Kötegelt importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4a546-132">Select **Batch import**.</span></span>
2. <span data-ttu-id="4a546-133">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4a546-133">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]