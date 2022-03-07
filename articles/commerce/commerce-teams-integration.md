---
title: A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése
description: Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce és a Microsoft Teams integrációjáról.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c22af9bf76818dd682b4147c3677cd1715e4cbf8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021989"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a>A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése

[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce és a Microsoft Teams integrációjáról.

A Dynamics 365 Commerce integrálható a Teams alkalmazással, hogy segítsen az ügyfeleknek és alkalmazottaiknak a termelékenység növelésében azáltal, hogy szinkronizálja a feladatkezelést a két alkalmazás között. A Commerce és a Teams integrációja által biztosított zökkenőmentes feladatkezelése lehetővé teszi, hogy az áruházvezetők és az alkalmazottak feladatlistákat hozzanak létre, feladatokat rendeljenek több üzlethez, és nyomon kövessék a feladatok állapotát az üzletekben, bármelyik alkalmazásból.

A Commerce és a Teams integrációja a Commerce 10.0.18-as verziójától érhető el.

## <a name="key-features"></a>Fő funkciók

Íme néhány, a Commerce és a Microsoft Teams integrációja által nyújtott legfontosabb funkciók közül:

- A Teams kiépítése a Commerce jól meghatározott információinak használatával, beleértve a szervezeti struktúrát és az üzletekre, dolgozókra, engedélyekre és üzleti környezetre vonatkozó információkat.
- Egyszerűen szinkronizálhatja a folyamatban lévő módosításokat (például új üzletek hozzáadását vagy új alkalmazottak felvételét) a Commerce és a Teams között, de a Commerce marad a szervezeti struktúrára vonatkozó adatok fő forrása.
- Integrálhatja a feladatkezelést a Commerce és a Teams között, hogy segítsen az áruházi dolgozóknak, az üzletvezetőknek, a regionális vezetőknek és a kommunikációs vezetőknek a feladatkezelés egyik alkalmazásból való kezelésében.

## <a name="prerequisites-for-using-integration-features"></a>Az integrációs funkciók használatának előfeltételei

A Microsoft Teams integrációs funkciók használatának megkezdése előtt a következő előfeltételeknek kell teljesülniük:

- Microsoft 365 business standard licenc (Ez a licenc tartalmazza a Teamst is.)
- Azure Active Directory (Azure AD) fiókok minden üzletvezető és dolgozó számára
- Azure AD-hitelesítéssel konfigurált pénztári (POS) rendszerek

## <a name="conceptual-architecture"></a>Koncepcionális architektúra

A következő ábra a Dynamics 365 Commerce és a Microsoft Teams integrációjának koncepcionális architektúráját mutatja be, példaként egy San Francisco-i áruházat használva. Mind a Teams, mind a Commerce pénztáralkalmazás adattárként használja a Microsoft Plannert, így a Teams által közzétett feladatok megjelennek a pénztáralkalmazásban, és a POS-alkalmazásban az áruházkezelők által létrehozott ad hoc feladatok megjelennek a Teams alkalmazásban, ami zökkenőmentes feladatkezelési élményt eredményez az alkalmazások között.    

![A Commerce és Teams integrációjának architektúrája](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a>További erőforrások

[A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése](enable-teams-integration.md)

[Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből](provision-teams-from-commerce.md)

[Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között](synchronize-tasks-teams-pos.md)

[Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban](manage-user-roles-teams.md)

[Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban](map-stores-existing-teams.md)

[Dynamics 365 Commerce és Microsoft Teams integrációja – GYIK](teams-integration-faq.md)
