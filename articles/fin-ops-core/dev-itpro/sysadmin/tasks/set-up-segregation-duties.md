---
title: Feladatkörök szétválasztásának beállítása
description: Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához.
author: peakerbl
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1c1521d6bbbe12964fef0942fcc4943f12a4360a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562497"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="b4935-103">Feladatkörök szétválasztásának beállítása</span><span class="sxs-lookup"><span data-stu-id="b4935-103">Set up segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b4935-104">Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához.</span><span class="sxs-lookup"><span data-stu-id="b4935-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="b4935-105">Ezt a fogalmat a feladatkörök szétválasztásának nevezzük.</span><span class="sxs-lookup"><span data-stu-id="b4935-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="b4935-106">Például nem biztos, hogy ugyanannak a személynek kell az árut átvennie és a szállítói kifizetést is feldolgoznia.</span><span class="sxs-lookup"><span data-stu-id="b4935-106">For example, you might not want the same person to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="b4935-107">A feladatkörök szétválasztása segít a csalás kockázatának csökkentésében, illetve a hibák és a szabálytalanságok észlelésében.</span><span class="sxs-lookup"><span data-stu-id="b4935-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="b4935-108">Használhatja a feladatkörök szétválasztását a belső ellenőrzési irányelvek végrehajtásához is.</span><span class="sxs-lookup"><span data-stu-id="b4935-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="b4935-109">A szabály létrehozásához hajtsa végre a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b4935-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="b4935-110">Csak egy rendszergazda hajthatja végre ezt a műveletet.</span><span class="sxs-lookup"><span data-stu-id="b4935-110">You must be a system administrator to complete the procedure.</span></span>

1. <span data-ttu-id="b4935-111">Ugrás a **Rendszerfelügyelet** > **Biztonság** > **Feladatkörök szétválasztása** > **Feladatkör-szétválasztási szabályok** elemre.</span><span class="sxs-lookup"><span data-stu-id="b4935-111">Go to **System administration** > **Security** > **Segregation of duties** > **Segregation of duties rules**.</span></span>
2. <span data-ttu-id="b4935-112">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="b4935-112">Click **New**.</span></span>
3. <span data-ttu-id="b4935-113">A **Név** mezőben adja meg a szabályhoz tartozó értéket.</span><span class="sxs-lookup"><span data-stu-id="b4935-113">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="b4935-114">Az **Első feladat** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b4935-114">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="b4935-115">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b4935-115">In the list, find and select the desired record.</span></span> <span data-ttu-id="b4935-116">Válassza ki azt az első feladatot, amelyet a szabály határoz meg.</span><span class="sxs-lookup"><span data-stu-id="b4935-116">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="b4935-117">A **Második feladat** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b4935-117">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="b4935-118">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b4935-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="b4935-119">Válassza ki azt a második feladatot, amelyet a szabály határoz meg.</span><span class="sxs-lookup"><span data-stu-id="b4935-119">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="b4935-120">Válasszon egy lehetőséget a **Súlyosság** mezőben.</span><span class="sxs-lookup"><span data-stu-id="b4935-120">In the **Severity** field, select an option.</span></span> <span data-ttu-id="b4935-121">Válassza ki azt a kockázatot, amely akkor lép fel, amikor ugyanaz a felhasználó vagy szerepkör hajtja végre mindkét feladatot.</span><span class="sxs-lookup"><span data-stu-id="b4935-121">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="b4935-122">Írjon be egy értéket a **Biztonsági kockázat** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b4935-122">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="b4935-123">Írja be a biztonsági kockázat leírását.</span><span class="sxs-lookup"><span data-stu-id="b4935-123">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="b4935-124">Írjon be egy értéket a **Biztonsági kockázatcsökkentés** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b4935-124">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="b4935-125">Írja le a műveleteket, amelyeket a biztonsági kockázat enyhítése érdekében vezet be.</span><span class="sxs-lookup"><span data-stu-id="b4935-125">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="b4935-126">A kockázatot enyhítheti például úgy, hogy részletesebb áttekintés ad a folyamatnak, havi vezetői ellenőrzést vezet be, vagy más részlegekkel is megoszt erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="b4935-126">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="b4935-127">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="b4935-127">Click **Save**.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="b4935-128">A szabályok létrehozása során a rendszer nem ellenőrzi a feladatkörök szétválasztására vonatkozó szabályoknak való megfelelést.</span><span class="sxs-lookup"><span data-stu-id="b4935-128">Compliance with the rules for segregation of duties is not verified when you create a rule.</span></span> <span data-ttu-id="b4935-129">Létrehozhat olyan szabályt, amely ütközik a meglévő szerepkörökkel.</span><span class="sxs-lookup"><span data-stu-id="b4935-129">You can create a rule that creates a conflict for existing roles.</span></span> <span data-ttu-id="b4935-130">A felhasználói szerepkör meglévő hozzárendelései az új szabállyal is ütközhetnek.</span><span class="sxs-lookup"><span data-stu-id="b4935-130">Existing user role assignments can also be in conflict with the new rule.</span></span> <span data-ttu-id="b4935-131">A szabályok létrehozása vagy módosítása után ellenőriznie kell a megfelelést.</span><span class="sxs-lookup"><span data-stu-id="b4935-131">You must validate compliance after you create or modify a rule.</span></span> <span data-ttu-id="b4935-132">További információk: [Feladatkörök szétválasztásával kapcsolatos ütközések azonosítása és feloldása](identify-resolve-conflicts-segregation-duties.md)</span><span class="sxs-lookup"><span data-stu-id="b4935-132">For more information, see [Identify and resolve conflicts in segregation of duties](identify-resolve-conflicts-segregation-duties.md)</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]