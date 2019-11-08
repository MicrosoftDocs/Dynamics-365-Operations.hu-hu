---
title: Karbantartási ütemezés költsége
description: Ez a cikk az Eszközkezelés karbantartási ütemezésének költségét ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b30fa3c142057b43202a8f5a323c0b425865e971
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571323"
---
# <a name="maintenance-schedule-cost"></a><span data-ttu-id="56dcf-103">Karbantartási ütemezés költsége</span><span class="sxs-lookup"><span data-stu-id="56dcf-103">Maintenance schedule cost</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="56dcf-104">Az Eszközkezelésben kiszámolható karbantartási ütemezés soraiban lévő költségvetési költség.</span><span class="sxs-lookup"><span data-stu-id="56dcf-104">In Asset Management, you can calculate budget costs on maintenance schedule lines.</span></span> <span data-ttu-id="56dcf-105">Ez akkor lehet hasznos, ha áttekintést szeretne kapni a várható költségekről, például a következő évre tervezett megelőző karbantartási feladatokkal kapcsolatos költségekről.</span><span class="sxs-lookup"><span data-stu-id="56dcf-105">This is useful if you want to get an overview of expected costs, for example, costs relating to planned preventive maintenance jobs for the next year.</span></span> <span data-ttu-id="56dcf-106">A számítások a karbantartási ütemezés „Karbantartási tervek”, „Karbantartási körök” és „Karbantartási kérések” típusú sorain.</span><span class="sxs-lookup"><span data-stu-id="56dcf-106">The calculations are based on existing maintenance schedule lines of type "Maintenance plans" and "Maintenance rounds" and "Maintenance requests".</span></span>

1. <span data-ttu-id="56dcf-107">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Karbantartási ütemezés költsége** elemre.</span><span class="sxs-lookup"><span data-stu-id="56dcf-107">Click **Asset management** > **Inquiries** > **Assets** > **Maintenance schedule cost**.</span></span>

2. <span data-ttu-id="56dcf-108">Ha pénzügyi dimenziókba csoportosítva szeretné a költségeket látni, a **Karbantartási ütemezés költsége** párbeszédpanelen válasszon ki egy **pénzügyi dimenziókészletet**.</span><span class="sxs-lookup"><span data-stu-id="56dcf-108">In the **Maintenance schedule cost** dialog, you can select a **Financial dimension set** if you want to see costs grouped in financial dimensions.</span></span>

>[!NOTE]
><span data-ttu-id="56dcf-109">A pénzügyi dimenziókészletek a **Főkönyv** > **Számlatükör** > **Dimenziók** > **Pénzügyi dimenziókészletek** részen állíthatók be.</span><span class="sxs-lookup"><span data-stu-id="56dcf-109">Financial dimension sets are set up in **General ledger** > **Chart of accounts** > **Dimensions** > **Financial dimension sets**.</span></span>

3. <span data-ttu-id="56dcf-110">A **Szint** mezőben adhatja meg, hogy a karbantartási ütemezés sorai milyen részletesen jelenítsék meg a munkavégzési helyszíneket.</span><span class="sxs-lookup"><span data-stu-id="56dcf-110">You can use the **Level** field to indicate how detailed you want the maintenance schedule lines to be regarding functional locations.</span></span> <span data-ttu-id="56dcf-111">Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a karbantartási ütemezés minden munkavégzési helyszínhez tartozó sora a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből.</span><span class="sxs-lookup"><span data-stu-id="56dcf-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="56dcf-112">Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a karbantartási ütemezési minden sorát megjeleníti az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="56dcf-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="56dcf-113">Ha adott eszközre vonatkozóan szeretne számítást végezni, kattintson a **Belefoglalandó rekordok** gyorslap **Szűrő** elemére, és válassza ki a megfelelő eszközöket.</span><span class="sxs-lookup"><span data-stu-id="56dcf-113">If you want to make a calculation for specific assets, click **Filter** on the **Records to include** FastTab, and select the relevant assets.</span></span> <span data-ttu-id="56dcf-114">Ha szükséges, megadhatja a költségszámítás **várható kezdési dátumát**, vagy kiválaszthat egy másik **állapotot** a költségszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="56dcf-114">If required, you can also specify an **Expected start** date for the cost calculation or select a different **Status** for the cost calculation</span></span>

5. <span data-ttu-id="56dcf-115">Kattintson az **OK** gombra az költségszámítás indításához.</span><span class="sxs-lookup"><span data-stu-id="56dcf-115">Click **OK** to start the cost calculation.</span></span>

6. <span data-ttu-id="56dcf-116">A **Karbantartási ütemezés költsége** lap > **Csoportosítás alapja...** műveleti ablaktáblacsoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="56dcf-116">On the **Maintenance schedule cost** tab > in the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the cost calculation.</span></span> <span data-ttu-id="56dcf-117">A kiválasztott műveleti ablaktáblacsoport gombjai ki vannak emelve.</span><span class="sxs-lookup"><span data-stu-id="56dcf-117">The selected action pane group buttons are highlighted.</span></span> <span data-ttu-id="56dcf-118">A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.</span><span class="sxs-lookup"><span data-stu-id="56dcf-118">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="56dcf-119">Ha új költségszámítási számítást szeretne végezni, kattintson a **Költségszámítás** gombra.</span><span class="sxs-lookup"><span data-stu-id="56dcf-119">Click the **Calculate cost** button if you want to make a new cost calculation.</span></span>

<span data-ttu-id="56dcf-120">A lenti ábra a karbantartás ütemezés költség-számításának eredményeit mutatja.</span><span class="sxs-lookup"><span data-stu-id="56dcf-120">The illustration below shows the results of a maintenance schedule cost calculation.</span></span>

![1. ábra](media/17-preventive-maintenance.png)

