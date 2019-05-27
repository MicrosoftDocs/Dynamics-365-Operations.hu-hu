---
title: Hitelkártya-tranzakciók importálása és karbantartása
description: Ez a témakör bemutatja, hogyan importálhatja és tarthatja karban a költséggel kapcsolatos hitelkártya-tranzakciókat. Ezeket a tranzakciókat be lehet állítani úgy, hogy importálásuk ütemezés alapján automatikusan ismétlődjön, vagy importálhatók manuálisan, szükség szerint.
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPbsMainDataLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 9674cf495b7fdd40d8672580b9d10e9ebe626bb0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565113"
---
# <a name="import-and-maintain-credit-card-transactions"></a><span data-ttu-id="6c8a7-104">Hitelkártya-tranzakciók importálása és karbantartása</span><span class="sxs-lookup"><span data-stu-id="6c8a7-104">Import and maintain credit card transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6c8a7-105">A költségjellegű hitelkártya-tranzakciókat be lehet úgy állítani, hogy importálásuk ismétlődő ütemezés szerint automatikusan megtörténjen.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-105">Expense-related credit card transactions can be set up so that they are automatically imported on a recurring schedule.</span></span> <span data-ttu-id="6c8a7-106">Másik lehetőségként a tranzakciók manuálisan is importálhatók szükség szerint.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-106">Alternatively, the transactions can be manually imported as they are required.</span></span> <span data-ttu-id="6c8a7-107">A hitelkártya-tranzakciók importálása a Hitelkártya-tranzakciók adatentitáson keresztül történik.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-107">The credit card transactions are imported through the Credit card transactions data entity.</span></span>

<span data-ttu-id="6c8a7-108">Az adatentitásokkal kapcsolatos további tudnivalókért lásd: [Adatentitások](../../dev-itpro/data-entities/data-entities.md).</span><span class="sxs-lookup"><span data-stu-id="6c8a7-108">For more information about data entities, see [Data entities](../../dev-itpro/data-entities/data-entities.md).</span></span>

## <a name="import-credit-card-transactions"></a><span data-ttu-id="6c8a7-109">Hitelkártya-tranzakciók importálása</span><span class="sxs-lookup"><span data-stu-id="6c8a7-109">Import credit card transactions</span></span>

1. <span data-ttu-id="6c8a7-110">A **Hitelkártyás tranzakciók** oldalon válassza a **Tranzakciók importálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-110">On the **Credit card transactions** page, select **Import transactions**.</span></span> <span data-ttu-id="6c8a7-111">Az adatkezelés első megnyitásakor a folytatás előtt a rendszernek frissítenie kell az entitások listáját.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-111">If you’re opening data management for the first time, the system must update the list of data entities before you can continue.</span></span>
2. <span data-ttu-id="6c8a7-112">A **Név** mezőben adja meg az importálási feladat egyedi leírását.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-112">In the **Name** field, enter a unique description of the import job.</span></span>
3. <span data-ttu-id="6c8a7-113">A **Forrásadatok formátuma** mezőben válassza ki az importálandó hitelkártya-tranzakciókat tartalmazó fájl formátumát.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-113">In the **Source data format** field, select the format of the file that contains the credit card transactions to import.</span></span>
4. <span data-ttu-id="6c8a7-114">Válassza a **Feltöltés** elemet, majd keresse meg és válassza ki az importálandó fájlt.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-114">Select **Upload**, and then find and select the file to import.</span></span>
5. <span data-ttu-id="6c8a7-115">A fájl feltöltését követően ellenőrizze a hitelkártya-tranzakciók fájljának hozzárendelését és a Hitelkártyás tranzakciók adatentitás oszlopait; ehhez válassza a csempén látható **Leképezés megtekintése** elemet.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-115">After the file has been uploaded, validate the mapping of the credit card transaction file and the columns of the Credit card transactions data entity by selecting the **View map** link on the tile.</span></span> <span data-ttu-id="6c8a7-116">Ha leképezési hibák vannak jelen, vagy ha módosítania kell a leképezést, a leképezés módosításait a **Megfeleltetés megjelenítése** lapon vagy a **Hozzárendelés adatai** lapon végezheti el.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-116">If there are mapping errors, or if you must change the mapping, make the mapping changes from either the **Mapping visualization** tab or the **Mapping details** tab.</span></span>
6. <span data-ttu-id="6c8a7-117">A hitelkártya-tranzakciók automatizálásához jelölje be az **Ismétlődő adatkezelési feladat létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-117">To automate the credit card transactions, select **Create recurring data job**.</span></span> <span data-ttu-id="6c8a7-118">Ezután beállíthatja az ismétlődést, amely meghatározza, hogy milyen gyakran kell importálni a hitelkártya-tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-118">You can then set the recurrence that defines how often credit card transactions should be imported.</span></span> <span data-ttu-id="6c8a7-119">Amikor elkészült, válassza az **OK** elemet.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-119">When you’ve finished, select **OK**.</span></span>
7. <span data-ttu-id="6c8a7-120">A kiválasztott fájl azonnali importálásához válassza az **Importálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-120">To import the selected file now, select **Import**.</span></span>
8. <span data-ttu-id="6c8a7-121">Ha az importálás során hibák lépnek fel, megtekintheti a végrehajtási naplót vagy az előkészítési adatokat, és megkeresheti a hibákat, amelyeket ki kell javítani a sikeres importálás biztosítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-121">If errors occur during the import, you can view the execution log or staging data to see the errors that you must fix to help guarantee a successful import.</span></span>

