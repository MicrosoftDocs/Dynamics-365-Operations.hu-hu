---
title: Raktári munka – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári munkát végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 08cc074fe851b952ebfc942ae3d1cb05240d3b91
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837441"
---
# <a name="troubleshoot-warehouse-work"></a><span data-ttu-id="31452-103">Raktári munka – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="31452-103">Troubleshoot warehouse work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31452-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári munkát végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="31452-104">This topic describes how to fix common issues that you might encounter while you work with warehouse work in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a><span data-ttu-id="31452-105">Nem helyezhetők át a sorozatszámos cikkeket tartalmazó azonosítótáblák, ha a nyomon követési dimenzióban engedélyezve van az üres kiadás és az üres nyugta.</span><span class="sxs-lookup"><span data-stu-id="31452-105">I can't move license plates that have serial number items when blank issue and blank receipt are allowed on the tracking dimension group.</span></span>

### <a name="issue-description"></a><span data-ttu-id="31452-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="31452-106">Issue description</span></span>

<span data-ttu-id="31452-107">Nem helyezhető át az azonosítótábla egy **Áthelyezés** menü használatával, ha a sorozatszámhoz a nyomon követési dimenzióban az *Üres kiadás megengedett* és az *Üres nyugta megengedett* beállítások vannak, és ha ugyanazon a helyen több azonosítótábla van megadva, amelyek közül néhány tartalmaz sorozatszámot, néhány pedig nem.</span><span class="sxs-lookup"><span data-stu-id="31452-107">You can't move a license plate by using a **Movement** menu item if the serial number has settings of *Blank issue allowed* and *Blank receipt allowed* on the tracking dimension group, and if there are multiple license plates in the same location, some of which have serial numbers and some of which don't have them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="31452-108">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="31452-108">Issue resolution</span></span>

<span data-ttu-id="31452-109">Ezt a hibát a [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687) részben lévő telepített változtatások javítják ki.</span><span class="sxs-lookup"><span data-stu-id="31452-109">This issue will be fixed by changes that are deployed in [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span></span> <span data-ttu-id="31452-110">Ezek a módosítások nem teszik kötelezővé a **Sorozatszám** mező kitöltését, ha az üres nyugta és az üres kiadás engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="31452-110">Those changes will make the **Serial number** field optional when blank receipt and blank issue are allowed.</span></span>

## <a name="i-receive-the-following-error-message-in-the-warehouse-management-mobile-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a><span data-ttu-id="31452-111">A következő hibaüzenet jelenik meg a Raktárkezelés mobilalkalmazásban a készletmozgások feldolgozásakor: „A készlet tulajdonosa %1 nem engedélyezett ebben a folyamatban.”</span><span class="sxs-lookup"><span data-stu-id="31452-111">I receive the following error message in the Warehouse Management mobile app when I process movements: "The inventory owner %1 is not allowed in this process."</span></span>

### <a name="issue-description"></a><span data-ttu-id="31452-112">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="31452-112">Issue description</span></span>

<span data-ttu-id="31452-113">A **Tulajdonos** követési dimenziója hiányzik, amikor a Raktárkezelés mobilalkalmazásban készletmozgatásokat végeznek.</span><span class="sxs-lookup"><span data-stu-id="31452-113">The **Owner** tracking dimension is missing when the Warehouse Management mobile app is used to make movements.</span></span> <span data-ttu-id="31452-114">Úgy látszik, hogy a Supply Chain Management kliens rendszeres készletmozgatási naplót használ, és csak akkor lehet feladni, ha a **Tulajdonos** dimenzió ki van töltve.</span><span class="sxs-lookup"><span data-stu-id="31452-114">A regular inventory transfer journal from the Supply Chain Management client appears to work as intended and can be posted only if the **Owner** dimension is filled in.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="31452-115">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="31452-115">Issue resolution</span></span>

<span data-ttu-id="31452-116">A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás.</span><span class="sxs-lookup"><span data-stu-id="31452-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="31452-117">A raktárkezelési folyamatok jelenleg csak a jogi személy tulajdonában álló készletet támogatják.</span><span class="sxs-lookup"><span data-stu-id="31452-117">Currently, warehouse management processes support only inventory that is owned by the legal entity.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]