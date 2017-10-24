---
title: "Továbbfejlesztett banki egyeztetés áttekintés"
description: "A cikk a továbbfejlesztett banki egyeztetés folyamatát ismerteti. A továbbfejlesztett banki egyeztetési funkcióval importálhatja a banki tranzakciókból automatikusan egyeztethető banki kivonatokat."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 33150777222faa97af7488c59ab13cb0fb9e8e2c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="advanced-bank-reconciliation-overview"></a><span data-ttu-id="e2614-104">Továbbfejlesztett banki egyeztetés áttekintés</span><span class="sxs-lookup"><span data-stu-id="e2614-104">Advanced bank reconciliation overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e2614-105">A cikk a továbbfejlesztett banki egyeztetés folyamatát ismerteti.</span><span class="sxs-lookup"><span data-stu-id="e2614-105">This article describes the flow for the advanced bank reconciliation process.</span></span> <span data-ttu-id="e2614-106">A továbbfejlesztett banki egyeztetési funkcióval importálhatja a banki tranzakciókból automatikusan egyeztethető banki kivonatokat.</span><span class="sxs-lookup"><span data-stu-id="e2614-106">The advanced bank reconciliation feature lets you import bank statements that can be automatically reconciled from within bank transactions.</span></span>

<span data-ttu-id="e2614-107">A továbbfejlesztett banki egyeztetés szolgáltatás lehetővé teszi a banki kivonatok importálását.</span><span class="sxs-lookup"><span data-stu-id="e2614-107">The advanced bank reconciliation feature lets you import bank statements.</span></span> <span data-ttu-id="e2614-108">Az importált banki kivonatot ezután automatikusan lehet egyeztetni, a banki tranzakciókon belül.</span><span class="sxs-lookup"><span data-stu-id="e2614-108">The imported bank statement can then be automatically reconciled from within bank transactions.</span></span> <span data-ttu-id="e2614-109">A lépések a következők a továbbfejlesztett banki egyeztetés folyamatban.</span><span class="sxs-lookup"><span data-stu-id="e2614-109">Here are the steps in the advanced bank reconciliation flow.</span></span>

1.  <span data-ttu-id="e2614-110">Banki kivonat importálásának beállítása.</span><span class="sxs-lookup"><span data-stu-id="e2614-110">Set up a bank statement import.</span></span>
    -   <span data-ttu-id="e2614-111">Banki kivonatok importálása az adatentitás keretrendszeren keresztül.</span><span class="sxs-lookup"><span data-stu-id="e2614-111">Import bank statements through the data entity framework.</span></span>
    -   <span data-ttu-id="e2614-112">Három jellemző banki kivonatformátum be vannak építve: ISO20022, BAI2 és MT940.</span><span class="sxs-lookup"><span data-stu-id="e2614-112">Three typical bank statement formats are built in: ISO20022, BAI2, and MT940.</span></span>
    -   <span data-ttu-id="e2614-113">A funkciót minden formátumba ki lehet terjeszteni.</span><span class="sxs-lookup"><span data-stu-id="e2614-113">The functionality can be extended to any format.</span></span>

2.  <span data-ttu-id="e2614-114">Állítsa be a továbbfejlesztett banki egyeztetés során használandó számsorozatot, és állítsa be a banki egyeztetési szabályokat.</span><span class="sxs-lookup"><span data-stu-id="e2614-114">Set up a number sequence to use for advanced bank reconciliation, and define the bank reconciliation matching rules.</span></span>
    -   <span data-ttu-id="e2614-115">Az egyeztetési szabály olyan kritériumok készlete, melyek a banki kivonat sorainak és a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition bankitranzakció-sorainak szűrésére szolgálnak az egyeztetési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="e2614-115">A reconciliation matching rule is a set of criteria that are used to filter bank statement lines and Microsoft Dynamics 365 for Finance and Operations, Enterprise edition bank transaction lines during the reconciliation process.</span></span> <span data-ttu-id="e2614-116">Üzleti gyakorlattól függően egynél több egyeztetési szabályt is beállíthat az egyeztetési folyamat automatizálása és optimalizálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="e2614-116">Depending on your business practice, you can set up more than one matching rule to automate and optimize your reconciliation process.</span></span>

3.  <span data-ttu-id="e2614-117">Banki kivonatok egyeztetése a Finance and Operations banki tranzakciókkal.</span><span class="sxs-lookup"><span data-stu-id="e2614-117">Reconcile bank statements with Finance and Operations bank transactions.</span></span>
    -   <span data-ttu-id="e2614-118">Automatikus egyeztetés végrehajtása és egyeztetési napló létrehozása.</span><span class="sxs-lookup"><span data-stu-id="e2614-118">Perform automatic matching and creation of reconciliation journals.</span></span>
    -   <span data-ttu-id="e2614-119">Banki kivonatok és a Finance and Operations banki tranzakciók megtekintése egymás mellett.</span><span class="sxs-lookup"><span data-stu-id="e2614-119">View bank statements and Finance and Operations bank transactions side by side.</span></span>
    -   <span data-ttu-id="e2614-120">A Finance and Operations banki tranzakciók automatikusan feladása, ha a banki kivonaton megjelennek, de a Finance and Operationsben nem jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="e2614-120">Automatically post Finance and Operations bank transactions if they appear on a bank statement but don't appear in Finance and Operations.</span></span>
    -   <span data-ttu-id="e2614-121">Egyeztetési kivonat létrehozása.</span><span class="sxs-lookup"><span data-stu-id="e2614-121">Generate a reconciliation statement.</span></span>






