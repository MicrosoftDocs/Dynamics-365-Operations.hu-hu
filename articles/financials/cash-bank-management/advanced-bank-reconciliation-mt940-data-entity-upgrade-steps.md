---
title: Speciális banki egyeztetés MT940 importálása - összetett adatentitás frissítése
description: Egy sorszámot kell hozzáadni a banki kivonat importálási entitásához az MT940 formátum támogatásához.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6c0eeb59726422177ed1122767b9d3142a1311a2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "343788"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a><span data-ttu-id="7c3fa-103">Speciális banki egyeztetés MT940 importálása - összetett adatentitás frissítése</span><span class="sxs-lookup"><span data-stu-id="7c3fa-103">Advanced bank reconciliation MT940 Import – Composite data entity upgrade</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7c3fa-104">Egy sorszámot kell hozzáadni a banki kivonat importálási entitásához az MT940 formátum támogatásához.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-104">A sequence number needs to be added to the bank statement import entity to support the MT940 format.</span></span> 

<span data-ttu-id="7c3fa-105">A következő lépések segítségével adja hozzá a banki kivonat importálási entitását az MT940 formátum támogatásához.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-105">Use the following steps to add the bank statement import entity to support the MT940 format.</span></span>

1.  <span data-ttu-id="7c3fa-106">Állítsa össze és szinkronizálja a következőket:</span><span class="sxs-lookup"><span data-stu-id="7c3fa-106">Compile and synchronize the following:</span></span>
    -   <span data-ttu-id="7c3fa-107">Összetett entitás\\BankStatementImportEntity</span><span class="sxs-lookup"><span data-stu-id="7c3fa-107">Composite Entity\\BankStatementImportEntity</span></span>
    -   <span data-ttu-id="7c3fa-108">Entitás\\BankStatementBalanceEntity</span><span class="sxs-lookup"><span data-stu-id="7c3fa-108">Entity\\BankStatementBalanceEntity</span></span>
    -   <span data-ttu-id="7c3fa-109">Entitás\\BankStatementDocumentEntity</span><span class="sxs-lookup"><span data-stu-id="7c3fa-109">Entity\\BankStatementDocumentEntity</span></span>
    -   <span data-ttu-id="7c3fa-110">Entitás\\BankStatementEntity</span><span class="sxs-lookup"><span data-stu-id="7c3fa-110">Entity\\BankStatementEntity</span></span>
    -   <span data-ttu-id="7c3fa-111">Entitás\\BankStatementLineEntity</span><span class="sxs-lookup"><span data-stu-id="7c3fa-111">Entity\\BankStatementLineEntity</span></span>
    -   <span data-ttu-id="7c3fa-112">Táblázatok\\BankStatementStaging</span><span class="sxs-lookup"><span data-stu-id="7c3fa-112">Tables\\BankStatementStaging</span></span>

2.  <span data-ttu-id="7c3fa-113">Adatok kezelése\\adatprojektek.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-113">Data management\\data projects.</span></span>
    1.  <span data-ttu-id="7c3fa-114">MT940 importálás projekt(ek) betöltése</span><span class="sxs-lookup"><span data-stu-id="7c3fa-114">Load MT940 import project(s)</span></span>
        1.  <span data-ttu-id="7c3fa-115">XLST megváltoztatása.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-115">Change XSLT.</span></span>
            -   <span data-ttu-id="7c3fa-116">Kattintson a **Térkép megtekintése** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-116">Click **View map**.</span></span>
            -   <span data-ttu-id="7c3fa-117">Kattintson a **Térkép megtekintése** menüpontra a banki kivonat dokumentumán.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-117">Click **View map** on the bank statement document.</span></span>
            -   <span data-ttu-id="7c3fa-118">Kattintson az **Átalakítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-118">Click **Transformations**</span></span>
            -   <span data-ttu-id="7c3fa-119">Törölje a BankReconiliation-to-Composite.xslt fájlt.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-119">Delete the BankReconiliation-to-Composite.xslt file.</span></span>
            -   <span data-ttu-id="7c3fa-120">Adja hozzá a BankReconiliation-to-Composite.xslt új verzióját.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-120">Add the new version of BankReconiliation-to-Composite.xsl.</span></span>

        2.  <span data-ttu-id="7c3fa-121">Jelenítse meg a **Sorszámot** a **Forrásadatok** elrendezésben.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-121">Expose the **Sequence Number** on **Source Data** layout.</span></span>
            1.  <span data-ttu-id="7c3fa-122">Forrásoldali adatformátum = XML-elem.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-122">Source data format = XML-Element.</span></span>
            2.  <span data-ttu-id="7c3fa-123">Entitás neve = banki kivonat</span><span class="sxs-lookup"><span data-stu-id="7c3fa-123">Entity name = Bank statements.</span></span>
            3.  <span data-ttu-id="7c3fa-124">Feltöltési adatfájl = SampleBankCompositeEntity.xml új verziója.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-124">Upload data file = new version SampleBankCompositeEntity.xml.</span></span>
            4.  <span data-ttu-id="7c3fa-125">Kattintson az **Igen** gombra a meglévő fájl felülírásához.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-125">Click **Yes** to overwrite the existing file.</span></span>
            5.  <span data-ttu-id="7c3fa-126">Kattintson az **Igen** egy új hozzárendelés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-126">Click **Yes** to generate a new mapping.</span></span>
            6.  <span data-ttu-id="7c3fa-127">Győződjön meg róla, hogy a S**orszám** hozzárendelése kész van-e.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-127">Verify that S**equenceNumber** is mapped.</span></span>
                -   <span data-ttu-id="7c3fa-128">Kattintson a **Térkép megtekintése** menüpontra az entitás kivonatán.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-128">Click **View Map** on the statement entity.</span></span>
                -   <span data-ttu-id="7c3fa-129">Ellenőrizze, hogy a **sorszám** hozzá van-e rendelve a forrásból az előkészítéshez.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-129">Verify that **SequenceNumber** is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="7c3fa-130">Importálja az új kivonatot.</span><span class="sxs-lookup"><span data-stu-id="7c3fa-130">Import the new statement.</span></span>




