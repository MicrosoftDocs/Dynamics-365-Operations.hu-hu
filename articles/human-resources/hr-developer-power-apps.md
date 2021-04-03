---
title: Talent bővítése a Power Apps és Power Automate szolgáltatásokkal
description: Ez a cikk néhány bővítési példaforgatókönyvet ír le a Microsoft Dynamics 365 Human Resources alkalmazáshoz, amelyek a Microsoft Power Apps és Microsoft Power Automate megoldásokat használják.
author: negudava
manager: tfehr
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: edc2352fa53ac93c582b608b65fc624ff5dcd2a4
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467073"
---
# <a name="extend-with-power-apps-and-power-automate"></a><span data-ttu-id="28968-103">Bővítés a Power Apps és a Power Automate szolgáltatásokkal</span><span class="sxs-lookup"><span data-stu-id="28968-103">Extend with Power Apps and Power Automate</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="28968-104">Ez a cikk néhány bővítési példaforgatókönyvet ír le a Microsoft Dynamics 365 Human Resources alkalmazáshoz, amelyek a Microsoft Power Apps és Microsoft Power Automate megoldásokat használják.</span><span class="sxs-lookup"><span data-stu-id="28968-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Human Resources that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="28968-105">Az egyes példákhoz társított megoldáscsomagot importálhatja a Power Apps környezetébe.</span><span class="sxs-lookup"><span data-stu-id="28968-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="28968-106">Majd használhatja a csomagokat iránymutatásként vagy kiindulási pontként a szervezetre vonatkozó forgatókönyvek végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="28968-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="28968-107">Ha a témakörben bemutatott sablonokat és alkalmazásokat „adott” állapotukban szeretné használni, ügyeljen arra, hogy tesztelje az összeset, és győződjön meg arról, hogy lefedik az Ön megvalósításához tartozó összes forgatókönyvet.</span><span class="sxs-lookup"><span data-stu-id="28968-107">If you want to use the templates and apps that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28968-108">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="28968-108">Prerequisites</span></span>

- <span data-ttu-id="28968-109">Csomagok importálásához felhasználóknak rendelkezniük kell a **Környezetkészítő** engedéllyel.</span><span class="sxs-lookup"><span data-stu-id="28968-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="28968-110">Az alkalmazások exportálásához vagy importálásához a felhasználóknak Power Apps Plan 2 licenccel, vagy Power Apps Plan 2 próbalicenccel kell rendelkezniük.</span><span class="sxs-lookup"><span data-stu-id="28968-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="integration-with-microsoft-365-power-automate"></a><span data-ttu-id="28968-111">Integráció a Microsoft 365 Power Automate szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="28968-111">Integration with Microsoft 365, Power Automate</span></span>

<span data-ttu-id="28968-112">Az **Integráció a Microsoft 365-tel** alkalmazás használható a csapatinformációk lekéréshez a bejelentkezett felhasználói számára a Microsoft 365-ből.</span><span class="sxs-lookup"><span data-stu-id="28968-112">The **Integration with Microsoft 365** app can be used to extract team information for signed-in users from Microsoft 365.</span></span> <span data-ttu-id="28968-113">A Human Resources szolgáltatásban található dolgozókra hivatkozik az alkalmazottazonosítók típusainak kiolvasásához.</span><span class="sxs-lookup"><span data-stu-id="28968-113">It references workers in Human Resources to extract employee identification types.</span></span> <span data-ttu-id="28968-114">A vezetők ellenőrizhetik az alkalmazottazonosítók lejárati dátumát.</span><span class="sxs-lookup"><span data-stu-id="28968-114">Managers can check expiration dates of employee ID types.</span></span> <span data-ttu-id="28968-115">Emlékeztetőt is küldhetnek e-mailben is, ha az alkalmazottazonosító típusa hamarosan lejár.</span><span class="sxs-lookup"><span data-stu-id="28968-115">They can also send an email reminder if the employee ID type is expiring.</span></span> <span data-ttu-id="28968-116">Az emlékeztetőt a Power Automate és a Power Apps küldi együttműködve.</span><span class="sxs-lookup"><span data-stu-id="28968-116">Power Automate integrates with Power Apps to send this reminder.</span></span> <span data-ttu-id="28968-117">A Power Automate visszaigazolást küld a Power Apps számára az emlékeztető elküldésekor.</span><span class="sxs-lookup"><span data-stu-id="28968-117">Confirmation will be sent back to Power Apps from Power Automate when the reminder is sent.</span></span> <span data-ttu-id="28968-118">Az azonosítótípusok közé tartozik a jogosítvány, az útlevél és az azonosítók egyéb elfogadható formái.</span><span class="sxs-lookup"><span data-stu-id="28968-118">Identification types include driver's license, passport, and other acceptable forms of ID.</span></span>

