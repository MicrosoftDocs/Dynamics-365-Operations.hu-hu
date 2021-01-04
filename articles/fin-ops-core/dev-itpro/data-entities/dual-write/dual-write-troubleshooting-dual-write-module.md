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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2241e7e6219f95115f55bc45a4d94550276e1e21
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683623"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a><span data-ttu-id="0f1ea-103">A(z) Finance and Operations alkalmazásokban lévő problémák elhárítása a kettős írás modullal</span><span class="sxs-lookup"><span data-stu-id="0f1ea-103">Troubleshoot issues with the dual-write module in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="0f1ea-104">Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="0f1ea-105">Pontosabban, ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a Finance and Operations-alkalmazások **kettős írás** modullal kapcsolatos problémái.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f1ea-106">Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="0f1ea-107">Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="0f1ea-108">A kettős írás modul nem tölthető be egy Finance and Operations-alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="0f1ea-108">You can't load the dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="0f1ea-109">Ha nem tudja megnyitni a **Kettős írás** lapot a **Kettős írás** csempe kiválasztásával az **Adatkezelés** munkaterületen, az adatintegrációs szolgáltatás valószínűleg üzemen kívül van.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="0f1ea-110">Hozzon létre egy támogató jegyet az adatintegrációs szolgáltatás újraindításának kérelmezéséhez.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-table-map"></a><span data-ttu-id="0f1ea-111">Hiba történt, amikor új táblaleképezést próbál létrehozni</span><span class="sxs-lookup"><span data-stu-id="0f1ea-111">Error when you try to create a new table map</span></span>

<span data-ttu-id="0f1ea-112">**A hiba javításához szükséges hitelesítő adatok:** ugyanaz a felhasználó, aki a kettős írást telepítette.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-112">**Required credentials to fix the issue:** The same user that setup dual-write.</span></span>

<span data-ttu-id="0f1ea-113">Előfordulhat, hogy a következő hibaüzenet jelenik meg, amikor új entitást próbál konfigurálni a kettős íráshoz.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-113">You might receive the following error message when you try to configure a new entity for dual-write.</span></span> <span data-ttu-id="0f1ea-114">A kettős írási kapcsolatot beállító felhasználó hozhatja csak létre a leképezést.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-114">The only user that can create a map is the user who setup the dual-write connection.</span></span>

<span data-ttu-id="0f1ea-115">*A válasz állapotkódja sikertelenséget jelez: 401 (Nem engedélyezett)*</span><span class="sxs-lookup"><span data-stu-id="0f1ea-115">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>


## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="0f1ea-116">Hiba a kettős írás felhasználói felületének megnyitásakor</span><span class="sxs-lookup"><span data-stu-id="0f1ea-116">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="0f1ea-117">Előfordulhat, hogy a következő hibaüzenet jelenik meg, amikor megpróbálja elérni a kettős írást az **Adatkezelés** munkaterületről:</span><span class="sxs-lookup"><span data-stu-id="0f1ea-117">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="0f1ea-118">*login.microsoftonline.com elutasította a csatlakozást.*</span><span class="sxs-lookup"><span data-stu-id="0f1ea-118">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="0f1ea-119">A hiba elhárításához jelentkezzen be egy InPrivate-ablakon a Microsoft Edge-ben, rejtett ablakban Chromiumon, vagy rejtett ablakban a Google Chrome-ban.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-119">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="0f1ea-120">Ezenkívül fel kell oldania vagy törölni kell a külső féltől származó cookie-kat.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-120">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a><span data-ttu-id="0f1ea-121">Hiba, amikor a környezetet összekapcsolja kettős íráshoz, vagy új táblaleképezést ad hozzá</span><span class="sxs-lookup"><span data-stu-id="0f1ea-121">Error when you link the environment for dual-write or add a new table mapping</span></span>

<span data-ttu-id="0f1ea-122">**Szükséges szerepkör a hiba javításához:** Rendszergazda a Finance and Operations alkalmazásokban és Dataverse alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-122">**Required role to fix the issue:** System administrator in both Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="0f1ea-123">A következő hiba merülhet fel összekapcsoláskor vagy leképezések létrehozásakor:</span><span class="sxs-lookup"><span data-stu-id="0f1ea-123">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="0f1ea-124">*A válasz állapotkódja sikertelenséget jelez: 403 (tokenexchange).<br> Munkamenet-azonosító: \<your session id\><br> Gyökérszintű tevékenységazonosító: \<your root activity id\>*</span><span class="sxs-lookup"><span data-stu-id="0f1ea-124">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="0f1ea-125">Ez a hiba akkor fordulhat elő, ha nincs megfelelő jogosultsága a kettős írás összekapcsolásához vagy a leképezések létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-125">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="0f1ea-126">Ez a hiba akkor is előfordulhat, ha a Dataverse-környezet alaphelyzetbe állítása a kettős írás csatolásának felbontása nélkül történt.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-126">This error can also occur if the Dataverse environment was reset without unlinking dual-write.</span></span> <span data-ttu-id="0f1ea-127">Minden olyan felhasználó, aki rendszergazdai szerepkörrel rendelkezik a Finance and Operations alkalmazásokban és a Dataverse szolgáltatásban is, összekapcsolhatja a környezeteket.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-127">Any user with system administrator role in both Finance and Operations apps and Dataverse can link the environments.</span></span> <span data-ttu-id="0f1ea-128">Csak a kettős írás kapcsolatot beállító felhasználó adhat hozzá új táblaleképezéseket.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-128">Only the user who setup the dual-write connection can add new table maps.</span></span> <span data-ttu-id="0f1ea-129">A telepítés után bármely rendszergazdai szerepkörrel rendelkező felhasználó nyomon követheti az állapotot, és szerkesztheti a leképezéseket.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-129">After setup, any user with system administrator role can monitor the status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-table-mapping"></a><span data-ttu-id="0f1ea-130">Hiba a táblaleképezés leállításakor</span><span class="sxs-lookup"><span data-stu-id="0f1ea-130">Error when you stop the table mapping</span></span>

