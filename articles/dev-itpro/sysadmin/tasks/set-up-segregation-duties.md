--- 
title: "Feladatkörök szétválasztásának beállítása"
description: "Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához."
author: maertenm
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 754f28cd2831d8a9a57c408518d240de460b732b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="93193-103">Feladatkörök szétválasztásának beállítása</span><span class="sxs-lookup"><span data-stu-id="93193-103">Set up segregation of duties</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="93193-104">Beállíthat szabályokat a más felhasználók által elvégzendő feladatok elválasztásához.</span><span class="sxs-lookup"><span data-stu-id="93193-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="93193-105">Ezt a fogalmat a feladatkörök szétválasztásának nevezzük.</span><span class="sxs-lookup"><span data-stu-id="93193-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="93193-106">Például nem biztos, hogy ugyanannak a személynek kell az árut átvennie és a szállítói kifizetést feldolgoznia.</span><span class="sxs-lookup"><span data-stu-id="93193-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="93193-107">A feladatkörök szétválasztása segít a csalás kockázatának csökkentésében, illetve a hibák és a szabálytalanságok észlelésében.</span><span class="sxs-lookup"><span data-stu-id="93193-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="93193-108">Használhatja a feladatkörök szétválasztását a belső ellenőrzési irányelvek végrehajtásához is.</span><span class="sxs-lookup"><span data-stu-id="93193-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="93193-109">A szabály létrehozásához hajtsa végre a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="93193-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="93193-110">Csak egy rendszergazda hajthatja végre ezt a műveletet.</span><span class="sxs-lookup"><span data-stu-id="93193-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="93193-111">Ez az eljárás a DAT bemutatócéggel jött létre.</span><span class="sxs-lookup"><span data-stu-id="93193-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="93193-112">Ugrás a Rendszerfelügyelet > Biztonság > Feladatkörök szétválasztása > Feladatkör-szétválasztási szabályok elemre.</span><span class="sxs-lookup"><span data-stu-id="93193-112">Go to System administration > Security > Segregation of duties > Segregation of duties rules.</span></span>
2. <span data-ttu-id="93193-113">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="93193-113">Click New.</span></span>
3. <span data-ttu-id="93193-114">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="93193-114">In the Name field, type a value.</span></span>
    * <span data-ttu-id="93193-115">Adja meg a szabály nevét.</span><span class="sxs-lookup"><span data-stu-id="93193-115">Enter a name for the rule.</span></span>  
4. <span data-ttu-id="93193-116">Az első feladat mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="93193-116">In the First duty field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="93193-117">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="93193-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="93193-118">Válassza ki azt az első feladatot, amelyet a szabály határoz meg.</span><span class="sxs-lookup"><span data-stu-id="93193-118">Select the first duty that is controlled by the rule.</span></span>  
6. <span data-ttu-id="93193-119">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="93193-119">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="93193-120">A második feladat mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="93193-120">In the Second duty field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="93193-121">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="93193-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="93193-122">Válassza ki azt a második feladatot, amelyet a szabály határoz meg.</span><span class="sxs-lookup"><span data-stu-id="93193-122">Select the second duty that is controlled by the rule.</span></span>  
9. <span data-ttu-id="93193-123">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="93193-123">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="93193-124">Válasszon egy lehetőséget a Súlyosság mezőben.</span><span class="sxs-lookup"><span data-stu-id="93193-124">In the Severity field, select an option.</span></span>
    * <span data-ttu-id="93193-125">Válassza ki azt a kockázatot, amely akkor lép fel, amikor ugyanaz a felhasználó vagy szerepkör hajtja végre mindkét feladatot.</span><span class="sxs-lookup"><span data-stu-id="93193-125">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="93193-126">Írjon be egy értéket a Biztonsági kockázat mezőbe.</span><span class="sxs-lookup"><span data-stu-id="93193-126">In the Security risk field, type a value.</span></span>
    * <span data-ttu-id="93193-127">Írja be a biztonsági kockázat leírását.</span><span class="sxs-lookup"><span data-stu-id="93193-127">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="93193-128">Írjon be egy értéket a Biztonsági kockázatcsökkentés mezőbe.</span><span class="sxs-lookup"><span data-stu-id="93193-128">In the Security mitigation field, type a value.</span></span>
    * <span data-ttu-id="93193-129">Írja le a műveleteket, amelyeket a biztonsági kockázat enyhítése érdekében vezet be.</span><span class="sxs-lookup"><span data-stu-id="93193-129">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="93193-130">A kockázatot enyhítheti például úgy, hogy részletesebb áttekintés ad a folyamatnak, havi vezetői ellenőrzést vezet be, vagy más részlegekkel is megoszt erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="93193-130">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>  
13. <span data-ttu-id="93193-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="93193-131">Click Save.</span></span>


