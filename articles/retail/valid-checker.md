---
title: Kiskereskedelmi tranzakció konzisztencia-ellenőrzése
description: Ebben a témakörben részletes leírást találhat a Microsoft Dynamics 365 for Retail kiskereskedelmi tranzakció konzisztencia-ellenőrzésére használatos funkciójáról.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: db01a12b92574b41f1f4fe7281c23992e0d36027
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "302387"
---
# <a name="retail-transaction-consistency-checker"></a><span data-ttu-id="68d04-103">Kiskereskedelmi tranzakció konzisztencia-ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="68d04-103">Retail transaction consistency checker</span></span>


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

<span data-ttu-id="68d04-104">Ebben a témakörben részletes leírást találhat a Microsoft Dynamics 365 for Finance and Operations 8.1.3 verziójában bemutatott kiskereskedelmi tranzakció konzisztencia-ellenőrzésére használatos funkcióról.</span><span class="sxs-lookup"><span data-stu-id="68d04-104">This topic describes the retail transaction consistency checker functionality introduced in Microsoft Dynamics 365 for Finance and Operations version 8.1.3.</span></span> <span data-ttu-id="68d04-105">A konzisztencia-ellenőrző azonosítja és elkülöníti az inkonzisztens tranzakciókat, mielőtt a kimutatásfeladási folyamat kezeli őket.</span><span class="sxs-lookup"><span data-stu-id="68d04-105">The consistency checker identifies and isolates inconsistent transactions before they are picked up by the statement posting process.</span></span>

<span data-ttu-id="68d04-106">Egy kimutatás feladása során a Retail szolgáltatásban a feladás sikertelen lehet, ha inkonzisztens adatok találhatók a kiskereskedelmi tranzakciók táblájában.</span><span class="sxs-lookup"><span data-stu-id="68d04-106">When a statement is posted in Retail, posting can fail due to inconsistent data in the retail transaction tables.</span></span> <span data-ttu-id="68d04-107">Az adatokkal kapcsolatos problémákat a pénztár (POS) alkalmazás előre nem látható problémái okozhatják, vagy ha a tranzakciók importálása nem megfelelően történt egy külső fél pénztárrendszeréből.</span><span class="sxs-lookup"><span data-stu-id="68d04-107">The data issue may be caused by by unforeseen issues in the point of sale (POS) application, or if transactions were incorrectly imported from third-party POS systems.</span></span> <span data-ttu-id="68d04-108">Az alábbiakban az inkonzisztenciák megjelenésére mutatunk be példákat:</span><span class="sxs-lookup"><span data-stu-id="68d04-108">Examples of how these inconsistencies may appear include:</span></span> 

  - <span data-ttu-id="68d04-109">A fejléctáblában szereplő tranzakciós végösszeg nem egyezik meg a sorokban található tranzakciók összegével.</span><span class="sxs-lookup"><span data-stu-id="68d04-109">The transaction total on the header table does not match the transaction total on the lines.</span></span>
  - <span data-ttu-id="68d04-110">A fejléctábla sorainak száma nem egyezik meg a tranzakciós tábla sorainak számával.</span><span class="sxs-lookup"><span data-stu-id="68d04-110">The line count on the header table does not match with the number of lines in the transaction table.</span></span>
  - <span data-ttu-id="68d04-111">A fejléctáblában szereplő adók nem egyeznek meg a sorokban szereplő adó összegével.</span><span class="sxs-lookup"><span data-stu-id="68d04-111">Taxes on the header table do not match the tax amount on the lines.</span></span> 
  
