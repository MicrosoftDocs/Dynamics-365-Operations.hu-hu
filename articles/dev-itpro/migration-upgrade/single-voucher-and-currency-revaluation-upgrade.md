---
title: Egyetlen bizonylatos naplók és pénznemes értékelések frissítése
description: Egyes szervezetek olyan naplókat adnak meg, amelyek egynél több ügyféllel vagy szállítóval rendelkező bizonylatot tartalmaznak, valamint a Kinnlevőségek és a Kötelezettségek devizaátértékelési folyamatát is. Ez a témakör bemutatja azokat a lépéseket, amelyeket ezeknek a szervezeteknek követniük kell, amikor frissítenek a Microsoft Dynamics 365 for Operations 1611-es verziójára.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 343fa226e1cf9072696082e9ebf0a1629e553ae9
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554520"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a><span data-ttu-id="a1d0a-104">Egyetlen bizonylatos naplók és pénznemértékelések frissítése</span><span class="sxs-lookup"><span data-stu-id="a1d0a-104">Upgrade single-voucher journals and currency revaluations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1d0a-105">Egyes szervezetek olyan naplókat adnak meg, amelyek egynél több ügyféllel vagy szállítóval rendelkező bizonylatot tartalmaznak, valamint a Kinnlevőségek és a Kötelezettségek devizaátértékelési folyamatát is.</span><span class="sxs-lookup"><span data-stu-id="a1d0a-105">Some organizations enter journals that contain a single voucher that has more than one customer or vendor, and they also run the Accounts receivable or Accounts payable foreign currency revaluation process.</span></span> <span data-ttu-id="a1d0a-106">Ez a témakör bemutatja azokat a lépéseket, amelyeket ezeknek a szervezeteknek követniük kell, amikor frissítenek a Microsoft Dynamics 365 for Operations 1611-es verziójára.</span><span class="sxs-lookup"><span data-stu-id="a1d0a-106">This topic describes the steps that these organizations should follow when they upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

<span data-ttu-id="a1d0a-107">Kövesse az alábbi lépéseket, amikor frissít a Microsoft Dynamics 365 for Operations 1611 verziójára.</span><span class="sxs-lookup"><span data-stu-id="a1d0a-107">Follow these steps when you upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

1.  <span data-ttu-id="a1d0a-108">A Dynamics 365 for Operations frissítése előtt futtassa le a devizaátértékelés folyamatait a Kinnlevőségeknél és a Kötelezettségeknél.</span><span class="sxs-lookup"><span data-stu-id="a1d0a-108">Before you upgrade to Dynamics 365 for Operations, run the foreign currency revaluation processes for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="a1d0a-109">A **Módszer** mezőben állítsa be a **Számla dátuma** értéket.</span><span class="sxs-lookup"><span data-stu-id="a1d0a-109">Set the **Method** field to **Invoice date**.</span></span> <span data-ttu-id="a1d0a-110">Átértékelési tranzakció jön létre, amely visszaállítja a legutóbbi devizaátértékelést.</span><span class="sxs-lookup"><span data-stu-id="a1d0a-110">A revaluation transaction is created that reverses the last foreign currency revaluation.</span></span> <span data-ttu-id="a1d0a-111">Emiatt a nyitott tranzakciók értékelése az eredeti könyvelési pénznemben történik.</span><span class="sxs-lookup"><span data-stu-id="a1d0a-111">Therefore, the open transactions are valued at their original accounting currency.</span></span>
2.  <span data-ttu-id="a1d0a-112">Frissítési a Dynamics 365 for Operations 1611 verzióra.</span><span class="sxs-lookup"><span data-stu-id="a1d0a-112">Upgrade to Dynamics 365 for Operations version 1611.</span></span>
3.  <span data-ttu-id="a1d0a-113">Futtassa le újra a devizaátértékelés folyamatait a Kinnlevőségeknél és a Kötelezettségeknél.</span><span class="sxs-lookup"><span data-stu-id="a1d0a-113">Run the Accounts receivable and Accounts payable foreign currency revaluation processes again.</span></span> <span data-ttu-id="a1d0a-114">Ekkor állítsa a **Módszer** mezőt **Normál** értékre.</span><span class="sxs-lookup"><span data-stu-id="a1d0a-114">This time, set the **Method** field to **Standard**.</span></span> <span data-ttu-id="a1d0a-115">Új átértékelési tranzakció jön létre, amelynek alapját a jelenlegi átváltási árfolyamok jelentik.</span><span class="sxs-lookup"><span data-stu-id="a1d0a-115">A new revaluation transaction is created that is based on the current exchange rates.</span></span> <span data-ttu-id="a1d0a-116">Ez a tranzakció rögzíti a nem realizált nyereséget/veszteséget és a megfelelő összefoglaló főkönyvi számlát.</span><span class="sxs-lookup"><span data-stu-id="a1d0a-116">This transaction records the unrealized gain/loss and the correct summary ledger account.</span></span>




