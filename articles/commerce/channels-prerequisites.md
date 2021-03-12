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
ms.openlocfilehash: 0705efac4659f96ebca1c67f6f0ab8d23c99d81e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997700"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="e65dc-103">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="e65dc-103">Channel setup prerequisites</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e65dc-104">Ez a témakör áttekintést nyújt a csatornabeállítási előfeltételekről a Microsoft Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="e65dc-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e65dc-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="e65dc-105">Overview</span></span>

<span data-ttu-id="e65dc-106">A Dynamics 365 Commerce csatorna létrehozása előtt számos előfeltétel-feladatnak be kell fejeződnie.</span><span class="sxs-lookup"><span data-stu-id="e65dc-106">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="e65dc-107">A következő előfeltétel-feladatok listája a csatorna típusa szerint van rendszerezve.</span><span class="sxs-lookup"><span data-stu-id="e65dc-107">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="e65dc-108">Néhány dokumentáció írása még folyamatban van, és a rendszer frissíti a hivatkozásokat az új tartalom közzététele során.</span><span class="sxs-lookup"><span data-stu-id="e65dc-108">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="e65dc-109">Inicializálás</span><span class="sxs-lookup"><span data-stu-id="e65dc-109">Initialization</span></span>

- [<span data-ttu-id="e65dc-110">Kiindulási adatok inicializálása</span><span class="sxs-lookup"><span data-stu-id="e65dc-110">Initialize seed data</span></span>](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="e65dc-111">Minden csatornatípushoz szükséges globális előfeltételek</span><span class="sxs-lookup"><span data-stu-id="e65dc-111">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="e65dc-112">A jogi személy struktúrájának meghatározása és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e65dc-112">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="e65dc-113">Szervezeti hierarchia konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e65dc-113">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="e65dc-114">Raktár beállítása</span><span class="sxs-lookup"><span data-stu-id="e65dc-114">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="e65dc-115">Áfa konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e65dc-115">Configure sales tax</span></span>](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="e65dc-116">E-mail-értesítési profil beállítása</span><span class="sxs-lookup"><span data-stu-id="e65dc-116">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="e65dc-117">Számsorozatok beállítása</span><span class="sxs-lookup"><span data-stu-id="e65dc-117">Set up number sequences</span></span>](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="e65dc-118">Alapértelmezett ügyfél és címjegyzék beállítása</span><span class="sxs-lookup"><span data-stu-id="e65dc-118">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="e65dc-119">Kiskereskedelmi csatornák előfeltételei</span><span class="sxs-lookup"><span data-stu-id="e65dc-119">Retail channel prerequisites</span></span>

- [<span data-ttu-id="e65dc-120">Infókódok és infókódcsoportok</span><span class="sxs-lookup"><span data-stu-id="e65dc-120">Info codes and info code groups</span></span>](info-codes-retail.md)
- [<span data-ttu-id="e65dc-121">Kiskereskedelmi funkcióprofil beállítása</span><span class="sxs-lookup"><span data-stu-id="e65dc-121">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="e65dc-122">Alkalmazotti címjegyzék beállítása</span><span class="sxs-lookup"><span data-stu-id="e65dc-122">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="e65dc-123">Képernyő-elrendezés beállítása</span><span class="sxs-lookup"><span data-stu-id="e65dc-123">Set up a screen layout</span></span>](pos-screen-layouts.md)
- [<span data-ttu-id="e65dc-124">Hardverállomás beállítása</span><span class="sxs-lookup"><span data-stu-id="e65dc-124">Set up a hardware station</span></span>](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="e65dc-125">Hívásközpont-csatorna előfeltételei</span><span class="sxs-lookup"><span data-stu-id="e65dc-125">Call Center channel prerequisites</span></span>

- <span data-ttu-id="e65dc-126">Hívásközponti paraméterek</span><span class="sxs-lookup"><span data-stu-id="e65dc-126">Call center parameters</span></span>
- [<span data-ttu-id="e65dc-127">Hívásközpont-megrendelés és visszatérítés fizetési módszerei</span><span class="sxs-lookup"><span data-stu-id="e65dc-127">Call center order and refund payment methods</span></span>](work-with-payments.md)
- [<span data-ttu-id="e65dc-128">Hívásközpont szállítási módjai és költségei</span><span class="sxs-lookup"><span data-stu-id="e65dc-128">Call center modes of delivery and charges</span></span>](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a><span data-ttu-id="e65dc-129">Online csatorna előfeltételei</span><span class="sxs-lookup"><span data-stu-id="e65dc-129">Online channel prerequisites</span></span>

- [<span data-ttu-id="e65dc-130">Online funkcióprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="e65dc-130">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="e65dc-131">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e65dc-131">Additional resources</span></span>

[<span data-ttu-id="e65dc-132">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="e65dc-132">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="e65dc-133">Szervezetek és szervezeti hierarchiák áttekintése</span><span class="sxs-lookup"><span data-stu-id="e65dc-133">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="e65dc-134">Szervezeti hierarchiák beállítása</span><span class="sxs-lookup"><span data-stu-id="e65dc-134">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="e65dc-135">Jogi személyek létrehozása</span><span class="sxs-lookup"><span data-stu-id="e65dc-135">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="e65dc-136">Kiskereskedelmi csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="e65dc-136">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="e65dc-137">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="e65dc-137">Set up an online channel</span></span>](channel-setup-online.md)