<span data-ttu-id="68d04-112">Ha a kimutatásfeladási folyamat feldolgozza az inkonzisztens tranzakciókat, akkor inkonzisztens értékesítési számlák és fizetési naplók keletkeznek, és emiatt a teljes kimutatásfeladási folyamat sikertelen lesz.</span><span class="sxs-lookup"><span data-stu-id="68d04-112">When inconsistent transactions are picked up by the statement posting process, inconsistent sales invoices and payment journals are created, and the entire statement posting process fails as a result.</span></span> <span data-ttu-id="68d04-113">Ha a kimutatásokat ebből az állapotból szeretné helyreállítani, ahhoz számos tranzakciós táblát érintő, komplex adathelyesbítési művelet szükséges.</span><span class="sxs-lookup"><span data-stu-id="68d04-113">Recovering the statements from such a state involves complex data fixes across multiple transaction tables.</span></span> <span data-ttu-id="68d04-114">A kereskedelmi tranzakció konzisztencia-ellenőrzője megelőzi az ehhez hasonló problémák létrejöttét.</span><span class="sxs-lookup"><span data-stu-id="68d04-114">The retail transaction consistency checker prevents such issues.</span></span>

<span data-ttu-id="68d04-115">Az alábbi ábrán a tranzakció konzisztencia-ellenőrzőjével végrehajtott feladási folyamat látható.</span><span class="sxs-lookup"><span data-stu-id="68d04-115">The following chart illustrates the posting process with the transaction consistency checker.</span></span>

<span data-ttu-id="68d04-116">![Kimutatásfeladási folyamat kiskereskedelmi tranzakció konzisztencia-ellenőrzőjével](./media/validchecker.png "Kimutatásfeladási folyamat kiskereskedelmi tranzakció konzisztencia-ellenőrzőjével")</span><span class="sxs-lookup"><span data-stu-id="68d04-116">![Statement posting process with retail transaction consistency checker](./media/validchecker.png "Statement posting process with retail transsaction consistency checker")</span></span>

<span data-ttu-id="68d04-117">Az **Üzleti tranzakciók ellenőrzése** kötegfolyamat ellenőrzi a kiskereskedelmi tranzakciós táblázatok konzisztenciáját az alábbi esetekben.</span><span class="sxs-lookup"><span data-stu-id="68d04-117">The **Validate store transactions** batch process checks the consistency of the retail transaction tables for the following scenarios.</span></span>

- <span data-ttu-id="68d04-118">Vevői számla – Ellenőrzi, hogy a kiskereskedelmi tranzakciós táblában szereplő vevői számla létezik a HQ-ban a vevői alapadatok között.</span><span class="sxs-lookup"><span data-stu-id="68d04-118">Customer account - Validates that the customer account in the retail transaction tables exists in the HQ customer master.</span></span>
- <span data-ttu-id="68d04-119">Sorok száma – Ellenőrzi, hogy a tranzakciós fejléctáblában rögzített sorok száma megegyezik az értékesítési tranzakciók táblájában található sorok számával.</span><span class="sxs-lookup"><span data-stu-id="68d04-119">Line count - Validates that the number of lines, as captured on the transaction header table, matches the number of lines in the sales transaction tables.</span></span>

## <a name="set-up-the-consistency-checker"></a><span data-ttu-id="68d04-120">Konzisztencia-ellenőrző beállítása</span><span class="sxs-lookup"><span data-stu-id="68d04-120">Set up the consistency checker</span></span>
<span data-ttu-id="68d04-121">Konfigurálja az „Üzleti tranzakciók ellenőrzése” kötegfolyamatot időszakos futás esetén a **Kiskereskedelem \> Kiskereskedelem IT \> POS-feladás** menüpontban.</span><span class="sxs-lookup"><span data-stu-id="68d04-121">Configure the "Validate store transactions" batch process, at **Retail \> Retail IT \> POS posting**, for periodic runs.</span></span> <span data-ttu-id="68d04-122">A kötegelt feladat az üzlet szervezeti hierarchiája alapján ütemezhető, hasonlóan a „Kimutatások kötegelt kiszámítása” és a „Kimutatások kötegelt feladása” folyamatok beállításához.</span><span class="sxs-lookup"><span data-stu-id="68d04-122">The batch job can be scheduled based on store organization hierarchy, similar to how the "Calculate statement in batch" and "Post statement in batch" processes are set up.</span></span> <span data-ttu-id="68d04-123">Javasoljuk, hogy úgy konfigurálja ezt a kötegfolyamatot, hogy az naponta többször fusson, és úgy ütemezze, hogy minden P-feladat végrehajtása végén fusson.</span><span class="sxs-lookup"><span data-stu-id="68d04-123">We recommend that you configure this batch process to run multiple times in a day and schedule it so that it runs at the end of every P-job execution.</span></span>

