---
title: "Adatok importálása több munkalapot tartalmazó Excel adatentitás-sablonokból"
description: "Ez a témakör leírja, hogyan importálhatók az adatok Excel adatentitás-sablonokkal a Microsoft Dynamics 365 Finance and Operations megoldásba."
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 5bc021ce9f0835f2eda310ef7818c9bc9be749f2
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="import-data-from-excel-data-entity-templates-that-have-multiple-worksheets"></a><span data-ttu-id="d9f8b-103">Adatok importálása több munkalapot tartalmazó Excel adatentitás-sablonokból</span><span class="sxs-lookup"><span data-stu-id="d9f8b-103">Import data from Excel data entity templates that have multiple worksheets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9f8b-104">Az adatkezelés a Microsoft Dynamics 365 for Finance and Operations megoldásban támogatja a Microsoft Excel-alapú sablonokat az adatentitások esetében.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-104">Data management in Microsoft Dynamics 365 for Finance and Operations supports Microsoft Excel-based templates for data entities.</span></span> <span data-ttu-id="d9f8b-105">Ezek a sablonok egy vagy több munkalapot is tartalmazhatnak.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-105">These templates can contain one or more worksheets.</span></span> <span data-ttu-id="d9f8b-106">A több munkalapot tartalmazó sablonok gyakran használatosak olyan esetekben, amikor célszerű egyetlen fájlban kezelni az adatokat, és több entitásba importálni őket.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-106">Templates with multiple worksheets are often used when it is convenient to manage data in a single file and import it to multiple data entities.</span></span> <span data-ttu-id="d9f8b-107">Jó példát jelentenek erre a telephelyek és a raktárak.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-107">An example would be sites and warehouses.</span></span>

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a><span data-ttu-id="d9f8b-108">Fájl feltöltése egyszer, és a hozzárendelése az összes entitáshoz</span><span class="sxs-lookup"><span data-stu-id="d9f8b-108">Upload a file once and map it to all entities</span></span>
<span data-ttu-id="d9f8b-109">Lássunk egy példát, amelyben egy Excel-fájl szerepel két munkalappal, amelyek a **Telephelyek** és **Raktárak** nevet viselik.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-109">Let’s take an example where there is one Excel file with worksheets called **Sites** and **Warehouses**.</span></span> <span data-ttu-id="d9f8b-110">Az adatimportálási projekt beállításához beállítjuk az első adatentitást, a **Telephelyeket**, majd feltöltjük a fájlt.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-110">To set up the data import project, you would add the first data entity, **Sites** and then upload the file.</span></span> <span data-ttu-id="d9f8b-111">A **Telephelyek** kiválasztható az ehhez az entitáshoz használandó munkalapként.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-111">You will be able to select **Sites** as the worksheet to be used for this entity.</span></span>

<span data-ttu-id="d9f8b-112">Ha a második entitást, a **Raktárakat** a **Fájl hozzáadása** képernyő elhagyása nélkül adjuk hozzá, a munkalap-keresés lehetővé teszi a **Raktárak** munkalap hozzáadását anélkül, hogy újra fel kellene tölteni a fájlt.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-112">If you add the second entity **Warehouses** without leaving the **Add file** form, the worksheet lookup will let you select the **Warehouses** worksheet without having to upload the file again.</span></span> <span data-ttu-id="d9f8b-113">Csak akkor kellene új fájlt feltölteni, ha a **Raktárak** adatai egy másik fájlban lennének.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-113">The only reason to upload a new file would be if the **Warehouses** data was in a different file.</span></span>

![Több munkalap](./media/AddFileMultipleWorkSheets.png) 

## <a name="fix-worksheet-to-entity-mapping"></a><span data-ttu-id="d9f8b-115">A munkalap és az entitás közötti megfeleltetés kijavítása</span><span class="sxs-lookup"><span data-stu-id="d9f8b-115">Fix worksheet to entity mapping</span></span>

