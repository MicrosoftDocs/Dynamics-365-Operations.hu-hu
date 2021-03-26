---
title: Excel-munkafüzet létrehozása a kiskereskedelmi tranzakciók szerkesztéséhez
description: Ez a témakör azt ismerteti, hogy miként hozhat léte Excel-munkafüzetet a kiskereskedelmi tranzakciók szerkesztéséhez a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3a4bc0a91ee2215dcde2f18575d58ab1ef2f5581
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207943"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a><span data-ttu-id="d9232-103">Excel-munkafüzet létrehozása a kiskereskedelmi tranzakciók szerkesztéséhez</span><span class="sxs-lookup"><span data-stu-id="d9232-103">Create an Excel workbook to edit retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9232-104">Ez a témakör azt ismerteti, hogy miként hozhat léte Excel-munkafüzetet a kiskereskedelmi tranzakciók szerkesztéséhez a Microsoft Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="d9232-104">This topic describes how to create an Excel workbook so that you can edit retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d9232-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="d9232-105">Overview</span></span>

<span data-ttu-id="d9232-106">Létezik egy előre meghatározott Excel-sablon, amelyet az ügyfelek a rendszer különböző részeiből érhetnek el, és a kiskereskedelmi tranzakciók szerkesztésére és auditálására használhatnak.</span><span class="sxs-lookup"><span data-stu-id="d9232-106">There is a predefined Excel template that customers can access from different parts of the system and use to edit and audit retail transactions.</span></span> <span data-ttu-id="d9232-107">Az ügyfelek azonban erre a célra egyéni Excel-munkafüzetet is létrehozhatnak.</span><span class="sxs-lookup"><span data-stu-id="d9232-107">However, customers can also create a custom Excel workbook for this purpose.</span></span>

## <a name="create-and-configure-an-excel-workbook"></a><span data-ttu-id="d9232-108">Excel-munkafüzet létrehozása és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d9232-108">Create and configure an Excel workbook</span></span>

<span data-ttu-id="d9232-109">Ha Excel-munkafüzetet kíván létrehozni és konfigurálni, hogy szerkeszthesse a kiskereskedelmi tranzakciókat, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d9232-109">To create and configure an Excel workbook so that you can edit retail transactions, follow these steps.</span></span>

1. <span data-ttu-id="d9232-110">Nyissa meg az Excelt, és hozzon létre egy üres munkafüzetet.</span><span class="sxs-lookup"><span data-stu-id="d9232-110">Open Excel, and create a blank workbook.</span></span>
1. <span data-ttu-id="d9232-111">A **Beszúrás** lapon válassza a **Saját bővítmények** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d9232-111">On the **Insert** tab, select **My add-ins**.</span></span>
1. <span data-ttu-id="d9232-112">A jobb oldali ablakban válassza a **Kiszolgáló adatainak hozzáadása** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="d9232-112">In the right pane, select the **Add server information** link.</span></span>
1. <span data-ttu-id="d9232-113">Írja be a kiszolgáló URL-címét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="d9232-113">Enter the server URL, and then select **OK**.</span></span>
1. <span data-ttu-id="d9232-114">Ha „Nem található kisalkalmazás-regisztráció” hibaüzenet jelenik meg, a probléma megoldásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="d9232-114">If you receive a "No applet registrations found" error message, follow these steps to resolve the issue:</span></span>

    1. <span data-ttu-id="d9232-115">A Commerce alkalmazásban lépjen a **Rendszerfelügyelet \> Beállítás \> Office alkalmazás paraméterei** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d9232-115">In Commerce, go to **System administration \> Setup \> Office app parameters**.</span></span>
    1. <span data-ttu-id="d9232-116">Az **Alkalmazás paraméterei** gyorslapon válassza az **Alkalmazásparaméterek inicializálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d9232-116">On the **App parameters** FastTab, select **Initialize app parameters**.</span></span>
    1. <span data-ttu-id="d9232-117">A megerősítést kérő üzenetmezőben válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="d9232-117">In the confirmation message box, select **OK**.</span></span>
    1. <span data-ttu-id="d9232-118">A **Regisztrált kisalkalmazások** gyorslapon válassza a **Kisalkalmazás regisztrációjának inicializálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d9232-118">On the **Registered applets** FastTab, select **Initialize applet registration**.</span></span>
    1. <span data-ttu-id="d9232-119">Szükség szerint ismételje meg az előző három lépést.</span><span class="sxs-lookup"><span data-stu-id="d9232-119">Repeat the previous three steps as required.</span></span>

