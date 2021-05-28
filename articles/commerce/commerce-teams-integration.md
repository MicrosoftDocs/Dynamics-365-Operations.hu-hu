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
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a><span data-ttu-id="48f1d-103">A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése</span><span class="sxs-lookup"><span data-stu-id="48f1d-103">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="48f1d-104">Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce és a Microsoft Teams integrációjáról.</span><span class="sxs-lookup"><span data-stu-id="48f1d-104">This topic presents an overview of Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="48f1d-105">A Dynamics 365 Commerce integrálható a Teams alkalmazással, hogy segítsen az ügyfeleknek és alkalmazottaiknak a termelékenység növelésében azáltal, hogy szinkronizálja a feladatkezelést a két alkalmazás között.</span><span class="sxs-lookup"><span data-stu-id="48f1d-105">Dynamics 365 Commerce is integrating with Teams to help customers and their employees improve productivity by synchronizing task management between the two applications.</span></span> <span data-ttu-id="48f1d-106">A Commerce és a Teams integrációja által biztosított zökkenőmentes feladatkezelése lehetővé teszi, hogy az áruházvezetők és az alkalmazottak feladatlistákat hozzanak létre, feladatokat rendeljenek több üzlethez, és nyomon kövessék a feladatok állapotát az üzletekben, bármelyik alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="48f1d-106">The seamless task management that Commerce and Teams integration provides lets store managers and employees create task lists, assign tasks to multiple stores, and track the status of tasks across stores, from either application.</span></span>

<span data-ttu-id="48f1d-107">A Commerce és a Teams integrációja a Commerce 10.0.18-as verziójától érhető el.</span><span class="sxs-lookup"><span data-stu-id="48f1d-107">Commerce and Teams integration is available as of the Commerce version 10.0.18 release.</span></span>

## <a name="key-features"></a><span data-ttu-id="48f1d-108">Fő funkciók</span><span class="sxs-lookup"><span data-stu-id="48f1d-108">Key features</span></span>

<span data-ttu-id="48f1d-109">Íme néhány, a Commerce és a Microsoft Teams integrációja által nyújtott legfontosabb funkciók közül:</span><span class="sxs-lookup"><span data-stu-id="48f1d-109">Here are some of the key features that the Commerce and Microsoft Teams integration provides:</span></span>

- <span data-ttu-id="48f1d-110">A Teams kiépítése a Commerce jól meghatározott információinak használatával, beleértve a szervezeti struktúrát és az üzletekre, dolgozókra, engedélyekre és üzleti környezetre vonatkozó információkat.</span><span class="sxs-lookup"><span data-stu-id="48f1d-110">Provision Teams by taking advantage of well-defined information from Commerce, such as the organizational structure and information about stores, workers, permissions, and business context.</span></span>
- <span data-ttu-id="48f1d-111">Egyszerűen szinkronizálhatja a folyamatban lévő módosításokat (például új üzletek hozzáadását vagy új alkalmazottak felvételét) a Commerce és a Teams között, de a Commerce marad a szervezeti struktúrára vonatkozó adatok fő forrása.</span><span class="sxs-lookup"><span data-stu-id="48f1d-111">Easily synchronize ongoing changes (for example, the addition of new stores or hiring of new employees) between Commerce and Teams, but keep Commerce as the master source of organizational structure data.</span></span>
- <span data-ttu-id="48f1d-112">Integrálhatja a feladatkezelést a Commerce és a Teams között, hogy segítsen az áruházi dolgozóknak, az üzletvezetőknek, a regionális vezetőknek és a kommunikációs vezetőknek a feladatkezelés egyik alkalmazásból való kezelésében.</span><span class="sxs-lookup"><span data-stu-id="48f1d-112">Integrate task management between Commerce and Teams to help store workers, store managers, regional managers, and communications managers handle task management from either application.</span></span>

## <a name="prerequisites-for-using-integration-features"></a><span data-ttu-id="48f1d-113">Az integrációs funkciók használatának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="48f1d-113">Prerequisites for using integration features</span></span>

<span data-ttu-id="48f1d-114">A Microsoft Teams integrációs funkciók használatának megkezdése előtt a következő előfeltételeknek kell teljesülniük:</span><span class="sxs-lookup"><span data-stu-id="48f1d-114">The following prerequisites must be in place before you can start to use Microsoft Teams integration features:</span></span>

- <span data-ttu-id="48f1d-115">Microsoft 365 business standard licenc (Ez a licenc tartalmazza a Teamst is.)</span><span class="sxs-lookup"><span data-stu-id="48f1d-115">Microsoft 365 Business Standard License (This license includes Teams.)</span></span>
- <span data-ttu-id="48f1d-116">Azure Active Directory (Azure AD) fiókok minden üzletvezető és dolgozó számára</span><span class="sxs-lookup"><span data-stu-id="48f1d-116">Azure Active Directory (Azure AD) accounts for all store managers and workers</span></span>
- <span data-ttu-id="48f1d-117">Azure AD-hitelesítéssel konfigurált pénztári (POS) rendszerek</span><span class="sxs-lookup"><span data-stu-id="48f1d-117">Point of sale (POS) systems that are configured with Azure AD authentication</span></span>

## <a name="conceptual-architecture"></a><span data-ttu-id="48f1d-118">Koncepcionális architektúra</span><span class="sxs-lookup"><span data-stu-id="48f1d-118">Conceptual architecture</span></span>

<span data-ttu-id="48f1d-119">A következő ábra a Dynamics 365 Commerce és a Microsoft Teams integrációjának koncepcionális architektúráját mutatja be, példaként egy San Francisco-i áruházat használva.</span><span class="sxs-lookup"><span data-stu-id="48f1d-119">The following illustration shows the conceptual architecture of Dynamics 365 Commerce and Microsoft Teams integration, using a San Francisco store as an example.</span></span> <span data-ttu-id="48f1d-120">Mind a Teams, mind a Commerce pénztáralkalmazás adattárként használja a Microsoft Plannert, így a Teams által közzétett feladatok megjelennek a pénztáralkalmazásban, és a POS-alkalmazásban az áruházkezelők által létrehozott ad hoc feladatok megjelennek a Teams alkalmazásban, ami zökkenőmentes feladatkezelési élményt eredményez az alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="48f1d-120">Both Teams and the Commerce POS application use Microsoft Planner as a repository so that tasks published from Teams appear in the POS application and ad hoc tasks created by store managers in the POS application appear in Teams, resulting in a seamless task management experience between the applications.</span></span>    

![A Commerce és Teams integrációjának architektúrája](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a><span data-ttu-id="48f1d-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="48f1d-122">Additional resources</span></span>

[<span data-ttu-id="48f1d-123">A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="48f1d-123">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="48f1d-124">Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből</span><span class="sxs-lookup"><span data-stu-id="48f1d-124">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="48f1d-125">Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között</span><span class="sxs-lookup"><span data-stu-id="48f1d-125">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="48f1d-126">Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="48f1d-126">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="48f1d-127">Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="48f1d-127">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="48f1d-128">Dynamics 365 Commerce és Microsoft Teams integrációja – GYIK</span><span class="sxs-lookup"><span data-stu-id="48f1d-128">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
