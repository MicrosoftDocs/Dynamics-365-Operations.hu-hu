---
title: Dynamics 365 Commerce értékelési környezet áttekintése
description: Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce értékelési környezetről.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: bdd634a04b6bbcf50d04cae8d670367268e57f1e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795883"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a><span data-ttu-id="48519-103">Dynamics 365 Commerce értékelési környezet áttekintése</span><span class="sxs-lookup"><span data-stu-id="48519-103">Dynamics 365 Commerce evaluation environment overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="48519-104">Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce értékelési környezetről.</span><span class="sxs-lookup"><span data-stu-id="48519-104">This topic gives an overview of the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

> [!NOTE]
> <span data-ttu-id="48519-105">A Commerce értékelési környezetek általában nem állnak rendelkezésre, és a partnerek és a vevők számára a kérelem alapján biztosítják.</span><span class="sxs-lookup"><span data-stu-id="48519-105">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="48519-106">További információért lépjen kapcsolatba Microsoft-partnerének kapcsolattartójával.</span><span class="sxs-lookup"><span data-stu-id="48519-106">For more information, reach out to your Microsoft partner contact.</span></span>

<span data-ttu-id="48519-107">A Commerce értékelési környezet egy opcionális, átfogó előzetes verziós környezete a Dynamics 365 Commerce alkalmazásnak, amely lehetővé teszi a partnerek és potenciális vásárlók számára a Commerce termék kipróbálását.</span><span class="sxs-lookup"><span data-stu-id="48519-107">The Commerce evaluation environment is an optional end-to-end environment of Dynamics 365 Commerce that lets partners and potential customers try out the Commerce product.</span></span>

<span data-ttu-id="48519-108">Az értékelési környezetek részben előre be vannak állítva, hogy csökkentsék a szükséges kiépítés utáni lépéseket.</span><span class="sxs-lookup"><span data-stu-id="48519-108">Evaluation environments are partially preconfigured to reduce the required post-provisioning steps.</span></span>

<span data-ttu-id="48519-109">Eltekintve néhány kisebb korlátozástól, amelyek nem befolyásolják a funkciókat és a működést, a Commerce értékelési környezet biztosítja a teljes Commerce-élményt, és az ügyfelek és a megvalósító partnerek felhasználhatják a termék értékeléséhez, visszajelzéshez és illeszkedés-/hiányelemzés elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="48519-109">Aside from some minor limitations that don't affect features or functionality, the Commerce evaluation environment provides the complete Commerce experience, and can be used by customers and implementation partners to evaluate the product, provide feedback, and do fit/gap analysis.</span></span>

## <a name="limitations-of-the-commerce-evaluation-environment"></a><span data-ttu-id="48519-110">A Commerce értékelési környezet korlátozásai</span><span class="sxs-lookup"><span data-stu-id="48519-110">Limitations of the Commerce evaluation environment</span></span>

<span data-ttu-id="48519-111">Bár a Commerce értékelési környezet teljes körű Commerce szolgáltatásokat és funkciókat kínál, néhány kisebb korlátozást van érvényben:</span><span class="sxs-lookup"><span data-stu-id="48519-111">Although the Commerce evaluation environment provides the full set of Commerce features and functionality, there are some minor limitations:</span></span>

- <span data-ttu-id="48519-112">Bár a Commerce értékelési környezet önmagában nem rendelkezik földrajzi korlátokkal, a környezet összetevői, például a Retail Cloud Scale Unit (RCSU) és az e-Commerce alkalmazások csak az Egyesült Államokban létesíthetők.</span><span class="sxs-lookup"><span data-stu-id="48519-112">Although the Commerce evaluation environment itself has no geographical limitations, components of the environment, such as the Retail Cloud Scale Unit (RCSU) and e-Commerce applications, should be provisioned only in the United States.</span></span>
- <span data-ttu-id="48519-113">A Commerce értékelési környezet használata 30 napra korlátozódik az e-Commerce létesítésének napjától számítva.</span><span class="sxs-lookup"><span data-stu-id="48519-113">Use of the Commerce evaluation environment is limited to 30 days from the date when e-Commerce is provisioned.</span></span>
- <span data-ttu-id="48519-114">A Commerce értékelési környezet csak olyan környezetben telepíthető és inicializálható, amely a demó topológiát használja, ahol a környezet minden összetevője egyetlen, felhőben szolgáltatott virtuális gépen (VM) van telepítve.</span><span class="sxs-lookup"><span data-stu-id="48519-114">The Commerce evaluation environment can be successfully deployed and initialized only in an environment that uses the demo topology, where all components of an environment are deployed on a single cloud-hosted virtual machine (VM).</span></span> <span data-ttu-id="48519-115">Ennek a topológiának a fő korlátja a párhuzamos felhasználók száma, amit a környezet támogatni tud.</span><span class="sxs-lookup"><span data-stu-id="48519-115">The main limitation of this topology is the number of concurrent users that the environment can support.</span></span>

## <a name="get-started"></a><span data-ttu-id="48519-116">Első lépések</span><span class="sxs-lookup"><span data-stu-id="48519-116">Get started</span></span>

<span data-ttu-id="48519-117">A Commerce értékelési környezet létesítéséhez lásd: [Commerce értékelési környezet kiépítése](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="48519-117">To provision the Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="48519-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="48519-118">Additional resources</span></span>

[<span data-ttu-id="48519-119">Dynamics 365 Commerce értékelési környezet kiépítése</span><span class="sxs-lookup"><span data-stu-id="48519-119">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="48519-120">Dynamics 365 Commerce értékelési környezet konfigurálása</span><span class="sxs-lookup"><span data-stu-id="48519-120">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="48519-121">BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben</span><span class="sxs-lookup"><span data-stu-id="48519-121">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="48519-122">Dynamics 365 Commerce értékelési környezet választható funkcióinak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="48519-122">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="48519-123">Dynamics 365 Commerce értékelési környezet GYIK</span><span class="sxs-lookup"><span data-stu-id="48519-123">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
