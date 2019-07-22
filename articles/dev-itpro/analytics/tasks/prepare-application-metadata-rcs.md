---
title: Az RCS-ben felhasználandó alkalmazás-metaadatok előkészítése
description: A cikk áttekinti, hogyan lehet a Finance and Operations alkalmazás metaadatait tartalmazó új Elektronikus jelentéskészítési (ER) konfigurációt létrehozni ER modell-leképezési konfigurációk Regulatory Configuration Service szolgáltatásban való kialakításához.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c1bd2298240fa789762a350e90888201c5a7ce45
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/04/2019
ms.locfileid: "1726983"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a><span data-ttu-id="cc1b1-103">Az RCS-ben felhasználandó alkalmazás-metaadatok előkészítése</span><span class="sxs-lookup"><span data-stu-id="cc1b1-103">Prepare application metadata to be used in RCS</span></span>
[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cc1b1-104">A következő lépések ismertetik, hogy a Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználók hogyan hozhatnak létre olyan új Elektronikus jelentéskészítési konfigurációt, amely tartalmazza a Microsoft Dynamics 365 for Finance and Operations alkalmazás metaadatait az ER modell-leképezési konfigurációk Regulatory Configuration Service (RCS) rendszerben való kialakításához.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains Microsoft Dynamics 365 for Finance and Operations application metadata for designing ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="cc1b1-105">Ez a konfiguráció olyan minta ER-modell-leképezési konfiguráció kialakításához használatos, amellyel hozzá lehet férni a külkereskedelmi tranzakciókhoz.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-105">This configuration will be used for designing a sample ER model mapping configuration to access foreign trade transactions.</span></span> <span data-ttu-id="cc1b1-106">Ebben a példában a mintavállalatra, a Litware, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket bármilyen vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company.</span></span> <span data-ttu-id="cc1b1-107">Az alábbi lépések végrehajtásához először hajtsa végre a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) cikk lépéseit.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-107">To complete these steps, you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cc1b1-108">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="cc1b1-108">Prerequisites</span></span>
1.  <span data-ttu-id="cc1b1-109">Lépjen a **Szervezeti adminisztráció** > **Munkaterületek** > **Elektronikus jelentés** részre.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-109">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2.  <span data-ttu-id="cc1b1-110">Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="cc1b1-111">Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) cikk lépéseit.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-111">If you don’t see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3.  <span data-ttu-id="cc1b1-112">Kattintson a **Metaadat-konfigurációk** elemre.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-112">Click **Metadata configurations**.</span></span> 
4.  <span data-ttu-id="cc1b1-113">Tegyük fel, hogy az RCS használatával olyan ER-megoldást szeretne kialakítani a Finance and Operation alkalmazáshoz, amely a külkereskedelmi üzleti tartományból származó adatokat tartalmazó elektronikus dokumentumokat készít.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-113">Assume that RCS will be used to design an ER solution for a Finance and Operation application that will generate electronic documents that contain information from foreign trade business domain.</span></span> <span data-ttu-id="cc1b1-114">Ha meg szeretné adni az ER-adatmodell és a szükséges adatok forrása közötti leképezést, akkor az RCS-ben hozzáféréssel kell rendelkeznie a Finance and Operations alkalmazás metaadataihoz.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-114">To specify the mapping between ER data model and sources of required data, in RCS we need to have access to metadata of the Finance and Operation application.</span></span> <span data-ttu-id="cc1b1-115">Ennek megfelelően az ER-megoldás tervezése során olyan új ER-metaadat-konfigurációt állítunk be, amely a kiválasztott üzleti tartományok ER-jelentéseinek a létrehozásához pillanatnyilag szükséges összes metaadatot tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-115">Therefore, as part of designing ER solution we configure a new ER metadata configuration containing all metadata that is currently required for generation ER reports for selected business domain.</span></span> 

## <a name="add-metadata-configuration"></a><span data-ttu-id="cc1b1-116">Metaadat-konfiguráció hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cc1b1-116">Add metadata configuration</span></span> 
1.  <span data-ttu-id="cc1b1-117">A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-117">Click **Create configuration** to open the drop dialog.</span></span> 
2.  <span data-ttu-id="cc1b1-118">A **Név** mezőbe írja be, hogy „Külkereskedelmi metaadatok”.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-118">In the **Name** field, type 'Foreign trade metadata'.</span></span> 
3.  <span data-ttu-id="cc1b1-119">Kattintson a **Konfiguráció létrehozása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-119">Click **Create configuration**.</span></span> 
4.  <span data-ttu-id="cc1b1-120">Kattintson a **Tervező** pontra.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-120">Click **Designer**.</span></span> 
5.  <span data-ttu-id="cc1b1-121">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-121">Click **Add**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cc1b1-122">Minden metaadatot a teljes pályázathoz, a kiválasztott modellekhez vagy a kiválasztott modulokhoz választhat ki.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-122">You can select all metadata for the entire application or selected models or selected modules.</span></span> <span data-ttu-id="cc1b1-123">Ne feledje, hogy ebben az esetben a program automatikusan felveszi a következő metaadatokat: a rekordok, a felsorolások és a kiterjesztett adattípusok táblázatai.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-123">Be aware that in this case the following metadata will be automatically added: tables of records, enumerations, and extended data types.</span></span> <span data-ttu-id="cc1b1-124">Ha további típusú metaadatokra van szüksége, akkor manuálisan kell őket felvennie.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-124">When additional types of metadata are needed, they must be added manually.</span></span> 
 
