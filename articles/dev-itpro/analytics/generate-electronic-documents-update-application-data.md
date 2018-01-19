---
title: "Elektronikus dokumentumok és alkalmazásadatok frissítése az Elektronikus jelentéskészítő eszköz használatával"
description: "Lehetőség van elektronikus jelentési (ER) formátumok tervezésére, amelyek kimenő elektronikus dokumentumok létrehozására használhatók a Finance and Operations alkalmazásban. Olyan ER-formátumokat is készíthet, amelyek a bejövő elektronikus dokumentumokat elemzik, és ezeknek a dokumentumoknak a tartalmát használják az alkalmazásadatok frissítésére."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 34654c458ce74bf2ee6c2d2bac655d6c399ca393
ms.contentlocale: hu-hu
ms.lasthandoff: 01/19/2018

---

# <a name="generate-electronic-documents-and-update-application-data-using-the-electronic-reporting-tool"></a><span data-ttu-id="88883-104">Elektronikus dokumentumok és alkalmazásadatok frissítése az Elektronikus jelentéskészítő eszköz használatával</span><span class="sxs-lookup"><span data-stu-id="88883-104">Generate electronic documents and update application data using the Electronic reporting tool</span></span>

<span data-ttu-id="88883-105">Lehetőség van elektronikus jelentési (ER) formátumok tervezésére, amelyek kimenő elektronikus dokumentumok létrehozására használhatók a Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="88883-105">You can design Electronic reporting (ER) formats that can be used in the Finance and Operations application to generate outgoing electronic documents.</span></span> <span data-ttu-id="88883-106">Olyan ER-formátumokat is készíthet, amelyek a bejövő elektronikus dokumentumokat elemzik, és ezeknek a dokumentumoknak a tartalmát használják az alkalmazásadatok frissítésére.</span><span class="sxs-lookup"><span data-stu-id="88883-106">You can also design ER formats that parse incoming electronic documents and use the content in those documents to update application data.</span></span> 

<span data-ttu-id="88883-107">Ezzel a funkcióval egyetlen ER-formátum használható a kimenő elektronikus dokumentumok létrehozására, majd az alkalmazásadatok frissítésére.</span><span class="sxs-lookup"><span data-stu-id="88883-107">With this functionality, a single ER format can be used to generate outgoing electronic documents and then update the application data.</span></span> <span data-ttu-id="88883-108">Ez a funkció a következő forgatókönyvek esetében használható:</span><span class="sxs-lookup"><span data-stu-id="88883-108">This feature can be used in the following scenarios:</span></span>

- <span data-ttu-id="88883-109">Az alkalmazásadatoknak a későbbi folyamatokban való ismételt felhasználásának elkerülésére az alkalmazás adatait az elektronikus dokumentumok létrehozása után azonnal megjelölheti.</span><span class="sxs-lookup"><span data-stu-id="88883-109">To prevent repeated usage of application data in subsequent processes you can mark an application’s data immediately after it is used to generate electronic documents.</span></span> <span data-ttu-id="88883-110">A fizetési tranzakciókat például azonnal megjelölheti már feldolgozottként, amint bekerülnek a generált fizetési üzenetbe.</span><span class="sxs-lookup"><span data-stu-id="88883-110">For example, you can mark payment transactions as already processed immediately after they have been included in a generated payment message.</span></span>
- <span data-ttu-id="88883-111">Az ER-logika használatával létrehozott elektronikus dokumentumok feldolgozási részleteinek tárolására.</span><span class="sxs-lookup"><span data-stu-id="88883-111">To store the processing details of electronic documents that have been generated using ER logic.</span></span> <span data-ttu-id="88883-112">Például egy ER-kifejezés használatával létrehozott egyedi fizetésiüzenet-azonosító.</span><span class="sxs-lookup"><span data-stu-id="88883-112">For example, a unique payment message identification that is generated using the ER expression.</span></span> <span data-ttu-id="88883-113">A kifejezés alapját az ER-párbeszédpanelen akkor megadott adatok adják, amikor az ER-formátumot dokumentumok létrehozásához futtatják.</span><span class="sxs-lookup"><span data-stu-id="88883-113">The expression is based on information entered in the ER dialog box when the ER format is run to generate documents.</span></span>

<span data-ttu-id="88883-114">Ezzel a funkcióval kapcsolatos további információért játssza le a Dokumentumok létrehozása alkalmazásadat-frissítéssel ER feladatútmutató-készletet (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része), amelyek bemutatja az Intrastat jelentéskészítés és archiválás részleteit.</span><span class="sxs-lookup"><span data-stu-id="88883-114">To learn more about this feature, play the set of ER Generate documents with application data update Task guides (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process), which walk you through the details of Intrastat reporting and archiving.</span></span> <span data-ttu-id="88883-115">A következő fájlok szükségesek a feladatútmutató egyes lépéseinek végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="88883-115">The following files are required to complete certain steps in these Task guides.</span></span> <span data-ttu-id="88883-116">Töltse le és mentse ezeket a fájlokat a helyi számítógépre.</span><span class="sxs-lookup"><span data-stu-id="88883-116">Download and save these files to your local machine.</span></span>

- [<span data-ttu-id="88883-117">ER adatmodellkonfiguráció: Instrastat (modell)</span><span class="sxs-lookup"><span data-stu-id="88883-117">ER data model configuration: Intrastat (model)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="88883-118">ER modell leképezésének konfigurációja: Intrastat (leképezés)</span><span class="sxs-lookup"><span data-stu-id="88883-118">ER model mapping configuration: Intrastat (mapping)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="88883-119">ER formátumkonfiguráció: Intrastat (formátum)</span><span class="sxs-lookup"><span data-stu-id="88883-119">ER format configuration: Intrastat (format)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)

