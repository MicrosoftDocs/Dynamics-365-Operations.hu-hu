---
title: Elektronikus dokumentumok létrehozása létrehozása és alkalmazásadatok frissítése ER használatával.
description: Lehetőség van elektronikus jelentési (ER) formátumok tervezésére, amelyek kimenő elektronikus dokumentumok létrehozására használhatók az alkalmazásban.
author: NickSelin
ms.date: 11/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 863c69446e9a7d447847483ec129788e85a8fd58
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750034"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a><span data-ttu-id="7874a-103">Elektronikus dokumentumok generálása és alkalmazásadatok frissítése ER használatával</span><span class="sxs-lookup"><span data-stu-id="7874a-103">Generate electronic documents and update application data by using ER</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7874a-104">Lehetőség van elektronikus jelentési (ER) formátumok tervezésére, amelyek kimenő elektronikus dokumentumok létrehozására használhatók az alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="7874a-104">You can design Electronic reporting (ER) formats that can be used in the application to generate outgoing electronic documents.</span></span> <span data-ttu-id="7874a-105">Olyan ER-formátumokat is készíthet, amelyek a bejövő elektronikus dokumentumokat elemzik, és ezeknek a dokumentumoknak a tartalmát használják az alkalmazásadatok frissítésére.</span><span class="sxs-lookup"><span data-stu-id="7874a-105">You can also design ER formats that parse incoming electronic documents and use the content in those documents to update application data.</span></span>

<span data-ttu-id="7874a-106">Ezzel a funkcióval egyetlen ER-formátum használható a kimenő elektronikus dokumentumok létrehozására, majd az alkalmazásadatok frissítésére.</span><span class="sxs-lookup"><span data-stu-id="7874a-106">With this functionality, a single ER format can be used to generate outgoing electronic documents and then update the application data.</span></span> <span data-ttu-id="7874a-107">Ez a funkció a következő forgatókönyvek esetében használható:</span><span class="sxs-lookup"><span data-stu-id="7874a-107">This feature can be used in the following scenarios:</span></span>

- <span data-ttu-id="7874a-108">Az alkalmazásadatoknak a későbbi folyamatokban való ismételt felhasználásának elkerülésére az alkalmazás adatait az elektronikus dokumentumok létrehozása után azonnal megjelölheti.</span><span class="sxs-lookup"><span data-stu-id="7874a-108">To prevent repeated usage of application data in subsequent processes you can mark an application’s data immediately after it is used to generate electronic documents.</span></span> <span data-ttu-id="7874a-109">A fizetési tranzakciókat például azonnal megjelölheti már feldolgozottként, amint bekerülnek a generált fizetési üzenetbe.</span><span class="sxs-lookup"><span data-stu-id="7874a-109">For example, you can mark payment transactions as already processed immediately after they have been included in a generated payment message.</span></span>
- <span data-ttu-id="7874a-110">Az ER-logika használatával létrehozott elektronikus dokumentumok feldolgozási részleteinek tárolására.</span><span class="sxs-lookup"><span data-stu-id="7874a-110">To store the processing details of electronic documents that have been generated using ER logic.</span></span> <span data-ttu-id="7874a-111">Például egy ER-kifejezés használatával létrehozott egyedi fizetésiüzenet-azonosító.</span><span class="sxs-lookup"><span data-stu-id="7874a-111">For example, a unique payment message identification that is generated using the ER expression.</span></span> <span data-ttu-id="7874a-112">A kifejezés alapját az ER-párbeszédpanelen akkor megadott adatok adják, amikor az ER-formátumot dokumentumok létrehozásához futtatják.</span><span class="sxs-lookup"><span data-stu-id="7874a-112">The expression is based on information entered in the ER dialog box when the ER format is run to generate documents.</span></span>

<span data-ttu-id="7874a-113">Ezzel a funkcióval kapcsolatos további információért játssza le a Dokumentumok létrehozása alkalmazásadat-frissítéssel ER feladatútmutató-készletet (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része), amelyek bemutatja az Intrastat jelentéskészítés és archiválás részleteit.</span><span class="sxs-lookup"><span data-stu-id="7874a-113">To learn more about this feature, play the set of ER Generate documents with application data update Task guides (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process), which walk you through the details of Intrastat reporting and archiving.</span></span> <span data-ttu-id="7874a-114">A következő fájlok szükségesek a feladatútmutató egyes lépéseinek végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="7874a-114">The following files are required to complete certain steps in these Task guides.</span></span> <span data-ttu-id="7874a-115">Töltse le és mentse ezeket a fájlokat a helyi számítógépre.</span><span class="sxs-lookup"><span data-stu-id="7874a-115">Download and save these files to your local machine.</span></span>

- [<span data-ttu-id="7874a-116">ER adatmodellkonfiguráció: Instrastat (modell)</span><span class="sxs-lookup"><span data-stu-id="7874a-116">ER data model configuration: Intrastat (model)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="7874a-117">ER modell leképezésének konfigurációja: Intrastat (leképezés)</span><span class="sxs-lookup"><span data-stu-id="7874a-117">ER model mapping configuration: Intrastat (mapping)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="7874a-118">ER formátumkonfiguráció: Intrastat (formátum)</span><span class="sxs-lookup"><span data-stu-id="7874a-118">ER format configuration: Intrastat (format)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]