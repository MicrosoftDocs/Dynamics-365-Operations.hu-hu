---
title: A szervizrendelések fokozatai
description: Szervizrendelési szakaszok definiálásával, és azok dolgozókhoz való hozzárendelésével, a szolgáltatási szervezeten belül dolgozó, különböző személyek által elvégzett feladatokon keresztül szabályozhatók a szervizrendelés folyamatai.
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b924be95c7e60598879e4d0cfd03193fe888dd7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569705"
---
# <a name="service-order-stages"></a><span data-ttu-id="cb56e-103">A szervizrendelések fokozatai</span><span class="sxs-lookup"><span data-stu-id="cb56e-103">Service order stages</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="cb56e-104">Annak érdekében, hogy meghatározza az elvégzendő feladatokat, a feladatok sorrendjét, és a feladatok elvégzéséért felelős dolgozókat, a szolgáltatási rendeléshez szakaszok beállítására van lehetőség.</span><span class="sxs-lookup"><span data-stu-id="cb56e-104">You can set up stages for a service order to define the tasks that must be completed, the order in which they are completed, and the workers who are responsible for completing them.</span></span> <span data-ttu-id="cb56e-105">Szervizrendelési szakaszok definiálásával, és azok dolgozókhoz való hozzárendelésével, a szolgáltatási szervezeten belül dolgozó, különböző személyek által elvégzett feladatokon keresztül szabályozhatóvá válnak a szervizrendelés folyamatai.</span><span class="sxs-lookup"><span data-stu-id="cb56e-105">By defining the stages for a service order and assigning them to workers, you can control the flow of a service order through the tasks that various people perform in the service organization.</span></span> <span data-ttu-id="cb56e-106">A szakaszok sorrendjének tartalmaznia kell a kezdő szakaszt.</span><span class="sxs-lookup"><span data-stu-id="cb56e-106">The sequence of stages must include an initial stage.</span></span>

<span data-ttu-id="cb56e-107">Az egyes szakaszokon belül engedélyezett műveleteket is meghatározhat.</span><span class="sxs-lookup"><span data-stu-id="cb56e-107">You can also define the actions that are permitted at each stage.</span></span> <span data-ttu-id="cb56e-108">Például ha az utolsó szakaszhoz tartozó jelölőnégyzetet leszámítva az összes **Feladás** jelölőnégyzet jelét törli, akkor megakadályozhatja, hogy egy szervizrendelés azelőtt feladásra kerüljön, hogy a rendelés összes szakasza feldolgozásra kerülne.</span><span class="sxs-lookup"><span data-stu-id="cb56e-108">For example, if you clear the **Post** check box for all stages except the final stage, you prevent any service orders from being posted before the service orders are processed through the complete sequence of stages.</span></span>

## <a name="branching-in-service-order-stages"></a><span data-ttu-id="cb56e-109">Szervizrendelési szakaszok elágaztatása</span><span class="sxs-lookup"><span data-stu-id="cb56e-109">Branching in service order stages</span></span>

<span data-ttu-id="cb56e-110">Ha egy szolgáltatási szakaszt állít be, a következő szakaszhoz több lehetőség vagy oldalág létrehozása közül választhat.</span><span class="sxs-lookup"><span data-stu-id="cb56e-110">When you set up a service stage, you can create multiple options, or branches, to select from for the next service stage.</span></span> <span data-ttu-id="cb56e-111">A kezdeti szakasz befejezése után az összes létrehozott ág közül választhat.</span><span class="sxs-lookup"><span data-stu-id="cb56e-111">All the branches that you create are available to select from when the initial stage is completed.</span></span> <span data-ttu-id="cb56e-112">Állítsa be például a **Tervezés** lehetőséget kezdeti szakaszként.</span><span class="sxs-lookup"><span data-stu-id="cb56e-112">For example, you set up **Planning** as an initial stage.</span></span> <span data-ttu-id="cb56e-113">Hozzon létre két szakaszt **Folyamatban** és **Érvénytelenítés** névvel, majd válassza a **Tervezés** szakaszt azok szülőjének.</span><span class="sxs-lookup"><span data-stu-id="cb56e-113">You create two stages named **In process** and **Cancel**, and then select **Planning** as the parent for them.</span></span> <span data-ttu-id="cb56e-114">Társítsa a **Tervezés** szakaszt az értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="cb56e-114">You assign the **Planning** stage to sales order.</span></span> <span data-ttu-id="cb56e-115">Amikor az értékesítési rendelés tervezési szakasza befejeződik, válassza a **Folyamatban** szakaszt, ha az értékesítési rendelés készen áll a munkára, vagy választhatja az **Érvénytelenítés** szakaszt, amennyiben az értékesítési rendelést érvénytelítették.</span><span class="sxs-lookup"><span data-stu-id="cb56e-115">When the planning stage for the sales order is completed, you can select the **In process** stage if the sales order is ready to work on, or you can select the **Cancel** stage if the sales order is canceled.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb56e-116">Lásd még</span><span class="sxs-lookup"><span data-stu-id="cb56e-116">See also</span></span>

[<span data-ttu-id="cb56e-117">Szervizrendelési fokozatok beállítása</span><span class="sxs-lookup"><span data-stu-id="cb56e-117">Set up service order stages</span></span>](set-up-service-order-stages.md)

[<span data-ttu-id="cb56e-118">Szervizrendelés fokozatának módosítása</span><span class="sxs-lookup"><span data-stu-id="cb56e-118">Change the service order stage</span></span>](change-service-order-stage.md)

  


