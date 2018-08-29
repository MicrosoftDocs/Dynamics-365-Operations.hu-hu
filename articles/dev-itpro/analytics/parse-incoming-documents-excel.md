---
title: "Bejövő dokumentumok elemzése Excel-formátumban"
description: "Ez a témakör a bejövő Microsoft Excel-fájlok tartalmának elemzéséhez használt elektronikus jelentési (ER) formátumok tervezésével kapcsolatos információkat tartalmaz."
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: 490a9325be25908564a40478a1ee29feea67fc02
ms.contentlocale: hu-hu
ms.lasthandoff: 08/13/2018

---

# <a name="parse-incoming-documents-in-excel-format"></a><span data-ttu-id="1221d-103">Bejövő dokumentumok elemzése Excel-formátumban</span><span class="sxs-lookup"><span data-stu-id="1221d-103">Parse incoming documents in Excel format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="1221d-104">Lehetőség van Elektronikus jelentési (ER) formátumok kialakítására olyan bejövő Microsoft Excel-fájlok elemzésére, amelyek az adatokat Microsoft Excel-munkafüzetekben jelenítik meg (XLSX formátumú fájlok).</span><span class="sxs-lookup"><span data-stu-id="1221d-104">You can design Electronic reporting (ER) formats to parse incoming Microsoft Excel files that represent data in Microsoft Excel workbooks (files in XLSX format).</span></span> <span data-ttu-id="1221d-105">Az ezekből a fájljokból származó tartalmakat felhasználhatja az alkalmazásadatok frissítésére.</span><span class="sxs-lookup"><span data-stu-id="1221d-105">You can then use the content from these files to update application data.</span></span> <span data-ttu-id="1221d-106">Ez hasznos a következő esetekben:</span><span class="sxs-lookup"><span data-stu-id="1221d-106">This is useful if you:</span></span>

- <span data-ttu-id="1221d-107">Egy új modell és formátum kialakítása, amelyet futásidőben akar tesztelni.</span><span class="sxs-lookup"><span data-stu-id="1221d-107">Design a new model and format and want to test them at run-time.</span></span> <span data-ttu-id="1221d-108">Ebben az esetben Excel szimulálni fogja az aktuális alkalmazás adatait.</span><span class="sxs-lookup"><span data-stu-id="1221d-108">In this case, Excel will simulate the actual application data.</span></span>
- <span data-ttu-id="1221d-109">Az Excelben való alkalmazáson túlmenően is kezelhet adatokat, és meghatározott jelentés benyújtásához importálhatja ezeket az adatokat.</span><span class="sxs-lookup"><span data-stu-id="1221d-109">Manage data beyond your application in Excel and want to import this data to submit a specific report.</span></span>

<span data-ttu-id="1221d-110">További tudnivalók ezzel a funkcióval kapcsolatban: játssza le a következő feladat útmutatókat **ER adatimportálás Microsoft Excel-fájlból (1. rész: tervezési formátum)** és **ER adatimportálás Microsoft Excel-fájlból (2. rész: adatok importálása)** (megtalálható itt: 7.5.4.3 informatikai szolgáltatási/megoldási összetevők megszerzése/fejlesztése, (10677) üzleti folyamat).</span><span class="sxs-lookup"><span data-stu-id="1221d-110">To learn more about this feature, play the task guides **ER Import data from a Microsoft Excel file (Part 1: Design format)** and **ER Import data from a Microsoft Excel file (Part 2: Import data)** (parts of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span> <span data-ttu-id="1221d-111">Ezek a feladat útmutatók végigvezetik azon, hogy kell a bejövő Excel-fájlt elemezni, amikor az ER formátumot használja adatok importálására a bejövő dokumentumból, illetve ezekkel frissíti az alkalmazásadatokat.</span><span class="sxs-lookup"><span data-stu-id="1221d-111">These task guides walk through how the incoming Excel file can be parsed by using the ER format to import information from incoming documents and update application data.</span></span> <span data-ttu-id="1221d-112">A feladat útmutatók fájljait letöltheti itt: [Microsoft letöltőközpont](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="1221d-112">You can download the task guide files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

<span data-ttu-id="1221d-113">A fent említett feladat útmutatók befejezéséhez töltse le a következő fájlokat.</span><span class="sxs-lookup"><span data-stu-id="1221d-113">Download the following files to complete the task guides mentioned above.</span></span>

| <span data-ttu-id="1221d-114">Tartalom leírása</span><span class="sxs-lookup"><span data-stu-id="1221d-114">Content description</span></span>                         | <span data-ttu-id="1221d-115">Fájl</span><span class="sxs-lookup"><span data-stu-id="1221d-115">File</span></span>                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="1221d-116">Bejövő fájl XLSX formátumban - sablon</span><span class="sxs-lookup"><span data-stu-id="1221d-116">Incoming file in .XLSX format - template</span></span>    | [<span data-ttu-id="1221d-117">1099import-template.xlsx</span><span class="sxs-lookup"><span data-stu-id="1221d-117">1099import-template.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |
| <span data-ttu-id="1221d-118">Bejövő fájl XLSX formátumban - mintaadatok</span><span class="sxs-lookup"><span data-stu-id="1221d-118">Incoming file in .XLSX format - sample data</span></span> | [<span data-ttu-id="1221d-119">1099import-data.xlsx</span><span class="sxs-lookup"><span data-stu-id="1221d-119">1099import-data.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)     |

<span data-ttu-id="1221d-120">Ha még nem játszotta le a következő feladat útmutatót [ER létrehozása - szükséges konfigurációk a külső fájlból történő adatimportáláshoz](./tasks/er-required-configurations-import-data.md) a jelenlegi Dynamics 365 for Finance and Operation alkalmazásban, töltse le a következő fájlt.</span><span class="sxs-lookup"><span data-stu-id="1221d-120">If you have not yet played the following task guide, [ER Create required configurations to import data from an external file](./tasks/er-required-configurations-import-data.md) in the current Dynamics 365 for Finance and Operation application, download the following file.</span></span>

| <span data-ttu-id="1221d-121">Tartalom leírása</span><span class="sxs-lookup"><span data-stu-id="1221d-121">Content description</span></span>    | <span data-ttu-id="1221d-122">Fájl</span><span class="sxs-lookup"><span data-stu-id="1221d-122">File</span></span>                                                            |
|------------------------|-----------------------------------------------------------------|
| <span data-ttu-id="1221d-123">ER modell konfigurációja</span><span class="sxs-lookup"><span data-stu-id="1221d-123">ER model configuration</span></span> | [<span data-ttu-id="1221d-124">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="1221d-124">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |

