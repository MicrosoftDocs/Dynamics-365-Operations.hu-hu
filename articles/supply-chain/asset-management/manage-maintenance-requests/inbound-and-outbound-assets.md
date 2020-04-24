---
title: Bejövő és kimenő eszközök
description: Ez a cikk a bejövő és kimenő eszközök Eszközök kezelése szolgáltatásban való regisztrálását ismerteti.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eb491b1c3eced52f6cfc69e3da028dfed36b823b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205184"
---
# <a name="inbound-and-outbound-assets"></a><span data-ttu-id="08e4d-103">Bejövő és kimenő eszközök</span><span class="sxs-lookup"><span data-stu-id="08e4d-103">Inbound and outbound assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="08e4d-104">Ha a cég más helyekről vagy ügyfelektől kapott eszközök javítási vagy karbantartási feladataival (is) foglalkozik, akkor az Eszközök kezelése szolgáltatással nyomon követhetők mind a cég felé küldött eszközök, mind a visszakerülő kimenő eszközök.</span><span class="sxs-lookup"><span data-stu-id="08e4d-104">If your company does repair jobs or maintenance jobs on assets that are received from other locations or customers, Asset Management can track both inbound assets that are on their way to your company and outbound assets that are being returned.</span></span>

> [!NOTE]
> <span data-ttu-id="08e4d-105">Ha bejövő és kimenő életciklus-állapotokkal szeretné kezelni a bejövő és a visszakerülő eszközöket, akkor az ilyen műveletek támogatásához életciklus-állapotokat és életciklusmodelleket kell beállítania a karbantartási kérésekhez.</span><span class="sxs-lookup"><span data-stu-id="08e4d-105">If you want to use inbound and outbound lifecycle states to manage assets that are coming in and being returned, you must set up maintenance request lifecycle states and lifecycle models to support these actions.</span></span> <span data-ttu-id="08e4d-106">További információ: [Karbantartási kérések](../setup-for-maintenance-requests/requests.md).</span><span class="sxs-lookup"><span data-stu-id="08e4d-106">For more information, see [Maintenance requests](../setup-for-maintenance-requests/requests.md).</span></span>

<span data-ttu-id="08e4d-107">Az Eszközök kezelése beállítása határozza meg, hogy használhatók-e bejövő és kimenő eszközök.</span><span class="sxs-lookup"><span data-stu-id="08e4d-107">The setup of Asset Management determines whether you can work with inbound and outbound assets.</span></span>

## <a name="register-assets-as-inbound"></a><span data-ttu-id="08e4d-108">Eszközök regisztrálása bejövőként</span><span class="sxs-lookup"><span data-stu-id="08e4d-108">Register assets as inbound</span></span>

