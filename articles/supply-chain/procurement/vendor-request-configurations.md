---
title: "Szállítókérés konfigurációi"
description: "Ez a témakör azokat a mezőket jeleníti meg, amelyeket ki kell tölteni egy új szállítókérésben."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: ba426692e2e404ab75e5730b8205115fc59e402f
ms.openlocfilehash: e9b22a6f846607e8afc5d4f01c685f1364b1c01d
ms.contentlocale: hu-hu
ms.lasthandoff: 02/08/2018

---

# <a name="vendor-request-configurations"></a><span data-ttu-id="8524a-103">Szállítókérés konfigurációi</span><span class="sxs-lookup"><span data-stu-id="8524a-103">Vendor request configurations</span></span>
[!include[banner](../includes/banner.md)]

<span data-ttu-id="8524a-104">A szállítókérés befejezéséhez egy szállítói kapcsolattartónak végre kell hajtania a potenciális szállító regisztrációs varázslóját.</span><span class="sxs-lookup"><span data-stu-id="8524a-104">To complete a vendor request, a vendor contact person must complete the prospective vendor registration wizard.</span></span>

<span data-ttu-id="8524a-105">A **Szállítókérés konfigurációi** űrlapon létrehozhat olyan profilokat, amelyek megadják a kötelező mezőket és a látható mezőket a potenciális szállító regisztrációs varázslójában.</span><span class="sxs-lookup"><span data-stu-id="8524a-105">In the **Vendor request configurations** form, you can create profiles that specify required fields and visible fields in the prospective vendor registration wizard.</span></span>

<span data-ttu-id="8524a-106">A szállítói regisztrációs varázsló azzal kezd, hogy megkérdezi a potenciális szállítói felhasználótól, hogy mely országban/régióban végzi tevékenységét.</span><span class="sxs-lookup"><span data-stu-id="8524a-106">The vendor registration wizard will start out by asking the prospective vendor user which country/region the vendor is doing business in.</span></span> <span data-ttu-id="8524a-107">Ez az információ határozza meg az alkalmazandó konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="8524a-107">This information determines the applicable configuration.</span></span> <span data-ttu-id="8524a-108">Ha nincs megadott konfiguráció egy ország/régió számára, akkor az alapértelmezett konfigurációt használja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="8524a-108">If no specific configuration is defined for a country/region, a default configuration will be used.</span></span>

### <a name="set-up-a-vendor-request-configuration"></a><span data-ttu-id="8524a-109">Szállítókérés konfigurációjának beállítása</span><span class="sxs-lookup"><span data-stu-id="8524a-109">Set up a vendor request configuration</span></span>

<span data-ttu-id="8524a-110">Alapértelmezés szerint rendelkezésre áll egy szállítókonfiguráció a Szállítókérés konfigurációs űrlapon.</span><span class="sxs-lookup"><span data-stu-id="8524a-110">By default, there is a vendor configuration available in the Vendor request configurations form.</span></span>

<span data-ttu-id="8524a-111">Nincs lehetőség országot/régiót kiválasztására az alapértelmezett konfigurációnál, így az **Országok/régiók** szakasz nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="8524a-111">It is not possible to select country/regions for the default configuration, so the **Countries/regions** section cannot be changed.</span></span>

1.  <span data-ttu-id="8524a-112">Kattintson a **Beszerzés és forrás** > **Beállítás** > **Szállítók** elemre, majd a **Szállítókérés konfigurációi** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8524a-112">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2.  <span data-ttu-id="8524a-113">Kattintson a **Mezők** fülre a listában szereplő mezők állapotának beállításához.</span><span class="sxs-lookup"><span data-stu-id="8524a-113">Click the **Fields** tab to set the status of the listed fields.</span></span>
-   <span data-ttu-id="8524a-114">Rejtett (nem látható)</span><span class="sxs-lookup"><span data-stu-id="8524a-114">Hidden (Not visible)</span></span>
-   <span data-ttu-id="8524a-115">Megjelenített (látható, de nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="8524a-115">Displayed (Visible but not mandatory)</span></span>
-   <span data-ttu-id="8524a-116">Szükséges (látható és kötelező)</span><span class="sxs-lookup"><span data-stu-id="8524a-116">Required (Visible and mandatory)</span></span>
3.  <span data-ttu-id="8524a-117">Kattintson a **Tartalom** lapfülre annak megadásához, hogy jelenjen-e meg szöveg a varázslóban, illetve hogy szerepeljen-e üzenet arra vonatkozóan, hogy a potenciális szállítói felhasználónak el kell fogadnia ezt ahhoz, hogy a varázsló következő lépésével folytathassa a műveletet.</span><span class="sxs-lookup"><span data-stu-id="8524a-117">Click the **Content** tab to specify if text is going to be shown on the wizard and if there should be an acknowledgement that the prospective vendor user must accept this before moving to the next step in the wizard.</span></span> <span data-ttu-id="8524a-118">Az információ vonatkozik mindazon feltételekre és kikötésekre, amelyeket a felhasználónak el kell fogadnia a folytatáshoz.</span><span class="sxs-lookup"><span data-stu-id="8524a-118">The acknowledgement will be requested for any terms and conditions that the user must accept to continue.</span></span>

<span data-ttu-id="8524a-119">Emellett megadhat egy megerősítő üzenetet is, amely akkor jelenik meg, amikor a varázsló lefutott, és Ön hozzáadhat egy vagy több kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="8524a-119">You can also enter a confirmation message that will be displayed when the wizard is finalized, and you can add one or more questionnaires.</span></span>

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a><span data-ttu-id="8524a-120">Hozzon létre egy szállítói konfigurációt egy adott ország/régió számára</span><span class="sxs-lookup"><span data-stu-id="8524a-120">Create a vendor configuration for a specific country/region</span></span>
1.  <span data-ttu-id="8524a-121">Kattintson a **Beszerzés és forrás** > **Beállítás** > **Szállítók** elemre, majd a **Szállítókérés konfigurációi** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8524a-121">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2.  <span data-ttu-id="8524a-122">Kattintson az **Új** lehetőségre egy új konfiguráció létrehozásához, és adja meg a konfiguráció nevét.</span><span class="sxs-lookup"><span data-stu-id="8524a-122">Click **New** to create a new configuration, and provide a name for the configuration.</span></span>
3.  <span data-ttu-id="8524a-123">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="8524a-123">Click **Save**.</span></span>
4.  <span data-ttu-id="8524a-124">Nyissa meg az **Országok/régiók** lapot, és válassza ki azt az országot/régiót, amelynél a konfigurációt használni kell.</span><span class="sxs-lookup"><span data-stu-id="8524a-124">Open the **Country/regions** tab to select the country/region that the configuration should be used for.</span></span>
5.  <span data-ttu-id="8524a-125">Hajtsa végre a következő konfigurációt, és kövesse following the guidelines for the default configuration.</span><span class="sxs-lookup"><span data-stu-id="8524a-125">Complete the configuration by following the guidelines for the default configuration.</span></span>


