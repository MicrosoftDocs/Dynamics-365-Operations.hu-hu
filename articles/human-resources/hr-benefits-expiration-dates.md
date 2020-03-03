---
title: Juttatások lejárati dátumainak kezelése
description: Ez az eljárás bemutatja, hogyan zárhat le vagy hosszabbíthat meg egy juttatást, és miként kezelheti a juttatásra jogosult dolgozók tagsági időszakát.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmBenefit, HcmMassBenefitExpiration, HcmMassBenefitExpirationResults, HcmWorker, HcmWorkerEnrollment
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 9a1e815e51b4dc232b546294d66337f80dbc30bc
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009344"
---
# <a name="manage-benefit-expiration-dates"></a><span data-ttu-id="e2766-103">Juttatások lejárati dátumainak kezelése</span><span class="sxs-lookup"><span data-stu-id="e2766-103">Manage benefit expiration dates</span></span>

<span data-ttu-id="e2766-104">Ez az eljárás bemutatja, hogyan zárhat le vagy hosszabbíthat meg egy juttatást, és miként kezelheti a juttatásra jogosult dolgozók tagsági időszakát.</span><span class="sxs-lookup"><span data-stu-id="e2766-104">This procedure shows how you can expire or extend a benefit, and manage the enrollment dates of workers that are enrolled in the benefit.</span></span> <span data-ttu-id="e2766-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e2766-105">The demo data company used to create this procedure is USMF.</span></span>

## <a name="benefit-expiration-dates"></a><span data-ttu-id="e2766-106">Juttatások lejárati dátumai</span><span class="sxs-lookup"><span data-stu-id="e2766-106">Benefit expiration dates</span></span>

1. <span data-ttu-id="e2766-107">Ugorjon az Emberi erőforrások > Juttatások > Juttatások pontra.</span><span class="sxs-lookup"><span data-stu-id="e2766-107">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="e2766-108">Bontsa ki a Kedvezményezett dolgozók adatterületet.</span><span class="sxs-lookup"><span data-stu-id="e2766-108">Expand the Enrolled workers FactBox.</span></span>
3. <span data-ttu-id="e2766-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e2766-109">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="e2766-110">A Műveleti ablaktáblán kattintson a Juttatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2766-110">On the Action Pane, click Benefit.</span></span>
5. <span data-ttu-id="e2766-111">Kattintson a Juttatások lejáratának beállítása vagy bővítése lehetőségre</span><span class="sxs-lookup"><span data-stu-id="e2766-111">Click Expire or extend benefits.</span></span>
6. <span data-ttu-id="e2766-112">A Juttatás új lejárati dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="e2766-112">In the New benefit expiration date field, enter a date and time.</span></span>
7. <span data-ttu-id="e2766-113">Kattintson a Lejárat lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2766-113">Click Expire.</span></span>
8. <span data-ttu-id="e2766-114">A Műveleti ablaktáblán kattintson a Juttatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2766-114">On the Action Pane, click Benefit.</span></span>
9. <span data-ttu-id="e2766-115">Kattintson a Juttatás lejáratának beállítása és bővítése – eredmények lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2766-115">Click Benefit expiration and extension results.</span></span>
10. <span data-ttu-id="e2766-116">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="e2766-116">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="e2766-117">A listában kattintson az Érintett dolgozók hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e2766-117">In the list, click the Workers affected link.</span></span>
12. <span data-ttu-id="e2766-118">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e2766-118">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="e2766-119">Kattintson a Személyzeti szám mezőben található hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e2766-119">Click to follow the link in the Personnel number field.</span></span>
14. <span data-ttu-id="e2766-120">Bontsa ki a Személyes adatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e2766-120">Expand the Personal information section.</span></span>
15. <span data-ttu-id="e2766-121">Kattintson a Juttatások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2766-121">Click Benefits.</span></span>
16. <span data-ttu-id="e2766-122">Keresse meg a juttatást és válassza ki a rekordot a listában.</span><span class="sxs-lookup"><span data-stu-id="e2766-122">In the list, find the benefit and select the record.</span></span> <span data-ttu-id="e2766-123">Ne feledje a juttatás nyújtásának új záró dátumát.</span><span class="sxs-lookup"><span data-stu-id="e2766-123">Note the new coverage end date.</span></span>
