---
title: Számlafizetési forgatókönyvek beállítása
description: Ez a témakör azt részletezi, hogy hogyan lehet a Dynamics 365 for Retail szolgáltatást úgy konfigurálni, hogy támogassa a számlakifizetésekkel kapcsolatos különböző eseteket.
author: josaw1
manager: AnnBe
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: b7132dc9b3c78fa04fcfc38ea72b5678ad08deb2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "302379"
---
# <a name="set-up-pay-invoice-scenarios"></a><span data-ttu-id="01f30-103">Számlafizetési forgatókönyvek beállítása</span><span class="sxs-lookup"><span data-stu-id="01f30-103">Set up pay invoice scenarios</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="01f30-104">A Dynamics 365 for Retail Számlafizetés funkcióját a következők támogatására terjesztették ki:</span><span class="sxs-lookup"><span data-stu-id="01f30-104">The Pay invoice functionality in Dynamics 365 for Retail has been expanded to support:</span></span>

- <span data-ttu-id="01f30-105">Több értékesítési rendelés számlájának kifizetése egyetlen pénztártranzakció során.</span><span class="sxs-lookup"><span data-stu-id="01f30-105">Payoff of multiple sales order invoices in a single POS transaction.</span></span>
- <span data-ttu-id="01f30-106">Különböző vevői számlatípusok kifizetése, mint például szabadszöveges számlák, projektalapú számlák és jóváírások.</span><span class="sxs-lookup"><span data-stu-id="01f30-106">Payment of various customer invoice types including free text invoices, project-based invoices, and credit notes.</span></span>

<span data-ttu-id="01f30-107">A forgatókönyvek engedélyezéséhez az alábbiakban leírtak szerint kell az üzletek funkcióprofilját konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="01f30-107">To enable these scenarios, the functionality profile for stores must be configured as outlined in below.</span></span>

1. <span data-ttu-id="01f30-108">Lépjen a **Kiskereskedelem \> Csatorna beállítása \> Pénztár beállítása \> Pénztárprofilok \> Funkcióprofilok** menüpontra, és válasszon ki egy olyan profilt, amely azokhoz az üzletekhez van kapcsolva, amelyekre vonatkozóan módosításokat szeretne végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="01f30-108">Go to **Retail \> Channel setup \> POS setup \> POS profiles \> Functionality profiles** and select a profile that's linked to the stores that you want to make the changes for.</span></span>
2. <span data-ttu-id="01f30-109">A **Funkciók** lapon szükség szerint konfigurálja az alábbi paramétereket.</span><span class="sxs-lookup"><span data-stu-id="01f30-109">On the **Functions** tab, configure the following parameters as needed.</span></span>

    - <span data-ttu-id="01f30-110">**Értékesítési rendelés – számla** – Válassza az **Igen** lehetőséget, ha szeretné engedélyezni a felhasználóknak, hogy egyetlen pénztártranzakció során egy vagy több értékesítési rendelésen alapuló számlát is kifizethessenek.</span><span class="sxs-lookup"><span data-stu-id="01f30-110">**Sales order invoice** – Select **Yes** to allow users to pay one or more sales order-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="01f30-111">**Szabadszöveges számla** – Válassza az **Igen** lehetőséget, ha szeretné engedélyezni a felhasználóknak, hogy egyetlen pénztártranzakció során egy vagy több szabadszöveges számlát is kifizethessenek.</span><span class="sxs-lookup"><span data-stu-id="01f30-111">**Free text invoice** – Select **Yes** to allow users to pay one or more free text-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="01f30-112">**Projektszámla** – Válassza az **Igen** lehetőséget, ha szeretné engedélyezni a felhasználóknak, hogy egyetlen pénztártranzakció során egy vagy több projektalapú számlát is kifizethessenek.</span><span class="sxs-lookup"><span data-stu-id="01f30-112">**Project invoice** – Select **Yes** to allow users to pay one or more project-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="01f30-113">**Értékesítési rendelés - jóváírás** – Válassza az **Igen** lehetőséget, ha szeretné engedélyezni a felhasználóknak, hogy több értékesítési rendelésen alapuló jóváírást egyenlíthessenek ki nyitott számlákra vonatkozóan, vagy hogy egy nyitott jóváírással kapcsolatban visszatérítést dolgozzanak fel a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="01f30-113">**Sales order credit note** – Select **Yes** to allow users to settle multiple sales order-based credit notes against open invoices or process a refund to the customer for an open credit note.</span></span>

> [!NOTE]
> <span data-ttu-id="01f30-114">A részleges összegek kifizetése vagy kiegyenlítése jelenleg még nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="01f30-114">Payment or settlement of partial amounts is not yet supported.</span></span>
