---
title: Szervezeti modellezési hierarchiák létrehozása B2B szervezetek számára
description: Ez a témakör azt ismerteti, hogyan lehet szervezeti modellezési hierarchiákat létrehozni B2B szervezetek számára.
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 450efd595a1cc1b72b2e62afbdd4518bcca59cb0
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035915"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a><span data-ttu-id="e5bc5-103">Szervezeti modellezési hierarchiák létrehozása B2B szervezetek számára</span><span class="sxs-lookup"><span data-stu-id="e5bc5-103">Create org modeling hierarchies for B2B organizations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e5bc5-104">Ez a témakör azt ismerteti, hogyan lehet szervezeti modellezési hierarchiákat létrehozni B2B szervezetek számára a Microsoft Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-104">This topic describes how to create organizational modeling hierarchies for business-to-business (B2B) organizations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="e5bc5-105">A Commerce központi felületén az üzleti partnereket a vevői és vevői hierarchiaentitások képviselik.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-105">In Commerce headquarters, business partner organizations are represented by customer and customer hierarchy entities.</span></span> <span data-ttu-id="e5bc5-106">Az üzleti partner szervezetét és felhasználóit vevőkként ábrázolja a rendszer, és a vevőhierarchiák segítségével társítja ezeket a vevőket egymáshoz.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-106">The business partner organization and its users are represented as customers, and customer hierarchies are used to associate those customers with each other.</span></span>

<span data-ttu-id="e5bc5-107">Amikor jóváhagyják egy üzleti partner kérését egy B2B e-kereskedelmi webhelyhez való csatlakozásra, a rendszer a következő műveleteket hajtja végre:</span><span class="sxs-lookup"><span data-stu-id="e5bc5-107">When a business partner request to join a B2B e-commerce site is approved, the following actions are performed:</span></span>

- <span data-ttu-id="e5bc5-108">A rendszerben két új vevőrekord jön létre: az üzleti partner szervezetéhez egy **Szervezet típusa** vevőrekord, a kérelmezőhöz (tehát a kérelmet benyújtó üzleti partnerhez) pedig egy **Személy típusa** vevőrekord.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-108">Two new customer records are created in the system: a **Type Organization** customer record for the business partner organization and a **Type Person** customer record for the requestor (that is, the business partner user who submitted the request).</span></span>
- <span data-ttu-id="e5bc5-109">Új vevőhierarchia jön létre a **Vevő \> Vevőhierarchia** pontban.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-109">A new customer hierarchy record is created under **Customer \> Customer hierarchy**.</span></span> <span data-ttu-id="e5bc5-110">Ennek a rekordnak a következő fejléctulajdonságai vannak:</span><span class="sxs-lookup"><span data-stu-id="e5bc5-110">This record has the following header properties:</span></span>

    - <span data-ttu-id="e5bc5-111">**Vevőhierarchia azonosítója** – a vevőhierarchia egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-111">**Customer hierarchy ID** – A unique ID for the customer hierarchy.</span></span> <span data-ttu-id="e5bc5-112">Ez az azonosító a Commerce központi felületén a Commerce megosztott paramétereiben meghatározott számsorozatot használja.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-112">This ID uses the number sequence that is defined in Commerce shared parameters in Commerce headquarters.</span></span>
    - <span data-ttu-id="e5bc5-113">**Név** – az üzleti partner szervezetének neve a beléptetési kérelemben megadottaknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-113">**Name** – The organization name of the business partner, as specified in the onboarding request.</span></span>
    - <span data-ttu-id="e5bc5-114">**Cél** – ez a tulajdonság az előre meghatározott **B2B szervezet** értékre van beállítva.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-114">**Purpose** – This property is set to the predefined value **B2B organization**.</span></span>
    - <span data-ttu-id="e5bc5-115">**Szervezet** – az üzleti partner vevőazonosítója.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-115">**Organization** – The customer ID of the business partner.</span></span>

<span data-ttu-id="e5bc5-116">A vevőhierarchia-rekord részletei:</span><span class="sxs-lookup"><span data-stu-id="e5bc5-116">Here are the details of the customer hierarchy record:</span></span>