<span data-ttu-id="cc1b1-125">Bizonyos külkereskedelmi tranzakciókkal kapcsolatos metaadatokat az elemek manuális kijelölésével kell kiválasztani.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-125">We have some foreign trade transactions related metadata by selecting metadata items manually.</span></span> 
  
6.  <span data-ttu-id="cc1b1-126">Kattintson az **Adatforrás hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-126">Click **Add data source**.</span></span> 
7.  <span data-ttu-id="cc1b1-127">Kattintson a **Táblarekordok** elemre.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-127">Click **Table records**.</span></span> 
8.  <span data-ttu-id="cc1b1-128">A gyorsszűrő használatával szűrheti a **Név** mezőt az „Intrastat” érték előfordulására.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-128">Use the Quick Filter to filter on the **Name** field with a value of 'Intrastat'.</span></span> 
9.  <span data-ttu-id="cc1b1-129">Az **Intrastat** táblarekordjának kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-129">Select the **Intrastat** table record.</span></span> 
10. <span data-ttu-id="cc1b1-130">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-130">Click **OK**.</span></span>
  
<span data-ttu-id="cc1b1-131">A rekordok Intrastat-táblázatára vonatkozó metaadat-információkat adtunk hozzá.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-131">We added metadata information about the Intrastat table of records.</span></span> 
  
11. <span data-ttu-id="cc1b1-132">A fastruktúrában bontsa ki a **Táblarekordok: Intrastat**\>**Kapcsolatok** részt.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-132">In the tree, expand **Table records Intrastat**\>**Relations**.</span></span> 
12. <span data-ttu-id="cc1b1-133">A fastruktúrában válassza ki a **Táblarekordok: Intrastat**\>**Relations\IntrastatCommodity (Táblarekordok: EcoResCategory)** részt.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-133">In the tree, select **Table records Intrastat**\>**Relations\IntrastatCommodity (Table records EcoResCategory)**.</span></span>   
13. <span data-ttu-id="cc1b1-134">Kattintson a **Metaadatok hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-134">Click **Add metadata**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cc1b1-135">A kiválasztott rekordtábla szükséges kapcsolatainak metaadatait manuálisan kell felvenni.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-135">Metadata about required relations for selected table of records must be added manually.</span></span> 
  
16. <span data-ttu-id="cc1b1-136">Kattintson az **Adatforrás hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-136">Click **Add data source**.</span></span> 
17. <span data-ttu-id="cc1b1-137">Kattintson a **Felsorolás** elemre.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-137">Click **Enumeration**.</span></span> 
18. <span data-ttu-id="cc1b1-138">A gyorsszűrő használatával szűrje a **Név** mezőt az „IntrastatDirection” értékre.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-138">Use the Quick Filter to filter on the **Name** field with a value of 'IntrastatDirection'.</span></span> 
19. <span data-ttu-id="cc1b1-139">Válassza ki az **IntrastatDirection felsorolása** rekordot.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-139">Select the **IntrastatDirection enumeration** record.</span></span> 
20. <span data-ttu-id="cc1b1-140">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-140">Click **OK**.</span></span> 
21. <span data-ttu-id="cc1b1-141">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-141">Click **Save**.</span></span>  
22. <span data-ttu-id="cc1b1-142">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-142">Close the page.</span></span> 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a><span data-ttu-id="cc1b1-143">A metaadat-konfiguráció piszkozatának befejezése</span><span class="sxs-lookup"><span data-stu-id="cc1b1-143">Complete the draft version of metadata configuration</span></span>
1.  <span data-ttu-id="cc1b1-144">Kattintson az **Állapot módosítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-144">Click **Change status**.</span></span> 
2.  <span data-ttu-id="cc1b1-145">Kattintson a **Befejezés** gombra.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-145">Click **Complete**.</span></span> 
3.  <span data-ttu-id="cc1b1-146">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-146">Click **OK**.</span></span> 
4.  <span data-ttu-id="cc1b1-147">Válassza ki a befejezett verziót **1**.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-147">Select the completed version **1**.</span></span> 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a><span data-ttu-id="cc1b1-148">A metaadat-konfiguráció befejezett verziójának exportálása az alkalmazásból XML-fájlként</span><span class="sxs-lookup"><span data-stu-id="cc1b1-148">Export the completed version of metadata configuration from application as XML file</span></span>
1.  <span data-ttu-id="cc1b1-149">Kattintson az **Átváltás** elemre.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-149">Click **Exchange**.</span></span> 
2.  <span data-ttu-id="cc1b1-150">Kattintson az **Exportálás XML-fájlként** elemre.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-150">Click **Export as XML file**.</span></span> 
3.  <span data-ttu-id="cc1b1-151">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-151">Click **OK**.</span></span> 
    
<span data-ttu-id="cc1b1-152">A létrehozott ER metaadat-konfigurációt olyan XML-fájlként mentette, amely importálható az RCS-be, és használható a külkereskedelmi üzleti tartomány metaadataira vonatkozó adatforrásként a Finance and Operations rendszerben.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-152">The created ER metadata configuration has been saved as XML file that can be imported to RCS and used as the source of information about metadata for the foreign trade business domain in Finance and Operations.</span></span> <span data-ttu-id="cc1b1-153">Az információ alapján meg tudjuk határozni az alkalmazás metaadatai és az ER-adatmodell közötti leképezést.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-153">Based on this information, we can specify the mapping between application metadata and ER data model.</span></span>