1. <span data-ttu-id="08e4d-109">Válassza az **Eszközök kezelése** \> **Közös** \> **Karbantartási kérések** \> **Aktív karbantartási kérések** elemet.</span><span class="sxs-lookup"><span data-stu-id="08e4d-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="08e4d-110">Válassza ki a karbantartási kérést.</span><span class="sxs-lookup"><span data-stu-id="08e4d-110">Select the maintenance request.</span></span>
3. <span data-ttu-id="08e4d-111">Válassza a **Karbantartási kérés állapotának frissítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="08e4d-111">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="08e4d-112">Válassza a **Bejövő** (vagy a bejövő eszközökhöz létrehozott másik életciklus-állapotot), majd az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="08e4d-112">Select **Inbound** (or another lifecycle state that you've created for inbound assets), and then select **OK**.</span></span>

![Eszközök regisztrálása bejövőként](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a><span data-ttu-id="08e4d-114">Bejövő eszközök regisztrálása fogadottként</span><span class="sxs-lookup"><span data-stu-id="08e4d-114">Register inbound assets as received</span></span>

1. <span data-ttu-id="08e4d-115">Válassza az **Eszközök kezelése** \> **Közös** \> **Bejövő / kimenő** \> **Bejövő eszközök** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="08e4d-115">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Inbound assets**.</span></span>
2. <span data-ttu-id="08e4d-116">Válassza ki az eszközt vagy a karbantartási kérést.</span><span class="sxs-lookup"><span data-stu-id="08e4d-116">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="08e4d-117">Válassza ki a **Tárgyi eszközök fogadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="08e4d-117">Select **Receive assets**.</span></span>
4. <span data-ttu-id="08e4d-118">A **Fogadott** mezőben adja meg a dátumot és az időpontot.</span><span class="sxs-lookup"><span data-stu-id="08e4d-118">In the **Received** field, enter the date and time.</span></span> <span data-ttu-id="08e4d-119">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="08e4d-119">Then select **OK**.</span></span> <span data-ttu-id="08e4d-120">A rekord eltűnik a **Bejövő eszközök** listaoldalról.</span><span class="sxs-lookup"><span data-stu-id="08e4d-120">The record is removed from the **Inbound assets** list page.</span></span>

![Bejövő eszközök regisztrálása fogadottként](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a><span data-ttu-id="08e4d-122">Eszközök regisztrálása kimenőként</span><span class="sxs-lookup"><span data-stu-id="08e4d-122">Register assets as outbound</span></span>

<span data-ttu-id="08e4d-123">A karbantartási vagy javítási feladat befejezése után regisztrálhatja az eszközt visszaküldöttként.</span><span class="sxs-lookup"><span data-stu-id="08e4d-123">When you've completed the maintenance or repair job, you can register the asset as returned.</span></span>

1. <span data-ttu-id="08e4d-124">Válassza az **Eszközök kezelése** \> **Közös** \> **Karbantartási kérések** \> **Aktív karbantartási kérések** elemet.</span><span class="sxs-lookup"><span data-stu-id="08e4d-124">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="08e4d-125">Válassza ki a karbantartási kérést.</span><span class="sxs-lookup"><span data-stu-id="08e4d-125">Select the maintenance request.</span></span>
3. <span data-ttu-id="08e4d-126">Válassza a **Karbantartási kérés állapotának frissítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="08e4d-126">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="08e4d-127">Válassza a **Kimenő** (vagy a kimenő eszközökhöz létrehozott másik életciklus-állapotot), majd az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="08e4d-127">Select **Outbound** (or another lifecycle state that you've created for outbound assets), and then select **OK**.</span></span>

## <a name="register-outbound-assets-as-delivered"></a><span data-ttu-id="08e4d-128">Kimenő eszközök regisztrálása átadottként</span><span class="sxs-lookup"><span data-stu-id="08e4d-128">Register outbound assets as delivered</span></span>

1. <span data-ttu-id="08e4d-129">Válassza az **Eszközök kezelése** \> **Közös** \> **Bejövő / kimenő** \> **Kimenő eszközök** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="08e4d-129">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Outbound assets**.</span></span>
2. <span data-ttu-id="08e4d-130">Válassza ki az eszközt vagy a karbantartási kérést.</span><span class="sxs-lookup"><span data-stu-id="08e4d-130">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="08e4d-131">Válassza ki az **Eszközök kézbesítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="08e4d-131">Select **Deliver assets**.</span></span>
4. <span data-ttu-id="08e4d-132">A **Kézbesítve** mezőben adja meg a dátumot és az időpontot.</span><span class="sxs-lookup"><span data-stu-id="08e4d-132">In the **Delivered** field, enter the date and time.</span></span> <span data-ttu-id="08e4d-133">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="08e4d-133">Then select **OK**.</span></span> <span data-ttu-id="08e4d-134">A rekord eltűnik a **Kimenő eszközök** listaoldalról.</span><span class="sxs-lookup"><span data-stu-id="08e4d-134">The record is removed from the **Outbound assets** list page.</span></span>
