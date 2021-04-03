---
title: Banki napló összetett entitásának frissítése
description: A következő lépéseket kell elvégeznie ahhoz, hogy az összetett BankJournalEntity lehetőséghez további BankTransactionType mezőt adjon hozzá.
author: ShylaThompson
manager: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 18137ca8cecc43b4269f14b36df2eb8063192e52
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236347"
---
# <a name="update-the-bank-journal-composite-entity"></a><span data-ttu-id="2e90a-103">Banki napló összetett entitásának frissítése</span><span class="sxs-lookup"><span data-stu-id="2e90a-103">Update the bank journal composite entity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2e90a-104">A következő lépéseket kell elvégeznie ahhoz, hogy az összetett BankJournalEntity lehetőséghez további BankTransactionType mezőt adjon hozzá.</span><span class="sxs-lookup"><span data-stu-id="2e90a-104">The following steps are needed in order to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

<span data-ttu-id="2e90a-105">A következő lépések segítségével az összetett BankJournalEntity lehetőséghez adja hozzá a további BankTransactionType mezőt.</span><span class="sxs-lookup"><span data-stu-id="2e90a-105">Use the following steps to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

1.  <span data-ttu-id="2e90a-106">Állítsa össze és szinkronizálja a következő banki napló összetett entitásokat, entitásokat és előkészítési táblákat:</span><span class="sxs-lookup"><span data-stu-id="2e90a-106">Compile and synchronize the following bank journal composite entities, entities, and staging tables:</span></span>
    -   <span data-ttu-id="2e90a-107">Összetett entitás\\BankJournalEntity</span><span class="sxs-lookup"><span data-stu-id="2e90a-107">Composite Entity\\BankJournalEntity</span></span>
    -   <span data-ttu-id="2e90a-108">Entitás\\BankJournalHeaderEntity</span><span class="sxs-lookup"><span data-stu-id="2e90a-108">Entity\\BankJournalHeaderEntity</span></span>
    -   <span data-ttu-id="2e90a-109">Entitás\\BankJournalLineEntity</span><span class="sxs-lookup"><span data-stu-id="2e90a-109">Entity\\BankJournalLineEntity</span></span>
    -   <span data-ttu-id="2e90a-110">Tábla\\BankJournalHeaderStaging</span><span class="sxs-lookup"><span data-stu-id="2e90a-110">Table\\BankJournalHeaderStaging</span></span>
    -   <span data-ttu-id="2e90a-111">Tábla\\BankJournalLineStaging</span><span class="sxs-lookup"><span data-stu-id="2e90a-111">Table\\BankJournalLineStaging</span></span>

2.  <span data-ttu-id="2e90a-112">Adatok kezelése\\adatprojektek</span><span class="sxs-lookup"><span data-stu-id="2e90a-112">Data management\\data projects</span></span>
    -   <span data-ttu-id="2e90a-113">Jelenítse meg a **Banki tranzakció** típusát a **Forrásadatok** elrendezésben.</span><span class="sxs-lookup"><span data-stu-id="2e90a-113">Expose the **Bank Transaction** type on **Source Data** layout.</span></span>
        -   <span data-ttu-id="2e90a-114">Forrásadatok formátuma = XML-elem</span><span class="sxs-lookup"><span data-stu-id="2e90a-114">Source data format = XML-Element</span></span>
        -   <span data-ttu-id="2e90a-115">Entitás neve = Banki napló</span><span class="sxs-lookup"><span data-stu-id="2e90a-115">Entity name = Bank Journal</span></span>
        -   <span data-ttu-id="2e90a-116">Adatfájl feltöltése = SampleBankJournalCompositeEntity.xml új verziója</span><span class="sxs-lookup"><span data-stu-id="2e90a-116">Upload data file = new version SampleBankJournalCompositeEntity.xml</span></span>
        -   <span data-ttu-id="2e90a-117">Kattintson az **Igen** gombra a meglévő fájl felülírásához.</span><span class="sxs-lookup"><span data-stu-id="2e90a-117">Click **Yes** to overwrite the existing file.</span></span>
        -   <span data-ttu-id="2e90a-118">Kattintson az **Igen** lehetőségre a hozzárendelés elejétől kezdve történő létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="2e90a-118">Click **Yes** to generate mapping from scratch.</span></span>
        -   <span data-ttu-id="2e90a-119">Győződjön meg róla, hogy hozzárendelte a Banki tranzakció típusát.</span><span class="sxs-lookup"><span data-stu-id="2e90a-119">Verify that the Bank Transaction Type is mapped.</span></span>
            -   <span data-ttu-id="2e90a-120">Kattintson a **Leképezés megtekintése** lehetőségre a Sor entitáson.</span><span class="sxs-lookup"><span data-stu-id="2e90a-120">Click **View map** on Line entity.</span></span>
            -   <span data-ttu-id="2e90a-121">Ellenőrizze, hogy a Banki tranzakció típusa hozzá van-e rendelve a forrásból az előkészítéshez.</span><span class="sxs-lookup"><span data-stu-id="2e90a-121">Verify that Bank Transaction type is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="2e90a-122">Importálja az új kivonatot.</span><span class="sxs-lookup"><span data-stu-id="2e90a-122">Import the new statement.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]