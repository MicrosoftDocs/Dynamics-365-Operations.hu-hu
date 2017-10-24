--- 
title: "Termelési folyamat verziójának deaktiválása"
description: "Ha már nincs szükség egy aktív termelésifolyamat-verzióra, inaktiválható."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 4a7eee6617e12d59a3d06207f5f6b58c93e28240
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="bf16a-103">Termelési folyamat verziójának deaktiválása</span><span class="sxs-lookup"><span data-stu-id="bf16a-103">Deactivate a production flow version</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bf16a-104">Ha már nincs szükség egy aktív termelésifolyamat-verzióra, inaktiválható.</span><span class="sxs-lookup"><span data-stu-id="bf16a-104">When an active production flow version is no longer needed, it can be deactivated.</span></span> <span data-ttu-id="bf16a-105">A beállítás használata csak akkor ajánlott, ha az összes kanbanszabály és -tevékenység befejeződött, és nem lesznek újra aktiválva.</span><span class="sxs-lookup"><span data-stu-id="bf16a-105">You should only use this option if all kanban rules and activities have ended and will not be activated again.</span></span> <span data-ttu-id="bf16a-106">Fontos megjegyezni, hogy a rendszer a termelésifolyamat-verzióhoz kapcsolódó összes kanbanszabály lejárati dátumát frissíti az aktuális dátummal és idővel.</span><span class="sxs-lookup"><span data-stu-id="bf16a-106">Note that the expiry date of all kanban rules related to this production flow version will be updated with the current date and time.</span></span> 

<span data-ttu-id="bf16a-107">Egy aktív termelésifolyamat-verzió módosításához vegye fontolóra az aktív verzió lejárati dátumának beállítását, majd egy új verzió létrehozását.</span><span class="sxs-lookup"><span data-stu-id="bf16a-107">To modify an active production flow version, consider setting an expiry date for the active version and create a new version.</span></span> <span data-ttu-id="bf16a-108">Ez lehetővé teszi a termelési műveletek folyatását az új verzió és a kapcsolódó kanbanszabályok előkészítésével párhuzamosan.</span><span class="sxs-lookup"><span data-stu-id="bf16a-108">This will allow you to continue your production operations while preparing the new version and related kanban rules.</span></span> 

<span data-ttu-id="bf16a-109">Az aktív termelésifolyamat-verzió lejáratának kikényszerítéséhez be kell állítani egy lejárati dátumot.</span><span class="sxs-lookup"><span data-stu-id="bf16a-109">To expire an active production flow version, you need to set an expiry date.</span></span> <span data-ttu-id="bf16a-110">Ebben az értelemben az inaktiválás inkább kivétel, mint szabály.</span><span class="sxs-lookup"><span data-stu-id="bf16a-110">In that sense, deactivation is more like an exception than a rule.</span></span> 

<span data-ttu-id="bf16a-111">Az eljáráshoz szükség van egy termelési folyamatra, amelynek a verziója inaktiválható.</span><span class="sxs-lookup"><span data-stu-id="bf16a-111">For this procedure you need a production flow with a version that can be deactivated.</span></span> <span data-ttu-id="bf16a-112">Ezt csak akkor próbálja meg éles környezetben, ha biztos abban, hogy a verzió teljesen elavult.</span><span class="sxs-lookup"><span data-stu-id="bf16a-112">Do not try this in a production environment unless you are 100% positive that the version is fully obsolete.</span></span>


## <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="bf16a-113">Termelési folyamat verziójának deaktiválása</span><span class="sxs-lookup"><span data-stu-id="bf16a-113">Deactivate a production flow version</span></span>
1. <span data-ttu-id="bf16a-114">Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bf16a-114">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="bf16a-115">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="bf16a-115">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="bf16a-116">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="bf16a-116">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bf16a-117">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="bf16a-117">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="bf16a-118">Kattintson az Inaktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="bf16a-118">Click Deactivate.</span></span>
    * <span data-ttu-id="bf16a-119">Ne folytassa, ha nem teljesen biztos abban, hogy a termelési folyamat verziója elavult.</span><span class="sxs-lookup"><span data-stu-id="bf16a-119">Do not proceed if you are not 100% positive that this production flow version is obsolete.</span></span> <span data-ttu-id="bf16a-120">Az OK gombra kattintva az összes aktív kanbanszabály lejár, és azonnal leáll a termelésifolyamat-verzió összes termelési és feltöltési tevékenysége.</span><span class="sxs-lookup"><span data-stu-id="bf16a-120">Clicking Ok will expire all active kanban rules and put an immediate stop to all production and replenishment activities of this production flow version.</span></span>  
6. <span data-ttu-id="bf16a-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="bf16a-121">Click OK.</span></span>


