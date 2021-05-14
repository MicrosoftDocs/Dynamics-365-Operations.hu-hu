---
title: Nem erősítheti meg szállítmányt, mert probléma van a naptárral
description: Nem erősítheti meg szállítmányt, mert probléma van a naptárral
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f1fccd10d8867252f32b37c77f9a3bad54157bdd
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938485"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a><span data-ttu-id="b93c6-103">Nem erősítheti meg szállítmányt, mert probléma van a naptárral</span><span class="sxs-lookup"><span data-stu-id="b93c6-103">You can't confirm a shipment because of an issue with the calendar</span></span>

<span data-ttu-id="b93c6-104">Hibakód: TRX2716</span><span class="sxs-lookup"><span data-stu-id="b93c6-104">Error code: TRX2716</span></span>

## <a name="symptoms"></a><span data-ttu-id="b93c6-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="b93c6-105">Symptoms</span></span>

<span data-ttu-id="b93c6-106">Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="b93c6-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="b93c6-107">A naptártípus (%1) megköveteli a találkozón (%2) történő be- és kijelentkezést.</span><span class="sxs-lookup"><span data-stu-id="b93c6-107">The calendar type %1 requires the appointment %2 to be checked in and out.</span></span>

<span data-ttu-id="b93c6-108">Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.</span><span class="sxs-lookup"><span data-stu-id="b93c6-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="b93c6-109">Ok</span><span class="sxs-lookup"><span data-stu-id="b93c6-109">Cause</span></span>

<span data-ttu-id="b93c6-110">Léteznek aktív találkozók a meglévő rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="b93c6-110">Active appointments for the load exist.</span></span> <span data-ttu-id="b93c6-111">Van például egy olyan szabály, amely megköveteli a járművezető bejelentkezését.</span><span class="sxs-lookup"><span data-stu-id="b93c6-111">For example, there is a rule that requires driver check-in.</span></span> <span data-ttu-id="b93c6-112">Emiatt a rakomány jelenleg olyan állapotban van, amelyben a szállítmány megerősítése sikertelen.</span><span class="sxs-lookup"><span data-stu-id="b93c6-112">Therefore, the load is currently in a state where shipment confirmation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="b93c6-113">Felbontás</span><span class="sxs-lookup"><span data-stu-id="b93c6-113">Resolution</span></span>

<span data-ttu-id="b93c6-114">A rakományhoz kapcsolódó aktív találkozókon megvizsgálhatja és kijavíthatja az esetleges problémákat.</span><span class="sxs-lookup"><span data-stu-id="b93c6-114">You must investigate and fix any issues with the active appointments that are linked to the load.</span></span>

1. <span data-ttu-id="b93c6-115">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="b93c6-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="b93c6-116">Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="b93c6-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="b93c6-117">A Művelet ablaktábla **Szállítás** fülén, a **Találkozók** csoportban válassza a **Találkozók ütemezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="b93c6-117">On the Action Pane, on the **Transportation** tab, in the **Appointments** group, select **Appointment scheduling**.</span></span>
1. <span data-ttu-id="b93c6-118">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="b93c6-118">Follow one of these steps:</span></span>

    - <span data-ttu-id="b93c6-119">Győződjön meg arról, hogy a gépjárművezető találkozóval kapcsolatos be- és kijelentkezése befejeződött.</span><span class="sxs-lookup"><span data-stu-id="b93c6-119">Make sure that driver check-in/check-out is completed for the appointment.</span></span>
    - <span data-ttu-id="b93c6-120">A találkozó befejezése vagy visszavonása.</span><span class="sxs-lookup"><span data-stu-id="b93c6-120">Complete or cancel the appointment.</span></span>
    - <span data-ttu-id="b93c6-121">A **Gépjárművezető bejelentkezéséhez szükséges** beállítás letiltása a kapcsolódó találkozószabályhoz.</span><span class="sxs-lookup"><span data-stu-id="b93c6-121">Disable the **Driver check-in required** option for the related appointment rule.</span></span>
