---
title: "Feltételes döntés konfigurálása munkafolyamatban"
description: "Ezt követően a következő eljárás segítségével állítsa be egy feltételes döntés tulajdonságait."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e9d5c8add546cad0446e863f64cac8f9cb603cbb
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="configure-a-conditional-decision-in-a-workflow"></a><span data-ttu-id="9bb5b-103">Feltételes döntés konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="9bb5b-103">Configure a conditional decision in a workflow</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="9bb5b-104">Ezt követően a következő eljárás segítségével állítsa be egy feltételes döntés tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-104">Use the following procedure to configure the properties of a conditional decision.</span></span>

<span data-ttu-id="9bb5b-105">A feltételes döntés egy olyan pont, ahol a munkafolyamat két ágra válik szét.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-105">A conditional decision is a point at which a workflow divides into two branches.</span></span> <span data-ttu-id="9bb5b-106">A munkafolyamat-szerkesztő feltételes döntésének konfigurálásához kattintson a jobb gombbal a feltételes döntésre, és kattintson a **Tulajdonságok** űrlap megnyitásához a **Tulajdonságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-106">To configure a conditional decision, in the workflow editor, right-click the conditional decision, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-a-decision"></a><span data-ttu-id="9bb5b-107">A döntés elnevezése</span><span class="sxs-lookup"><span data-stu-id="9bb5b-107">Name a decision</span></span>
<span data-ttu-id="9bb5b-108">A következő lépések segítségével elnevezheti a feltételes döntést.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-108">Follow these steps to enter a name for a conditional decision.</span></span>
1.  <span data-ttu-id="9bb5b-109">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-109">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="9bb5b-110">Adja meg a feltételes döntés egyedi nevét a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-110">In the **Name** field, enter a unique name for the conditional decision.</span></span>

## <a name="set-conditions"></a><span data-ttu-id="9bb5b-111"> Feltételek beállítása</span><span class="sxs-lookup"><span data-stu-id="9bb5b-111">Set conditions</span></span>
<span data-ttu-id="9bb5b-112">A rendszer eldönti, hogy mely ágat használja: a benyújtott dokumentum kiértékelésével határozza meg, hogy az megfelel-e bizonyos feltételeknek.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-112">The system determines which branch is used by evaluating the submitted document to determine whether it meets specific conditions.</span></span>
1.  <span data-ttu-id="9bb5b-113">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-113">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="9bb5b-114">Kattintson a **Feltétel hozzáadása** parancsra.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-114">Click **Add condition**.</span></span>
3.  <span data-ttu-id="9bb5b-115">Feltétel megadása.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-115">Enter a condition.</span></span>
4.  <span data-ttu-id="9bb5b-116">Ha szükséges, adjon meg további feltételeket.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-116">Enter additional conditions, if they are required.</span></span>
5.  <span data-ttu-id="9bb5b-117">Ha ellenőrizni szeretné, hogy a megadott feltételek helyesen vannak-e konfigurálva, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="9bb5b-117">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>
    1.  <span data-ttu-id="9bb5b-118">Kattintson a **Teszt** elemre a **Munkafolyamati feltétel tesztelése** űrlap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-118">Click **Test** to open the **Test workflow condition** form.</span></span>
    2.  <span data-ttu-id="9bb5b-119">Válasszon ki egy bejegyzést a képernyő **Feltétel érvényesítése** területén.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-119">Select a record in the **Validate condition** area of the form.</span></span>
    3.  <span data-ttu-id="9bb5b-120">Kattintson a **Teszt** gombra.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-120">Click **Test**.</span></span> <span data-ttu-id="9bb5b-121">A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy a meghatározott feltételeknek megfeleljen-e.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-121">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4.  <span data-ttu-id="9bb5b-122">Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** űrlapra történő visszalépéshez.</span><span class="sxs-lookup"><span data-stu-id="9bb5b-122">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>






