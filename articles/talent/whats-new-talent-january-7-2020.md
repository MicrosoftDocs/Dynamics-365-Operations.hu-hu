---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2020. január 7.)
description: Ez a cikk a Microsoft Dynamics 365 Talent új vagy módosított funkcióit írja le.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461407"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a><span data-ttu-id="31eed-103">Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2020. január 7.)</span><span class="sxs-lookup"><span data-stu-id="31eed-103">What's new or changed in Dynamics 365 Talent (January 7, 2020)</span></span>

<span data-ttu-id="31eed-104">Ez a cikk a Dynamics 365 Talent szolgáltatásban található új vagy módosított funkciókat írja le.</span><span class="sxs-lookup"><span data-stu-id="31eed-104">This article describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="31eed-105">Változások az Attract-ben</span><span class="sxs-lookup"><span data-stu-id="31eed-105">Changes in Attract</span></span>

<span data-ttu-id="31eed-106">A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="31eed-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="31eed-107">Változások az Onboard alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="31eed-107">Changes in Onboard</span></span>

<span data-ttu-id="31eed-108">A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="31eed-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="31eed-109">A Core HR módosításai</span><span class="sxs-lookup"><span data-stu-id="31eed-109">Changes in Core HR</span></span>

<span data-ttu-id="31eed-110">A szakaszban ismertetett módosítások a 8.1.2697-ös buildre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="31eed-110">Changes described in this section apply to build number 8.1.2697.</span></span> <span data-ttu-id="31eed-111">A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="31eed-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a><span data-ttu-id="31eed-112">Nem törölhet olyan alkalmazottakat, akiknél nem szerepelnek a foglalkoztatási rekordok – (386157)</span><span class="sxs-lookup"><span data-stu-id="31eed-112">Can't delete workers that don't have employment records - (386157)</span></span>

<span data-ttu-id="31eed-113">Ez a módosítás hozzáad egy törlési beállítást **Munkanélküli dolgozók** képernyőjéhez.</span><span class="sxs-lookup"><span data-stu-id="31eed-113">This change adds a delete option in the **Workers without employment** form.</span></span> <span data-ttu-id="31eed-114">A dolgozók akkor jelennek meg ezen a képernyőn, ha a dolgozóhoz nem léteznek jövőbeli, aktív vagy múltbeli munkaviszonyok.</span><span class="sxs-lookup"><span data-stu-id="31eed-114">Workers appear in this form when no future, active, or historical employments exist for the worker.</span></span> <span data-ttu-id="31eed-115">Ebben a verzióban a törlés csak a rendszergazdák számára engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="31eed-115">In this release, delete is only enabled for System Administrators.</span></span> <span data-ttu-id="31eed-116">A következő heti kiadásban azonban a biztonsági frissítés minden HR-segéd szerepkörrel rendelkező felhasználó számára lehetővé teszi, hogy a foglalkoztatás nélküli alkalmazottakat eltávolítsa.</span><span class="sxs-lookup"><span data-stu-id="31eed-116">However, in next week's release, security will be updated to allow all users with the HR assistant role to remove employees without employments.</span></span> <span data-ttu-id="31eed-117">Ezeket a változtatásokat manuálisan is elvégezheti a következő lépéseket követve.</span><span class="sxs-lookup"><span data-stu-id="31eed-117">You can also make these changes manually by following the following steps.</span></span>

1. <span data-ttu-id="31eed-118">Ugrás a **Biztonsági konfiguráció** elemre.</span><span class="sxs-lookup"><span data-stu-id="31eed-118">Go to **Security configuration**.</span></span>
2. <span data-ttu-id="31eed-119">A **Jogosultságok** lapon szűrje a **Jogosultságok** listáját a **Dolgozók karbantartása** céljából.</span><span class="sxs-lookup"><span data-stu-id="31eed-119">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>
3. <span data-ttu-id="31eed-120">Válassza a **Hivatkozások** oszlopban a **Megjelenítendő menüelemek** elemet.</span><span class="sxs-lookup"><span data-stu-id="31eed-120">In the **References** column, select **Display menu items**.</span></span>
4. <span data-ttu-id="31eed-121">A **Megjelenítendő menüelemek** közül válassza ki a **HcmWOrkersWithoutEmployment** elemet.</span><span class="sxs-lookup"><span data-stu-id="31eed-121">In **Display menu items**, select **HcmWOrkersWithoutEmployment**.</span></span>
5. <span data-ttu-id="31eed-122">A **Törlési** engedélyt módosítsa Engedélyezre.</span><span class="sxs-lookup"><span data-stu-id="31eed-122">Set the **Delete** permission to Grant.</span></span>
6. <span data-ttu-id="31eed-123">Válassza ki a **Nem közzétett objektumok** lapot.</span><span class="sxs-lookup"><span data-stu-id="31eed-123">Select the **Unpublished objects** tab.</span></span>
7. <span data-ttu-id="31eed-124">Válassza az **Összes közzététele** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="31eed-124">Select **Publish all**.</span></span>