<span data-ttu-id="d9f8b-116">A munkalap és az adatentitás közötti megfeleltetés az importálási feladatban a rácsban javítható ki.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-116">The mapping of the worksheet to a data entity in the import job can be fixed from the grid.</span></span> <span data-ttu-id="d9f8b-117">A **Munkalap** rácsbeli oszlop mutatja a megfeleltetett fájlból származó a munkalapokat.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-117">The **Worksheet** column in the grid shows the worksheets from the file that was mapped.</span></span> <span data-ttu-id="d9f8b-118">A legördülő menüből választhat egy másik munkalapot.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-118">You can choose a different worksheet from the drop-down menu.</span></span> <span data-ttu-id="d9f8b-119">Ha a kiválasztott munkalap már hozzá van rendelve egy entitáshoz az adatprojektben, a rendszer megkérdezi, hogy jóváhagyja-e a módosítást.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-119">If the chosen worksheet is already mapped to an entity in the data project, the system asks you to confirm the change.</span></span> <span data-ttu-id="d9f8b-120">Azt ajánljuk, hogy a rácsban javítsa ki az összes megfeleltetést.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-120">We recommend that you fix all mappings in the grid.</span></span>

![Munkalap-megfeleltetés frissítése](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a><span data-ttu-id="d9f8b-122">Ismételt hozzárendelés egy új fájlhoz</span><span class="sxs-lookup"><span data-stu-id="d9f8b-122">Re-map to a new file</span></span>

<span data-ttu-id="d9f8b-123">Azokban az esetekben, amikor ugyanannak a fájlnak egy új verzióját, vagy egy teljesen új fájlt kell feltölteni a meglévő entitásokhoz egy adatprojektben, a **Fájl hozzáadása** lehetőséget kell használni, és az entitásokat újra hozzá kell adni úgy, mintha első alkalommal adnák hozzá őket.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-123">In cases where a new version of the same file or a completely new file must be uploaded for existing entities in a data project, you must use the **Add file** experience, and add the entities again as if they were being added for the first time.</span></span> <span data-ttu-id="d9f8b-124">A rendszer megerősíti, hogy felül kívánja-e írni a meglévő entitásokat a folytatás előtt az adatprojektben.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-124">The system will confirm that you want to overwrite the existing entities in the data project before proceeding.</span></span> <span data-ttu-id="d9f8b-125">Azok az entitások, amelyeket nem adtak hozzá újra (vagy nem írtak felül) továbbra is megtartják a korábbi hozzárendeléseket a korábbi fájlból.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-125">Entities that are not added again (or overwritten) will continue to hold the previous mappings from the previous file.</span></span>

## <a name="upload-a-file-using-run-project"></a><span data-ttu-id="d9f8b-126">Fájl feltöltése a Projekt futtatása lehetőséggel</span><span class="sxs-lookup"><span data-stu-id="d9f8b-126">Upload a file using Run project</span></span>

<span data-ttu-id="d9f8b-127">Egy importálási projekt végrehajtásához feltölthet egy Excel-fájlt a **Projekt futtatása** funkció használatával.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-127">You can upload an Excel file while using the **Run project** option to execute an import project.</span></span> <span data-ttu-id="d9f8b-128">Ügyelnie kell arra, hogy csak olyan fájlokat töltsön fel, amelyek ugyanazokat a munkalapokat tartalmazzák, mint a meglévő leképezések az adatentitásokhoz az adatprojektben.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-128">You must be careful to upload only files that have the same worksheets as the existing mappings on the data entities in the data project.</span></span> <span data-ttu-id="d9f8b-129">Ha egy munkalap nem található az újonnan feltöltött fájlban, a rendszer hibaüzenetet jelenít meg, és az importálás leáll.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-129">If a worksheet is not found in the newly uploaded file, the system displays an error and will stop the import.</span></span> <span data-ttu-id="d9f8b-130">Ha egy entitás esetében módosítani kell a hozzárendelést a munkalaphoz, akkor az adatprojektben a hozzárendeléseket először frissíteni kell az adatprojektből, mielőtt a fájlt használná **Projekt futtatása** funkcióban.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-130">If the mapping to the worksheet must be changed for an entity, then the mappings in the data project must be first updated from within the data project before using the file in the **Run project** experience.</span></span>


