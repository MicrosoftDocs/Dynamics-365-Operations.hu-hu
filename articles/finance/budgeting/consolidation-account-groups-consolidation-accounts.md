---
title: Konszolidációsszámla-csoportok és további konszolidációs számlák
description: Ez a témakör konszolidációsszámla-csoportokról és további konszolidációs számlákról nyújt tájékoztatást, és elmagyarázza, hogyan történik ezek használata a Microsoft Dynamics 365 Finance rendszerben.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: roschlom
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5a4e3b4d7bb1d5feefd843cdc347b4a08f94a85a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982188"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a><span data-ttu-id="aa4d4-103">Konszolidációsszámla-csoportok és további konszolidációs számlák</span><span class="sxs-lookup"><span data-stu-id="aa4d4-103">Consolidation account groups and additional consolidation accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aa4d4-104">Ez a témakör konszolidációsszámla-csoportokról és további konszolidációs számlákról nyújt tájékoztatást, és elmagyarázza, hogyan történik ezek használata a Microsoft Dynamics 365 Finance rendszerben.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-104">This topic provides information about consolidation account groups and additional consolidation accounts, and explains how they are used in Microsoft Dynamics 365 Finance.</span></span>

<a name="consolidation-account-groups"></a><span data-ttu-id="aa4d4-105">Konszolidációsszámla-csoportok</span><span class="sxs-lookup"><span data-stu-id="aa4d4-105">Consolidation account groups</span></span>
----------------------------

<span data-ttu-id="aa4d4-106">Konszolidációsszámla-csoportok segítségével számlacsoportokat hozhat létre, amelyeket adatok összesítéséhez használhat.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-106">Consolidation account groups let you create groups of the accounts that you want to use to consolidate data.</span></span> <span data-ttu-id="aa4d4-107">Leggyakrabban a konszolidációsszámla-csoport egy kormányzati megbízáson alapuló számlatükröt jelent, vagy a vállalat központja által meghatározott számlákat rendel egy csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-107">Most often, a consolidation account group represents a government-mandated chart of accounts or maps accounts to a group that is defined by the company's headquarters.</span></span> <span data-ttu-id="aa4d4-108">A konszolidációsszámla-csoportok a **Konszolidáció** modul **Beállítások** területén találhatók.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-108">You can find consolidation account groups in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="aa4d4-109">Amikor hozzáad egy új csoportot, adja meg a számlacsoport egyedi azonosítóját és egy nevet.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-109">When you add a new group, you enter a unique identifier for the account group and a name.</span></span>

## <a name="additional-consolidation-accounts"></a><span data-ttu-id="aa4d4-110">További konszolidációs számlák</span><span class="sxs-lookup"><span data-stu-id="aa4d4-110">Additional consolidation accounts</span></span>
<span data-ttu-id="aa4d4-111">További konszolidációs számlák segítségével egy már meglévő számlatükörben található számla egy konszolidációsszámla-csoporthoz rendelhető hozzá.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-111">Additional consolidation accounts let you assign an account from an existing chart of accounts to a consolidation account group.</span></span> <span data-ttu-id="aa4d4-112">Ezután meghatározhatja a konszolidációs számla értékét és nevét.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-112">You can then specify a consolidation account value and name.</span></span> 

<span data-ttu-id="aa4d4-113">További konszolidációs számlák találhatók a **Konszolidáció** modul **Beállítások** területén.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-113">You can find additional consolidation accounts in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="aa4d4-114">Új konszolidációs számla létrehozásakor meg kell adnia a következő információkat:</span><span class="sxs-lookup"><span data-stu-id="aa4d4-114">When you create a new consolidation account, you must specify the following information:</span></span>

-   <span data-ttu-id="aa4d4-115">**Fő számla** – ezt a mező egy keresés, amely az oldalon megadott számlatükrön alapuló összes fő számlát mutatja.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-115">**Main account** – This field is a lookup that shows all the main accounts that are based on the chart of accounts that you selected on the page.</span></span> <span data-ttu-id="aa4d4-116">Egy számla kijelölésekor a neve automatikusan bekerül a **Fő számla neve** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-116">When you select an account, the name is automatically entered in the **Main account name** field.</span></span>
-   <span data-ttu-id="aa4d4-117">**Konszolidációsszámla-csoport** – e mező segítségével adja meg a csoportot, amelyhez hozzá kívánja rendelni a számlát.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-117">**Consolidation account group** – Use this field to specify the group to assign the account to.</span></span> <span data-ttu-id="aa4d4-118">Ha a két különböző módon összegez, ugyanazt a mind a négy konszolidációsszámla-csoporthoz hozzá kell adnia.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-118">If you consolidate in two different ways, you must add the same account to all four consolidation account groups.</span></span>
-   <span data-ttu-id="aa4d4-119">**Konszolidációs számla** – a konszolidációs számla értékének megadása.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-119">**Consolidation account** – Enter the value of the consolidation account.</span></span> <span data-ttu-id="aa4d4-120">Ez az érték nem feltétlenül egy a számlatükörből származó számla.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-120">This value doesn't have to be an account from a chart of accounts.</span></span> <span data-ttu-id="aa4d4-121">Minden olyan érték lehet, amelyre szüksége van.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-121">It can be any value that you require.</span></span>
-   <span data-ttu-id="aa4d4-122">**Konszolidációs számla neve** – a számla nevének megadása, amely meg fog jelenni a lekérdezésekben és jelentésekben.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-122">**Consolidation account name** – Enter the name of account as you want it to appear on inquiries and reports.</span></span>
-   <span data-ttu-id="aa4d4-123">**SAT-szint** – ezzel a mezővel számlakivonatokat küldhet a mexikói adóhatóságnak.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-123">**SAT level** – This field is used to report account statements to the Mexican tax authorities.</span></span> 

<span data-ttu-id="aa4d4-124">Amikor befejezte a konszolidációsszámla-csoportok és kiegészítő konszolidációs számlák létrehozását, kiválaszthatja a csoportot az online Konszolidálás folyamat során.</span><span class="sxs-lookup"><span data-stu-id="aa4d4-124">When you've finished creating your consolidation account groups and additional consolidation accounts, you can select the group in the Consolidate online process.</span></span>


<span data-ttu-id="aa4d4-125">További információkért lásd: [Konszolidációs csoportok és további konszolidációs számlák létrehozása](../general-ledger/tasks/create-consolidation-groups.md)</span><span class="sxs-lookup"><span data-stu-id="aa4d4-125">For more information, see [Create consolidation groups and additional consolidation accounts](../general-ledger/tasks/create-consolidation-groups.md).</span></span> 



