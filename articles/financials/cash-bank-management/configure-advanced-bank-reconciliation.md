---
title: "Továbbfejlesztett banki egyeztetés beállításának folyamata"
description: "A Továbbfejlesztett banki egyeztetés lehetővé teszi Önnek az elektronikus banki kivonatok és az automatikus egyeztetés importálását a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition banki tranzakcióiba.  Ez a cikk a beállítási folyamatokról nyújt tájékoztatást az egyeztetésre vonatkozóan."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2fb263b615635943cfce8f1b6c0ea4702002705e
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="advanced-bank-reconciliation-setup-process"></a><span data-ttu-id="b40dd-104">Továbbfejlesztett banki egyeztetés beállításának folyamata</span><span class="sxs-lookup"><span data-stu-id="b40dd-104">Advanced bank reconciliation setup process</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b40dd-105">A Továbbfejlesztett banki egyeztetés lehetővé teszi Önnek az elektronikus banki kivonatok és az automatikus egyeztetés importálását a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition banki tranzakcióiba.</span><span class="sxs-lookup"><span data-stu-id="b40dd-105">Advanced bank reconciliation allows you to import electronic bank statements and automatically reconcile with bank transactions in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>  <span data-ttu-id="b40dd-106">Ez a cikk a beállítási folyamatokról nyújt tájékoztatást az egyeztetésre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="b40dd-106">This article will explain the set up processes for reconciliation.</span></span>  

<span data-ttu-id="b40dd-107">Számos darabot a továbbfejlesztett banki egyeztetés funkció használata előtt be kell állítani.</span><span class="sxs-lookup"><span data-stu-id="b40dd-107">There are a number of pieces that must be set up before using the advanced bank reconciliation functionality.</span></span> <span data-ttu-id="b40dd-108">A Bankkivonat importálásának beállításával kapcsolatos további tudnivalókért lásd: [A banki kivonat importálási folyamatának beállítása](set-up-advanced-bank-reconciliation-import-process.md).</span><span class="sxs-lookup"><span data-stu-id="b40dd-108">For more information about setting up bank statement import, see [Set up the bank statement import process](set-up-advanced-bank-reconciliation-import-process.md).</span></span>  <span data-ttu-id="b40dd-109">Az egyeztetési folyamatra vonatkozó követelmények alább vannak részletezve.</span><span class="sxs-lookup"><span data-stu-id="b40dd-109">Requirements for set up of the reconciliation process are detailed below.</span></span>

## <a name="transaction-codes"></a><span data-ttu-id="b40dd-110">Tranzakciókódok</span><span class="sxs-lookup"><span data-stu-id="b40dd-110">Transaction codes</span></span>
<span data-ttu-id="b40dd-111">A tranzakciókódok a banki egyeztetési szabályok részeként használhatók.</span><span class="sxs-lookup"><span data-stu-id="b40dd-111">Transaction codes can be used as part of the bank reconciliation matching rules.</span></span>  <span data-ttu-id="b40dd-112">Tranzakciókódok segítségével biztosítható, hogy csak az azonos típusú tranzakciók kerüljenek egyeztetésre a Finance and Operations és a bankszámlakivonat között.</span><span class="sxs-lookup"><span data-stu-id="b40dd-112">Transaction codes will help to match only the same types of transactions between Finance and Operations and your bank statement.</span></span>  <span data-ttu-id="b40dd-113">Ezen típusú egyeztetés végrehajtásához először meg kell határozni a banki tranzakciókhoz használt tranzakciótípusokat a Finance and Operationsből, majd e típusokat hozzá kell rendelni a bank kivonatán szereplő tranzakciókódokhoz.</span><span class="sxs-lookup"><span data-stu-id="b40dd-113">In order to do this type of matching, you must first define transaction types used for bank transactions from Finance and Operations, then map those types to statement transaction codes used by your bank.</span></span>  <span data-ttu-id="b40dd-114">A Finance and Operations banki tranzakcióinak tranzakciótípusai a **Banki tranzakciótípusok** lapon vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="b40dd-114">Transaction types for Finance and Operations bank transactions are defined on the **Bank transaction type** page.</span></span>  <span data-ttu-id="b40dd-115">Itt adhatja meg a tranzakció típusával társított feladásokhoz használt fő számlát is.</span><span class="sxs-lookup"><span data-stu-id="b40dd-115">This is also where you define the main account to be used for postings associated with that transaction type.</span></span> 

<span data-ttu-id="b40dd-116">Miután meghatározta a Finance and Operations banki tranzakciókódjait, rendelje hozzá azokat az elektronikus banki kivonatokban használt tranzakciókódokhoz.</span><span class="sxs-lookup"><span data-stu-id="b40dd-116">Once your Finance and Operations bank transaction codes are defined, you then map those to the transaction codes used in your electronic bank statements.</span></span>  <span data-ttu-id="b40dd-117">Ez a leképezési folyamat a **Tranzakciókód-hozzárendelés** oldalon hajtható végre.</span><span class="sxs-lookup"><span data-stu-id="b40dd-117">This mapping process is done using the **Transaction code mapping** page.</span></span>  <span data-ttu-id="b40dd-118">A tranzakciókódok hozzárendelését minden bankszámlánál külön el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="b40dd-118">Transaction code mapping is completed separately for each bank account.</span></span>

