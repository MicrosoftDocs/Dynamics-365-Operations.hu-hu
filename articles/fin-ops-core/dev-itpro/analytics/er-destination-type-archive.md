---
title: Archivált ER céltípusa
description: Ez a témakör arról tartalmaz tájékoztatást, hogyan kell konfigurálni egy archiválási célt az Elektronikus jelentéskészítési (ER) formátumok egyes MAPPA vagy FÁJL összetevőihez.
author: NickSelin
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 079eda04fcc41fc637419a83452db10b89ed1ab9
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894028"
---
# <a name="archive-er-destination-type"></a><span data-ttu-id="2bc58-103">Archivált ER céltípusa</span><span class="sxs-lookup"><span data-stu-id="2bc58-103">Archive ER destination type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2bc58-104">Beállíthat egy archiválási célhelyet a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok **Mappa** vagy **Fájl** összetevőihez.</span><span class="sxs-lookup"><span data-stu-id="2bc58-104">You can configure an archive destination for each **Folder** or **File** component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="2bc58-105">A célhely beállításai alapján a létrejövő dokumentumot a rendszer az ER-feladatok listájának egy rekordja csatolmányaként tárolja.</span><span class="sxs-lookup"><span data-stu-id="2bc58-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span> <span data-ttu-id="2bc58-106">Az eredményeket a **Szervezeti adminisztráció** \> **Elektronikus jelentés** \> **Elektronikus jelentéskészítési feladatok** elemnél tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="2bc58-106">To view the results, go to **Organization administration** \> **Electronic reporting** \> **Electronic reporting jobs**.</span></span>

