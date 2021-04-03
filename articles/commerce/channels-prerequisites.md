---
title: Csatornák beállításának előfeltételei
description: Ez a témakör áttekintést nyújt a csatornabeállítási előfeltételekről a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: samjarawan
manager: annbe
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 270f751e860e56a03e20df720c088f275d0298e7
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477924"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="9e9b4-103">Csatorna beállításainak előfeltételei</span><span class="sxs-lookup"><span data-stu-id="9e9b4-103">Channel setup prerequisites</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9e9b4-104">Ez a témakör áttekintést nyújt a csatornabeállítási előfeltételekről a Microsoft Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="9e9b4-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9e9b4-105">A Dynamics 365 Commerce csatorna létrehozása előtt számos előfeltétel-feladatnak be kell fejeződnie.</span><span class="sxs-lookup"><span data-stu-id="9e9b4-105">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="9e9b4-106">A következő előfeltétel-feladatok listája a csatorna típusa szerint van rendszerezve.</span><span class="sxs-lookup"><span data-stu-id="9e9b4-106">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="9e9b4-107">Néhány dokumentáció írása még folyamatban van, és a rendszer frissíti a hivatkozásokat az új tartalom közzététele során.</span><span class="sxs-lookup"><span data-stu-id="9e9b4-107">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="9e9b4-108">Inicializálás</span><span class="sxs-lookup"><span data-stu-id="9e9b4-108">Initialization</span></span>

- [<span data-ttu-id="9e9b4-109">Kiindulási adatok inicializálása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-109">Initialize seed data</span></span>](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="9e9b4-110">Minden csatornatípushoz szükséges globális előfeltételek</span><span class="sxs-lookup"><span data-stu-id="9e9b4-110">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="9e9b4-111">A jogi személy struktúrájának meghatározása és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-111">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="9e9b4-112">Szervezeti hierarchia konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-112">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="9e9b4-113">Raktár beállítása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-113">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="9e9b4-114">Áfa konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-114">Configure sales tax</span></span>](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="9e9b4-115">E-mail-értesítési profil beállítása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-115">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="9e9b4-116">Számsorozatok beállítása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-116">Set up number sequences</span></span>](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="9e9b4-117">Alapértelmezett ügyfél és címjegyzék beállítása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-117">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="9e9b4-118">Kiskereskedelmi csatornák előfeltételei</span><span class="sxs-lookup"><span data-stu-id="9e9b4-118">Retail channel prerequisites</span></span>

- [<span data-ttu-id="9e9b4-119">Infókódok és infókódcsoportok</span><span class="sxs-lookup"><span data-stu-id="9e9b4-119">Info codes and info code groups</span></span>](info-codes-retail.md)
- [<span data-ttu-id="9e9b4-120">Kiskereskedelmi funkcióprofil beállítása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-120">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="9e9b4-121">Alkalmazotti címjegyzék beállítása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-121">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="9e9b4-122">Képernyő-elrendezés beállítása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-122">Set up a screen layout</span></span>](pos-screen-layouts.md)
- [<span data-ttu-id="9e9b4-123">Hardverállomás beállítása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-123">Set up a hardware station</span></span>](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="9e9b4-124">Hívásközpont-csatorna előfeltételei</span><span class="sxs-lookup"><span data-stu-id="9e9b4-124">Call Center channel prerequisites</span></span>

- <span data-ttu-id="9e9b4-125">Hívásközponti paraméterek</span><span class="sxs-lookup"><span data-stu-id="9e9b4-125">Call center parameters</span></span>
- [<span data-ttu-id="9e9b4-126">Hívásközpont-megrendelés és visszatérítés fizetési módszerei</span><span class="sxs-lookup"><span data-stu-id="9e9b4-126">Call center order and refund payment methods</span></span>](work-with-payments.md)
- [<span data-ttu-id="9e9b4-127">Hívásközpont szállítási módjai és költségei</span><span class="sxs-lookup"><span data-stu-id="9e9b4-127">Call center modes of delivery and charges</span></span>](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a><span data-ttu-id="9e9b4-128">Online csatorna előfeltételei</span><span class="sxs-lookup"><span data-stu-id="9e9b4-128">Online channel prerequisites</span></span>

- [<span data-ttu-id="9e9b4-129">Online funkcióprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-129">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="9e9b4-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9e9b4-130">Additional resources</span></span>

[<span data-ttu-id="9e9b4-131">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="9e9b4-131">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="9e9b4-132">Szervezetek és szervezeti hierarchiák áttekintése</span><span class="sxs-lookup"><span data-stu-id="9e9b4-132">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="9e9b4-133">Szervezeti hierarchiák beállítása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-133">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="9e9b4-134">Jogi személyek létrehozása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-134">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="9e9b4-135">Kiskereskedelmi csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-135">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="9e9b4-136">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="9e9b4-136">Set up an online channel</span></span>](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
