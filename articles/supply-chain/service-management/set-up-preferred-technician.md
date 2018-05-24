---
title: "Preferált technikus beállítása"
description: "Szolgáltatási szerződéshez vagy szervizrendeléshez bármelyik dolgozót kiválaszthatja preferált technikusként."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable, SMADispatchBoard
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
ms.openlocfilehash: 390e436b63fdfe82e0b743e7f286cae3bb29be55
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---


# <a name="set-up-a-preferred-technician"></a><span data-ttu-id="951a4-103">Preferált technikus beállítása</span><span class="sxs-lookup"><span data-stu-id="951a4-103">Set up a preferred technician</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="951a4-104">Szolgáltatási szerződéshez vagy szervizrendeléshez bármelyik dolgozót kiválaszthatja preferált technikusként.</span><span class="sxs-lookup"><span data-stu-id="951a4-104">You can select any worker as a preferred technician for a service agreement or service order.</span></span> <span data-ttu-id="951a4-105">Ugyanakkor a dolgozót érdemes felvenni a megfelelő kiszálló csoportba, hogy szerepeljen a **Diszpécserközpont** listáján.</span><span class="sxs-lookup"><span data-stu-id="951a4-105">However, it is a good idea to add the worker to the appropriate dispatch team so that the worker is included on the **Dispatch board**.</span></span>

## <a name="assign-employee-to-a-dispatch-team"></a><span data-ttu-id="951a4-106">Alkalmazott hozzárendelése kiszálló csoporthoz</span><span class="sxs-lookup"><span data-stu-id="951a4-106">Assign employee to a dispatch team</span></span>

1.  <span data-ttu-id="951a4-107">Kattintson az **Emberi erőforrások** \> **Közös** \> **Dolgozók** \> **Dolgozók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="951a4-107">Click **Human resources** \> **Common** \> **Workers** \> **Workers**.</span></span> <span data-ttu-id="951a4-108">A dolgozó adatlapjának megnyitásához kattintson duplán a dolgozóra.</span><span class="sxs-lookup"><span data-stu-id="951a4-108">Double-click a worker to open the worker details page.</span></span> <span data-ttu-id="951a4-109">A **Műveleti ablakban** kattintson a **Beállítás** \> **Kiszálló csoport** elemre a **Kiszálló dolgozók** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="951a4-109">On the **Action Pane**, click **Setup** \>**Dispatch team** to open the **Dispatch workers** form.</span></span>

2.  <span data-ttu-id="951a4-110">A **Kiszálló csoport** mezőben válassza ki, hogy melyik csoporthoz szeretné hozzárendelni a dolgozót.</span><span class="sxs-lookup"><span data-stu-id="951a4-110">In the **Dispatch team** field, select the team to assign the worker to.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a><span data-ttu-id="951a4-111">Javasolt technikus hozzárendelése a szolgáltatási szerződéshez</span><span class="sxs-lookup"><span data-stu-id="951a4-111">Assign a preferred technician to a service agreement</span></span>

1.  <span data-ttu-id="951a4-112">Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="951a4-112">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span> <span data-ttu-id="951a4-113">Kattintson duplán a szolgáltatási szerződésre a részleteket tartalmazó képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="951a4-113">Double-click a service agreement to open the details form.</span></span>

2.  <span data-ttu-id="951a4-114">Az **Általános** lapon válassza a **Preferált technikus** mezőt, majd adja meg a megfelelő kiszálló csoport egy tagját a szolgáltatási szerződés javasolt technikusaként.</span><span class="sxs-lookup"><span data-stu-id="951a4-114">On the **General** tab, select the **Preferred technician** field, and then select a member of the appropriate dispatch team as the preferred technician for the service agreement.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-order"></a><span data-ttu-id="951a4-115">Javasolt technikus hozzárendelése a szervizrendeléshez</span><span class="sxs-lookup"><span data-stu-id="951a4-115">Assign a preferred technician to a service order</span></span>

1.  <span data-ttu-id="951a4-116">Kattintson a következőkre: **Szolgáltatáskezelés** \> **Rendszeres** \> **Diszpécserközpont**.</span><span class="sxs-lookup"><span data-stu-id="951a4-116">Click **Service management** \> **Periodic** \> **Dispatch board**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="951a4-117">A <STRONG>Diszpécserközpont</STRONG> képernyőn adja meg a megjeleníteni kívánt küldési tevékenységek dátumtartományát.</span><span class="sxs-lookup"><span data-stu-id="951a4-117">In the <STRONG>Dispatch board</STRONG> form, specify a date range for dispatch activities to view.</span></span> <span data-ttu-id="951a4-118">Állítsa be, hogy megjeleníti-e a lezárt tevékenységeket, illetve azt, hogy csak a saját csoportok tevékenységlistáját jeleníti-e meg, vagy mindazokét, akiknek a megfigyelésére jogosult.</span><span class="sxs-lookup"><span data-stu-id="951a4-118">Also, specify whether to display closed activities and whether to limit the dispatch activity list to teams that you belong to or are authorized to monitor.</span></span> <span data-ttu-id="951a4-119">Kattintson az <STRONG>OK</STRONG> gombra a <STRONG>Diszpécserközpont</STRONG> képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="951a4-119">Click <STRONG>OK</STRONG> to open the <STRONG>Dispatch board</STRONG>.</span></span></P>



2.  <span data-ttu-id="951a4-120">Válassza ki a módosítandó szerviztevékenység sort.</span><span class="sxs-lookup"><span data-stu-id="951a4-120">Select the line of the service activity to modify.</span></span>

3.  <span data-ttu-id="951a4-121">A **Kapcsolódó** lap **Dolgozó** listájában rendelje hozzá a megfelelő kiszálló csoport egyik tagját a szervizhívás javasolt technikusaként.</span><span class="sxs-lookup"><span data-stu-id="951a4-121">On the **Related** tab, use the **Worker** list to assign a member of the appropriate dispatch team as the preferred technician for the service call.</span></span>

## <a name="see-also"></a><span data-ttu-id="951a4-122">Lásd még</span><span class="sxs-lookup"><span data-stu-id="951a4-122">See also</span></span>

[<span data-ttu-id="951a4-123">Szolgáltatási szerződések</span><span class="sxs-lookup"><span data-stu-id="951a4-123">Service agreements</span></span>](service-agreements.md)

[<span data-ttu-id="951a4-124">Szervizrendelések létrehozása manuálisan</span><span class="sxs-lookup"><span data-stu-id="951a4-124">Create service orders manually</span></span>](create-service-orders-manually.md)

<span data-ttu-id="951a4-125">[Szolgáltatási szerződések (képernyő)](https://technet.microsoft.com/en-us/library/aa617823\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="951a4-125">[Service agreements (form)](https://technet.microsoft.com/en-us/library/aa617823\(v=ax.60\))</span></span>
  



