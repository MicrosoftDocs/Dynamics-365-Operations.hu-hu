---
title: "Költségobjektum-dimenziók"
description: "Amikor költségeket elemez, a költségobjektum-dimenziók segítségével határozza meg, hová kerülnek a költségek. Használja a költségobjektum-dimenziókat a költségek hozzárendelésének meghatározására. Ez a témakör tájékoztatást nyújt a költségobjektum-dimenziókkal kapcsolatban."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: ca455665907b7896d580bfcabea87a18c1884445
ms.contentlocale: hu-hu
ms.lasthandoff: 07/18/2017

---

# <a name="cost-object-dimensions"></a><span data-ttu-id="85e15-105">Költségobjektum-dimenziók</span><span class="sxs-lookup"><span data-stu-id="85e15-105">Cost object dimensions</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="85e15-106">Amikor költségeket elemez, a költségobjektum-dimenziók segítségével határozza meg, hová kerülnek a költségek.</span><span class="sxs-lookup"><span data-stu-id="85e15-106">When you analyze costs, you use cost element dimensions to determine where costs flow to.</span></span> <span data-ttu-id="85e15-107">Használja a költségobjektum-dimenziókat a költségek hozzárendelésének meghatározására.</span><span class="sxs-lookup"><span data-stu-id="85e15-107">You use cost object dimensions to determine where you should assign costs.</span></span> <span data-ttu-id="85e15-108">Ez a témakör tájékoztatást nyújt a költségobjektum-dimenziókkal kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="85e15-108">This topic provides information about cost object dimensions.</span></span>

<span data-ttu-id="85e15-109">A költségobjektum lehet bármilyen olyan típusú objektum, amellyel becslést akar végezni, amelyhez költségeket akar rendelni, vagy amelyet közvetlenül mérni kíván.</span><span class="sxs-lookup"><span data-stu-id="85e15-109">A cost object can be any type of object that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="85e15-110">A tipikus költségobjektumok közé tartoznak a termékek, projektek, erőforrások, részlegek, költséghelyek és földrajzi területek.</span><span class="sxs-lookup"><span data-stu-id="85e15-110">Typical cost objects include products, projects, resources, departments, cost centers, and geographical regions.</span></span> <span data-ttu-id="85e15-111">A vezetés a költségobjektumokat a költségek mennyiségének megállapítására és nyereségességi elemzés elvégzésére használja.</span><span class="sxs-lookup"><span data-stu-id="85e15-111">Management uses cost objects to quantify costs and also to drive profitability analysis.</span></span>

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a><span data-ttu-id="85e15-112">Költségobjektum-dimenziók és költségobjektum-dimenziótagok</span><span class="sxs-lookup"><span data-stu-id="85e15-112">Cost object dimensions and cost object dimension members</span></span>
<span data-ttu-id="85e15-113">A költségobjektumok *költségobjektum-dimenzióként* ismertek.</span><span class="sxs-lookup"><span data-stu-id="85e15-113">Cost objects are known as *cost object dimensions*.</span></span> <span data-ttu-id="85e15-114">Miután eldöntötte, hogy a költségobjektum-dimenzió mely entitáshoz tartozzon, meg kell határoznia az egyedi dimenzióértékeket vagy importálnia kell azokat a költségkönyvelésbe más forrásokból.</span><span class="sxs-lookup"><span data-stu-id="85e15-114">After you’ve decided which entity the cost object dimension should refer to, you must specify the individual dimension values or import them into Cost accounting from other source systems.</span></span> <span data-ttu-id="85e15-115">Ezek az egyes dimenzióértékek *költségobjektum-dimenziótagokként* ismertek.</span><span class="sxs-lookup"><span data-stu-id="85e15-115">These individual dimension values are known as *cost object dimension members*.</span></span> <span data-ttu-id="85e15-116">Példa: Ön a költséghely elnevezésű pénzügyi dimenziót akarja költségobjektum-dimenzióként használni.</span><span class="sxs-lookup"><span data-stu-id="85e15-116">For example, you want to use the financial dimension that is named Cost center as the cost object dimension.</span></span> <span data-ttu-id="85e15-117">Ahhoz, hogy lássa, hogyan kerülnek a költségek az egyes költséghelyekhez, importálnia kell a költségobjektum-dimenziótagokat.</span><span class="sxs-lookup"><span data-stu-id="85e15-117">To see how costs flow to the individual cost centers, you must import the cost object dimension members.</span></span> <span data-ttu-id="85e15-118">Ebben az esetben a költségobjektum-dimenziótagok a tényleges költséghelyek, például értékesítés, termelés, felügyelet vagy földrajzi hely.</span><span class="sxs-lookup"><span data-stu-id="85e15-118">In this case, the cost object dimension members are the actual cost centers, such as Sales, Production, Administration, and Geographic locations.</span></span> <span data-ttu-id="85e15-119">Az alábbi képernyőképen látható példa a költséghelyeket ábrázolja költségobjektum-dimenzióként, ahol a tényleges költséghelyek a költségobjektum-dimenziótagok.</span><span class="sxs-lookup"><span data-stu-id="85e15-119">The following screenshot shows an example of Cost Centers as the cost object dimension with its actual cost centers as cost object dimension members.</span></span> 

<span data-ttu-id="85e15-120">[![cost-object-dimensions](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="85e15-120">[![cost-object-dimensions](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span></span>

## <a name="import-cost-object-dimension-members-through-data-connectors"></a><span data-ttu-id="85e15-121">Költségobjektum-dimenziókagok importálása át adatcsatolókon keresztül</span><span class="sxs-lookup"><span data-stu-id="85e15-121">Import cost object dimension members through data connectors</span></span>
<span data-ttu-id="85e15-122">Ahhoz, hogy a költségobjektum-dimenziótagokat könnyebben lehessen importálni, használja az adatcsatolókat az értékek lekéréséhez azokból az entitásokból, amelyeket költségobjektum-dimenzióként akar használni.</span><span class="sxs-lookup"><span data-stu-id="85e15-122">To make the import of cost object dimension members easier, you use data connectors to retrieve the values from the entities that you want to use as cost object dimensions.</span></span> <span data-ttu-id="85e15-123">Használhat előre elkészített adatcsatolókat vagy egyedi, saját összeállítású adatcsatolókat.</span><span class="sxs-lookup"><span data-stu-id="85e15-123">You can use either the pre-built data connectors or custom data connectors that you build.</span></span>




