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
ms.openlocfilehash: 6ad8911df00fde4675d4d9b52fcdd52ff58d4983b177316a7606de277328226b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742464"
---
# <a name="channel-setup-prerequisites"></a>Csatorna beállításainak előfeltételei

[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a csatornabeállítási előfeltételekről a Microsoft Dynamics 365 Commerce szolgáltatásban.

A Dynamics 365 Commerce csatorna létrehozása előtt számos előfeltétel-feladatnak be kell fejeződnie. A következő előfeltétel-feladatok listája a csatorna típusa szerint van rendszerezve.

> [!NOTE]
> Néhány dokumentáció írása még folyamatban van, és a rendszer frissíti a hivatkozásokat az új tartalom közzététele során.

## <a name="initialization"></a>Inicializálás

- [Kiindulási adatok inicializálása](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a>Minden csatornatípushoz szükséges globális előfeltételek

- [A jogi személy struktúrájának meghatározása és konfigurálása](channels-legal-entities.md) 
- [Szervezeti hierarchia konfigurálása](channels-org-hierarchies.md)
- [Raktár beállítása](channels-setup-warehouse.md)
- [Áfa konfigurálása](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [E-mail-értesítési profil beállítása](email-notification-profiles.md)
- [Számsorozatok beállítása](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [Alapértelmezett ügyfél és címjegyzék beállítása](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a>Kiskereskedelmi csatornák előfeltételei

- [Infókódok és infókódcsoportok](info-codes-retail.md)
- [Kiskereskedelmi funkcióprofil beállítása](retail-functionality-profile.md)
- [Alkalmazotti címjegyzék beállítása](new-address-book.md)
- [Képernyő-elrendezés beállítása](pos-screen-layouts.md)
- [Hardverállomás beállítása](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a>Hívásközpont-csatorna előfeltételei

- Hívásközponti paraméterek
- [Hívásközpont-megrendelés és visszatérítés fizetési módszerei](work-with-payments.md)
- [Hívásközpont szállítási módjai és költségei](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a>Online csatorna előfeltételei

- [Online funkcióprofil létrehozása](online-functionality-profile.md)

## <a name="additional-resources"></a>További erőforrások

[Csatornák áttekintése](channels-overview.md)

[Szervezetek és szervezeti hierarchiák áttekintése](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Szervezeti hierarchiák beállítása](channels-org-hierarchies.md)

[Jogi személyek létrehozása](channels-legal-entities.md)

[Kiskereskedelmi csatorna beállítása](channel-setup-retail.md)
    
[Online csatorna beállítása](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
