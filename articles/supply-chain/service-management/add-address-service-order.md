---
title: "Cím hozzáadása szolgáltatási rendeléshez"
description: "Ez a témakör bemutatja, hogyan lehet hozzáadni egy vevő címét a szervizrendeléshez."
author: YuyuScheller
manager: AnnBe
ms.date: 05/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e6dfa27b2101e84fbab678e781c26126cf1db898
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="add-an-address-to-a-service-order"></a><span data-ttu-id="b17e0-103">Cím hozzáadása szolgáltatási rendeléshez</span><span class="sxs-lookup"><span data-stu-id="b17e0-103">Add an address to a service order</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="b17e0-104">Ez a témakör bemutatja, hogyan lehet hozzáadni egy vevő címét a szervizrendeléshez.</span><span class="sxs-lookup"><span data-stu-id="b17e0-104">This topic describes how to add a customer address to a service order.</span></span> <span data-ttu-id="b17e0-105">A szervizrendelések létrehozásakor abból a projektből veszi át a program a címadatokat, amelyhez a szervizrendelés csatolva van.</span><span class="sxs-lookup"><span data-stu-id="b17e0-105">When you create a service order, the address information is transferred from the project that the service order is attached to.</span></span> <span data-ttu-id="b17e0-106">Azonban kiválaszthat egy másodlagos helyet azon címek közül, amelyek már szerepelnek a Microsoft Dynamics AX rendszerben vevők, szállítók, helyek, raktár, szolgáltatási rendelések és projektek esetén.</span><span class="sxs-lookup"><span data-stu-id="b17e0-106">However, you can select an alternative location from addresses that are already entered in Microsoft Dynamics AX for customers, vendors, sites, warehouses, service orders, and projects.</span></span>

<span data-ttu-id="b17e0-107">Létre is hozhat új címeket.</span><span class="sxs-lookup"><span data-stu-id="b17e0-107">You can also create a new address.</span></span> <span data-ttu-id="b17e0-108">Alapértelmezés szerint az új cím átkerül a projekthez.</span><span class="sxs-lookup"><span data-stu-id="b17e0-108">By default, the new address is transferred to the project.</span></span> <span data-ttu-id="b17e0-109">Azonban megadhatja, hogy az új címnek csak a szolgáltatás jelenlegi példánya esetén van jelentősége.</span><span class="sxs-lookup"><span data-stu-id="b17e0-109">However, you can specify that the new address is only relevant for this instance of the service.</span></span> <span data-ttu-id="b17e0-110">Ebben az esetben az új cím nem kerül át a projekthez.</span><span class="sxs-lookup"><span data-stu-id="b17e0-110">If you do, the new address is not transferred to the project.</span></span>

## <a name="create-a-customer-address-for-a-service-order"></a><span data-ttu-id="b17e0-111">Vevő cím létrehozása egy szervizrendeléshez</span><span class="sxs-lookup"><span data-stu-id="b17e0-111">Create a customer address for a service order</span></span>

<span data-ttu-id="b17e0-112">Egy cím hozzáadásához a szervizrendeléshez, tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="b17e0-112">To add an address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="b17e0-113">Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.</span><span class="sxs-lookup"><span data-stu-id="b17e0-113">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="b17e0-114">Nyissa meg azt a szervizrendelést, amelyhez címet szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="b17e0-114">Open the service order that you want to create an address for.</span></span>

3.  <span data-ttu-id="b17e0-115">Kattintson a **Műveleti ablaktáblában** lévő **Szerkesztés** lehetőségre, majd válassza a **Fejlécnézet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b17e0-115">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="b17e0-116">A **Cím** gyorslapon kattintson a **Cím hozzáadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b17e0-116">On the **Address** FastTab, click **Add address**.</span></span>

5.  <span data-ttu-id="b17e0-117">Az **Új cím** képernyőn adjon meg egy egyedi nevet a cím számára, majd töltse ki a többi mezőt.</span><span class="sxs-lookup"><span data-stu-id="b17e0-117">In the **New address** form, enter a unique name for the address and complete the remaining fields.</span></span> 
    

    > [!WARNING]
    > <P><span data-ttu-id="b17e0-118">Ha egy létező cím nevével megegyező nevet ad meg, akkor a többi mezőbe beírt adatok felülírják a már meglévő címhez tartozó adatokat.</span><span class="sxs-lookup"><span data-stu-id="b17e0-118">If you enter the same name as an existing address, the information that you enter in the remaining fields will overwrite information for the existing address.</span></span></P>


6.  <span data-ttu-id="b17e0-119">Kattintson az **OK** gombra az új címnek a szervizrendeléshez másolásához.</span><span class="sxs-lookup"><span data-stu-id="b17e0-119">Click **OK** to copy the new address to your service order.</span></span>

## <a name="specify-an-alternative-address-on-a-service-order"></a><span data-ttu-id="b17e0-120">Másodlagos cím megadása egy szervizrendelésen</span><span class="sxs-lookup"><span data-stu-id="b17e0-120">Specify an alternative address on a service order</span></span>

<span data-ttu-id="b17e0-121">Egy másodlagos cím hozzáadásához a szervizrendeléshez, tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="b17e0-121">To add an alternative address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="b17e0-122">Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.</span><span class="sxs-lookup"><span data-stu-id="b17e0-122">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="b17e0-123">Nyissa meg azt a szervizrendelést, amelyhez másodlagos címet szeretne megadni.</span><span class="sxs-lookup"><span data-stu-id="b17e0-123">Open the service order that you want to enter an alternative address for.</span></span>

3.  <span data-ttu-id="b17e0-124">Kattintson a **Műveleti ablaktáblában** lévő **Szerkesztés** lehetőségre, majd válassza a **Fejlécnézet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b17e0-124">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="b17e0-125">A **Cím** gyorslapon kattintson az **Egyéb cím** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b17e0-125">On the **Address** FastTab, click **Other address**.</span></span>

5.  <span data-ttu-id="b17e0-126">A **Cím kiválasztása** űrlapon, a **Bejegyzéstípus** mezőben válassza ki a **Szervizrendelések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b17e0-126">In the **Address selection** form, in the **Record type** field, select **Service orders**.</span></span>

6.  <span data-ttu-id="b17e0-127">Válasszon ki egy címet, majd kattintson az **OK** gombra a szervizrendeléshez való másoláshoz.</span><span class="sxs-lookup"><span data-stu-id="b17e0-127">Select an address, and then click **OK** to copy it to your service order.</span></span>


  