<span data-ttu-id="2bc58-107">Ezen opcióval a generált dokumentum elküldhető egy Microsoft SharePoint vagy Microsoft Azure Storage mappába.</span><span class="sxs-lookup"><span data-stu-id="2bc58-107">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="2bc58-108">A kiválasztott dokumentumtípus által meghatározott célra történő eredményküldéshez állítsa a **Bekapcsolva** opciót **Igen** állapotba.</span><span class="sxs-lookup"><span data-stu-id="2bc58-108">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="2bc58-109">Csak azok a dokumentumtípusok választhatók ki, amelyeknél a csoport beállítása **File**.</span><span class="sxs-lookup"><span data-stu-id="2bc58-109">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="2bc58-110">A dokumentumok [típusait](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) itt határozhatja meg: **Szervezeti adminisztráció** \> **Dokumentumkezelés** \> **Dokumentumtípusok**.</span><span class="sxs-lookup"><span data-stu-id="2bc58-110">You define document [types](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="2bc58-111">Az ER célok konfigurálásának folyamata megegyezik a dokumentumkezelő rendszer konfigurálásával.</span><span class="sxs-lookup"><span data-stu-id="2bc58-111">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="2bc58-112">[![Dokumentumtípusok lapja](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="2bc58-112">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="2bc58-113">A hely határozza meg, hogy a file hol kerül tárolásra.</span><span class="sxs-lookup"><span data-stu-id="2bc58-113">The location determines where the file is saved.</span></span> <span data-ttu-id="2bc58-114">Az **Archívum** cél engedélyezése után az eredmény menthető a Feladat archívumba.</span><span class="sxs-lookup"><span data-stu-id="2bc58-114">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="2bc58-115">Az eredményeket a **Szervezeti adminisztráció** \> **Elektronikus jelentés** \> **Elektronikus jelentéskészítési archivált feladatok** elemnél tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="2bc58-115">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="2bc58-116">A Feladatarchívum ponthoz a dokumentumtípust az alkalmazásban a következő helyen választhatja ki: **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** \> **Elektronikus jelentéskészítés paraméterei**.</span><span class="sxs-lookup"><span data-stu-id="2bc58-116">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="2bc58-117">További információ: [Az elektronikus jelentéskészítési (ER) keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="2bc58-117">For more information, see [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="2bc58-118">SharePoint</span><span class="sxs-lookup"><span data-stu-id="2bc58-118">SharePoint</span></span>

<span data-ttu-id="2bc58-119">A fájlt egy kijelölt SharePoint mappába is mentheti.</span><span class="sxs-lookup"><span data-stu-id="2bc58-119">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="2bc58-120">Az alapértelmezett SharePoint kiszolgálót itt határozhatja meg: **Szervezeti adminisztráció** \> **Dokumentumkezelés** \> **Dokumentumkezelés paraméterei**.</span><span class="sxs-lookup"><span data-stu-id="2bc58-120">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="2bc58-121">A **SharePoint** lapon konfigurálja a SharePoint mappát.</span><span class="sxs-lookup"><span data-stu-id="2bc58-121">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="2bc58-122">Ezt követően kiválaszthatja azt azon mappaként, ahova az ER-kimenetet menti a rendszer.</span><span class="sxs-lookup"><span data-stu-id="2bc58-122">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="2bc58-123">Ezen dokumentumtípus esetén ki kell választani a **SharePoint**-helyet.</span><span class="sxs-lookup"><span data-stu-id="2bc58-123">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="2bc58-124">[![SharePoint-mappa kiválasztása](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="2bc58-124">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="2bc58-125">Azure Storage</span><span class="sxs-lookup"><span data-stu-id="2bc58-125">Azure Storage</span></span>

<span data-ttu-id="2bc58-126">Ha a dokumentumtípus helye **Azure tárhely**, a fájl menthető az Azure Storage tárhelyre.</span><span class="sxs-lookup"><span data-stu-id="2bc58-126">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

> [!NOTE] 
> <span data-ttu-id="2bc58-127">Az ER-keretrendszer véglegesen tárolja a fájlokat az Azure Blob tárolóban ellentétben az Adatkezelési keretrendszerrel, amely a hét napos adatmegőrzési szabályzatot alkalmazza a feldolgozandó dokumentumokra.</span><span class="sxs-lookup"><span data-stu-id="2bc58-127">The ER framework permanently stores files in Azure Blob storage unlike the Data management framework that applies the seven-day retention policy for documents that must be processed.</span></span> <span data-ttu-id="2bc58-128">További információ: [API az üzenetek állapotának lekéréséhez](../data-entities/recurring-integrations.md#api-for-getting-message-status) és [Állapot-ellenőrző API](../data-entities/data-management-api.md#status-check-api).</span><span class="sxs-lookup"><span data-stu-id="2bc58-128">For more information, see [API for getting message status](../data-entities/recurring-integrations.md#api-for-getting-message-status) and [Status check API](../data-entities/data-management-api.md#status-check-api).</span></span> <span data-ttu-id="2bc58-129">Az ER-vel kapcsolatos fájlok az Azure Blob storage-ban lesznek tárolva az alkalmazástábla-rekordok mellékleteként, amíg szükséges.</span><span class="sxs-lookup"><span data-stu-id="2bc58-129">The ER-related files will be stored in Azure Blob storage as attachments of application table records as long as necessary.</span></span> <span data-ttu-id="2bc58-130">Egyetlen fájl törlődik az Azure Blob storage-ból az alkalmazástábla-rekorddal együtt, amelyhez ez a fájl csatolva volt.</span><span class="sxs-lookup"><span data-stu-id="2bc58-130">A single file will be deleted from Azure Blob storage along with the application table record that this file was attached to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2bc58-131">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2bc58-131">Additional resources</span></span>

- [<span data-ttu-id="2bc58-132">Elektronikus jelentéskészítés (ER) áttekintése</span><span class="sxs-lookup"><span data-stu-id="2bc58-132">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="2bc58-133">Elektronikus jelentéskészítés (ER) céljai</span><span class="sxs-lookup"><span data-stu-id="2bc58-133">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="2bc58-134">A dokumentumkezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="2bc58-134">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]