- <span data-ttu-id="e5bc5-117">A kérelmező vevőrekordja a vevőhierarchiához van társítva.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-117">The customer record of the requestor is associated with the customer hierarchy.</span></span>
- <span data-ttu-id="e5bc5-118">A rendszergazdai szerepkör a kérelmezőhöz van társítva.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-118">The administrator role is associated with the requestor.</span></span>

<span data-ttu-id="e5bc5-119">Amikor a rendszergazda további felhasználókat ad hozzá egy B2B webhely üzleti partner szervezetéhez, a Commerce központi felületén minden felhasználóhoz létrejön egy új vevőrekord.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-119">When the administrator adds more users are to the business partner organization on a B2B site, a new customer record for each user is created in Commerce headquarters.</span></span> <span data-ttu-id="e5bc5-120">A rendszer ezt a vevőrekordot az üzleti partnerhez kapcsolódó vevői hierarchiarekordhoz is hozzáadja, a szerepköre pedig felhasználó.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-120">This customer record is also added to the relevant customer hierarchy record for the business partner and has the role of a "user."</span></span>

> [!NOTE]
> <span data-ttu-id="e5bc5-121">A legtöbb esetben egy hierarchiában található vevőrekordok megfelelő tulajdonságértékének meg kell egyeznie egymással.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-121">In most cases, the corresponding property values of all customer records in a hierarchy should match.</span></span> <span data-ttu-id="e5bc5-122">Például mivel minden üzleti partner felhasználójának hasonló árakat kell kapnia a termékekre, ezért az árcsoportnak és a társított konfigurációknak is egyezniük kell.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-122">For example, because all business partner users should get similar prices for products, their price group and associated configurations should match.</span></span> <span data-ttu-id="e5bc5-123">A rendszer azonban nem érvényesíti ezt a konzisztenciát.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-123">However, the system doesn't enforce this consistency.</span></span> <span data-ttu-id="e5bc5-124">Ezért a Commerce központi felületének adott felhasználói felelősek azért, hogy a tulajdonságértékek és konfigurációk egy adott hierarchiában lévő összes vevőre vonatkozóan megegyezzenek egymással.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-124">Therefore, the relevant Commerce headquarters users are responsible for ensuring that the property values and configurations match for all customers in a given hierarchy.</span></span>

<span data-ttu-id="e5bc5-125">A Commerce központi felületének felhasználói egymás mellé helyezve megtekinthetik a hierarchia összes vevőrekordjának tulajdonságértékeit.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-125">Commerce headquarters users can look at the property values for all customer records in the hierarchy in a side-by-side view.</span></span> <span data-ttu-id="e5bc5-126">Válassza ki a megfelelő vevőrekord-tulajdonságokat a legördülő menü lapnevének kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-126">Select the relevant customer record properties by selecting the tab names on the drop-down menu.</span></span> <span data-ttu-id="e5bc5-127">A felhasználók közvetlenül megtekinthetik és szerkeszthetik az ebből a nézetből származó tulajdonságértékeket.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-127">Users can directly view and edit the property values from this view.</span></span> <span data-ttu-id="e5bc5-128">Másik lehetőségként ha a rendszergazdai vevőrekord összes értékét szeretné alkalmazni az összes felhasználói vevőrekordra, a vevőhierarchia részletes adatai között válassza a **Felülbírálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e5bc5-128">Alternatively, if you want to apply all the values from the administrator customer record to all the user customer records, select **Override** in the customer hierarchy details.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e5bc5-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e5bc5-129">Additional resources</span></span>

[<span data-ttu-id="e5bc5-130">B2B e-kereskedelmi webhely beállítása</span><span class="sxs-lookup"><span data-stu-id="e5bc5-130">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="e5bc5-131">Üzleti partner típusú felhasználók kezelése a B2B e-kereskedelmi webhelyeken</span><span class="sxs-lookup"><span data-stu-id="e5bc5-131">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="e5bc5-132">A B2B e-commerce webhelyekhez használt vevői számlafizetési mód konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e5bc5-132">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)

[<span data-ttu-id="e5bc5-133">Termékmennyiség-korlátok beállítása B2B e-kereskedelmi webhelyekhez</span><span class="sxs-lookup"><span data-stu-id="e5bc5-133">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)