## <a name="matching-rules-and-matching-rule-sets"></a><span data-ttu-id="b40dd-119">Az Egyeztetési szabályok és a megfelelő szabálykészletek</span><span class="sxs-lookup"><span data-stu-id="b40dd-119">Matching rules and matching rule sets</span></span>
<span data-ttu-id="b40dd-120">Az egyeztetési szabályok lehetővé teszik a Finance and Operations banki tranzakciói és a bankszámlakivonat tranzakciói közötti automatikus egyeztetést.</span><span class="sxs-lookup"><span data-stu-id="b40dd-120">Matching rules allow you to define criteria for automatic reconciliation between Finance and Operations bank transactions and bank statement transactions.</span></span>  <span data-ttu-id="b40dd-121">Egyeztetési szabályok beállításához használja az **Egyeztetési szabályok** oldalt.</span><span class="sxs-lookup"><span data-stu-id="b40dd-121">Set up of matching rules is done on **Reconciliation matching rules** page.</span></span>  <span data-ttu-id="b40dd-122">További tudnivalókért lásd: [Banki egyeztetési szabályok beállítása](set-up-bank-reconciliation-matching-rules.md).</span><span class="sxs-lookup"><span data-stu-id="b40dd-122">For more information, see [Set up bank reconciliation matching rules](set-up-bank-reconciliation-matching-rules.md).</span></span> 

<span data-ttu-id="b40dd-123">Az egyeztetési szabálykészlet olyan egyeztetési szabályok csoportjainak meghatározására szolgál, amelyeket a rendszer sorrendben futtat a banki kivonat egyeztetési folyamata során.</span><span class="sxs-lookup"><span data-stu-id="b40dd-123">Matching rule sets are used to define a group of matching rules that are run in sequence during the bank reconciliation process.</span></span>  <span data-ttu-id="b40dd-124">Az egyeztetési szabálykészletek konfigurálása az **Egyeztetési szabálykészletek** oldalon történik.</span><span class="sxs-lookup"><span data-stu-id="b40dd-124">Matching rule sets are configured on the **Reconciliation matching rule sets** page.</span></span>

## <a name="cash-and-bank-management-parameters"></a><span data-ttu-id="b40dd-125">Készpénz- és bankkezelési paraméterek</span><span class="sxs-lookup"><span data-stu-id="b40dd-125">Cash and bank management parameters</span></span>
<span data-ttu-id="b40dd-126">A **Készpénz- és bankkezelési paraméterek** oldalon számos, kifejezetten a továbbfejlesztett banki egyeztetési folyamattal kapcsolatos paraméter található.</span><span class="sxs-lookup"><span data-stu-id="b40dd-126">There are a number of parameters specific to the advanced bank reconciliation process on the **Cash and bank management parameters** page.</span></span>  <span data-ttu-id="b40dd-127">A **Kivonatsor mennyiségének megjelenítése tartozik/követel oszlopokban** módosítja a **Banki kivonat** oldalon szereplő összegek nézetét.</span><span class="sxs-lookup"><span data-stu-id="b40dd-127">The **Show statement line amount in debit/credit** changes the view of amounts on the **Bank statement** page.</span></span>  <span data-ttu-id="b40dd-128">Ha ezt a beállítást választja, a banki kivonat tranzakcióösszegei külön-külön a tartozik és követel oszlopokban fognak megjelenni.</span><span class="sxs-lookup"><span data-stu-id="b40dd-128">If this option is selected, the bank statement transaction amounts will be shown in separate debit and credit columns.</span></span>  <span data-ttu-id="b40dd-129">Ha nem ezt választja, akkor a banki kivonat tranzakcióösszegei a megfelelő jellel egy összegmezőben fognak megjelenni.</span><span class="sxs-lookup"><span data-stu-id="b40dd-129">If not selected, the bank statement transaction amounts will be shown in a single amount column with the appropriate sign.</span></span> 

<span data-ttu-id="b40dd-130">A Paraméterek lapon beállított ellenőrzési beállítások felülírják az egyeztetési szabályokban beállított kiválasztásokat.</span><span class="sxs-lookup"><span data-stu-id="b40dd-130">The validation options set on the parameters page override the selections set on matching rules.</span></span>  <span data-ttu-id="b40dd-131">Például nem lehet manuálisan vagy automatikusan egyeztetni dokumentumokat a paraméterek lapon beállított dátumkülönbségen túl.</span><span class="sxs-lookup"><span data-stu-id="b40dd-131">For example, you cannot manually or automatically match documents beyond the date difference set on the parameters page.</span></span>  <span data-ttu-id="b40dd-132">Ha a beállítás **Tranzakciótípus hozzárendelésének ellenőrzése** lehetőségre van beállítva, a tranzakciótípusokat a Finance and Operations banki tranzakciói és a banki kivonat tranzakciói között le kell képezni a tranzakciók manuálisan vagy automatikusan történő egyeztetéséhez.</span><span class="sxs-lookup"><span data-stu-id="b40dd-132">Also, if the option to **Validate transaction type mapping** is selected, the transaction types must be mapped between the Finance and Operations bank transaction and bank statement transaction in order for the transactions to be manually or automatically matched.</span></span> 

