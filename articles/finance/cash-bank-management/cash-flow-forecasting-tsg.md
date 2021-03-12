---
title: A pénzforgalmi előrejelzés beállításaival kapcsolatos hibák elhárítása
description: Ez a témakör olyan kérdésekre ad választ, amelyek a pénzforgalmi előrejelzés konfigurálásakor merülhetnek fel. Tartalmazza a pénzforgalmi beállításokra, a pénzforgalom frissítésére és a Power BI pénzforgalomra vonatkozó gyakran feltett kérdéseket (GYIK) is.
author: panolte
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 89eb2f1bcfc73a6a7171a275532b2356e858e87c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985287"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a><span data-ttu-id="b70e6-104">A pénzforgalmi előrejelzés beállításaival kapcsolatos hibák elhárítása</span><span class="sxs-lookup"><span data-stu-id="b70e6-104">Troubleshoot cash flow forecasting setup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b70e6-105">Ez a témakör olyan kérdésekre ad választ, amelyek a pénzforgalmi előrejelzés konfigurálásakor merülhetnek fel.</span><span class="sxs-lookup"><span data-stu-id="b70e6-105">This topic provides answers to questions that you might have when you configure cash flow forecasting.</span></span> <span data-ttu-id="b70e6-106">Tartalmazza a pénzforgalmi beállításokra, a pénzforgalom frissítésére és a Power BI pénzforgalomra vonatkozó gyakran feltett kérdéseket (GYIK) is.</span><span class="sxs-lookup"><span data-stu-id="b70e6-106">It addresses frequently asked questions (FAQ) about the setup for cash flow, updates to cash flow, and cash flow Power BI.</span></span>

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a><span data-ttu-id="b70e6-107">Miért jelenik meg a pénzforgalom csak egyetlen jogi személynél?</span><span class="sxs-lookup"><span data-stu-id="b70e6-107">Why is cash flow shown for only one legal entity?</span></span>

<span data-ttu-id="b70e6-108">A pénzforgalmi előrejelzés konfigurálása és számítása jogi személyenként történik.</span><span class="sxs-lookup"><span data-stu-id="b70e6-108">Cash flow forecasting is configured and calculated per legal entity.</span></span> <span data-ttu-id="b70e6-109">A Power BI-jelentések és a pénzforgalmi előrejelzések képesség a Finance Insights alkalmazásban megjelenítik az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="b70e6-109">Power BI reports and the cash flow forecasts capability in Finance insights show the results.</span></span>

<span data-ttu-id="b70e6-110">A pénzforgalmi előrejelzést minden egyes jogi személyhez be kell állítani, amelyikhez előrejelzést szeretne látni.</span><span class="sxs-lookup"><span data-stu-id="b70e6-110">Cash flow forecasting must be set up for each legal entity that you want to see a forecast for.</span></span> <span data-ttu-id="b70e6-111">Ellenőrizze a pénzforgalmi előrejelzés konfigurációját minden jogi személye esetében.</span><span class="sxs-lookup"><span data-stu-id="b70e6-111">Review the configuration of cash flow forecasting in all your legal entities.</span></span> <span data-ttu-id="b70e6-112">Alternatív lehetőségként tekintse át az összes jogi személy konfigurációját a pénzforgalmi előrejelzésre vonatkozóan, és győződjön meg arról, hogy a szándéknak megfelelően legyenek beállítva.</span><span class="sxs-lookup"><span data-stu-id="b70e6-112">Alternatively, review the configuration of all the legal entities for cash flow forecasting, and make sure that they are set as you intended.</span></span>

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a><span data-ttu-id="b70e6-113">Miért nem jeleníti meg a Power BI az összes pénzforgalmi adatot?</span><span class="sxs-lookup"><span data-stu-id="b70e6-113">Why doesn't Power BI show all the cash flow data?</span></span>

<span data-ttu-id="b70e6-114">Több lépést kell végrehajtani ahhoz, hogy a pénzforgalmi előrejelzések megjelenjenek a Power BI-nézetekben.</span><span class="sxs-lookup"><span data-stu-id="b70e6-114">Several steps must be completed before cash flow forecasts can appear in Power BI views.</span></span> <span data-ttu-id="b70e6-115">Tekintse át az alábbi ellenőrző listát, és győződjön meg arról, hogy minden lépést elvégzett:</span><span class="sxs-lookup"><span data-stu-id="b70e6-115">Review the following checklist, and make sure that every step has been completed:</span></span>

