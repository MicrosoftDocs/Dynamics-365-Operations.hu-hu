---
title: Féléves értékcsökkenési szabály módszertana
description: Ez a témakör azt mutatja be, hogy a tárgyi eszközökhöz milyen módszerrel számítják ki az értékcsökkenést a féléves szabály alapján, amely az eszköz első és utolsó évében a szolgáltatásban számított hat hónapos értékcsökkenést számítja ki.
author: moaamer
manager: Ann Beebe
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: cb027513da086d882942c4677892b15cf8e7b338
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260805"
---
# <a name="half-year-depreciation-convention-methodology"></a><span data-ttu-id="9bfeb-103">Féléves értékcsökkenési szabály módszertana</span><span class="sxs-lookup"><span data-stu-id="9bfeb-103">Half-year depreciation convention methodology</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="9bfeb-104">Ez a témakör azt mutatja be, hogy milyen módszer van alkalmazva a tárgyi eszközökhöz az értékcsökkenés kiszámítására a féléves szabályok használatával.</span><span class="sxs-lookup"><span data-stu-id="9bfeb-104">This topic describes the method that is used in fixed assets to calculate depreciation using the half-year convention.</span></span> <span data-ttu-id="9bfeb-105">A Féléves szabály egy eszköz első és utolsó évében kiszámítja az értékcsökkenést hat hónapra.</span><span class="sxs-lookup"><span data-stu-id="9bfeb-105">The half-year convention calculates six months of depreciation during an asset’s first and last year of service.</span></span> <span data-ttu-id="9bfeb-106">Az értékcsökkenési szabályokkal kapcsolatos további tudnivalókért lásd: [Értékcsökkenési módszerek és szabályok](Fixed-asset-depreciation-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="9bfeb-106">For more information about depreciation conventions, see [Depreciation methods and conventions](Fixed-asset-depreciation-conventions.md).</span></span> 

<span data-ttu-id="9bfeb-107">Amikor a hathónapos értékcsökkenési szabályt használja, a rendszer a beszerzés évét vagy az eszköz üzembe helyezésének évét használja, majd az adott évtől számított öt éves értékcsökkenést számítja ki, majd hat hónapot hozzáad.</span><span class="sxs-lookup"><span data-stu-id="9bfeb-107">When you use the six-month depreciation convention, the system uses the acquisition year or the year that the asset was placed in service, then calculates five years of depreciation from that year, and then adds six months.</span></span> <span data-ttu-id="9bfeb-108">Ennek a folyamatnak a szemléltetéséhez képzeljen el egy olyan eszközt, amelyet a 50 000 dollárért vettek 2020 augusztusában.</span><span class="sxs-lookup"><span data-stu-id="9bfeb-108">To illustrate this process, consider an asset that was acquired for the price of 50,000, and placed in service in April 2020.</span></span> <span data-ttu-id="9bfeb-109">Azt is feltételezi, hogy az eszköznek ötéves élettartama van.</span><span class="sxs-lookup"><span data-stu-id="9bfeb-109">Also assume that the asset has a five-year service life.</span></span>

<span data-ttu-id="9bfeb-110">Az üzemelés első éve 2020 decemberében kezdődik ami azt jelenti, hogy az eszköz ötéves élettartamának vége 2024 december.</span><span class="sxs-lookup"><span data-stu-id="9bfeb-110">The first year of service will conclude in December 2020, which means the end of the asset’s five-year service life will be December 2024.</span></span> <span data-ttu-id="9bfeb-111">A féléves értékcsökkenési szabály hat hónapot ad hozzá az eszköz élettartamához, ami azt jelenti, hogy a hasznos élettartam 2025 júniusában fog befejeződni.</span><span class="sxs-lookup"><span data-stu-id="9bfeb-111">The half-year depreciation convention will add six months to the asset’s life, which means its service life will end in June 2025.</span></span> 

> <span data-ttu-id="9bfeb-112">Évenkénti értékcsökkenés 50000/5 = 10 000 havi értékcsökkenés 10000/12 = 833,33</span><span class="sxs-lookup"><span data-stu-id="9bfeb-112">Yearly depreciation 50,000/5 = 10,000 monthly depreciation 10,000/12 = 833.33</span></span> <br>
> <span data-ttu-id="9bfeb-113">Első évi értékcsökkenés 10000/2 = 5 000 és az azt követő havi értékcsökkenés 5000/9 = 555,56</span><span class="sxs-lookup"><span data-stu-id="9bfeb-113">First year depreciation 10,000/2 = 5,000  and the subsequent monthly depreciation 5,000/9 = 555.56</span></span>

   <span data-ttu-id="9bfeb-114">[![Féléves értékcsökkenési szabály értékcsökkenési ütemezése](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)</span><span class="sxs-lookup"><span data-stu-id="9bfeb-114">[![Depreciation schedule for half-year depreciation convention](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)</span></span>

<span data-ttu-id="9bfeb-115">A féléves konvencióval hozzáadott meghosszabbított értékcsökkenési időszakok pontosabban osztják fel az értékcsökkenést.</span><span class="sxs-lookup"><span data-stu-id="9bfeb-115">The extended depreciation periods that are added by the half-year convention provide more accurate allocation of depreciation.</span></span> <span data-ttu-id="9bfeb-116">A hat hónapos szabály egyenletesebben képviseli az értékcsökkenést, ami az eredménykimutatásban történő jelentéshez hasznos.</span><span class="sxs-lookup"><span data-stu-id="9bfeb-116">The six-month convention represents depreciation expenses more equally, which is useful for reporting on the profit and loss statement.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]