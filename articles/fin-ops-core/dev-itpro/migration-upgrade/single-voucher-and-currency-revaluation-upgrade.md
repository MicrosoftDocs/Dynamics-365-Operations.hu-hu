---
title: Egyetlen bizonylatos naplók és pénznemértékelések frissítése
description: A témakör az egyetlen bizonylatos naplók és pénznemértékelések frissítését ismerteti.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fb4eca4933716105789d3bbc21dd374395211d1d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559521"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a><span data-ttu-id="822bd-103">Egyetlen bizonylatos naplók és pénznemértékelések frissítése</span><span class="sxs-lookup"><span data-stu-id="822bd-103">Upgrade single-voucher journals and currency revaluations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="822bd-104">Egyes szervezetek olyan naplókat adnak meg, amelyek egynél több ügyféllel vagy szállítóval rendelkező bizonylatot tartalmaznak, valamint a Kinnlevőségek és a Kötelezettségek devizaátértékelési folyamatát is.</span><span class="sxs-lookup"><span data-stu-id="822bd-104">Some organizations enter journals that contain a single voucher that has more than one customer or vendor, and they also run the Accounts receivable or Accounts payable foreign currency revaluation process.</span></span> <span data-ttu-id="822bd-105">Ez a témakör bemutatja azokat a lépéseket, amelyeket ezeknek a szervezeteknek követniük kell, amikor frissítenek a Microsoft Dynamics 365 for Operations 1611-es verziójára.</span><span class="sxs-lookup"><span data-stu-id="822bd-105">This topic describes the steps that these organizations should follow when they upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

<span data-ttu-id="822bd-106">Kövesse az alábbi lépéseket, amikor frissít a Microsoft Dynamics 365 for Operations 1611 verziójára.</span><span class="sxs-lookup"><span data-stu-id="822bd-106">Follow these steps when you upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

1.  <span data-ttu-id="822bd-107">A Finance and Operations frissítése előtt futtassa le a devizaátértékelés folyamatait a Kinnlevőségeknél és a Kötelezettségeknél.</span><span class="sxs-lookup"><span data-stu-id="822bd-107">Before you upgrade to Finance and Operations, run the foreign currency revaluation processes for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="822bd-108">A **Módszer** mezőben állítsa be a **Számla dátuma** értéket.</span><span class="sxs-lookup"><span data-stu-id="822bd-108">Set the **Method** field to **Invoice date**.</span></span> <span data-ttu-id="822bd-109">Átértékelési tranzakció jön létre, amely visszaállítja a legutóbbi devizaátértékelést.</span><span class="sxs-lookup"><span data-stu-id="822bd-109">A revaluation transaction is created that reverses the last foreign currency revaluation.</span></span> <span data-ttu-id="822bd-110">Emiatt a nyitott tranzakciók értékelése az eredeti könyvelési pénznemben történik.</span><span class="sxs-lookup"><span data-stu-id="822bd-110">Therefore, the open transactions are valued at their original accounting currency.</span></span>
2.  <span data-ttu-id="822bd-111">Frissítés a 1611 verzióra.</span><span class="sxs-lookup"><span data-stu-id="822bd-111">Upgrade to version 1611.</span></span>
3.  <span data-ttu-id="822bd-112">Futtassa le újra a devizaátértékelés folyamatait a Kinnlevőségeknél és a Kötelezettségeknél.</span><span class="sxs-lookup"><span data-stu-id="822bd-112">Run the Accounts receivable and Accounts payable foreign currency revaluation processes again.</span></span> <span data-ttu-id="822bd-113">Ekkor állítsa a **Módszer** mezőt **Normál** értékre.</span><span class="sxs-lookup"><span data-stu-id="822bd-113">This time, set the **Method** field to **Standard**.</span></span> <span data-ttu-id="822bd-114">Új átértékelési tranzakció jön létre, amelynek alapját a jelenlegi átváltási árfolyamok jelentik.</span><span class="sxs-lookup"><span data-stu-id="822bd-114">A new revaluation transaction is created that is based on the current exchange rates.</span></span> <span data-ttu-id="822bd-115">Ez a tranzakció rögzíti a nem realizált nyereséget/veszteséget és a megfelelő összefoglaló főkönyvi számlát.</span><span class="sxs-lookup"><span data-stu-id="822bd-115">This transaction records the unrealized gain/loss and the correct summary ledger account.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]