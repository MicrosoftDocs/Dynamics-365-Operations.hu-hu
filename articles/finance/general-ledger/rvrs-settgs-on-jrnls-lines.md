---
title: Naplók és sorok sztornírozási beállításai
description: Ez a témakör azt ismerteti, hogy egy általános naplón bevitt sztornírozási bejegyzés miért nem jelenik meg a feladott tranzakción.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 74020f6fc9b0fa8e05a1e2a09fd13dcd60490dc0
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028566"
---
# <a name="reverse-settings-on-journals-and-lines"></a><span data-ttu-id="4c3d0-103">Naplók és sorok sztornírozási beállításai</span><span class="sxs-lookup"><span data-stu-id="4c3d0-103">Reverse settings on journals and lines</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c3d0-104">Ez a témakör azt ismerteti, hogy egy általános naplón bevitt sztornírozási bejegyzés miért nem jelenik meg a feladott tranzakción.</span><span class="sxs-lookup"><span data-stu-id="4c3d0-104">This topic addresses why a reversing entry that was entered on a general journal might not be included on the posted transaction.</span></span>  

## <a name="symptom"></a><span data-ttu-id="4c3d0-105">Tünet</span><span class="sxs-lookup"><span data-stu-id="4c3d0-105">Symptom</span></span>

<span data-ttu-id="4c3d0-106">Az általános napló tartalmaz egy sztornírozási bejegyzést és egy sztornírozási dátumot a naplóban.</span><span class="sxs-lookup"><span data-stu-id="4c3d0-106">A general journal includes a reversing entry and reversing date on the journal.</span></span> <span data-ttu-id="4c3d0-107">A napló feladásakor egyik bizonylat sztornírozása sem történt meg.</span><span class="sxs-lookup"><span data-stu-id="4c3d0-107">When you post the journal, none of the vouchers are reversed.</span></span> <span data-ttu-id="4c3d0-108">Miért történik ez?</span><span class="sxs-lookup"><span data-stu-id="4c3d0-108">Why does this happen?</span></span>

## <a name="resolution"></a><span data-ttu-id="4c3d0-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="4c3d0-109">Resolution</span></span>

<span data-ttu-id="4c3d0-110">A napló feladásakor a sztornírozási folyamat csak a **Sztornírozási bejegyzés** és **Sztornírozási dátum** beállítást figyeli a bizonylat **Sorok** szakaszában.</span><span class="sxs-lookup"><span data-stu-id="4c3d0-110">When the journal is posted, the reversing process looks only at the **Revering entry** and **Reversing date** settings on the **Lines** section of the voucher.</span></span> <span data-ttu-id="4c3d0-111">Ez a megközelítés lehetővé teszi a napló számára, hogy néhány olyan bizonylatot is tartalmazzon, amelyek sztornírozásra meg vannak jelölve, és másikat is, amelyek nincsenek megjelölve.</span><span class="sxs-lookup"><span data-stu-id="4c3d0-111">This approach allows a journal to include some vouchers that are marked for reversing, and others that are not.</span></span>

<span data-ttu-id="4c3d0-112">A napló értékeit csak alapértelmezettként használja a rendszer, amikor *új* sorokat ad hozzá.</span><span class="sxs-lookup"><span data-stu-id="4c3d0-112">The values from the journal are only used as defaults when adding *new* lines.</span></span> <span data-ttu-id="4c3d0-113">A napló értékeinek módosítása nem érinti a meglévő sorokat.</span><span class="sxs-lookup"><span data-stu-id="4c3d0-113">Changing the values on the journal doesn’t affect existing lines.</span></span> <span data-ttu-id="4c3d0-114">Ebben a példában először a bizonylatsorok lettek megadva.</span><span class="sxs-lookup"><span data-stu-id="4c3d0-114">In this example, the voucher lines were entered first.</span></span> <span data-ttu-id="4c3d0-115">Amikor azelőtt adja meg a sor részletes adatait, mielőtt naplót sztornírozási naplóként jelölné meg, a sztornírozási bejegyzésként és dátumként való megjelölést a rendszer nem alkalmazza egyik meglévő sorra sem.</span><span class="sxs-lookup"><span data-stu-id="4c3d0-115">When you enter the line detail before designating the journal as reversing, the designation as a reversing entry and date won't be applied to any existing lines.</span></span>

<span data-ttu-id="4c3d0-116">A sztornírozási bejegyzés vagy sztornírozási dátum módosítása egy meglévő soron továbbviszi a módosítást a többi sorra ugyanazon a bizonylaton.</span><span class="sxs-lookup"><span data-stu-id="4c3d0-116">Changing the reversing entry or reversing date on an existing line propagates that change to other lines in the same voucher.</span></span> <span data-ttu-id="4c3d0-117">A teljesítmény optimalizálása érdekében a rács nem frissül a módosítások más sorokra történő továbbvitele után.</span><span class="sxs-lookup"><span data-stu-id="4c3d0-117">To optimize performance, the grid is not refreshed after propagating changes to other Lines.</span></span> <span data-ttu-id="4c3d0-118">A módosított értékeket a rács frissítésével jelenítheti meg.</span><span class="sxs-lookup"><span data-stu-id="4c3d0-118">You can display the updated values by refreshing the grid.</span></span>


