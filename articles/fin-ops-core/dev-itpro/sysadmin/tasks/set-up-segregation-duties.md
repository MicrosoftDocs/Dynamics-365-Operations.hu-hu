---
title: Feladatkörök szétválasztásának beállítása
description: Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához.
author: maertenm
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 47747cba7f83d0b43a284750cff232824e00053a
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982406"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="babb6-103">Feladatkörök szétválasztásának beállítása</span><span class="sxs-lookup"><span data-stu-id="babb6-103">Set up segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="babb6-104">Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához.</span><span class="sxs-lookup"><span data-stu-id="babb6-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="babb6-105">Ezt a fogalmat a feladatkörök szétválasztásának nevezzük.</span><span class="sxs-lookup"><span data-stu-id="babb6-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="babb6-106">Például nem biztos, hogy ugyanannak a személynek kell az árut átvennie és a szállítói kifizetést feldolgoznia.</span><span class="sxs-lookup"><span data-stu-id="babb6-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="babb6-107">A feladatkörök szétválasztása segít a csalás kockázatának csökkentésében, illetve a hibák és a szabálytalanságok észlelésében.</span><span class="sxs-lookup"><span data-stu-id="babb6-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="babb6-108">Használhatja a feladatkörök szétválasztását a belső ellenőrzési irányelvek végrehajtásához is.</span><span class="sxs-lookup"><span data-stu-id="babb6-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="babb6-109">A szabály létrehozásához hajtsa végre a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="babb6-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="babb6-110">Csak egy rendszergazda hajthatja végre ezt a műveletet.</span><span class="sxs-lookup"><span data-stu-id="babb6-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="babb6-111">Ez az eljárás a DAT bemutatócéggel jött létre.</span><span class="sxs-lookup"><span data-stu-id="babb6-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="babb6-112">Lépjen a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Biztonság > Feladatkörök szétválasztása > Feladatkörök szétválasztási szabályai** részre.</span><span class="sxs-lookup"><span data-stu-id="babb6-112">Go to **Navigation pane > Modules > System administration > Security > Segregation of duties > Segregation of duties rules** .</span></span>
2. <span data-ttu-id="babb6-113">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="babb6-113">Click **New** .</span></span>
3. <span data-ttu-id="babb6-114">A **Név** mezőben adja meg a szabályhoz tartozó értéket.</span><span class="sxs-lookup"><span data-stu-id="babb6-114">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="babb6-115">Az **Első feladat** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="babb6-115">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="babb6-116">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="babb6-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="babb6-117">Válassza ki azt az első feladatot, amelyet a szabály határoz meg.</span><span class="sxs-lookup"><span data-stu-id="babb6-117">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="babb6-118">A **Második feladat** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="babb6-118">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="babb6-119">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="babb6-119">In the list, find and select the desired record.</span></span> <span data-ttu-id="babb6-120">Válassza ki azt a második feladatot, amelyet a szabály határoz meg.</span><span class="sxs-lookup"><span data-stu-id="babb6-120">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="babb6-121">Válasszon egy lehetőséget a **Súlyosság** mezőben.</span><span class="sxs-lookup"><span data-stu-id="babb6-121">In the **Severity** field, select an option.</span></span> <span data-ttu-id="babb6-122">Válassza ki azt a kockázatot, amely akkor lép fel, amikor ugyanaz a felhasználó vagy szerepkör hajtja végre mindkét feladatot.</span><span class="sxs-lookup"><span data-stu-id="babb6-122">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="babb6-123">Írjon be egy értéket a **Biztonsági kockázat** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="babb6-123">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="babb6-124">Írja be a biztonsági kockázat leírását.</span><span class="sxs-lookup"><span data-stu-id="babb6-124">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="babb6-125">Írjon be egy értéket a **Biztonsági kockázatcsökkentés** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="babb6-125">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="babb6-126">Írja le a műveleteket, amelyeket a biztonsági kockázat enyhítése érdekében vezet be.</span><span class="sxs-lookup"><span data-stu-id="babb6-126">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="babb6-127">A kockázatot enyhítheti például úgy, hogy részletesebb áttekintés ad a folyamatnak, havi vezetői ellenőrzést vezet be, vagy más részlegekkel is megoszt erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="babb6-127">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="babb6-128">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="babb6-128">Click **Save** .</span></span>

