--- 
title: "Árfolyamszámítás (Magyarország)"
description: "Ez a feladat végigvezeti Önt az átlagos átváltási árfolyam kiszámításának folyamatán."
author: v-oloski
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Hungary
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0fc481c1086e981c4c5a67c4b8f7cf655bfe52ae
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="exchange-rate-calculation-hungary"></a><span data-ttu-id="ac521-103">Árfolyamszámítás (Magyarország)</span><span class="sxs-lookup"><span data-stu-id="ac521-103">Exchange rate calculation (Hungary)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ac521-104">Ez a feladat végigvezeti Önt az átlagos átváltási árfolyam kiszámításának folyamatán.</span><span class="sxs-lookup"><span data-stu-id="ac521-104">This task walks you through running an average exchange rate calculation.</span></span> 

<span data-ttu-id="ac521-105">Az átváltási árfolyamok naplósorokhoz számíthatók ki.</span><span class="sxs-lookup"><span data-stu-id="ac521-105">You can calculate the exchange rates for journal lines.</span></span> <span data-ttu-id="ac521-106">Készpénzes és banki tranzakciókhoz a napi átváltási árfolyam vagy egy átlagos átváltási árfolyam használható.</span><span class="sxs-lookup"><span data-stu-id="ac521-106">For cash and bank transactions, you can use either the daily exchange rate or an average exchange rate.</span></span> <span data-ttu-id="ac521-107">Pénztár és bank naplósorokban az átlagos átváltási árfolyam kiszámításához a könyvelési pénznem és a külföldi pénznem összesített összegei használatosak a tranzakció megadott időpontja előtt.</span><span class="sxs-lookup"><span data-stu-id="ac521-107">For petty cash and bank journal lines, the calculation of the average exchange rate uses the summarized amounts of the accounting currency and the foreign currency before the specified transaction date.</span></span>

<span data-ttu-id="ac521-108">Ez a feladat a DEMF bemutatócég adatainak segítségével jött létre, és a jogi személy székhelyének országát/régióját Magyarországra állítottuk.</span><span class="sxs-lookup"><span data-stu-id="ac521-108">This task was created using the demo data company DEMF with the country/region of legal entity primary address updated to be Hungary.</span></span> <span data-ttu-id="ac521-109">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="ac521-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="ac521-110">Ugorjon a Főkönyv > Naplóbejegyzések > Általános naplók pontra.</span><span class="sxs-lookup"><span data-stu-id="ac521-110">Go to General ledger > Journal entries > General journals.</span></span>
2. <span data-ttu-id="ac521-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ac521-111">Click New.</span></span>
3. <span data-ttu-id="ac521-112">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ac521-112">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="ac521-113">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="ac521-113">Click Lines.</span></span>
5. <span data-ttu-id="ac521-114">A Számla típusa mezőben válassza a Vevő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ac521-114">In the Account type field, select 'Customer'.</span></span>
6. <span data-ttu-id="ac521-115">A Számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ac521-115">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="ac521-116">Írjon be bármilyen összeget a Terhelés mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ac521-116">In the Debit field, enter any amount.</span></span>
8. <span data-ttu-id="ac521-117">Az Ellenszámla típusa mezőben válassza a „Bank” értéket.</span><span class="sxs-lookup"><span data-stu-id="ac521-117">In the Offset account type field, select 'Bank'.</span></span>
9. <span data-ttu-id="ac521-118">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ac521-118">In the Offset account field, specify the desired values.</span></span>
10. <span data-ttu-id="ac521-119">A Pénznem mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ac521-119">In the Currency field, enter or select a value.</span></span>
    * <span data-ttu-id="ac521-120">Használhatja az „USD” értéket.</span><span class="sxs-lookup"><span data-stu-id="ac521-120">You may use value 'USD'.</span></span>  
11. <span data-ttu-id="ac521-121">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="ac521-121">Click Functions.</span></span>
12. <span data-ttu-id="ac521-122">Kattintson az Árfolyam-számítási szabályok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ac521-122">Click Exchange rate calculation.</span></span>
13. <span data-ttu-id="ac521-123">Adjon meg egy
Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="ac521-123">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="ac521-124">Válasszon ki egy tranzakciódátumot egy időszak meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="ac521-124">Select a transaction date to specify a period.</span></span> <span data-ttu-id="ac521-125">A rendszer azokat a főkönyvi tranzakciókat veszi figyelembe az átlagos árfolyam számításánál, amelyek tranzakciódátumai az ezen mezőbe beírt dátumra esnek vagy azt követik, valamint a naplósor tranzakciódátumánál korábbiak.</span><span class="sxs-lookup"><span data-stu-id="ac521-125">Ledger transactions are included in the calculation of the average exchange rate if the transaction dates are on or after the date that you enter in this field, and before the transaction date of the journal line.</span></span> <span data-ttu-id="ac521-126">Ha ezt a mezőt üresen hagyja, a rendszer a számítás során figyelembe veszi mindazokat a főkönyvi tranzakciókat, amelyek tranzakciódátuma a naplósor tranzakciódátuma elé esik.</span><span class="sxs-lookup"><span data-stu-id="ac521-126">If you leave this field blank, the calculation includes all ledger transactions for which the transaction dates are before the transaction date of the journal line.</span></span>  
14. <span data-ttu-id="ac521-127">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="ac521-127">Expand the Records to include section.</span></span>
    * <span data-ttu-id="ac521-128">Majd a Belefoglalandó rekordok fül használatával állítson be kiválasztási feltételeket az átváltási árfolyam számításában szerepeltetni kívánt sorokhoz.</span><span class="sxs-lookup"><span data-stu-id="ac521-128">Use ‘Records to include tab’ to set up selection criteria for the lines to include in the exchange rate calculation.</span></span> <span data-ttu-id="ac521-129">Ha nem állít be kiválasztási feltételeket a Szűrő űrlapon, a kiválasztott számítási módszer kerül felhasználásra az aktuális naplóban lévő minden sorhoz.</span><span class="sxs-lookup"><span data-stu-id="ac521-129">If you do not set up selection criteria in the Filter form, the calculation method that you selected is used for all lines in the current journal.</span></span>  
15. <span data-ttu-id="ac521-130">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ac521-130">Click OK.</span></span>


