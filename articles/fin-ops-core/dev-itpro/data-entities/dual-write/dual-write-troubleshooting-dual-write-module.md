---
title: A(z) Finance and Operations alkalmazásokban lévő problémák elhárítása a kettős írás modullal
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a Finance and Operations-alkalmazások kettős írás modullal kapcsolatos problémái.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172760"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a><span data-ttu-id="ee7cb-103">A(z) Finance and Operations alkalmazásokban lévő problémák elhárítása a kettős írás modullal</span><span class="sxs-lookup"><span data-stu-id="ee7cb-103">Troubleshoot issues with the Dual-write module in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="ee7cb-104">Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="ee7cb-105">Pontosabban, ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a Finance and Operations-alkalmazások **kettős írás** modullal kapcsolatos problémái.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee7cb-106">Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="ee7cb-107">Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="ee7cb-108">A kettős írás modul nem tölthető be egy Finance and Operations-alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="ee7cb-108">You can't load the Dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="ee7cb-109">Ha nem tudja megnyitni a **Kettős írás** lapot a **Kettős írás** csempe kiválasztásával az **Adatkezelés** munkaterületen, az adatintegrációs szolgáltatás valószínűleg üzemen kívül van.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="ee7cb-110">Hozzon létre egy támogató jegyet az adatintegrációs szolgáltatás újraindításának kérelmezéséhez.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a><span data-ttu-id="ee7cb-111">Hiba történt, amikor új entitásleképezést próbál létrehozni</span><span class="sxs-lookup"><span data-stu-id="ee7cb-111">Error when you try to create a new entity mapping</span></span>

<span data-ttu-id="ee7cb-112">**A hiba javításához szükséges hitelesítő adatok:** Azure AD bérlői rendszergazda</span><span class="sxs-lookup"><span data-stu-id="ee7cb-112">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="ee7cb-113">Előfordulhat, hogy a következő hibaüzenet jelenik meg, amikor új entitást próbál konfigurálni a kettős íráshoz:</span><span class="sxs-lookup"><span data-stu-id="ee7cb-113">You might receive the following error message when you try to configure a new entity for dual-write:</span></span>

<span data-ttu-id="ee7cb-114">*A válasz állapotkódja sikertelenséget jelez: 401 (Nem engedélyezett)*</span><span class="sxs-lookup"><span data-stu-id="ee7cb-114">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>

<span data-ttu-id="ee7cb-115">Ez a hiba azért fordul elő, mert új entitásleképezést csak Azure AD bérlői rendszergazda adhat hozzá.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-115">This error occurs because only an Azure AD tenant admin can add a new entity mapping.</span></span>

<span data-ttu-id="ee7cb-116">A hiba javításához jelentkezzen be a Finance and Operations alkalmazásba Azure AD rendszergazda bérlőként.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-116">To fix the issue, sign in to the Finance and Operations app as an Azure AD admin tenant.</span></span> <span data-ttu-id="ee7cb-117">El kell látogatnia a web.PowerApps.com oldalra is, és újra érvényesíteni a kapcsolatot.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-117">You must also go to web.PowerApps.com and revalidate your connection.</span></span>

## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="ee7cb-118">Hiba a kettős írás felhasználói felületének megnyitásakor</span><span class="sxs-lookup"><span data-stu-id="ee7cb-118">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="ee7cb-119">Előfordulhat, hogy a következő hibaüzenet jelenik meg, amikor megpróbálja elérni a kettős írást az **Adatkezelés** munkaterületről:</span><span class="sxs-lookup"><span data-stu-id="ee7cb-119">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="ee7cb-120">*login.microsoftonline.com elutasította a csatlakozást.*</span><span class="sxs-lookup"><span data-stu-id="ee7cb-120">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="ee7cb-121">A hiba elhárításához jelentkezzen be egy InPrivate-ablakon a Microsoft Edge-ben, rejtett ablakban Chromiumon, vagy rejtett ablakban a Google Chrome-ban.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-121">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="ee7cb-122">Ezenkívül fel kell oldania vagy törölni kell a külső féltől származó cookie-kat.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-122">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a><span data-ttu-id="ee7cb-123">Hiba, amikor a környezetet összekapcsolja kettős íráshoz, vagy új entitásleképezést ad hozzá</span><span class="sxs-lookup"><span data-stu-id="ee7cb-123">Error when you link the environment for dual-write or add a new entity mapping</span></span>

<span data-ttu-id="ee7cb-124">**A hiba javításához szükséges hitelesítő adatok:** Azure AD bérlői rendszergazda</span><span class="sxs-lookup"><span data-stu-id="ee7cb-124">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="ee7cb-125">A következő hiba merülhet fel összekapcsoláskor vagy leképezések létrehozásakor:</span><span class="sxs-lookup"><span data-stu-id="ee7cb-125">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="ee7cb-126">*A válasz állapotkódja sikertelenséget jelez: 403 (tokenexchange).<br> Munkamenet-azonosító: \<az Ön munkamenet-azonosítója\><br> Gyökérszintű tevékenységazonosító: \<az Ön gyökérszintű tevékenységazonosítója\>*</span><span class="sxs-lookup"><span data-stu-id="ee7cb-126">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="ee7cb-127">Ez a hiba akkor fordulhat elő, ha nincs megfelelő jogosultsága a kettős írás összekapcsolásához vagy a leképezések létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-127">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="ee7cb-128">A környezetek csatolásához és az új entitás-hozzárendelések hozzáadásához egy Azure AD bérlői rendszergazdai fiókot kell használnia.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-128">You must use an Azure AD tenant admin account to link environments and add new entity mappings.</span></span> <span data-ttu-id="ee7cb-129">A telepítés után azonban nem rendszergazdai fiókkal lehet ellenőrizni az állapotot, és szerkesztheti a leképezéseket.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-129">However, after setup, you can use a non-admin account to monitor status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-entity-mapping"></a><span data-ttu-id="ee7cb-130">Hiba az entitásleképezés leállításakor</span><span class="sxs-lookup"><span data-stu-id="ee7cb-130">Error when you stop the entity mapping</span></span>

<span data-ttu-id="ee7cb-131">A következő hibaüzenetek jelenhetnek meg az entitásleképezések leállításakor:</span><span class="sxs-lookup"><span data-stu-id="ee7cb-131">You might receive the following error message when you try to stop the entity mappings:</span></span>

<span data-ttu-id="ee7cb-132">*\[Tiltott\], \[{"status":403,"source":"","message":"Hiba a jogkivonat cseréjéből: A felhasználónak nincs engedélye a kapcsolathoz való hozzáféréshez dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], A távoli kiszolgáló hibát adott vissza: (403) Tiltott.*</span><span class="sxs-lookup"><span data-stu-id="ee7cb-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="ee7cb-133">Ez a hiba akkor fordul elő, ha a csatolt Common Data Service-környezet nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-133">This error occurs when the linked Common Data Service environment isn't available.</span></span>

<span data-ttu-id="ee7cb-134">A hiba elhárításához hozzon létre egy jegyet az adatintegrációs csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="ee7cb-135">A hálózati nyomkövetést csatolja annak érdekében, hogy az adatintegrációs csoport megjelölje a leképezéseket a háttérben **nem futóként**.</span><span class="sxs-lookup"><span data-stu-id="ee7cb-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>
