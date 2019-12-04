---
title: Alkalmazásspecifikus metaadatok előkészítése az RCS és ER számára
description: Ez a témakör azt mutatja be, hogyan kell előkészíteni az alkalmazásspecifikus metaadatokat a Regulatory Configuration Service (RCS) és az elektronikus jelentés (ER) számára.
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 89d36c305bc9210f7906cd4288e33e5028baecdb
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771260"
---
# <a name="prepare-application-specific-metadata-for-rcs-and-er"></a><span data-ttu-id="d903c-103">Alkalmazásspecifikus metaadatok előkészítése az RCS és ER számára</span><span class="sxs-lookup"><span data-stu-id="d903c-103">Prepare application-specific metadata for RCS and ER</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d903c-104">Ez a témakör a következő feladatok példáival nyújt útmutatót:</span><span class="sxs-lookup"><span data-stu-id="d903c-104">This topic walks you through examples of the following tasks:</span></span>

- [<span data-ttu-id="d903c-105">RCS-ben felhasználandó alkalmazás-metaadatok előkészítése</span><span class="sxs-lookup"><span data-stu-id="d903c-105">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)
- [<span data-ttu-id="d903c-106">Alkalmazás-metaadatokhoz való hozzáférés egy ER-konfiguráció használatával</span><span class="sxs-lookup"><span data-stu-id="d903c-106">Access application metadata by using an ER configuration</span></span>](#access-application-metadata-by-using-an-er-configuration)
- [<span data-ttu-id="d903c-107">Alkalmazás-metaadatokhoz való hozzáférés összekapcsolt alkalmazások használatával</span><span class="sxs-lookup"><span data-stu-id="d903c-107">Access application metadata by using connected applications</span></span>](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a><span data-ttu-id="d903c-108">RCS-ben felhasználandó alkalmazás-metaadatok előkészítése</span><span class="sxs-lookup"><span data-stu-id="d903c-108">Prepare application metadata that can be used in RCS</span></span>

<span data-ttu-id="d903c-109">A következő eljárás ismerteti, hogy a Finance and Operations megoldásban a **Rendszergazda** vagy **Elektronikus jelentések fejlesztője** szerepkörrel rendelkező felhasználók hogyan hozhatnak létre olyan új Elektronikus jelentéskészítési konfigurációt, amely tartalmazza az alkalmazás metaadatait, és amely az ER modell-leképezési konfigurációk Regulatory Configuration Service (RCS) rendszerben való kialakításához használt.</span><span class="sxs-lookup"><span data-stu-id="d903c-109">The following procedure shows how a user who has the **System Administrator** or **Electronic Reporting Developer** role can create an Electronic reporting (ER) configuration that contains metadata for the application, and that is used to design ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="d903c-110">A példában létrehozott minta ER-modell-leképezési konfigurációval hozzá lehet férni a külkereskedelmi tranzakciókhoz.</span><span class="sxs-lookup"><span data-stu-id="d903c-110">The sample ER model mapping configuration that is created in this example will be used to access foreign trade transactions.</span></span>

<span data-ttu-id="d903c-111">A példában tegyük fel, hogy az RCS használatával olyan ER-megoldást szeretnének kialakítani az alkalmazáshoz, amely a külkereskedelmi üzleti tartományból származó adatokat tartalmazó elektronikus dokumentumokat készít.</span><span class="sxs-lookup"><span data-stu-id="d903c-111">For this example, you want to use RCS to design an ER solution for the application that will be used to generate electronic documents that contain information from the foreign trade business domain.</span></span> <span data-ttu-id="d903c-112">Ha meg szeretné adni az ER-adatmodell és a szükséges adatok forrása közötti leképezést, akkor az RCS-ben hozzáféréssel kell rendelkeznie az alkalmazás metaadataihoz.</span><span class="sxs-lookup"><span data-stu-id="d903c-112">To specify the mapping between the ER data model and the sources of required data, you must have access to application metadata in RCS.</span></span> <span data-ttu-id="d903c-113">Ennek megfelelően az ER-megoldás tervezési folyamata során olyan új ER-metaadat-konfigurációt kell beállítani, amely a kiválasztott üzleti tartományok ER-jelentéseinek a létrehozásához pillanatnyilag szükséges összes metaadatot tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="d903c-113">Therefore, as part of the process of designing the ER solution, you must configure a new ER metadata configuration that contains all the metadata that is currently required in order to generate ER reports for the selected business domain.</span></span>

> [!NOTE]
> <span data-ttu-id="d903c-114">Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket bármilyen vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="d903c-114">In this example, you will create a configuration for the sample company, Litware, Inc. These steps can be performed in any company.</span></span>

1. <span data-ttu-id="d903c-115">Ugorjon a **Szervezeti adminisztráció \> Munkaterületek \> Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="d903c-115">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="d903c-116">Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="d903c-116">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="d903c-117">Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltatók létrehozása, és megjelölésük aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárásban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d903c-117">If you don't see this configuration provider, complete the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="d903c-118">Kattintson a **Metaadat-konfigurációk** elemre.</span><span class="sxs-lookup"><span data-stu-id="d903c-118">Select **Metadata configurations**.</span></span>
4. <span data-ttu-id="d903c-119">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-119">Select **Create configuration**.</span></span>
5. <span data-ttu-id="d903c-120">Írjon be egy nevet a legördülő párbeszédpanel **Név** mezőjébe.</span><span class="sxs-lookup"><span data-stu-id="d903c-120">In the drop-down dialog box, in the **Name** field, enter a name.</span></span> <span data-ttu-id="d903c-121">A példa esetében adja meg a **Külkereskedelmi metaadatok** szöveget.</span><span class="sxs-lookup"><span data-stu-id="d903c-121">For this example, enter **Foreign trade metadata**.</span></span>
6. <span data-ttu-id="d903c-122">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-122">Select **Create configuration**.</span></span>
7. <span data-ttu-id="d903c-123">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-123">Select **Designer**.</span></span>
8. <span data-ttu-id="d903c-124">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-124">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d903c-125">Minden metaadatot kiválaszthat a teljes alkalmazáshoz, a kiválasztott modellekhez vagy a kiválasztott modulokhoz.</span><span class="sxs-lookup"><span data-stu-id="d903c-125">You can select all metadata either for the whole application, or for selected models or modules.</span></span> <span data-ttu-id="d903c-126">Mindkét esetben a program automatikusan felveszi a következő metaadatokat: a rekordok, a felsorolások és a kiterjesztett adattípusok táblázatai (EDT).</span><span class="sxs-lookup"><span data-stu-id="d903c-126">In both cases, be aware that the following metadata will be automatically added: tables of records, enumerations, and extended data types (EDTs).</span></span> <span data-ttu-id="d903c-127">Ha további típusú metaadatokra van szüksége, akkor manuálisan kell őket felvennie.</span><span class="sxs-lookup"><span data-stu-id="d903c-127">When additional types of metadata are required, they must be manually added.</span></span>

    <span data-ttu-id="d903c-128">Hozzá kell adni bizonyos külkereskedelmi tranzakciókkal kapcsolatos metaadatokat, és manuálisan ki kell választani a metaadatelemeket.</span><span class="sxs-lookup"><span data-stu-id="d903c-128">You must add some metadata that is related to foreign trade transactions and manually select metadata items.</span></span>

9. <span data-ttu-id="d903c-129">Jelölje be az **Adatforrás hozzáadása \> Táblához tartozó rekordok** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-129">Select **Add data source \> Table records**.</span></span>
10. <span data-ttu-id="d903c-130">Az **Intrastat** értékére szűrjön a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="d903c-130">Filter on a value of **Intrastat** in the **Name** field.</span></span>
11. <span data-ttu-id="d903c-131">Az **Intrastat** táblarekordjának kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="d903c-131">Select the **Intrastat** table record.</span></span>
12. <span data-ttu-id="d903c-132">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-132">Select **OK**.</span></span>

    <span data-ttu-id="d903c-133">A rekordok Intrastat-táblázatára vonatkozó metaadat-információkat kell hozzáadnia.</span><span class="sxs-lookup"><span data-stu-id="d903c-133">You must add metadata information about the Intrastat table of records.</span></span>

13. <span data-ttu-id="d903c-134">A fastruktúrában válassza ki a **Táblarekordok: Intrastat \> \>Kapcsolatok\> IntrastatCommodity (Táblarekordok: EcoResCategory)** részt.</span><span class="sxs-lookup"><span data-stu-id="d903c-134">In the tree, select **Table records Intrastat \> \>Relations \> IntrastatCommodity (Table records EcoResCategory)**.</span></span>
14. <span data-ttu-id="d903c-135">Válassza a **Metaadatok hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-135">Select **Add metadata**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d903c-136">A kiválasztott rekordtábla szükséges kapcsolatainak metaadatait manuálisan kell felvenni.</span><span class="sxs-lookup"><span data-stu-id="d903c-136">Metadata about required relations for the selected table of records must be added manually.</span></span>

15. <span data-ttu-id="d903c-137">**Adatforrás hozzáadása** lehetőség választása.</span><span class="sxs-lookup"><span data-stu-id="d903c-137">Select **Add data source**.</span></span>
16. <span data-ttu-id="d903c-138">A **Számbavétel** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="d903c-138">Select **Enumeration**.</span></span>
17. <span data-ttu-id="d903c-139">Az **IntrastatDirection** értékére szűrjön a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="d903c-139">Filter on a value of **IntrastatDirection** in the **Name** field.</span></span>
18. <span data-ttu-id="d903c-140">Válassza ki az **IntrastatDirection** felsorolásrekordot.</span><span class="sxs-lookup"><span data-stu-id="d903c-140">Select the **IntrastatDirection** enumeration record.</span></span>
19. <span data-ttu-id="d903c-141">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-141">Select **OK**.</span></span>
20. <span data-ttu-id="d903c-142">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-142">Select **Save**.</span></span>
21. <span data-ttu-id="d903c-143">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d903c-143">Close the page.</span></span>
22. <span data-ttu-id="d903c-144">A metaadat-konfiguráció piszkozatának befejezése:</span><span class="sxs-lookup"><span data-stu-id="d903c-144">Complete the draft version of the metadata configuration:</span></span>

    1. <span data-ttu-id="d903c-145">Válassza az **Állapot módosítása \>Teljes** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-145">Select **Change status \> Complete**.</span></span>
    2. <span data-ttu-id="d903c-146">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-146">Select **OK**.</span></span>
    3. <span data-ttu-id="d903c-147">Válassza ki a befejezett verziót 1.</span><span class="sxs-lookup"><span data-stu-id="d903c-147">Select the completed version 1.</span></span>

23. <span data-ttu-id="d903c-148">A metaadat-konfiguráció befejezett verziójának exportálása az alkalmazásból XML-fájlként:</span><span class="sxs-lookup"><span data-stu-id="d903c-148">Export the completed version of the metadata configuration from the application as an XML file:</span></span>

    1. <span data-ttu-id="d903c-149">Válassza ki az **Exchange \> Export XML-fájlként** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-149">Select **Exchange \> Export as XML file**.</span></span>
    2. <span data-ttu-id="d903c-150">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-150">Select **OK**.</span></span>

<span data-ttu-id="d903c-151">A létrehozott ER-metaadat konfigurációt a rendszer **Foreign trade metadata. XML** fájlként menti.</span><span class="sxs-lookup"><span data-stu-id="d903c-151">The ER metadata configuration that you created is saved as the **Foreign trade metadata.xml** file.</span></span> <span data-ttu-id="d903c-152">Ezt követően importálhatja az RCS-be, hogy használható metaadatok forrásaként szerepeljen a külkereskedelmi üzleti tartományban.</span><span class="sxs-lookup"><span data-stu-id="d903c-152">You can now import it into RCS, so that it can be used as the source of metadata for the foreign trade business domain.</span></span> <span data-ttu-id="d903c-153">Az információ alapján meg tudja határozni az alkalmazás metaadatai és az ER-adatmodell közötti leképezést.</span><span class="sxs-lookup"><span data-stu-id="d903c-153">Based on this information, you can specify the mapping between application metadata and the ER data model.</span></span>

## <a name="access-application-metadata-by-using-an-er-configuration"></a><span data-ttu-id="d903c-154">Alkalmazás-metaadatokhoz való hozzáférés egy ER-konfiguráció használatával</span><span class="sxs-lookup"><span data-stu-id="d903c-154">Access application metadata by using an ER configuration</span></span>

<span data-ttu-id="d903c-155">A következő eljárás bemutatja, hogy egy RCS felhasználó, aki rendelkezik a **Rendszergazda** vagy az **Elektronikus jelentéskészítési fejlesztő** szerepkörrel, megtervezhet egy új ER-modellhozzárendelést az alkalmazás metaadatainak segítségével.</span><span class="sxs-lookup"><span data-stu-id="d903c-155">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata from the application.</span></span> <span data-ttu-id="d903c-156">Az alkalmazás metaadatainak egy olyan ER-metaadat konfigurációval érhető el, amely minta metaadatkészletet tartalmaz, amelyek a külföldi kereskedelmi tranzakciók eléréséhez használható.</span><span class="sxs-lookup"><span data-stu-id="d903c-156">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span>

<span data-ttu-id="d903c-157">Mielőtt teljesítené ezt az eljárást, végre kell hajtania a következő eljárásokat:</span><span class="sxs-lookup"><span data-stu-id="d903c-157">Before you can complete this procedure, you must first complete the following procedures:</span></span>

- [<span data-ttu-id="d903c-158">Konfigurációszolgáltatók létrehozása és megjelölése aktívként</span><span class="sxs-lookup"><span data-stu-id="d903c-158">Create configuration providers and mark them as active</span></span>](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [<span data-ttu-id="d903c-159">RCS-ben felhasználandó alkalmazás-metaadatok előkészítése</span><span class="sxs-lookup"><span data-stu-id="d903c-159">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)

1. <span data-ttu-id="d903c-160">Ugorjon az **Összes munkaterület \> Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="d903c-160">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="d903c-161">Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="d903c-161">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="d903c-162">Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltatók létrehozása, és megjelölésük aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárásban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d903c-162">If you don't see this configuration provider, complete the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="d903c-163">Importálja az alkalmazáshoz tartozó metaadatokat tartalmazó ER-metaadat konfigurációt, valamint a külkereskedelmi üzleti tartományhoz elektronikus dokumentumokat létrehozó konfigurációs konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="d903c-163">Import the ER metadata configuration that contains metadata for the application, and that is configured to generate electronic documents for the foreign trade business domain.</span></span> <span data-ttu-id="d903c-164">Létrehozta ezt az ER-metaadat konfigurációt, és exportálta XML-fájlként az [ RCS-ben felhasználandó alkalmazás-metaadatok előkészítése](#prepare-application-metadata-that-can-be-used-in-rcs) eljárásban a témakör korábbi részében.</span><span class="sxs-lookup"><span data-stu-id="d903c-164">You created this ER metadata configuration and exported it as an XML file in the [Prepare application metadata that can be used in RCS](#prepare-application-metadata-that-can-be-used-in-rcs) procedure earlier in this topic.</span></span>

    1. <span data-ttu-id="d903c-165">Kattintson a **Metaadat-konfigurációk** elemre.</span><span class="sxs-lookup"><span data-stu-id="d903c-165">Select **Metadata configurations**.</span></span>
    2. <span data-ttu-id="d903c-166">**Árfolyam** kijelölése.</span><span class="sxs-lookup"><span data-stu-id="d903c-166">Select **Exchange**.</span></span>
    3. <span data-ttu-id="d903c-167">Kattintson a **Betöltés XML-fájlból** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d903c-167">Select **Load from XML file**.</span></span>
    4. <span data-ttu-id="d903c-168">Tallózással válassza ki a **Foreign trade metadata.xml** fájlt.</span><span class="sxs-lookup"><span data-stu-id="d903c-168">Browse to select the **Foreign trade metadata.xml** file.</span></span>
    5. <span data-ttu-id="d903c-169">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-169">Select **OK**.</span></span>
    6. <span data-ttu-id="d903c-170">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d903c-170">Close the page.</span></span>

4. <span data-ttu-id="d903c-171">Adatmodell-konfiguráció létrehozása:</span><span class="sxs-lookup"><span data-stu-id="d903c-171">Create a data model configuration:</span></span>

    1. <span data-ttu-id="d903c-172">Válassza a **Jelentéskészítési konfigurációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-172">Select **Reporting configurations**.</span></span>
    2. <span data-ttu-id="d903c-173">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-173">Select **Create configuration**.</span></span>
    3. <span data-ttu-id="d903c-174">Írjon be a legördülő párbeszédpanel **Név** mezőjébe ezt: **Külkereskedelmi modell**.</span><span class="sxs-lookup"><span data-stu-id="d903c-174">In the drop-down dialog box, in the **Name** field, enter **Foreign trade model**.</span></span>
    4. <span data-ttu-id="d903c-175">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-175">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="d903c-176">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-176">Select **Designer**.</span></span>
    6. <span data-ttu-id="d903c-177">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="d903c-177">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="d903c-178">A **Név** mezőbe írja be a következőt: **Gyökér**.</span><span class="sxs-lookup"><span data-stu-id="d903c-178">In the **Name** field, type **Root**.</span></span>
        2. <span data-ttu-id="d903c-179">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-179">Select **Add**.</span></span>
    
    7. <span data-ttu-id="d903c-180">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="d903c-180">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="d903c-181">A **Név** mezőbe írja be a **Tranzakció** szöveget.</span><span class="sxs-lookup"><span data-stu-id="d903c-181">In the **Name** field, type **Transaction**.</span></span>
        2. <span data-ttu-id="d903c-182">A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-182">In the **Item type** field, select **Record list**.</span></span>
        3. <span data-ttu-id="d903c-183">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-183">Select **Add**.</span></span>
 
    8. <span data-ttu-id="d903c-184">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="d903c-184">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="d903c-185">A **Név** mezőbe írja be az **Árucikk-kód** szöveget.</span><span class="sxs-lookup"><span data-stu-id="d903c-185">In the **Name** field, type **Commodity code**.</span></span>
        2. <span data-ttu-id="d903c-186">A **Cikktípus** mezőben válassza ki a **Karakterlánc** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-186">In the **Item type** field, select **String**.</span></span>
        3. <span data-ttu-id="d903c-187">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-187">Select **Add**.</span></span>

    9. <span data-ttu-id="d903c-188">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="d903c-188">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="d903c-189">A Név mezőbe írja be a következőt: **Számlázott összeg**.</span><span class="sxs-lookup"><span data-stu-id="d903c-189">In the Name field, type **Invoiced amount**.</span></span>
        2. <span data-ttu-id="d903c-190">A **Cikktípus** mezőben válassza ki a **Valós** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-190">In the **Item type** field, select **Real**.</span></span>
        3. <span data-ttu-id="d903c-191">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-191">Select **Add**.</span></span>

    10. <span data-ttu-id="d903c-192">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="d903c-192">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="d903c-193">A **Név** mezőbe írja be a következőt: **Dátum**.</span><span class="sxs-lookup"><span data-stu-id="d903c-193">In the **Name** field, type **Date**.</span></span>
        2. <span data-ttu-id="d903c-194">A **Cikktípus** mezőben válassza ki a **Dátum** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-194">In the **Item type** field, select **Date**.</span></span>
        3. <span data-ttu-id="d903c-195">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-195">Select **Add**.</span></span>
 
    11. <span data-ttu-id="d903c-196">Válassza a **Hozzáadás \> Gyökérreferencia** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-196">Select **Add \> Root reference**.</span></span>
    12. <span data-ttu-id="d903c-197">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-197">Select **OK**.</span></span>
    13. <span data-ttu-id="d903c-198">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-198">Select **Save**.</span></span>
    14. <span data-ttu-id="d903c-199">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d903c-199">Close the page.</span></span>
    15. <span data-ttu-id="d903c-200">Válassza az **Állapot módosítása \>Teljes** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-200">Select **Change status \> Complete**.</span></span>
    16. <span data-ttu-id="d903c-201">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-201">Select **OK**.</span></span>

5. <span data-ttu-id="d903c-202">Modell-leképezési konfiguráció létrehozása:</span><span class="sxs-lookup"><span data-stu-id="d903c-202">Create a model mapping configuration:</span></span>

    1. <span data-ttu-id="d903c-203">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-203">Select **Create configuration**.</span></span>
    2. <span data-ttu-id="d903c-204">A legördülő párbeszédpanel **Új** mezőjébe írja be ezt: **Külkereskedelmi modell adatmodellen alapuló modell-leképezés**.</span><span class="sxs-lookup"><span data-stu-id="d903c-204">In the drop-down dialog box, in the **New** field, enter **Model Mapping based on data model Foreign trade model**.</span></span>
    3. <span data-ttu-id="d903c-205">A **Név** mezőbe írja be, hogy **Külkereskedelmi leképezés**.</span><span class="sxs-lookup"><span data-stu-id="d903c-205">In the **Name** field, enter **Foreign trade mapping**.</span></span>
    4. <span data-ttu-id="d903c-206">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-206">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="d903c-207">Válassza az **Előfeltételek** gyorslap **Szerkesztés** elemét.</span><span class="sxs-lookup"><span data-stu-id="d903c-207">On the **Prerequisites** FastTab, select **Edit**.</span></span>
    6. <span data-ttu-id="d903c-208">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-208">Select **New**.</span></span>
    7. <span data-ttu-id="d903c-209">Az **Előfeltétel összetevő típusa** mezőben válassza ki a **Konfiguráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-209">In the **Prerequisite component type** field, select **Configuration**.</span></span>
    8. <span data-ttu-id="d903c-210">A **Külkereskedelmi metaadatok** konfiguráció kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="d903c-210">Select the **Foreign trade metadata** configuration.</span></span>
    9. <span data-ttu-id="d903c-211">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-211">Select **Save**.</span></span> <span data-ttu-id="d903c-212">Figyelje meg, hogy a hivatkozás hozzáadódik a **Külkereskedelmi metaadat** konfiguráció 1. verziójához.</span><span class="sxs-lookup"><span data-stu-id="d903c-212">Notice that the reference is added to version 1 of the **Foreign trade metadata** configuration.</span></span> <span data-ttu-id="d903c-213">A konfiguráció alkalmazás metaadatait a program felkínálja, miközben a modell hozzárendelését tervezik.</span><span class="sxs-lookup"><span data-stu-id="d903c-213">Application metadata from this configuration will be offered while the model mapping is designed.</span></span>
    10. <span data-ttu-id="d903c-214">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d903c-214">Close the page.</span></span>
    11. <span data-ttu-id="d903c-215">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-215">Select **Designer**.</span></span>
    12. <span data-ttu-id="d903c-216">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-216">Select **Designer**.</span></span>
    13. <span data-ttu-id="d903c-217">A fastruktúrában válassza ki a következőt: **Dynamics 365 for Operations \> Tábla rekordjai** csomópont.</span><span class="sxs-lookup"><span data-stu-id="d903c-217">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
    14. <span data-ttu-id="d903c-218">Válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-218">Select **Add root**.</span></span>
    15. <span data-ttu-id="d903c-219">A **Név** mezőbe írja be a **Intrastat** szót.</span><span class="sxs-lookup"><span data-stu-id="d903c-219">In the **Name** field, enter **Intrastat**.</span></span>
    16. <span data-ttu-id="d903c-220">Az **Intrastat** táblarekordjainak kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="d903c-220">Select **Intrastat** table records.</span></span>
    17. <span data-ttu-id="d903c-221">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-221">Select **OK**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d903c-222">Csak két tábla van felkínálva, mert csak két tábla lett hozzáadva a jelenleg használt metaadatok készletéhez.</span><span class="sxs-lookup"><span data-stu-id="d903c-222">Only two tables are offered, because only two tables were added to the set of metadata that is currently used.</span></span>

    18. <span data-ttu-id="d903c-223">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-223">Select **Bind**.</span></span>
    19. <span data-ttu-id="d903c-224">A fastruktúrában válassza ki az **Instrastat \> AmountMST** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-224">In the tree, select **Intrastat \> AmountMST**.</span></span>
    20. <span data-ttu-id="d903c-225">A fán jelölje be a **Transaction = Intrastat \> Számlázott összeg** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-225">In the tree, select **Transaction = Intrastat \> Invoiced amount**.</span></span>
    21. <span data-ttu-id="d903c-226">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-226">Select **Bind**.</span></span>
    22. <span data-ttu-id="d903c-227">A fastruktúrában válassza ki az **Instrastat \> TransDate** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-227">In the tree, select **Intrastat \> TransDate**.</span></span>
    23. <span data-ttu-id="d903c-228">A fastruktúrában válassza ki a **Tranzakció = Intrastat \> Dátum** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-228">In the tree, select **Transaction = Intrastat \> Date**.</span></span>
    24. <span data-ttu-id="d903c-229">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-229">Select **Bind**.</span></span>
    25. <span data-ttu-id="d903c-230">A faszerkezetben válassza ki ezt: **Intrastat \> \>Kapcsolatok \> IntrastatCommodity \> Kód**.</span><span class="sxs-lookup"><span data-stu-id="d903c-230">In the tree, select **Intrastat \> \>Relations \> IntrastatCommodity \> Code**.</span></span>
    26. <span data-ttu-id="d903c-231">A fán jelölje be a **Transaction = Intrastat \> Árucikk kódja** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-231">In the tree, select **Transaction = Intrastat \> Commodity code**.</span></span>
    27. <span data-ttu-id="d903c-232">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-232">Select **Bind**.</span></span>
    28. <span data-ttu-id="d903c-233">A **Validálás**kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="d903c-233">Select **Validate**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d903c-234">Az érvényesítés befejezését követően az adatmodell elemeit az adatforrások olyan cikkeihez társította, amelyek leírása az alkalmazási metaadatoknak a hivatkozott ER-metaadat konfigurációkból származó beállításával történik.</span><span class="sxs-lookup"><span data-stu-id="d903c-234">After validation is completed, you've successfully bound elements of the data model to items of the data sources that are described by using details of the application metadata from the referenced ER metadata configuration.</span></span>

    29. <span data-ttu-id="d903c-235">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-235">Select **Save**.</span></span>

<span data-ttu-id="d903c-236">A szükséges módon a meglévő metaadatok készletét az alkalmazásban kibővítheti.</span><span class="sxs-lookup"><span data-stu-id="d903c-236">As you require, you can extend the existing set of metadata in the application.</span></span> <span data-ttu-id="d903c-237">Ezt követően exportálhatja az alkalmazásból származó ER-metaadat konfiguráció új, kész verzióját, importálhatja a RCS-be, és frissítheti a konfigurált modell-hozzárendelési konfiguráció előfeltételeit, hogy az importált metaadat-konfiguráció egy új verziójára hivatkozzon.</span><span class="sxs-lookup"><span data-stu-id="d903c-237">You can then export the new completed version of the ER metadata configuration, import it into RCS, and update the prerequisites of the configured model mapping configuration to refer to a new version of the imported metadata configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="d903c-238">Ez a módszer az alkalmazás metaadatainak információinak beolvasására az egyetlen elérhető módszer a helyileg telepített alkalmazások esetében (azaz amikor a helyi üzleti adatok \[LBD\] vagy telephelyi, telepítési modell használata történik az alkalmazásban).</span><span class="sxs-lookup"><span data-stu-id="d903c-238">This method for getting information about application metadata is the only available method for applications that are locally deployed (that is, when a local business data \[LBD\], or on-premises, deployment model is used for the application).</span></span>

## <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="d903c-239">Alkalmazás-metaadatokhoz való hozzáférés összekapcsolt alkalmazások használatával</span><span class="sxs-lookup"><span data-stu-id="d903c-239">Access application metadata by using connected applications</span></span>

<span data-ttu-id="d903c-240">A következő eljárás bemutatja, hogy egy RCS felhasználó, aki rendelkezik a **Rendszergazda** vagy az **Elektronikus jelentéskészítési fejlesztő** szerepkörrel, megtervezhet egy új ER-modellhozzárendelést az alkalmazás metaadatainak segítségével.</span><span class="sxs-lookup"><span data-stu-id="d903c-240">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata of the application.</span></span> <span data-ttu-id="d903c-241">Alkalmazás-metaadatokhoz való hozzáférés online RCS összekapcsolt alkalmazások használatával történik</span><span class="sxs-lookup"><span data-stu-id="d903c-241">Application metadata will be accessed online by using RCS connected application.</span></span> <span data-ttu-id="d903c-242">A minta ER-modell-hozzárendelést a külföldi kereskedelmi tranzakciók elérése érdekében konfigurálja a program.</span><span class="sxs-lookup"><span data-stu-id="d903c-242">A sample ER model mapping will be configured to access foreign trade transactions.</span></span>

<span data-ttu-id="d903c-243">A jelen eljárás lépéseinek lezáráshoz először hajtsa végre az [Konfigurációszolgáltatók létrehozása és aktívként történő megjelölésük](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárás lépéseit az RCS-ben.</span><span class="sxs-lookup"><span data-stu-id="d903c-243">To complete this procedure, you must first complete the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure in RCS.</span></span> <span data-ttu-id="d903c-244">Ha még nem végezte el a témakör lépéseit [Alkalmazás-metaadatokhoz való hozzáférés ER-konfiguráció használatával](#access-application-metadata-by-using-an-er-configuration) korábban a témakörben, nyissa meg az [Elektronikus jelentéskészítési feladat-útmutatók a Dynamics 365 for Finance and Operations 8.1 alkalmazáshoz](https://go.microsoft.com/fwlink/?linkid=2082739) lapot a következő ER-konfigurációk letöltéséhez és előzetes helyi mentéséhez: **Foreign trade metadata.xml**, **Foreign trade model.xml** és **Foreign trade mapping.xml**.</span><span class="sxs-lookup"><span data-stu-id="d903c-244">If you haven't yet completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, go to [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page to download the following ER configuration files in advance and save them locally: **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml**.</span></span>


### <a name="get-required-er-configurations"></a><span data-ttu-id="d903c-245">Szükséges elektronikus jelentéskészítés-konfigurációk lekérése</span><span class="sxs-lookup"><span data-stu-id="d903c-245">Get required ER configurations</span></span>

<span data-ttu-id="d903c-246">Ha már végrehajtotta az [Alkalmazás-metaadatokhoz való hozzáférés ER-konfiguráció használatával](#access-application-metadata-by-using-an-er-configuration) eljárásban megadott lépéseket korábban a témakörben, akkor az aktuális RCS már rendelkezik az összes szükséges ER konfigurációval (külkereskedelmi metaadatok, modell-hozzárendelési konfigurációk) az aktuális ER-példányban.</span><span class="sxs-lookup"><span data-stu-id="d903c-246">If you've already completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, you already have all the required ER configurations (the foreign trade metadata, model, and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="d903c-247">Ebben az esetben ki lehet hagyni ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="d903c-247">In that case, you can skip this procedure.</span></span>

1. <span data-ttu-id="d903c-248">Ugorjon az **Összes munkaterület \> Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="d903c-248">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="d903c-249">Válassza a **Jelentéskészítési konfigurációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-249">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="d903c-250">Töltse be a **Foreign trade metadata.xml**, **Foreign trade model.xml** és **Foreign trade mapping.xml** konfigurációs fájlokat, a következő lépéseket ismételve meg mindegyikhez:</span><span class="sxs-lookup"><span data-stu-id="d903c-250">Load the **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml** configuration files repeating the following chain of steps for each of them:</span></span>

    1. <span data-ttu-id="d903c-251">**Exchange** kijelölése.</span><span class="sxs-lookup"><span data-stu-id="d903c-251">Select **Exchange**.</span></span>
    2. <span data-ttu-id="d903c-252">Kattintson a **Betöltés XML-fájlból** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d903c-252">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="d903c-253">**Tallózás** és fájl kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="d903c-253">Select **Browse**, and select a file.</span></span>
    4. <span data-ttu-id="d903c-254">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-254">Select **OK**.</span></span>

### <a name="register-the-connection-with-the-application"></a><span data-ttu-id="d903c-255">A kapcsolat regisztrálása az alkalmazással</span><span class="sxs-lookup"><span data-stu-id="d903c-255">Register the connection with the application</span></span>

1. <span data-ttu-id="d903c-256">Ugorjon az **Összes munkaterület \> Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="d903c-256">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="d903c-257">Kattintson az **Összekapcsolt alkalmazások** elemre.</span><span class="sxs-lookup"><span data-stu-id="d903c-257">Select **Connected applications**.</span></span>
3. <span data-ttu-id="d903c-258">Ellenőrizze, hogy a konfigurált alkalmazás Microsoft Azure alapú-e, és hogy a felhasználók számára elérhető-e általában a RCS.</span><span class="sxs-lookup"><span data-stu-id="d903c-258">Make sure that the configured application is based on Microsoft Azure, and that it is accessible in general to RCS users.</span></span> <span data-ttu-id="d903c-259">Az aktuális RCS felhasználó hozzá kell férjen a regisztráció alatt levő konfigurált alkalmazáshoz az alkalmazás felhasználóként olyan szerepkörben, amely lehetővé teszi az alkalmazás metaadatainak elérését.</span><span class="sxs-lookup"><span data-stu-id="d903c-259">The current RCS user must have access to the configured application being registered as a user of this application in a role that gives him or her privileges to access the application's metadata.</span></span>
4. <span data-ttu-id="d903c-260">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-260">Select **New**.</span></span>
5. <span data-ttu-id="d903c-261">A **Név** mezőbe írja be **MyConnectedApp** a csatlakoztatott pályázat neveként.</span><span class="sxs-lookup"><span data-stu-id="d903c-261">In the **Name** field, enter **MyConnectedApp** as the name of the connected application.</span></span>
6. <span data-ttu-id="d903c-262">Az **Alkalmazás** mezőben adja meg az alkalmazás URL-címét.</span><span class="sxs-lookup"><span data-stu-id="d903c-262">In the **Application** field, specify the URL of the application.</span></span>
7. <span data-ttu-id="d903c-263">A **Bérlő** mezőben adja meg az alkalmazás szolgáltatóját.</span><span class="sxs-lookup"><span data-stu-id="d903c-263">In the **Tenant** field, specify the provider of the application.</span></span>
8. <span data-ttu-id="d903c-264">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-264">Select **Save**.</span></span> 
9. <span data-ttu-id="d903c-265">Ha ellenőrzi a kapcsolatot a konfigurált alkalmazással, akkor a **Csatlakozás a távoli alkalmazáshoz** lapon kattintson a **Kattintson ide a kijelölt távoli alkalmazáshoz való kapcsolódáshoz** elemre.</span><span class="sxs-lookup"><span data-stu-id="d903c-265">When you check the connection to the configured application, on the **Connect to remote application** page, select the **Select here to connect to selected remote application** link.</span></span> 
10. <span data-ttu-id="d903c-266">Válassza a **Kapcsolat ellenőrzése** lehetőséget konfigurált alkalmazáshoz való hozzáférés ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="d903c-266">Select **Check connection** to validate access to the configured application.</span></span>
11. <span data-ttu-id="d903c-267">Válassza **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-267">Select **Close**.</span></span>

<span data-ttu-id="d903c-268">Amikor az eljárás befejeződött és a kapcsolat ellenőrzése sikeres volt, a program frissíti a verziószámot és a bérlő adatait a konfigurált alkalmazáshoz az aktuális rácsban.</span><span class="sxs-lookup"><span data-stu-id="d903c-268">After you complete this procedure and validation of the connection succeeds, the version and tenant details for the configured application will be updated in the current grid.</span></span>

### <a name="review-the-existing-model-mapping-configuration"></a><span data-ttu-id="d903c-269">Meglévő modell leképezés konfiguráció áttekintése</span><span class="sxs-lookup"><span data-stu-id="d903c-269">Review the existing model mapping configuration</span></span>

1. <span data-ttu-id="d903c-270">Ugorjon az **Összes munkaterület \> Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="d903c-270">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="d903c-271">Válassza a **Jelentéskészítési konfigurációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-271">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="d903c-272">A fán válassza ki a **Foreign trade model \> Foreign trade mapping** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-272">In the tree, select **Foreign trade model \> Foreign trade mapping**.</span></span>
4. <span data-ttu-id="d903c-273">Válassza az **Előfeltételek** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="d903c-273">Select the **Prerequisites** FasTab.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d903c-274">Ez a leképezés jelenleg a metaadat-konfigurációra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="d903c-274">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="d903c-275">A konfiguráció alkalmazás metaadatait a program felkínálja, miközben a modell hozzárendelését tervezik.</span><span class="sxs-lookup"><span data-stu-id="d903c-275">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

4. <span data-ttu-id="d903c-276">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-276">Select **Designer**.</span></span>
5. <span data-ttu-id="d903c-277">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-277">Select **Designer**.</span></span>
6. <span data-ttu-id="d903c-278">A fastruktúrában válassza ki a következőt: **Dynamics 365 for Operations \> Tábla rekordjai** csomópont.</span><span class="sxs-lookup"><span data-stu-id="d903c-278">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
7. <span data-ttu-id="d903c-279">Válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-279">Select **Add root**.</span></span>
8. <span data-ttu-id="d903c-280">A **Tábla** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d903c-280">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d903c-281">Ez a leképezés jelenleg a metaadat-konfigurációra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="d903c-281">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="d903c-282">A konfiguráció alkalmazás metaadatait a program felkínálja, miközben a modell hozzárendelését tervezik.</span><span class="sxs-lookup"><span data-stu-id="d903c-282">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

9. <span data-ttu-id="d903c-283">Válassza a **Mégse** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-283">Select **Cancel**.</span></span>

### <a name="assign-the-connected-application-to-a-model-mapping"></a><span data-ttu-id="d903c-284">Csatlakoztatott alkalmazás társítása a modell-hozzárendeléshez</span><span class="sxs-lookup"><span data-stu-id="d903c-284">Assign the connected application to a model mapping</span></span>

1. <span data-ttu-id="d903c-285">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="d903c-285">Select **Edit**.</span></span>
2. <span data-ttu-id="d903c-286">A **Csatlakoztatott alkalmazás mezőben** válassza ki a **MyConnectedApp** alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="d903c-286">In the **Connected application field**, select the **MyConnectedApp** application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d903c-287">Ez a leképezés a kiválasztott összekapcsolt alkalmazás metaadataira vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="d903c-287">This mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="d903c-288">Ha ugyanaz a leképezés a metaadatok konfigurációját és a kapcsolódó alkalmazást egyszerre hivatkozza, a program a csatlakoztatott alkalmazás metaadatait fogja használni.</span><span class="sxs-lookup"><span data-stu-id="d903c-288">If a mapping refers to the metadata configuration and the connected application at the same time, the metadata of the connected application will be used.</span></span>

3. <span data-ttu-id="d903c-289">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-289">Select **Designer**.</span></span>
4. <span data-ttu-id="d903c-290">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-290">Select **Designer**.</span></span>
5. <span data-ttu-id="d903c-291">A fastruktúrában válassza ki a következőt: **Dynamics 365 for Operations \> Tábla rekordjai** csomópont.</span><span class="sxs-lookup"><span data-stu-id="d903c-291">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
6. <span data-ttu-id="d903c-292">Válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="d903c-292">Select **Add root**.</span></span>
7. <span data-ttu-id="d903c-293">A **Tábla** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d903c-293">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d903c-294">Ennél a pontnál már több, mint két alkalmazástábla szerepelt, mivel ez a leképezés a társított alkalmazás összes metaadatát felhasználja.</span><span class="sxs-lookup"><span data-stu-id="d903c-294">At this point, more than two application tables are offered, because this mapping uses all the metadata of the connected application that has been assigned to it.</span></span>

8. <span data-ttu-id="d903c-295">Válassza a **Mégse** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d903c-295">Select **Cancel**.</span></span>
9. <span data-ttu-id="d903c-296">A **Validálás**kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="d903c-296">Select **Validate**.</span></span>

<span data-ttu-id="d903c-297">Az adatmodell elemeit az adatforrások olyan cikkeihez társítottuk, amelyek leírása az ehhez a leképezéshez hozzárendelt összekapcsolt alkalmazás metaadatainak részleteivel történik.</span><span class="sxs-lookup"><span data-stu-id="d903c-297">You've now bound elements of the data model to items of the data sources that are described by using details of the metadata of the connected application that has been assigned to this mapping.</span></span>

<span data-ttu-id="d903c-298">Ha egy másik verziójú alkalmazás metaadatainak használatával kell értékelnie ezt a modellt, akkor regisztráljon egy másik összekapcsolt alkalmazást, rendelje hozzá a modell hozzárendeléséhez, és ellenőrizze az új metaadatokkal összevetve.</span><span class="sxs-lookup"><span data-stu-id="d903c-298">When you must evaluate this model mapping by using the metadata of a different version of the application, register another connected application, assign it to this model mapping, and validate it against the new metadata.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d903c-299">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d903c-299">Additional resources</span></span>

<span data-ttu-id="d903c-300">Azt is megteheti, hogy lejátssza az **RCS-ben felhasználandó alkalmazás-metaadatok előkészítése** feladat-útmutatót az alkalmazásban, valamint az **Alkalmazás-metaadatokhoz való hozzáférés egy ER-konfiguráció használatával** és az **RCS és a hozzáférés modulban. az alkalmazás metaadatainak a csatlakoztatott alkalmazások** feladat-útmutatókat az RCS-ben.</span><span class="sxs-lookup"><span data-stu-id="d903c-300">Alternatively, you can play the **Prepare application metadata that can be used in RCS** task guide in the application as as well as the **Access application metadata by using an ER configuration** and **Access application metadata by using connected applications** task guides in RCS.</span></span> <span data-ttu-id="d903c-301">Ezeket a feladat-útmutatókat az [Elektronikus jelentéskészítési feladat-útmutatók a Dynamics 365 for Finance and Operations 8.1 alkalmazáshoz](https://go.microsoft.com/fwlink/?linkid=2082739) oldalról lehet letölteni.</span><span class="sxs-lookup"><span data-stu-id="d903c-301">These task guides can be downloaded from the [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page.</span></span>
