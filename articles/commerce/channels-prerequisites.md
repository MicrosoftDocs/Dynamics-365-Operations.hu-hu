---
title: Csatornák beállításának előfeltételei
description: Ez a témakör áttekintést nyújt a csatornabeállítási előfeltételekről a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.openlocfilehash: b861d90f1333c8f6e61a83602ed74e30b65f3dc1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002289"
---
# <a name="channel-setup-prerequisites"></a>Csatornák beállításának előfeltételei


[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a csatornabeállítási előfeltételekről a Microsoft Dynamics 365 Commerce szolgáltatásban.

## <a name="overview"></a>Áttekintés

A Dynamics 365 Commerce csatorna létrehozása előtt számos előfeltétel-feladatnak be kell fejeződnie. A következő előfeltétel-feladatok listája a csatorna típusa szerint van rendszerezve.

> [!NOTE]
> Néhány dokumentáció írása még folyamatban van, és a rendszer frissíti a hivatkozásokat az új tartalom közzététele során.

## <a name="initialization"></a>Inicializálás

- [Kiindulási adatok inicializálása](../retail/enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a>Minden csatornatípushoz szükséges globális előfeltételek

- [A jogi személy struktúrájának meghatározása és konfigurálása](channels-legal-entities.md) 
- [Szervezeti hierarchia konfigurálása](channels-org-hierarchies.md)
- [Raktár beállítása](channels-setup-warehouse.md)
- [Áfa konfigurálása](https://docs.microsoft.com/en-us/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json)
- [E-mail-értesítési profil beállítása](email-notification-profiles.md)
- [Számsorozatok beállítása](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/commerce/toc.json)
- [Alapértelmezett ügyfél és címjegyzék beállítása](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a>Kiskereskedelmi csatornák előfeltételei

- [Infókódok és infókódcsoportok](https://docs.microsoft.com/en-us/dynamics365/retail/info-codes-retail?toc=/dynamics365/commerce/toc.json)
- [Kiskereskedelmi funkcióprofil beállítása](retail-functionality-profile.md)
- [Alkalmazotti címjegyzék beállítása](new-address-book.md)
- [Képernyő-elrendezés beállítása](https://docs.microsoft.com/en-us/dynamics365/retail/pos-screen-layouts?toc=/dynamics365/commerce/toc.json)
- [Hardverállomás beállítása](https://docs.microsoft.com/en-us/dynamics365/retail/retail-hardware-station-configuration-installation?toc=/dynamics365/commerce/toc.json)

## <a name="call-center-channel-prerequisites"></a>Hívásközpont-csatorna előfeltételei

- Hívásközponti paraméterek
- Hívásközponti visszatérítési módok
- Bérlettípusok
- Fizetési szolgáltatások
- Rendelésvárakoztatási kódok

## <a name="online-channel-prerequisites"></a>Online csatorna előfeltételei

- [Online funkcióprofil létrehozása](online-functionality-profile.md)

## <a name="additional-resources"></a>További erőforrások

[Csatornák áttekintése](channels-overview.md)

[Szervezetek és szervezeti hierarchiák áttekintése](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Szervezeti hierarchiák beállítása](channels-org-hierarchies.md)

[Jogi személyek létrehozása](channels-legal-entities.md)

[Kiskereskedelmi csatorna beállítása](channel-setup-retail.md)
    
[Online csatorna beállítása](channel-setup-online.md)
