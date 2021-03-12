---
title: Továbbfejlesztett banki egyeztetés áttekintés
description: A cikk a továbbfejlesztett banki egyeztetés folyamatát ismerteti. A továbbfejlesztett banki egyeztetési funkcióval importálhatja a banki tranzakciókból automatikusan egyeztethető banki kivonatokat.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09128f33d4208bc5c987683bb881aa1129b0dc8e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985436"
---
# <a name="advanced-bank-reconciliation-overview"></a><span data-ttu-id="7d96f-104">Továbbfejlesztett banki egyeztetés áttekintés</span><span class="sxs-lookup"><span data-stu-id="7d96f-104">Advanced bank reconciliation overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7d96f-105">A cikk a továbbfejlesztett banki egyeztetés folyamatát ismerteti.</span><span class="sxs-lookup"><span data-stu-id="7d96f-105">This article describes the flow for the advanced bank reconciliation process.</span></span> <span data-ttu-id="7d96f-106">A továbbfejlesztett banki egyeztetési funkcióval importálhatja a banki tranzakciókból automatikusan egyeztethető banki kivonatokat.</span><span class="sxs-lookup"><span data-stu-id="7d96f-106">The advanced bank reconciliation feature lets you import bank statements that can be automatically reconciled from within bank transactions.</span></span>

<span data-ttu-id="7d96f-107">A továbbfejlesztett banki egyeztetés szolgáltatás lehetővé teszi a banki kivonatok importálását.</span><span class="sxs-lookup"><span data-stu-id="7d96f-107">The advanced bank reconciliation feature lets you import bank statements.</span></span> <span data-ttu-id="7d96f-108">Az importált banki kivonatot ezután automatikusan lehet egyeztetni, a banki tranzakciókon belül.</span><span class="sxs-lookup"><span data-stu-id="7d96f-108">The imported bank statement can then be automatically reconciled from within bank transactions.</span></span> <span data-ttu-id="7d96f-109">A lépések a következők a továbbfejlesztett banki egyeztetés folyamatban.</span><span class="sxs-lookup"><span data-stu-id="7d96f-109">Here are the steps in the advanced bank reconciliation flow.</span></span>

1.  <span data-ttu-id="7d96f-110">Banki kivonat importálásának beállítása.</span><span class="sxs-lookup"><span data-stu-id="7d96f-110">Set up a bank statement import.</span></span>
    -   <span data-ttu-id="7d96f-111">Banki kivonatok importálása az adatentitás keretrendszeren keresztül.</span><span class="sxs-lookup"><span data-stu-id="7d96f-111">Import bank statements through the data entity framework.</span></span>
    -   <span data-ttu-id="7d96f-112">Három jellemző banki kivonatformátum be vannak építve: ISO20022, BAI2 és MT940.</span><span class="sxs-lookup"><span data-stu-id="7d96f-112">Three typical bank statement formats are built in: ISO20022, BAI2, and MT940.</span></span>
    -   <span data-ttu-id="7d96f-113">A funkciót minden formátumba ki lehet terjeszteni.</span><span class="sxs-lookup"><span data-stu-id="7d96f-113">The functionality can be extended to any format.</span></span>

2.  <span data-ttu-id="7d96f-114">Állítsa be a továbbfejlesztett banki egyeztetés során használandó számsorozatot, és állítsa be a banki egyeztetési szabályokat.</span><span class="sxs-lookup"><span data-stu-id="7d96f-114">Set up a number sequence to use for advanced bank reconciliation, and define the bank reconciliation matching rules.</span></span>
    -   <span data-ttu-id="7d96f-115">Az egyeztetési szabály olyan kritériumok készlete, mely a banki kivonat sorainak és a Microsoft Dynamics 365 Finance banki bizonylat sorainak szűrésére szolgálnak az egyeztetési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="7d96f-115">A reconciliation matching rule is a set of criteria that are used to filter bank statement lines and Microsoft Dynamics 365 Finance bank transaction lines during the reconciliation process.</span></span> <span data-ttu-id="7d96f-116">Üzleti gyakorlattól függően egynél több egyeztetési szabályt is beállíthat az egyeztetési folyamat automatizálása és optimalizálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="7d96f-116">Depending on your business practice, you can set up more than one matching rule to automate and optimize your reconciliation process.</span></span>

3.  <span data-ttu-id="7d96f-117">Banki kivonatok egyeztetése a Finance banki tranzakciókkal.</span><span class="sxs-lookup"><span data-stu-id="7d96f-117">Reconcile bank statements with Finance bank transactions.</span></span>
    -   <span data-ttu-id="7d96f-118">Automatikus egyeztetés végrehajtása és egyeztetési napló létrehozása.</span><span class="sxs-lookup"><span data-stu-id="7d96f-118">Perform automatic matching and creation of reconciliation journals.</span></span>
    -   <span data-ttu-id="7d96f-119">Banki kivonatok és a Finance banki tranzakciók megtekintése egymás mellett.</span><span class="sxs-lookup"><span data-stu-id="7d96f-119">View bank statements and Finance bank transactions side by side.</span></span>
    -   <span data-ttu-id="7d96f-120">A Finance banki tranzakciók automatikusan feladása, ha a banki kivonaton megjelennek, de a Finance and Operationsben nem jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="7d96f-120">Automatically post Finance bank transactions if they appear on a bank statement but don't appear in the Finance app.</span></span>
    -   <span data-ttu-id="7d96f-121">Egyeztetési kivonat létrehozása.</span><span class="sxs-lookup"><span data-stu-id="7d96f-121">Generate a reconciliation statement.</span></span>





