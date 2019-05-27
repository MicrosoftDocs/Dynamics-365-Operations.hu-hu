---
title: Elektronikus jelentés formátumainak módosítása Microsoft Excel sablonok újbóli alkalmazásával
description: Ez a témakör azt ismerteti, hogyan módosíthatja az elektronikus jelentési (ER) formátumot, amely az üzleti dokumentumok létrehozásához használatos, egy módosított Excel-sablon újbóli alkalmazásával.
author: NickSelin
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8707f7b184bb66648edd0e48672c5514a0a5caf1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545007"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a><span data-ttu-id="2fb50-103">Elektronikus jelentés formátumainak módosítása Microsoft Excel sablonok újbóli alkalmazásával</span><span class="sxs-lookup"><span data-stu-id="2fb50-103">Modify Electronic reporting formats by reapplying Excel templates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2fb50-104">Az elektronikus jelentési (ER) eszköz üzleti dokumentumok elektronikus formában való létrehozásához használatos.</span><span class="sxs-lookup"><span data-stu-id="2fb50-104">The Electronic reporting (ER) tool is used to generate business documents in an electronic format.</span></span> <span data-ttu-id="2fb50-105">Üzleti dokumentum létrehozásához ER-formátumot kell létrehozni, és ezután az ER-tervező segítségével meg kell határozni az üzleti dokumentum elrendezését, és megadni az adatokat, amelyeknek szerepelniük kell benne.</span><span class="sxs-lookup"><span data-stu-id="2fb50-105">To generate a business document, you must create an ER format, and then use the ER designer to define the layout of the business document and specify the data that should be included in it.</span></span> <span data-ttu-id="2fb50-106">Ezt követően futtathatja az üzleti dokumentum létrehozásához az ER-formátumot.</span><span class="sxs-lookup"><span data-stu-id="2fb50-106">You can then run the ER format to generate the business document.</span></span>

<span data-ttu-id="2fb50-107">Az ER-eszközzel üzleti dokumentumokat lehet létrehozni Microsoft Excel-fájlok formájában.</span><span class="sxs-lookup"><span data-stu-id="2fb50-107">The ER tool can be used to generate business documents as Microsoft Excel files.</span></span> <span data-ttu-id="2fb50-108">Egy Excel-dokumentumot lehet sablonként használni a dokumentumokhoz.</span><span class="sxs-lookup"><span data-stu-id="2fb50-108">You can use an Excel document as a template for these documents.</span></span> <span data-ttu-id="2fb50-109">Dokumentumelrendezés definiálásához az ER-tervezőben importálhatja a sablonként használni kívánt az Excel-dokumentum tartalmát a meghatározott ER-formátumba.</span><span class="sxs-lookup"><span data-stu-id="2fb50-109">To define the document layout in the ER designer, you can import the contents of the Excel document that you want to use as a template into the defined ER format.</span></span> <span data-ttu-id="2fb50-110">A folyamat további részleteivel kapcsolatban, valamint gyakorlásként hajtsa végre az **ER Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése** című feladat-útmutatót (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része).</span><span class="sxs-lookup"><span data-stu-id="2fb50-110">For more details, and to practice this scenario, play the task guide **ER Design a configuration for generating reports in OPENXML format** (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span>

<span data-ttu-id="2fb50-111">Ha módosítja az Excel-dokumentumot, amely üzletidokumentum-sablonként szolgál, az új ER-funkció lehetővé teszi a frissített sablon újbóli alkalmazását az ER-formátumra.</span><span class="sxs-lookup"><span data-stu-id="2fb50-111">If you edit the Excel document that is used as a template for a business document, new ER functionality lets you reapply the updated template to the ER format.</span></span> <span data-ttu-id="2fb50-112">Az ER-formátum ekkor frissül, hogy megfeleljen a frissített sablonnak.</span><span class="sxs-lookup"><span data-stu-id="2fb50-112">The ER format is then updated so that it adheres to the updated template.</span></span> <span data-ttu-id="2fb50-113">A funkcióval kapcsolatos további részletekért hajtsa végre az **Elektronikus jelentés formátumának módosítása Microsoft Excel sablon újbóli alkalmazásával** című feladat-útmutatót (a 7.5.5.3 Módosított informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10683)).</span><span class="sxs-lookup"><span data-stu-id="2fb50-113">For more details about this functionality, play the task guide **ER Modify a format by reapplying an Excel template** (part of the 7.5.5.3 Acquire/Develop IT service/solution components (10683) business process).</span></span> <span data-ttu-id="2fb50-114">A frissített sablon importálása feladatútmutató-lépésben használja a kifizetési jelentés Excel fájl módosított sablonját (SampleVendPaymWsReport2) sablonként.</span><span class="sxs-lookup"><span data-stu-id="2fb50-114">In the task guide step where you import an updated template, use the modified template of the Payment Report Excel file, SampleVendPaymWsReport2, as a template.</span></span>
