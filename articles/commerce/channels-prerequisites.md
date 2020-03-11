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
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8a0927f6ee9b2d5bed1327bb223ceca85ecc16a0
ms.sourcegitcommit: 161e85eb0a6b772b60ba8b2578a3de149ce5bfd7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/22/2020
ms.locfileid: "3081315"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="ca52b-103">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="ca52b-103">Channel setup prerequisites</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ca52b-104">Ez a témakör áttekintést nyújt a csatornabeállítási előfeltételekről a Microsoft Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="ca52b-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ca52b-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="ca52b-105">Overview</span></span>

<span data-ttu-id="ca52b-106">A Dynamics 365 Commerce csatorna létrehozása előtt számos előfeltétel-feladatnak be kell fejeződnie.</span><span class="sxs-lookup"><span data-stu-id="ca52b-106">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="ca52b-107">A következő előfeltétel-feladatok listája a csatorna típusa szerint van rendszerezve.</span><span class="sxs-lookup"><span data-stu-id="ca52b-107">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="ca52b-108">Néhány dokumentáció írása még folyamatban van, és a rendszer frissíti a hivatkozásokat az új tartalom közzététele során.</span><span class="sxs-lookup"><span data-stu-id="ca52b-108">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="ca52b-109">Inicializálás</span><span class="sxs-lookup"><span data-stu-id="ca52b-109">Initialization</span></span>

- [<span data-ttu-id="ca52b-110">Kiindulási adatok inicializálása</span><span class="sxs-lookup"><span data-stu-id="ca52b-110">Initialize seed data</span></span>](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="ca52b-111">Minden csatornatípushoz szükséges globális előfeltételek</span><span class="sxs-lookup"><span data-stu-id="ca52b-111">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="ca52b-112">A jogi személy struktúrájának meghatározása és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ca52b-112">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="ca52b-113">Szervezeti hierarchia konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ca52b-113">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="ca52b-114">Raktár beállítása</span><span class="sxs-lookup"><span data-stu-id="ca52b-114">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="ca52b-115">Áfa konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ca52b-115">Configure sales tax</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="ca52b-116">E-mail-értesítési profil beállítása</span><span class="sxs-lookup"><span data-stu-id="ca52b-116">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="ca52b-117">Számsorozatok beállítása</span><span class="sxs-lookup"><span data-stu-id="ca52b-117">Set up number sequences</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="ca52b-118">Alapértelmezett ügyfél és címjegyzék beállítása</span><span class="sxs-lookup"><span data-stu-id="ca52b-118">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="ca52b-119">Kiskereskedelmi csatornák előfeltételei</span><span class="sxs-lookup"><span data-stu-id="ca52b-119">Retail channel prerequisites</span></span>

- [<span data-ttu-id="ca52b-120">Infókódok és infókódcsoportok</span><span class="sxs-lookup"><span data-stu-id="ca52b-120">Info codes and info code groups</span></span>](info-codes-retail.md)
- [<span data-ttu-id="ca52b-121">Kiskereskedelmi funkcióprofil beállítása</span><span class="sxs-lookup"><span data-stu-id="ca52b-121">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="ca52b-122">Alkalmazotti címjegyzék beállítása</span><span class="sxs-lookup"><span data-stu-id="ca52b-122">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="ca52b-123">Képernyő-elrendezés beállítása</span><span class="sxs-lookup"><span data-stu-id="ca52b-123">Set up a screen layout</span></span>](pos-screen-layouts.md)
- [<span data-ttu-id="ca52b-124">Hardverállomás beállítása</span><span class="sxs-lookup"><span data-stu-id="ca52b-124">Set up a hardware station</span></span>](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="ca52b-125">Hívásközpont-csatorna előfeltételei</span><span class="sxs-lookup"><span data-stu-id="ca52b-125">Call Center channel prerequisites</span></span>

- <span data-ttu-id="ca52b-126">Hívásközponti paraméterek</span><span class="sxs-lookup"><span data-stu-id="ca52b-126">Call center parameters</span></span>
- [<span data-ttu-id="ca52b-127">Hívásközpont-megrendelés és visszatérítés fizetési módszerei</span><span class="sxs-lookup"><span data-stu-id="ca52b-127">Call center order and refund payment methods</span></span>](work-with-payments.md)
- [<span data-ttu-id="ca52b-128">Hívásközpont szállítási módjai és költségei</span><span class="sxs-lookup"><span data-stu-id="ca52b-128">Call center modes of delivery and charges</span></span>](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a><span data-ttu-id="ca52b-129">Online csatorna előfeltételei</span><span class="sxs-lookup"><span data-stu-id="ca52b-129">Online channel prerequisites</span></span>

- [<span data-ttu-id="ca52b-130">Online funkcióprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="ca52b-130">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="ca52b-131">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ca52b-131">Additional resources</span></span>

[<span data-ttu-id="ca52b-132">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="ca52b-132">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="ca52b-133">Szervezetek és szervezeti hierarchiák áttekintése</span><span class="sxs-lookup"><span data-stu-id="ca52b-133">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="ca52b-134">Szervezeti hierarchiák beállítása</span><span class="sxs-lookup"><span data-stu-id="ca52b-134">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="ca52b-135">Jogi személyek létrehozása</span><span class="sxs-lookup"><span data-stu-id="ca52b-135">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="ca52b-136">Kiskereskedelmi csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="ca52b-136">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="ca52b-137">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="ca52b-137">Set up an online channel</span></span>](channel-setup-online.md)
