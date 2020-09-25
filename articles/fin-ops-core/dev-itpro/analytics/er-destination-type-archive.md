---
title: Archivált ER céltípusa
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy archiválási célhelyet a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8797a68507a5116c6adbf1f2d805838fa507958c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745585"
---
# <a name="archive-destination"></a><span data-ttu-id="897cb-103">Archív cél</span><span class="sxs-lookup"><span data-stu-id="897cb-103">Archive destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="897cb-104">Beállíthat egy archiválási célhelyet a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez.</span><span class="sxs-lookup"><span data-stu-id="897cb-104">You can configure an archive destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="897cb-105">A célhely beállításai alapján a létrejövő dokumentumot a rendszer az ER-feladatok listájának egy rekordja csatolmányaként tárolja.</span><span class="sxs-lookup"><span data-stu-id="897cb-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span>

<span data-ttu-id="897cb-106">Ezen opcióval a generált dokumentum elküldhető egy Microsoft SharePoint vagy Microsoft Azure Storage mappába.</span><span class="sxs-lookup"><span data-stu-id="897cb-106">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="897cb-107">A kiválasztott dokumentumtípus által meghatározott célra történő eredményküldéshez állítsa a **Bekapcsolva** opciót **Igen** állapotba.</span><span class="sxs-lookup"><span data-stu-id="897cb-107">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="897cb-108">Csak azok a dokumentumtípusok választhatók ki, amelyeknél a csoport beállítása **File**.</span><span class="sxs-lookup"><span data-stu-id="897cb-108">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="897cb-109">A dokumentumok [típusait](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) itt határozhatja meg: **Szervezeti adminisztráció** \> **Dokumentumkezelés** \> **Dokumentumtípusok**.</span><span class="sxs-lookup"><span data-stu-id="897cb-109">You define document [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="897cb-110">Az ER célok konfigurálásának folyamata megegyezik a dokumentumkezelő rendszer konfigurálásával.</span><span class="sxs-lookup"><span data-stu-id="897cb-110">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="897cb-111">[![Dokumentumtípusok lapja](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="897cb-111">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="897cb-112">A hely határozza meg, hogy a file hol kerül tárolásra.</span><span class="sxs-lookup"><span data-stu-id="897cb-112">The location determines where the file is saved.</span></span> <span data-ttu-id="897cb-113">Az **Archívum** cél engedélyezése után az eredmény menthető a Feladat archívumba.</span><span class="sxs-lookup"><span data-stu-id="897cb-113">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="897cb-114">Az eredményeket a **Szervezeti adminisztráció** \> **Elektronikus jelentés** \> **Elektronikus jelentéskészítési archivált feladatok** elemnél tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="897cb-114">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="897cb-115">A Feladatarchívum ponthoz a dokumentumtípust az alkalmazásban a következő helyen választhatja ki: **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** \> **Elektronikus jelentéskészítés paraméterei**.</span><span class="sxs-lookup"><span data-stu-id="897cb-115">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="897cb-116">További információ: [Az elektronikus jelentéskészítési (ER) keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="897cb-116">For more information, [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="897cb-117">SharePoint</span><span class="sxs-lookup"><span data-stu-id="897cb-117">SharePoint</span></span>

<span data-ttu-id="897cb-118">A fájlt egy kijelölt SharePoint mappába is mentheti.</span><span class="sxs-lookup"><span data-stu-id="897cb-118">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="897cb-119">Az alapértelmezett SharePoint kiszolgálót itt határozhatja meg: **Szervezeti adminisztráció** \> **Dokumentumkezelés** \> **Dokumentumkezelés paraméterei**.</span><span class="sxs-lookup"><span data-stu-id="897cb-119">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="897cb-120">A **SharePoint** lapon konfigurálja a SharePoint mappát.</span><span class="sxs-lookup"><span data-stu-id="897cb-120">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="897cb-121">Ezt követően kiválaszthatja azt azon mappaként, ahova az ER-kimenetet menti a rendszer.</span><span class="sxs-lookup"><span data-stu-id="897cb-121">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="897cb-122">Ezen dokumentumtípus esetén ki kell választani a **SharePoint**-helyet.</span><span class="sxs-lookup"><span data-stu-id="897cb-122">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="897cb-123">[![SharePoint-mappa kiválasztása](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="897cb-123">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="897cb-124">Azure Storage</span><span class="sxs-lookup"><span data-stu-id="897cb-124">Azure Storage</span></span>

<span data-ttu-id="897cb-125">Ha a dokumentumtípus helye **Azure tárhely**, a fájl menthető az Azure Storage tárhelyre.</span><span class="sxs-lookup"><span data-stu-id="897cb-125">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="897cb-126">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="897cb-126">Additional resources</span></span>

- [<span data-ttu-id="897cb-127">Elektronikus jelentéskészítés (ER) áttekintése</span><span class="sxs-lookup"><span data-stu-id="897cb-127">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="897cb-128">Elektronikus jelentéskészítés (ER) céljai</span><span class="sxs-lookup"><span data-stu-id="897cb-128">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="897cb-129">A dokumentumkezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="897cb-129">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)
