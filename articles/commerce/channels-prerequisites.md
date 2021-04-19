---
title: Csatornák beállításának előfeltételei
description: Ez a témakör áttekintést nyújt a csatornabeállítási előfeltételekről a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: samjarawan
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 33fcead6c0b08db17f24b638376a23b8b6024a5b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800519"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="2e0e2-103">Csatorna beállításainak előfeltételei</span><span class="sxs-lookup"><span data-stu-id="2e0e2-103">Channel setup prerequisites</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2e0e2-104">Ez a témakör áttekintést nyújt a csatornabeállítási előfeltételekről a Microsoft Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="2e0e2-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="2e0e2-105">A Dynamics 365 Commerce csatorna létrehozása előtt számos előfeltétel-feladatnak be kell fejeződnie.</span><span class="sxs-lookup"><span data-stu-id="2e0e2-105">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="2e0e2-106">A következő előfeltétel-feladatok listája a csatorna típusa szerint van rendszerezve.</span><span class="sxs-lookup"><span data-stu-id="2e0e2-106">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="2e0e2-107">Néhány dokumentáció írása még folyamatban van, és a rendszer frissíti a hivatkozásokat az új tartalom közzététele során.</span><span class="sxs-lookup"><span data-stu-id="2e0e2-107">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="2e0e2-108">Inicializálás</span><span class="sxs-lookup"><span data-stu-id="2e0e2-108">Initialization</span></span>

- [<span data-ttu-id="2e0e2-109">Kiindulási adatok inicializálása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-109">Initialize seed data</span></span>](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="2e0e2-110">Minden csatornatípushoz szükséges globális előfeltételek</span><span class="sxs-lookup"><span data-stu-id="2e0e2-110">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="2e0e2-111">A jogi személy struktúrájának meghatározása és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-111">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="2e0e2-112">Szervezeti hierarchia konfigurálása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-112">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="2e0e2-113">Raktár beállítása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-113">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="2e0e2-114">Áfa konfigurálása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-114">Configure sales tax</span></span>](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="2e0e2-115">E-mail-értesítési profil beállítása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-115">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="2e0e2-116">Számsorozatok beállítása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-116">Set up number sequences</span></span>](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="2e0e2-117">Alapértelmezett ügyfél és címjegyzék beállítása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-117">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="2e0e2-118">Kiskereskedelmi csatornák előfeltételei</span><span class="sxs-lookup"><span data-stu-id="2e0e2-118">Retail channel prerequisites</span></span>

- [<span data-ttu-id="2e0e2-119">Infókódok és infókódcsoportok</span><span class="sxs-lookup"><span data-stu-id="2e0e2-119">Info codes and info code groups</span></span>](info-codes-retail.md)
- [<span data-ttu-id="2e0e2-120">Kiskereskedelmi funkcióprofil beállítása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-120">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="2e0e2-121">Alkalmazotti címjegyzék beállítása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-121">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="2e0e2-122">Képernyő-elrendezés beállítása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-122">Set up a screen layout</span></span>](pos-screen-layouts.md)
- [<span data-ttu-id="2e0e2-123">Hardverállomás beállítása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-123">Set up a hardware station</span></span>](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="2e0e2-124">Hívásközpont-csatorna előfeltételei</span><span class="sxs-lookup"><span data-stu-id="2e0e2-124">Call Center channel prerequisites</span></span>

- <span data-ttu-id="2e0e2-125">Hívásközponti paraméterek</span><span class="sxs-lookup"><span data-stu-id="2e0e2-125">Call center parameters</span></span>
- [<span data-ttu-id="2e0e2-126">Hívásközpont-megrendelés és visszatérítés fizetési módszerei</span><span class="sxs-lookup"><span data-stu-id="2e0e2-126">Call center order and refund payment methods</span></span>](work-with-payments.md)
- [<span data-ttu-id="2e0e2-127">Hívásközpont szállítási módjai és költségei</span><span class="sxs-lookup"><span data-stu-id="2e0e2-127">Call center modes of delivery and charges</span></span>](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a><span data-ttu-id="2e0e2-128">Online csatorna előfeltételei</span><span class="sxs-lookup"><span data-stu-id="2e0e2-128">Online channel prerequisites</span></span>

- [<span data-ttu-id="2e0e2-129">Online funkcióprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-129">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="2e0e2-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2e0e2-130">Additional resources</span></span>

[<span data-ttu-id="2e0e2-131">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="2e0e2-131">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="2e0e2-132">Szervezetek és szervezeti hierarchiák áttekintése</span><span class="sxs-lookup"><span data-stu-id="2e0e2-132">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="2e0e2-133">Szervezeti hierarchiák beállítása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-133">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="2e0e2-134">Jogi személyek létrehozása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-134">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="2e0e2-135">Kiskereskedelmi csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-135">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="2e0e2-136">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="2e0e2-136">Set up an online channel</span></span>](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