> [!NOTE]
> <span data-ttu-id="6c8a7-122">Ha egynél több fájlformátumot kell importálni, külön importálási feladatot kell létrehoznia minden formátumtípushoz.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-122">If you must import more than one file format, you must create separate import jobs for each format type.</span></span>

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a><span data-ttu-id="6c8a7-123">Kilépett alkalmazottak hitelkártyás tranzakcióinak ismételt hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="6c8a7-123">Reassign the credit card transactions for terminated employees</span></span>

<span data-ttu-id="6c8a7-124">Alkalmazotti rekord lezárását követően az alkalmazott Active Directory Domain Services (AD DS) fiókja letiltásra kerül.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-124">After an employee record is terminated, the employee’s Active Directory Domain Services (AD DS) account is disabled.</span></span> <span data-ttu-id="6c8a7-125">Lehet viszont, hogy még mindig vannak aktív hitelkártya-tranzakciók, amelyeket kiadásként könyvelni kell és vissza kell téríteni.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-125">However, there might be active credit card transactions that must still be expensed and reimbursed.</span></span> <span data-ttu-id="6c8a7-126">A **Hitelkártyás tranzakciók** oldalon minden olyan alkalmazotti hitelkártya-tranzakciót ismételten hozzárendelhet, ahol a társított alkalmazott kilépett.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-126">From the **Credit card transactions** page, you can reassign the employee for any credit card transaction where the associated employee has been terminated.</span></span>

<span data-ttu-id="6c8a7-127">Válasszon ki egy vagy több hitelkártyás tranzakciót, majd ezután válassza a **Tranzakciók ismételt hozzárendelése** elemet.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-127">Select one or more credit card transactions, and then select **Reassign transactions**.</span></span> <span data-ttu-id="6c8a7-128">Ezután kiválaszthat egy másik alkalmazottat, akihez hozzárendelheti a hitelkártyás tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-128">You can then select another employee to assign the credit card transactions to.</span></span> <span data-ttu-id="6c8a7-129">A hitelkártyás tranzakciók ismételt hozzárendelése után a tranzakciók kiválaszthatók egy költségjelentéshez, és a költségjelentések szokásos visszaigénylési folyamatával fizethető ki a visszatérítés.</span><span class="sxs-lookup"><span data-stu-id="6c8a7-129">After the credit card transactions have been reassigned, they can be selected for an expense report and paid through the usual process for expense report reimbursement.</span></span>
