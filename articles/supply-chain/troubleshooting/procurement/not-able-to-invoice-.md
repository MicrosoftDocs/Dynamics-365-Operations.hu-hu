---
title: Vevő által értékesített értékesítési rendelést nem lehet számlázni
description: A Számla automatikus feladása beállítás engedélyezése után a továbbiakban nem lehet kiszámlázni az eredeti értékesítési rendelést és az eredeti közvetlen kiszállítású beszerzési rendelést.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ab18a2a1dec4b70c55a55637b087c6b11023aa40
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026571"
---
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a><span data-ttu-id="0c40f-103">Vevő által értékesített értékesítési rendelést nem lehet számlázni</span><span class="sxs-lookup"><span data-stu-id="0c40f-103">You can't invoice a customer-facing sales order</span></span>

<span data-ttu-id="0c40f-104">Tudásbáziscikk száma: 4611793</span><span class="sxs-lookup"><span data-stu-id="0c40f-104">KB number: 4611793</span></span>

## <a name="symptoms"></a><span data-ttu-id="0c40f-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="0c40f-105">Symptoms</span></span>

<span data-ttu-id="0c40f-106">A **Számla automatikus feladása** beállítás engedélyezése után a szállító **Vállalatközeli** oldalán a továbbiakban nem lehet kiszámlázni az eredeti értékesítési rendelést és az eredeti közvetlen kiszállítású beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="0c40f-106">You can no longer invoice the original sales order and the original direct delivery purchase order after you enable the **Post invoice automatically** option on the **Intercompany** page for a vendor.</span></span>

## <a name="resolution"></a><span data-ttu-id="0c40f-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="0c40f-107">Resolution</span></span>

<span data-ttu-id="0c40f-108">A vállalatközi és a közvetlen kiszállítású rendelési számlák szinkronizálási viselkedését a [Paraméterek beállítása vállalatközi rendelés feladása során](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order) helyen szereplő paraméterek vezérlik és kényszerítik.</span><span class="sxs-lookup"><span data-stu-id="0c40f-108">The synchronization behavior for intercompany and direct delivery order invoices is controlled and forced by the parameters that are described in [Set up parameters to post an intercompany order](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).</span></span>

<span data-ttu-id="0c40f-109">A paraméterek beállítása után először számlázni kell a vállalatközi értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="0c40f-109">After you set those parameters, you must invoice the intercompany sales order first.</span></span> <span data-ttu-id="0c40f-110">A program ezután szinkronizálja az eredeti értékesítési és beszerzési rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="0c40f-110">The original sales orders and purchase orders will then be synchronized.</span></span>