<span data-ttu-id="28968-119">Ez az alkalmazást egyéb esetekre is kiterjesztheti.</span><span class="sxs-lookup"><span data-stu-id="28968-119">You can extend this app for other scenarios.</span></span> <span data-ttu-id="28968-120">Használhatja például a csapatok szabadságadatainak, a naptári események és a csapatok bármilyen eseményeinek megjelenítésére is.</span><span class="sxs-lookup"><span data-stu-id="28968-120">For example, you can use it to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="28968-121">Az **Integráció a Microsoft 365 és Power Automate-szolgáltatásokkal** alkalmazás letöltéséhez ugorjon az [Integráció a Microsoft 365 alkalmazással](https://go.microsoft.com/fwlink/?linkid=2081787) oldalra a Microsoft Letöltőközpontban.</span><span class="sxs-lookup"><span data-stu-id="28968-121">To download the **Integration with Microsoft 365, Power Automate** app, go to [Integration with Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sql-connect-and-execute"></a><span data-ttu-id="28968-122">Power Automate – SQL csatlakozás és végrehajtás</span><span class="sxs-lookup"><span data-stu-id="28968-122">Power Automate – SQL Connect and execute</span></span>

<span data-ttu-id="28968-123">A **Power Automate – SQL csatlakozás és végrehajtás** sablon csatlakozik a Microsoft SQL Server kiszolgálóhoz, és lehetővé teszi az SQL-lekérdezések futtatását.</span><span class="sxs-lookup"><span data-stu-id="28968-123">The **Power Automate – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="28968-124">Bár ez a sablon SQL-táblákat olvas be és frissít, kiterjesztheti azt, és más esetekhez is használhatja.</span><span class="sxs-lookup"><span data-stu-id="28968-124">Although this template reads and updates SQL tables, you can extend it and use it for other scenarios.</span></span> <span data-ttu-id="28968-125">Például használhatja a Dataverse szolgáltatásban az előkészítési táblák kitöltésére az SQL Serverről származó rekordokkal, és az előkészítési tábla rendszeres időközönkénti szinkronizálásához növekményes leküldéssel az SQL Server kiszolgálóról.</span><span class="sxs-lookup"><span data-stu-id="28968-125">For example, you can use it to fill a staging table in Dataverse with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="28968-126">A Speciális lekérdezés szolgáltatás a Flow modullal integrálható az adatok átalakításának és a növekményes küldésének lehetővé tételéhez.</span><span class="sxs-lookup"><span data-stu-id="28968-126">Advanced Query is integrated with Flow to enable Data transformation and incremental push.</span></span>

<span data-ttu-id="28968-127">A **Power Automate – SQL csatlakozás és végrehajtás** sablon letöltéséhez nyissa meg a [Power Automate – SQL csatlakozás és végrehajtás](https://go.microsoft.com/fwlink/?linkid=2081789) elemet a Microsoft letöltőközpontban.</span><span class="sxs-lookup"><span data-stu-id="28968-127">To download the **Power Automate – SQL Connect and execute** template, go to [Power Automate – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="28968-128">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="28968-128">Additional resources</span></span>

[<span data-ttu-id="28968-129">A Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="28968-129">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]