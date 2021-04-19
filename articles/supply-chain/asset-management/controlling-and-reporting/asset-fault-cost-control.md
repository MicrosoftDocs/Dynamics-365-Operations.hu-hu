---
title: Hibás eszköz költségkontrollja
description: Ez a cikk az Eszközkezelés hibás eszköz költségkontrolljának költségét ismerteti.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 44b101c3b386c3edd8aec4c44e8ee834519718ec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811182"
---
# <a name="asset-fault-cost-control"></a><span data-ttu-id="9b496-103">Hibás eszköz költségkontrollja</span><span class="sxs-lookup"><span data-stu-id="9b496-103">Asset fault cost control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="9b496-104">Az Eszközkezelés modulban kiszámíthatja a hibáseszköz-regisztrációk költségét, így áttekintést kaphat a tényleges költségekről a költségvetési költségekhez képest.</span><span class="sxs-lookup"><span data-stu-id="9b496-104">In Asset Management, you can calculate costs on asset fault registrations to get an overview of actual costs compared to budget costs.</span></span> <span data-ttu-id="9b496-105">A tényleges költségek a feladott tranzakciókon alapulnak.</span><span class="sxs-lookup"><span data-stu-id="9b496-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="9b496-106">A dátum a hiba dátuma, amikor a hibajelenség rögzítése megtörtént.</span><span class="sxs-lookup"><span data-stu-id="9b496-106">The date is the fault date on which the symptom was recorded.</span></span>

1. <span data-ttu-id="9b496-107">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközhiba** > **Hibás eszköz költségkontrollja**.</span><span class="sxs-lookup"><span data-stu-id="9b496-107">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault cost control**.</span></span>

2. <span data-ttu-id="9b496-108">Ha szükséges, a **Hibás eszköz költségkontrollja** párbeszédablakban válasszon ki egy pénzügyi dimenziót, amelyet be kíván venni a számításba.</span><span class="sxs-lookup"><span data-stu-id="9b496-108">In the **Asset fault cost control** dialog, select a financial dimension set to be included in the calculation, if required.</span></span>

4. <span data-ttu-id="9b496-109">Ha a nulla költséget tartalmazó eredményeket nem szeretné megjeleníteni, állítsa a **Nulla kihagyása** választógombot „Igen” értékre.</span><span class="sxs-lookup"><span data-stu-id="9b496-109">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="9b496-110">A **Szint** mezőben megadhatja, hogy a költségellenőrzési sorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket.</span><span class="sxs-lookup"><span data-stu-id="9b496-110">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="9b496-111">Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a hibás eszköz költségkontrolljának minden munkavégzési helyszínhez tartozó sora a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből.</span><span class="sxs-lookup"><span data-stu-id="9b496-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="9b496-112">Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a hibás eszköz költségkontrollja minden sorát megjeleníti az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="9b496-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault cost control lines on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="9b496-113">Ha szűkíteni szeretné a keresést, kiválaszthat meghatározott eszközöket, meghibásodási dátumokat és hibaokokat a **Szerepeltetni kívánt rekordok** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="9b496-113">If you want to limit the search, you can select specific assets, fault dates, and fault causes on the **Records to include** FastTab.</span></span>

7. <span data-ttu-id="9b496-114">Kattintson az **OK** gombra az számítás indításához.</span><span class="sxs-lookup"><span data-stu-id="9b496-114">Click **OK** to start the calculation.</span></span>

8. <span data-ttu-id="9b496-115">Kattintson a **Csoportosítási szempont...** gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="9b496-115">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="9b496-116">A kiválasztott **Csoportosítási szempont…** ablaktáblacsoport gombjai ki vannak emelve.</span><span class="sxs-lookup"><span data-stu-id="9b496-116">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="9b496-117">A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.</span><span class="sxs-lookup"><span data-stu-id="9b496-117">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="9b496-118">Példa</span><span class="sxs-lookup"><span data-stu-id="9b496-118">Example</span></span>

<span data-ttu-id="9b496-119">Ez a példa egy eszköz hibás költségellenőrzési számítását jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="9b496-119">This example shows an asset fault cost control calculation.</span></span>

- <span data-ttu-id="9b496-120">Az **Eredeti költségvetés** mezőben a munkarendelési előrejelzésből származó költségvetési költségek láthatók.</span><span class="sxs-lookup"><span data-stu-id="9b496-120">The **Original budget** field shows budget costs from the work order forecast.</span></span> 
- <span data-ttu-id="9b496-121">A **Tényleges költség** mező a munkarendeléseken feladott költségeket jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="9b496-121">The **Actual cost** field shows posted costs on work orders.</span></span> 
- <span data-ttu-id="9b496-122">A **Vállalt költség** mezőben a teljes költség látható, amelyet a vállalat a munkarendelésekkel kapcsolatban vállalt.</span><span class="sxs-lookup"><span data-stu-id="9b496-122">The **Committed cost** field shows total costs that your company is committed to in relation to work orders.</span></span>

    ![1. ábra](media/05-controlling-and-reporting.png)

<span data-ttu-id="9b496-124">A hibák beállításával kapcsolatos tudnivalókat lásd a [Hibakezelés](../setup-for-work-orders/fault-management.md) témakörben.</span><span class="sxs-lookup"><span data-stu-id="9b496-124">For information about how to set up faults, see the [Fault management](../setup-for-work-orders/fault-management.md) topic.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]