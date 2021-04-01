---
title: Hipotézis meghatározása és mérőszámok megadása egy kísérlethez
description: Ez a témakör azt mutatja be, hogyan lehet a Dynamics 365 Commerce rendszerben e-kereskedelmi webhelyeken futtatott kísérlethez hipotézist és sikerességi mérőszámokat meghatározni.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 91614cda804cae4574fce4c9cfb31c63d876f19b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238630"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a><span data-ttu-id="f7082-103">Hipotézis meghatározása és sikerességi mérőszámok megadása egy kísérlethez</span><span class="sxs-lookup"><span data-stu-id="f7082-103">Identify a hypothesis and determine success metrics for an experiment</span></span>
<span data-ttu-id="f7082-104">A kísérletezési életciklus első fázisa tartalmazza a kísérlethez tartozó hipotézis, valamint a sikeresség értékeléséhez nyomon követni kívánt mérőszámok meghatározását.</span><span class="sxs-lookup"><span data-stu-id="f7082-104">The first phase in the experimentation lifecycle includes identifying the hypothesis for the experiment and determining the metrics you'll track to evaluate success.</span></span> <span data-ttu-id="f7082-105">A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó [kísérletet lehet létrehozni és futtatni](experimentation-overview.md) a Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="f7082-105">The following diagram shows all of the steps involved in [setting up and running an experiment](experimentation-overview.md) on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="f7082-106">A további lépések külön témákban szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="f7082-106">Additional steps are covered in separate topics.</span></span> 

<span data-ttu-id="f7082-107">[ ![Kísérletezés felhasználói interakciósorozata – Azonosítás](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="f7082-107">[ ![Experimentation user journey - Identify](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span></span>

<span data-ttu-id="f7082-108">A hipotézis egy olyan kijelentés, amelyben megjósolja a kísérlet kimenetelét.</span><span class="sxs-lookup"><span data-stu-id="f7082-108">A hypothesis is a statement where you predict the outcome of the experiment.</span></span> <span data-ttu-id="f7082-109">Számos tényező befolyásolja a hipotézist, így például a felhasználói magatartásról és a összegyűjtött webhely adatairól folytatott kutatás.</span><span class="sxs-lookup"><span data-stu-id="f7082-109">Many factors go into defining a hypothesis, for example, research about user behavior and website data you've collected.</span></span> <span data-ttu-id="f7082-110">A hipotézissel meghatározhatja, hogy milyen feltételezést vagy elméletet szeretne igazolni a kísérletével.</span><span class="sxs-lookup"><span data-stu-id="f7082-110">With the hypothesis, you'll define the assumption or theory you want to validate with your experiment.</span></span> <span data-ttu-id="f7082-111">Egy példa a kísérlethez meghatározható hipotézisre: „*ha a honlapomon egy fehér póló képe látható, akkor az több kattintást hoz majd, mint egy tengerkék pulóver a nyári hónapokban, mivel az emberek könnyű és világos színű ruhadarabokat viselnek a nyári hónapokban.*”</span><span class="sxs-lookup"><span data-stu-id="f7082-111">An example of a hypothesis for your experiment may be "*a picture of a white t-shirt on my home page will drive a higher clickthrough rate than a navy sweater during summer months because people want to wear something lightweight and light colored in the summer.*"</span></span> <span data-ttu-id="f7082-112">Ebben az esetben a fehér pólót és a tengerkék pulóvert tartalmazó változatokat hoz létre, és ezeket egyszerre közzé is teheti.</span><span class="sxs-lookup"><span data-stu-id="f7082-112">In that case, you'll create variations that include a white t-shirt and a navy sweater, and publish both at the same time.</span></span>

<span data-ttu-id="f7082-113">A hipotézis igazolásához egy kísérlet sikerességét vagy sikertelenségét közvetlenül a felhasználói műveletekhez kell kötni: például, hogy a webhely felhasználója rákattint-e egy hivatkozásra vagy gombra.</span><span class="sxs-lookup"><span data-stu-id="f7082-113">To validate a hypothesis, the success or failure of an experiment should be directly tied to user actions; for example, if the website user clicks on a link or button.</span></span> <span data-ttu-id="f7082-114">Ezeknek a műveleteknek meg kell egyezniük a harmadik fél szolgáltatás által a kísérlet nyomon követésére szolgáló jelentésekbe foglalt eseményekkel.</span><span class="sxs-lookup"><span data-stu-id="f7082-114">These actions must correspond with events that will be reported to the third-party service tracking the experiment.</span></span> <span data-ttu-id="f7082-115">Az idő előhaladásával a műveletet végrehajtó felhasználók százalékát a program mérőszámként összesíti, amelyekről jelentéseket készíthet vagy amelyeken elemzéseket folytathat le.</span><span class="sxs-lookup"><span data-stu-id="f7082-115">Over time, the percentage of users that take the action will be tallied as a metric you can use to generate reports and conduct analyses.</span></span> <span data-ttu-id="f7082-116">Az összes rendelkezésre álló esemény és attribútum áttekintéséhez lásd a [Commerce-összetevővel kapcsolatos események a diagnosztikához és a hibaelhárításhoz](dev-itpro/retail-component-events-diagnostics-troubleshooting.md) témakört.</span><span class="sxs-lookup"><span data-stu-id="f7082-116">To review all of the available events and attributes, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>

## <a name="previous-step"></a><span data-ttu-id="f7082-117">Előző lépés</span><span class="sxs-lookup"><span data-stu-id="f7082-117">Previous step</span></span>
[<span data-ttu-id="f7082-118">Kísérletezés a Dynamics 365 Commerce rendszerben</span><span class="sxs-lookup"><span data-stu-id="f7082-118">Experimentation in Dynamics 365 Commerce</span></span>](experimentation-overview.md)


## <a name="next-step"></a><span data-ttu-id="f7082-119">Következő lépés</span><span class="sxs-lookup"><span data-stu-id="f7082-119">Next step</span></span>
[<span data-ttu-id="f7082-120">Kísérlet beállítása</span><span class="sxs-lookup"><span data-stu-id="f7082-120">Set up an experiment</span></span>](experimentation-setup.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]