1. <span data-ttu-id="d9232-120">Válassza ki a **Tervezés**, majd a **Tábla hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d9232-120">Select **Design**, and then select **Add table**.</span></span>
1. <span data-ttu-id="d9232-121">A módosítandó adatok alapján jelölje ki azokat az entitásokat, amelyeket szerkesztésre hozzá kell adni az Excel-munkafüzethez.</span><span class="sxs-lookup"><span data-stu-id="d9232-121">Based on the data that has to be modified, select the entities that must be added to the Excel workbook for editing.</span></span> <span data-ttu-id="d9232-122">Használja az alábbi táblát hivatkozásként.</span><span class="sxs-lookup"><span data-stu-id="d9232-122">Use the following table as a reference.</span></span>

    | <span data-ttu-id="d9232-123">Tranzakció típusa</span><span class="sxs-lookup"><span data-stu-id="d9232-123">Transaction type</span></span> | <span data-ttu-id="d9232-124">Használandó adatentitások</span><span class="sxs-lookup"><span data-stu-id="d9232-124">Data entities to use</span></span> |
    |------------------|----------------------|
    | <span data-ttu-id="d9232-125">Készpénzzel fizetett, azonnal átvett tranzakciók, online rendelések, aszinkron vevői rendelések, aszinkron vevői ajánlatok</span><span class="sxs-lookup"><span data-stu-id="d9232-125">Cash and carry transactions, Online orders, Async customer orders, Async customer quotes</span></span> | <span data-ttu-id="d9232-126">Tranzakció (auditálható), Értékesítési tranzakció (auditálható), Fizetési tranzakciók (auditálható), Adótranzakciók (auditálható), Engedményes tranzakciók (auditálható), Költségtranzakciók (auditálható)</span><span class="sxs-lookup"><span data-stu-id="d9232-126">Transaction (auditable), Sales transaction (auditable), Payment transactions (auditable), Tax transactions (auditable), Discount transactions (auditable), Charge transactions (auditable)</span></span> |
    | <span data-ttu-id="d9232-127">Banki befizetés</span><span class="sxs-lookup"><span data-stu-id="d9232-127">Bank drop</span></span> | <span data-ttu-id="d9232-128">Tranzakció (auditálható), Banki fizetőeszközzel történt tranzakciók (auditálható)</span><span class="sxs-lookup"><span data-stu-id="d9232-128">Transaction (auditable), Banked tender transactions (auditable)</span></span> |
    | <span data-ttu-id="d9232-129">Széfes befizetés</span><span class="sxs-lookup"><span data-stu-id="d9232-129">Safe drop</span></span> | <span data-ttu-id="d9232-130">Tranzakció (auditálható), Széfes fizetőeszközzel történt tranzakciók (auditálható)</span><span class="sxs-lookup"><span data-stu-id="d9232-130">Transaction (auditable), Safe tender transactions (auditable)</span></span> |
    | <span data-ttu-id="d9232-131">Fizetőeszköz-elszámolás</span><span class="sxs-lookup"><span data-stu-id="d9232-131">Tender declaration</span></span> | <span data-ttu-id="d9232-132">Tranzakció (auditálható), Fizetőeszköz-elszámolási tranzakciók (auditálható)</span><span class="sxs-lookup"><span data-stu-id="d9232-132">Transaction (auditable), Tender declaration transactions (auditable)</span></span> |
    | <span data-ttu-id="d9232-133">Bevétel, Költség</span><span class="sxs-lookup"><span data-stu-id="d9232-133">Income, Expense</span></span> | <span data-ttu-id="d9232-134">Tranzakció (auditálható), Bevétel/Költségtranzakciók (auditálható), Fizetési tranzakciók (auditálható)</span><span class="sxs-lookup"><span data-stu-id="d9232-134">Transaction (auditable), Income/Expense transactions (auditable), Payment transactions (auditable)</span></span> |
    | <span data-ttu-id="d9232-135">Kezdőösszeg meghatározása, Fizetőeszköz kivétele, Váltópénz betétele, Visszajáró fizetőeszköze, Számlakifizetés, Vevői letét</span><span class="sxs-lookup"><span data-stu-id="d9232-135">Declare starting amount, Tender removal, Float entry, Change tender, Invoice payment, Customer deposit</span></span> | <span data-ttu-id="d9232-136">Tranzakció (auditálható), Fizetési tranzakciók (auditálható)</span><span class="sxs-lookup"><span data-stu-id="d9232-136">Transaction (auditable), Payment transactions (auditable)</span></span> |

    > [!NOTE]
    > <span data-ttu-id="d9232-137">Fontos, hogy minden Excel-munkafüzethez csak egy adatentitást adjon hozzá.</span><span class="sxs-lookup"><span data-stu-id="d9232-137">It's important that you add only one data entity to each Excel workbook.</span></span> <span data-ttu-id="d9232-138">Ezenkívül a kulcsszimbólummal jelölt összes mezőt hozzá kell adni a megfelelő munkafüzethez.</span><span class="sxs-lookup"><span data-stu-id="d9232-138">Additionally, all fields that are marked by a key symbol must be added to the relevant workbook.</span></span>