<span data-ttu-id="0f1ea-131">A következő hibaüzenetek jelenhetnek meg a táblaleképezések leállításakor:</span><span class="sxs-lookup"><span data-stu-id="0f1ea-131">You might receive the following error message when you try to stop the table mappings:</span></span>

<span data-ttu-id="0f1ea-132">*\[Tiltott\], \[{"status":403,"source":"","message":"Hiba a jogkivonat cseréjéből: A felhasználónak nincs engedélye a kapcsolathoz való hozzáféréshez dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], A távoli kiszolgáló hibát adott vissza: (403) Tiltott.*</span><span class="sxs-lookup"><span data-stu-id="0f1ea-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="0f1ea-133">Ez a hiba akkor fordul elő, ha a csatolt Dataverse-környezet nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-133">This error occurs when the linked Dataverse environment isn't available.</span></span>

<span data-ttu-id="0f1ea-134">A hiba elhárításához hozzon létre egy jegyet az adatintegrációs csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="0f1ea-135">A hálózati nyomkövetést csatolja annak érdekében, hogy az adatintegrációs csoport megjelölje a leképezéseket a háttérben **nem futóként**.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>

## <a name="error-while-trying-to-start-an-table-mapping"></a><span data-ttu-id="0f1ea-136">Hiba történt egy táblaleképezés indításának kísérlete közben</span><span class="sxs-lookup"><span data-stu-id="0f1ea-136">Error while trying to start an table mapping</span></span>

<span data-ttu-id="0f1ea-137">A következőhöz hasonlító hibaüzenet jelenhet meg, amikor a leképezés állapotát **Futás** értékre akarja állítani:</span><span class="sxs-lookup"><span data-stu-id="0f1ea-137">You might receive an error like the following when you try to set that state of a mapping to **Running**:</span></span>

<span data-ttu-id="0f1ea-138">*A kezdeti adatszinkronizálás nem hajtható végre. Hiba: kettős írási hiba – a beépülő modul regiszrtálása nem sikerült: Nem sikerült a kettős írási keresési metaadat létrehozása. Hiba objektumreferenciája nincs beállítva egy objektum példányára.*</span><span class="sxs-lookup"><span data-stu-id="0f1ea-138">*Unable to complete initial data sync. Error: dual-write failure - plugin registration failed: Unable to build dual-write lookup metadata. Error object reference not set to an instance of an object.*</span></span>

<span data-ttu-id="0f1ea-139">A hiba javítása a hiba okának függvénye:</span><span class="sxs-lookup"><span data-stu-id="0f1ea-139">The fix for this error depends on the cause of the error:</span></span>

+ <span data-ttu-id="0f1ea-140">Ha a leképezés függő leképezésekkel rendelkezik, akkor győződjön meg róla, hogy engedélyezi az táblaleképezés függő leképezését.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-140">If the mapping has dependent mappings, then make sure to enable the dependent mappings of this table mapping.</span></span>
+ <span data-ttu-id="0f1ea-141">A leképezésből valószínűleg hiányzik a forrás- vagy célmezők.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-141">The mapping might be missing source or destination fields.</span></span> <span data-ttu-id="0f1ea-142">Ha hiányzik egy mező a Finance and Operations alkalmazásban, akkor kövesse a következő szakasz lépéseit: [Hiányzó entitásmezők problémája leképezésekben](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps).</span><span class="sxs-lookup"><span data-stu-id="0f1ea-142">If a field in the Finance and Operations app is missing, then follow the steps in the section [Missing entity fields issue on maps](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps).</span></span> <span data-ttu-id="0f1ea-143">Ha hiányzik egy mező a Dataverse szolgáltatásból, kattintson a **Táblák frissítése** gombra a leképezésen, így a mezőket a rendszer automatikusan visszatölti a leképezésbe.</span><span class="sxs-lookup"><span data-stu-id="0f1ea-143">If a field in Dataverse is missing, then click **Refresh tables** button on the mapping so that the fields are automatically populated back into the mapping.</span></span>