- <span data-ttu-id="b70e6-116">Pénzforgalom beállítása minden egyes jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="b70e6-116">Set up cash flow for each legal entity.</span></span>
- <span data-ttu-id="b70e6-117">A Főkönyvi paraméterek pontban állítsa be a rendszer pénznemét és a rendszer árfolyamtípusát.</span><span class="sxs-lookup"><span data-stu-id="b70e6-117">In General ledger parameters, set the system currency and the system exchange rate type.</span></span>
- <span data-ttu-id="b70e6-118">Állítsa be a főkönyvi könyvelési pénznemet és az árfolyam típusát.</span><span class="sxs-lookup"><span data-stu-id="b70e6-118">Set the ledger accounting currency and the exchange rate type.</span></span>
- <span data-ttu-id="b70e6-119">Írja be a tranzakció pénzneme és a könyvelési pénznem közötti átváltási árfolyamot.</span><span class="sxs-lookup"><span data-stu-id="b70e6-119">Enter exchange rates between the transaction currency and the accounting currency.</span></span>
- <span data-ttu-id="b70e6-120">Írja be a könyvelési pénznem és a rendszer pénzneme közötti átváltási árfolyamot.</span><span class="sxs-lookup"><span data-stu-id="b70e6-120">Enter exchange rates between the accounting currency and the system currency.</span></span>
- <span data-ttu-id="b70e6-121">Írja be a könyvelési pénznem és az egyes bankok pénzneme közötti átváltási árfolyamot.</span><span class="sxs-lookup"><span data-stu-id="b70e6-121">Enter exchange rates between the accounting currency and each bank currency.</span></span>

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a><span data-ttu-id="b70e6-122">Miért működött a Power BI pénzforgalom a korábbi verziókban, de most üres?</span><span class="sxs-lookup"><span data-stu-id="b70e6-122">Why did cash flow Power BI work in previous versions but is now blank?</span></span>

<span data-ttu-id="b70e6-123">Ellenőrizze, hogy az Entitástár Pénzforgalmi mérő V2 és LedgerCovLiquidityMeasurement mértékei konfigurálva vannak-e.</span><span class="sxs-lookup"><span data-stu-id="b70e6-123">Verify that the "Cash flow measure V2" and "LedgerCovLiquidityMeasurement" measurements from Entity store have been configured.</span></span> <span data-ttu-id="b70e6-124">Az Entitástárban található adatokkal való munkáról lásd: [Power BI-integrációja az Entitástárral](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Ellenőrizze, hogy a Power BI-tartalom megtekintéséhez szükséges összes lépést elvégezte-e.</span><span class="sxs-lookup"><span data-stu-id="b70e6-124">For more information about how to work with data in Entity store, see [Power BI integration with Entity store](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Verify that all the steps that are required to view Power BI content have been completed.</span></span> <span data-ttu-id="b70e6-125">További információkért lásd: [Készpénz áttekintés - Power BI tartalom](Cash-Overview-Power-BI-content.md).</span><span class="sxs-lookup"><span data-stu-id="b70e6-125">For more information, see [Cash overview Power BI content](Cash-Overview-Power-BI-content.md).</span></span>

## <a name="have-the-entity-store-entities-been-refreshed"></a><span data-ttu-id="b70e6-126">Frissültek-e az Entitástár entitásai?</span><span class="sxs-lookup"><span data-stu-id="b70e6-126">Have the Entity store entities been refreshed?</span></span>

<span data-ttu-id="b70e6-127">Rendszeresen frissítenie kell az entitásokat, hogy az adatok pontosak és aktuálisak legyenek.</span><span class="sxs-lookup"><span data-stu-id="b70e6-127">You must periodically refresh your entities to ensure that the data is current and accurate.</span></span> <span data-ttu-id="b70e6-128">Egy adott entitás manuális frissítéséhez lépjen a **Rendszerfelügyelet \> Beállítás \> Entitástár** pontra, jelölje ki az entitást, majd válassza a **Frissítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b70e6-128">To manually refresh a specific entity, go to **System administration \> Setup \> Entity store**, select the entity, and then select **Refresh**.</span></span> <span data-ttu-id="b70e6-129">Az adatok automatikusan is frissíthetők.</span><span class="sxs-lookup"><span data-stu-id="b70e6-129">The data can also be updated automatically.</span></span> <span data-ttu-id="b70e6-130">Az **Entitástár** lapon állítsa az **Automatikus frissítés engedélyezve** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="b70e6-130">On the **Entity store** page, set the **Automatic refresh enabled** option to **Yes**.</span></span>
