---
title: "Speciális banki egyeztetés MT940 importálása - összetett adatentitás frissítése"
description: "Egy sorszámot kell hozzáadni a banki kivonat importálási entitásához az MT940 formátum támogatásához."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a76558d220e98de85060d23d6e5d8df1c0cd1baf
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a><span data-ttu-id="faf78-103">Speciális banki egyeztetés MT940 importálása - összetett adatentitás frissítése</span><span class="sxs-lookup"><span data-stu-id="faf78-103">Advanced bank reconciliation MT940 Import – Composite data entity upgrade</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="faf78-104">Egy sorszámot kell hozzáadni a banki kivonat importálási entitásához az MT940 formátum támogatásához.</span><span class="sxs-lookup"><span data-stu-id="faf78-104">A sequence number needs to be added to the bank statement import entity to support the MT940 format.</span></span> 

<span data-ttu-id="faf78-105">A következő lépések segítségével adja hozzá a banki kivonat importálási entitását az MT940 formátum támogatásához.</span><span class="sxs-lookup"><span data-stu-id="faf78-105">Use the following steps to add the bank statement import entity to support the MT940 format.</span></span>

1.  <span data-ttu-id="faf78-106">Állítsa össze és szinkronizálja a következőket:</span><span class="sxs-lookup"><span data-stu-id="faf78-106">Compile and synchronize the following:</span></span>
    -   <span data-ttu-id="faf78-107">Összetett entitás\\BankStatementImportEntity</span><span class="sxs-lookup"><span data-stu-id="faf78-107">Composite Entity\\BankStatementImportEntity</span></span>
    -   <span data-ttu-id="faf78-108">Entitás\\BankStatementBalanceEntity</span><span class="sxs-lookup"><span data-stu-id="faf78-108">Entity\\BankStatementBalanceEntity</span></span>
    -   <span data-ttu-id="faf78-109">Entitás\\BankStatementDocumentEntity</span><span class="sxs-lookup"><span data-stu-id="faf78-109">Entity\\BankStatementDocumentEntity</span></span>
    -   <span data-ttu-id="faf78-110">Entitás\\BankStatementEntity</span><span class="sxs-lookup"><span data-stu-id="faf78-110">Entity\\BankStatementEntity</span></span>
    -   <span data-ttu-id="faf78-111">Entitás\\BankStatementLineEntity</span><span class="sxs-lookup"><span data-stu-id="faf78-111">Entity\\BankStatementLineEntity</span></span>
    -   <span data-ttu-id="faf78-112">Táblázatok\\BankStatementStaging</span><span class="sxs-lookup"><span data-stu-id="faf78-112">Tables\\BankStatementStaging</span></span>

2.  <span data-ttu-id="faf78-113">Adatok kezelése\\adatprojektek.</span><span class="sxs-lookup"><span data-stu-id="faf78-113">Data management\\data projects.</span></span>
    1.  <span data-ttu-id="faf78-114">MT940 importálás projekt(ek) betöltése</span><span class="sxs-lookup"><span data-stu-id="faf78-114">Load MT940 import project(s)</span></span>
        1.  <span data-ttu-id="faf78-115">XLST megváltoztatása.</span><span class="sxs-lookup"><span data-stu-id="faf78-115">Change XSLT.</span></span>
            -   <span data-ttu-id="faf78-116">Kattintson a **Térkép megtekintése** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="faf78-116">Click **View map**.</span></span>
            -   <span data-ttu-id="faf78-117">Kattintson a **Térkép megtekintése** menüpontra a banki kivonat dokumentumán.</span><span class="sxs-lookup"><span data-stu-id="faf78-117">Click **View map** on the bank statement document.</span></span>
            -   <span data-ttu-id="faf78-118">Kattintson az **Átalakítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="faf78-118">Click **Transformations**</span></span>
            -   <span data-ttu-id="faf78-119">Törölje a BankReconiliation-to-Composite.xslt fájlt.</span><span class="sxs-lookup"><span data-stu-id="faf78-119">Delete the BankReconiliation-to-Composite.xslt file.</span></span>
            -   <span data-ttu-id="faf78-120">Adja hozzá a BankReconiliation-to-Composite.xslt új verzióját.</span><span class="sxs-lookup"><span data-stu-id="faf78-120">Add the new version of BankReconiliation-to-Composite.xsl.</span></span>

        2.  <span data-ttu-id="faf78-121">Jelenítse meg a **Sorszámot** a **Forrásadatok** elrendezésben.</span><span class="sxs-lookup"><span data-stu-id="faf78-121">Expose the **Sequence Number** on **Source Data** layout.</span></span>
            1.  <span data-ttu-id="faf78-122">Forrásoldali adatformátum = XML-elem.</span><span class="sxs-lookup"><span data-stu-id="faf78-122">Source data format = XML-Element.</span></span>
            2.  <span data-ttu-id="faf78-123">Entitás neve = banki kivonat</span><span class="sxs-lookup"><span data-stu-id="faf78-123">Entity name = Bank statements.</span></span>
            3.  <span data-ttu-id="faf78-124">Feltöltési adatfájl = SampleBankCompositeEntity.xml új verziója.</span><span class="sxs-lookup"><span data-stu-id="faf78-124">Upload data file = new version SampleBankCompositeEntity.xml.</span></span>
            4.  <span data-ttu-id="faf78-125">Kattintson az **Igen** gombra a meglévő fájl felülírásához.</span><span class="sxs-lookup"><span data-stu-id="faf78-125">Click **Yes** to overwrite the existing file.</span></span>
            5.  <span data-ttu-id="faf78-126">Kattintson az **Igen** egy új hozzárendelés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="faf78-126">Click **Yes** to generate a new mapping.</span></span>
            6.  <span data-ttu-id="faf78-127">Győződjön meg róla, hogy a S**orszám** hozzárendelése kész van-e.</span><span class="sxs-lookup"><span data-stu-id="faf78-127">Verify that S**equenceNumber** is mapped.</span></span>
                -   <span data-ttu-id="faf78-128">Kattintson a **Térkép megtekintése** menüpontra az entitás kivonatán.</span><span class="sxs-lookup"><span data-stu-id="faf78-128">Click **View Map** on the statement entity.</span></span>
                -   <span data-ttu-id="faf78-129">Ellenőrizze, hogy a **sorszám** hozzá van-e rendelve a forrásból az előkészítéshez.</span><span class="sxs-lookup"><span data-stu-id="faf78-129">Verify that **SequenceNumber** is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="faf78-130">Importálja az új kivonatot.</span><span class="sxs-lookup"><span data-stu-id="faf78-130">Import the new statement.</span></span>





