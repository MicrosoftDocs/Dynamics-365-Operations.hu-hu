---
title: Talent bővítése a Power Apps és Power Automate szolgáltatásokkal
description: Ez a cikk néhány bővítési forgatókönyvet ír le a Microsoft Dynamics 365 Human Resources alkalmazáshoz, amelyek a Microsoft Power Apps és Microsoft Power Automate megoldásokat használják.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: Dynamics 365 Human Resources;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core;Experience Apps;Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8d4185b958ed35e9d2bc764db8ea77b3a2f53c37
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029865"
---
# <a name="extend-with-power-apps-and-power-automate"></a><span data-ttu-id="bd1e8-103">Bővítés a Power Apps és a Power Automate szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="bd1e8-103">Extend with Power Apps and Power Automate</span></span>

<span data-ttu-id="bd1e8-104">Ez a cikk néhány bővítési forgatókönyvet ír le a Microsoft Dynamics 365 Human Resources alkalmazáshoz, amelyek a Microsoft Power Apps és Microsoft Power Automate megoldásokat használják.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Human Resources that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="bd1e8-105">Az egyes példákhoz társított megoldáscsomagot importálhatja a Power Apps környezetébe.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="bd1e8-106">Majd használhatja a csomagokat iránymutatásként vagy kiindulási pontként a szervezetre vonatkozó forgatókönyvek végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd1e8-107">Ha a témakörben bemutatott sablonokat és alkalmazásokat „adott” állapotukban szeretné használni, ügyeljen arra, hogy tesztelje az összeset, és győződjön meg arról, hogy lefedik az Ön megvalósításához tartozó összes forgatókönyvet.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-107">If you want to use the templates and apps that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bd1e8-108">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="bd1e8-108">Prerequisites</span></span>

- <span data-ttu-id="bd1e8-109">Csomagok importálásához felhasználóknak rendelkezniük kell a **Környezetkészítő** engedéllyel.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="bd1e8-110">Az alkalmazások exportálásához vagy importálásához a felhasználóknak Power Apps Plan 2 licenccel, vagy Power Apps Plan 2 próbalicenccel kell rendelkezniük.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="integration-with-office-365-power-automate"></a><span data-ttu-id="bd1e8-111">Integráció az Office 365 és a Power Automate alkalmazással</span><span class="sxs-lookup"><span data-stu-id="bd1e8-111">Integration with Office 365, Power Automate</span></span>

<span data-ttu-id="bd1e8-112">Az **Office 365 integráció** alkalmazást használható a csapatinformációk lekéréshez a Microsoft Office 365 bejelentkezett felhasználói számára.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-112">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="bd1e8-113">A Human Resources szolgáltatásban található dolgozókra hivatkozik az alkalmazottazonosítók típusainak kiolvasásához.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-113">It references workers in Human Resources to extract employee identification types.</span></span> <span data-ttu-id="bd1e8-114">A vezetők ellenőrizhetik az alkalmazottazonosítók lejárati dátumát.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-114">Managers can check expiration dates of employee ID types.</span></span> <span data-ttu-id="bd1e8-115">Emlékeztetőt is küldhetnek e-mailben is, ha az alkalmazottazonosító típusa hamarosan lejár.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-115">They can also send an email reminder if the employee ID type is expiring.</span></span> <span data-ttu-id="bd1e8-116">Az emlékeztetőt a Power Automate és a Power Apps küldi együttműködve.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-116">Power Automate integrates with Power Apps to send this reminder.</span></span> <span data-ttu-id="bd1e8-117">A Power Automate visszaigazolást küld a Power Apps számára az emlékeztető elküldésekor.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-117">Confirmation will be sent back to Power Apps from Power Automate when the reminder is sent.</span></span> <span data-ttu-id="bd1e8-118">Az azonosítótípusok közé tartozik a jogosítvány, az útlevél és az azonosítók egyéb elfogadható formái.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-118">Identification types include driver's license, passport, and other acceptable forms of ID.</span></span>

<span data-ttu-id="bd1e8-119">Ez az alkalmazást egyéb esetekre is kiterjesztheti.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-119">You can extend this app for other scenarios.</span></span> <span data-ttu-id="bd1e8-120">Használhatja például a csapatok szabadságadatainak, a naptári események és a csapatok bármilyen eseményeinek megjelenítésére is.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-120">For example, you can use it to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="bd1e8-121">Az **Integráció az Office 365 és Power Automate alkalmazással** letöltéséhez ugorjon az [Integráció az Office 365 alkalmazással](https://go.microsoft.com/fwlink/?linkid=2081787) oldalra a Microsoft Letöltőközpontban.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-121">To download the **Integration with Office 365, Power Automate** app, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sql-connect-and-execute"></a><span data-ttu-id="bd1e8-122">Power Automate – SQL csatlakozás és végrehajtás</span><span class="sxs-lookup"><span data-stu-id="bd1e8-122">Power Automate – SQL Connect and execute</span></span>

<span data-ttu-id="bd1e8-123">A **Power Automate – SQL csatlakozás és végrehajtás** sablon csatlakozik a Microsoft SQL Server kiszolgálóhoz, és lehetővé teszi az SQL-lekérdezések futtatását.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-123">The **Power Automate – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="bd1e8-124">Bár ez a sablon SQL-táblákat olvas be és frissít, kiterjesztheti azt, és más esetekhez is használhatja.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-124">Although this template reads and updates SQL tables, you can extend it and use it for other scenarios.</span></span> <span data-ttu-id="bd1e8-125">Például használhatja a Common Data Service szolgáltatásban az előkészítési táblák kitöltésére az SQL Serverről származó rekordokkal, és az előkészítési tábla rendszeres időközönkénti szinkronizálásához növekményes leküldéssel az SQL Server kiszolgálóról.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-125">For example, you can use it to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="bd1e8-126">A Speciális lekérdezés szolgáltatás a Flow modullal integrálható az adatok átalakításának és a növekményes küldésének lehetővé tételéhez.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-126">Advanced Query is integrated with Flow to enable Data transformation and incremental push.</span></span>

<span data-ttu-id="bd1e8-127">A **Power Automate – SQL csatlakozás és végrehajtás** sablon letöltéséhez nyissa meg a [Power Automate – SQL csatlakozás és végrehajtás](https://go.microsoft.com/fwlink/?linkid=2081789) elemet a Microsoft letöltőközpontban.</span><span class="sxs-lookup"><span data-stu-id="bd1e8-127">To download the **Power Automate – SQL Connect and execute** template, go to [Power Automate – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bd1e8-128">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="bd1e8-128">Additional resources</span></span>

[<span data-ttu-id="bd1e8-129">A Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="bd1e8-129">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[<span data-ttu-id="bd1e8-130">Alkalmazás bérlők és környezetek közötti áttelepítése</span><span class="sxs-lookup"><span data-stu-id="bd1e8-130">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