## <a name="results-of-validation-process"></a><span data-ttu-id="68d04-124">Ellenőrzési folyamat eredményei</span><span class="sxs-lookup"><span data-stu-id="68d04-124">Results of validation process</span></span>
<span data-ttu-id="68d04-125">A kötegfolyamat által végzett ellenőrzés eredményeit a rendszer felcímkézi a megfelelő kiskereskedelmi tranzakcióra.</span><span class="sxs-lookup"><span data-stu-id="68d04-125">The results of the validation check by the batch process are tagged on the appropriate retail transaction.</span></span> <span data-ttu-id="68d04-126">A kiskereskedelmi tranzakció rekordján található **Ellenőrzés állapota** mező vagy **Sikeres** vagy **Hiba** értékre van beállítva, és az utolsó ellenőrzés futásának dátuma a **Legutóbbi ellenőrzés időpontja** mezőben látható.</span><span class="sxs-lookup"><span data-stu-id="68d04-126">The **Validation status** field on the retail transaction record is either set to **Successful** or **Error**, and the date of the last validation run appears on the **Last validation time** field.</span></span>

<span data-ttu-id="68d04-127">Ha további, ellenőrzési hibához kapcsolódó leíróbb jellegű hibaüzenetet szeretne megtekinteni, válassza ki a megfelelő kiskereskedelmi üzlet tranzakciós rekordját, majd kattintson az **Ellenőrzési hibák** gombra.</span><span class="sxs-lookup"><span data-stu-id="68d04-127">To view more descriptive error text relating to a validation failure, select the relevant retail store transaction record and click the **Validation errors** button.</span></span>

<span data-ttu-id="68d04-128">Azokat a tranzakciókat, amelyek nem feleltek meg az ellenőrzésen, valamint a még nem ellenőrzött tranzakciókat a rendszer nem szerepelteti a kimutatásokban.</span><span class="sxs-lookup"><span data-stu-id="68d04-128">Transactions that fail the validation check and transactions that have not yet been validated will not be pulled into statements.</span></span> <span data-ttu-id="68d04-129">A „Kimutatás számítása” folyamat során a felhasználók értesítést kapnak, ha olyan tranzakciók találhatók, amelyeknek szerepelniük kellett volna a kimutatásban, de mégsem szerepeltek.</span><span class="sxs-lookup"><span data-stu-id="68d04-129">During the "Calculate statement" process, users will be notified if there are transactions that could have been included in the statement but weren't.</span></span>

<span data-ttu-id="68d04-130">Ha ellenőrzési probléma merül fel, a hiba javítása csak a Microsoft ügyfélszolgálata segítségével lehetséges.</span><span class="sxs-lookup"><span data-stu-id="68d04-130">If a validation error is found, the only way to fix the error is to contact Microsoft Support.</span></span> <span data-ttu-id="68d04-131">A jövőbeli kiadások egyikében hozzáadásra kerül majd a lehetőség, amely segítségével a felhasználók maguk is kijavíthatják a rekordokat a felhasználói felületen, amelyek sikertelenek voltak.</span><span class="sxs-lookup"><span data-stu-id="68d04-131">In a future release, capability will be added so that users can fix the records that failed through the user interface.</span></span> <span data-ttu-id="68d04-132">A később hozzáférhetővé váló naplózási és auditálási lehetőségek segítségével a módosítások előzményei is nyomon követhetők lesznek.</span><span class="sxs-lookup"><span data-stu-id="68d04-132">Logging and auditing capabilities will also be made available to trace the history of the modifications.</span></span>

> [!NOTE]
> <span data-ttu-id="68d04-133">A jövőbeli kiadásokban olyan további ellenőrzési szabályokat adunk hozzá, amellyel még több eset ellenőrzése válik lehetővé.</span><span class="sxs-lookup"><span data-stu-id="68d04-133">Additional validation rules to support more scenarios will be added in a future release.</span></span>