1. <span data-ttu-id="d9232-139">A munkafüzet konfigurálása után alkalmazza a szükséges szűrőket.</span><span class="sxs-lookup"><span data-stu-id="d9232-139">After the workbook is configured, apply the required filters.</span></span> <span data-ttu-id="d9232-140">Ügyeljen arra, hogy ugyanazokat a szűrőket alkalmazza a fájl összes munkalapjára.</span><span class="sxs-lookup"><span data-stu-id="d9232-140">Be sure to apply the same filters to all the worksheets in the file.</span></span> <span data-ttu-id="d9232-141">Ne töltsön be nagyon nagy mennyiségű adatot az Excel-fájlba.</span><span class="sxs-lookup"><span data-stu-id="d9232-141">Avoid loading very large amounts of data into the Excel file.</span></span> <span data-ttu-id="d9232-142">Ellenkező esetben a teljesítmény csökkenhet, valamint az Excel és a rendszer lelassulhat.</span><span class="sxs-lookup"><span data-stu-id="d9232-142">Otherwise, performance might be affected, and Excel and your system might slow down.</span></span> <span data-ttu-id="d9232-143">Azt javasoljuk, hogy mindig a „Vállalat” és a „Kimutatásszám” vagy a „Tranzakciószám” kifejezést használja szűrőként a fájlhoz.</span><span class="sxs-lookup"><span data-stu-id="d9232-143">We recommend that you always use "Company" and either "Statement Number" or "Transaction Number" as filters for your file.</span></span>
1. <span data-ttu-id="d9232-144">A szűrők konfigurálása után válassza a **Frissítés** lehetőséget az adatok betöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="d9232-144">After the filters are configured, select **Refresh** to load the data.</span></span>
1. <span data-ttu-id="d9232-145">Szerkessze a szükséges adatokat, majd tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="d9232-145">Edit the required data, and then publish it.</span></span> <span data-ttu-id="d9232-146">Ha a **Közzététel** gomb nem érhető el, valószínűleg néhány kulcsmező nem lett hozzáadva az Excel-munkafüzethez.</span><span class="sxs-lookup"><span data-stu-id="d9232-146">If the **Publish** button is unavailable, some key fields probably weren't added to the Excel workbook.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d9232-147">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d9232-147">Additional resources</span></span>

[<span data-ttu-id="d9232-148">Készpénzzel fizetett, azonnal átvett és készpénzkezelési tranzakciók szerkesztése és auditálása</span><span class="sxs-lookup"><span data-stu-id="d9232-148">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="d9232-149">Online rendeléses és aszinkron vevői rendeléses tranzakciók szerkesztése és auditálása</span><span class="sxs-lookup"><span data-stu-id="d9232-149">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="d9232-150">Kiskereskedelmi tranzakciók pénzügyi dimenzióinak szerkesztése</span><span class="sxs-lookup"><span data-stu-id="d9232-150">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="d9232-151">Mezők hozzáadása Excel-munkafüzethez a kiskereskedelmi tranzakciók szerkesztéséhez</span><span class="sxs-lookup"><span data-stu-id="d9232-151">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]