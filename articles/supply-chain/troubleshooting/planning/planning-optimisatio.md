---
title: A tervezett beszerzési rendelés akkor jön létre, ha a negatív napokon belül beszerzés létezik
description: Ha a fedezeti kód Min/max, a Tervezési optimalizálás tervezett beszerzési rendelést hoz létre, ha a negatív napokon belüli beszerzés létezik.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo,MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 826496c2de956ff949dd79ab8aa643053719bf75
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026581"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a><span data-ttu-id="1063b-103">A tervezett beszerzési rendelés akkor jön létre, ha a negatív napokon belül beszerzés létezik</span><span class="sxs-lookup"><span data-stu-id="1063b-103">Planned purchase order is created when a purchase exists within negative days</span></span>

<span data-ttu-id="1063b-104">Tudásbáziscikk száma: 4614298</span><span class="sxs-lookup"><span data-stu-id="1063b-104">KB number: 4614298</span></span>

## <a name="symptoms"></a><span data-ttu-id="1063b-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="1063b-105">Symptoms</span></span>

<span data-ttu-id="1063b-106">Ha a fedezeti kód *Min/max*, a Tervezési optimalizálás tervezett beszerzési rendelést hoz létre, ha a negatív napokon belüli beszerzés létezik.</span><span class="sxs-lookup"><span data-stu-id="1063b-106">If the coverage code is *Min/max*, Planning Optimization creates a planned purchase order when a purchase exists within negative days.</span></span>

## <a name="resolution"></a><span data-ttu-id="1063b-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="1063b-107">Resolution</span></span>

<span data-ttu-id="1063b-108">A tervezési optimalizálás nem támogatja a negatív napokat.</span><span class="sxs-lookup"><span data-stu-id="1063b-108">Planning Optimization doesn't support negative days.</span></span> <span data-ttu-id="1063b-109">Ugyanakkor mindig gondoskodik arról, hogy a tervezett rendelések ne legyenek ütemezéve az aktuális dátumhoz képest az átfutási időben.</span><span class="sxs-lookup"><span data-stu-id="1063b-109">However, it always ensures that planned orders won't be scheduled within the lead time relative to the current date.</span></span> <span data-ttu-id="1063b-110">Például a beszerzés átfutási ideje 10 nap, és a beszerzési rendelés várhatóan a mai naptól számítva nyolc nap múlva érkezik.</span><span class="sxs-lookup"><span data-stu-id="1063b-110">For example, the purchase lead time is 10 days, and a purchase order is expected to arrive eight days from today.</span></span> <span data-ttu-id="1063b-111">Ebben az esetben a beszerzési rendelés lesz a mai naptól számított ötödik napon lesz igény szerinti beszállításként használva.</span><span class="sxs-lookup"><span data-stu-id="1063b-111">In this case, the purchase order will be used as supply for demand that is five days from today.</span></span>

<span data-ttu-id="1063b-112">Ezért javasoljuk, hogy úgy módosítsa az átfutási időket, hogy minden (vagy szinte az összes) esetet lefedje.</span><span class="sxs-lookup"><span data-stu-id="1063b-112">Therefore, we recommend that you adjust your lead times to cover all (or almost all) of your scenarios.</span></span>