<span data-ttu-id="b40dd-133">Továbbá konfigurálnia kell a szükséges számsorozatokat a **Készpénz- és bankkezelési paraméterek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="b40dd-133">You also must configure the necessary number sequences on the **Cash and bank management parameters** page.</span></span>  <span data-ttu-id="b40dd-134">A **Számsorozatok** lapon állítsa be a számsorozat-kódokat az **Azonosító, az Utasítás azonosítója, az Egyeztetési azonosító, és a banki egyeztetés** Letöltés hivatkozásra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="b40dd-134">On the **Number sequences** tab, set number sequence codes for the Download **ID, Statement ID, Reconcile ID, and Bank reconciliation** references.</span></span>

## <a name="bank-account-reconciliation-options"></a><span data-ttu-id="b40dd-135">Bankszámla-egyeztetés beállítások</span><span class="sxs-lookup"><span data-stu-id="b40dd-135">Bank account reconciliation options</span></span>
<span data-ttu-id="b40dd-136">Először engedélyeznie kell a bankszámlához tartozó Továbbfejlesztett banki egyeztetést.</span><span class="sxs-lookup"><span data-stu-id="b40dd-136">You must first enable Advanced bank reconciliation for the bank account.</span></span>  <span data-ttu-id="b40dd-137">Számos további beállítás érhető el a **Bankszámla** oldalon a Továbbfejlesztett banki egyeztetés funkció engedélyezése után.</span><span class="sxs-lookup"><span data-stu-id="b40dd-137">A number of additional options are available on the **Bank account** page once the Advanced bank reconciliation functionality is enabled.</span></span> 

<span data-ttu-id="b40dd-138">A **Banki kivonatok használata az elektronikus fizetések visszaigazolására** funkció a banki egyeztetés funkcióját az elektronikus fizetési állapotokba integrálja.</span><span class="sxs-lookup"><span data-stu-id="b40dd-138">**Use bank statements as confirmation of electronic payment** functionality integrates the bank reconciliation functionality with electronic payment statuses.</span></span>  <span data-ttu-id="b40dd-139">Ha ez engedélyezve van, a banki bizonylat automatikusan létrejön az **Elküldött** állapotra beállított elektronikus fizetési állapotra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="b40dd-139">When this is enabled, a bank document will automatically be created for the electronic payment status is set to **Sent**.</span></span>  <span data-ttu-id="b40dd-140">Ezenkívül az elektronikus fizetések állapota az **Elküldött** állapotról **Fogadott** állapotra fog frissülni a fizetés megfeleltetése, egyeztetése és feladása után.</span><span class="sxs-lookup"><span data-stu-id="b40dd-140">In addition, the status of an electronic payment will be updated from **Sent** to **Received** after the payment is matched, reconciled, and posted.</span></span> 

<span data-ttu-id="b40dd-141">**A kimutatásokban szereplő bankszámla neve** mező neve az elektronikus banki kivonatokban szereplő bankszámlára vonatkozó névvel egyezik meg.</span><span class="sxs-lookup"><span data-stu-id="b40dd-141">The **Bank account name in statements** field is the name used for the bank account on your electronic bank statements.</span></span>  <span data-ttu-id="b40dd-142">Ez a név annak eldöntésekor használatos, hogy mely tranzakciók kerüljenek importálásra azon kivonatból származó bankszámlára vonatkozóan, amely több bankszámlára vonatkozó információkat tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="b40dd-142">This name is used when determining what transactions to import for a bank account from a statement that may contain information for multiple bank accounts.</span></span> 

<span data-ttu-id="b40dd-143">Az **Egyeztetés az importálás után** lehetőségre történő beállítás automatikusan ellenőrzi a banki kivonatot, új banki egyeztetést és munkalapot hoz létre, és futtatja az Alapértelmezett egyeztetési szabálykészletet.</span><span class="sxs-lookup"><span data-stu-id="b40dd-143">The option to **Reconcile after import** will automatically validate the bank statement, create a new bank reconciliation and worksheet, and run the Default matching rule set.</span></span>  <span data-ttu-id="b40dd-144">Ez a funkció automatizálja a folyamatot addig a pontig, ahol már a tranzakciókat kézzel kell egymáshoz rendelni.</span><span class="sxs-lookup"><span data-stu-id="b40dd-144">This functionality automates the process up to the point of the transactions that must be manually matched.</span></span>  <span data-ttu-id="b40dd-145">A bankszámla beállítása visszaáll alapértelmezésre az importáláskor.</span><span class="sxs-lookup"><span data-stu-id="b40dd-145">The setting on the bank account will default when importing.</span></span>



