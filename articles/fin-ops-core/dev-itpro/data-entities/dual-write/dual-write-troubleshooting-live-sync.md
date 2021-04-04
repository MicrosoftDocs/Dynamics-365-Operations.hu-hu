---
title: Élő szinkronizálási problémák elhárítása
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók az élő szinkronizálás problémái.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: b40b71eb45ae5a95a732c9554356afcddecb750e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566813"
---
# <a name="troubleshoot-live-synchronization-issues"></a><span data-ttu-id="f9404-103">Élő szinkronizálási problémák elhárítása</span><span class="sxs-lookup"><span data-stu-id="f9404-103">Troubleshoot live synchronization issues</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="f9404-104">Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="f9404-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="f9404-105">Pontosabban, olyan információkat tartalmaz, amelyek segítségével javíthatók az élő szinkronizálás problémái.</span><span class="sxs-lookup"><span data-stu-id="f9404-105">Specifically, it provides information that can help you fix issues with live synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9404-106">Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik.</span><span class="sxs-lookup"><span data-stu-id="f9404-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="f9404-107">Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.</span><span class="sxs-lookup"><span data-stu-id="f9404-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-row-in-a-finance-and-operations-app"></a><span data-ttu-id="f9404-108">Az élő szinkronizálás 403 Tiltott hibát jelez, amikor létrehoz egy sort egy Finance and Operations alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="f9404-108">Live synchronization throws a 403 Forbidden error when you create a row in a Finance and Operations app</span></span>

<span data-ttu-id="f9404-109">A következő hibaüzenet jelenhet meg, amikor létrehoz egy sort a Finance and Operations alkalmazásban:</span><span class="sxs-lookup"><span data-stu-id="f9404-109">You might receive the following error message when you create a row in a Finance and Operations app:</span></span>

<span data-ttu-id="f9404-110">*\[{\\"hiba\\":{\\"kód\\":\\"0x80072560\\",\\"üzenet\\":\\„A felhasználó nem a szervezet tagja\\"}}\], A távoli kiszolgáló a következő hibát küldte vissza: (403) Tiltott.”}}".*</span><span class="sxs-lookup"><span data-stu-id="f9404-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"The user is not a member of the organization.\\"}}\], The remote server returned an error: (403) Forbidden."}}".*</span></span>

<span data-ttu-id="f9404-111">A hiba elhárításához kövesse a [Rendszerkövetelmények és előfeltételek](requirements-and-prerequisites.md) szakasz lépéseit.</span><span class="sxs-lookup"><span data-stu-id="f9404-111">To fix the issue, follow the steps in [System requirements and prerequisites](requirements-and-prerequisites.md).</span></span> <span data-ttu-id="f9404-112">Ezeknek a lépéseknek a végrehajtásához Dataverse szolgáltatásban létrehozott kettős írású felhasználóknak rendelkezniük kell a rendszergazda szerepkörrel.</span><span class="sxs-lookup"><span data-stu-id="f9404-112">To complete those steps, the dual-write application users who are created in Dataverse must have the system admin role.</span></span> <span data-ttu-id="f9404-113">Az alapértelmezett tulajdonos csapatnak is rendelkeznie kell a rendszeradminisztrátori szerepkörrel.</span><span class="sxs-lookup"><span data-stu-id="f9404-113">The default owning team must also have the system admin role.</span></span>

## <a name="live-synchronization-for-any-table-consistently-throws-a-similar-error-when-you-create-a-row-in-a-finance-and-operations-app"></a><span data-ttu-id="f9404-114">Egy tábla élő szinkronizálása folyamatosan hasonló hibát ad vissza, amikor egy sort hoz létre a Finance and Operations alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="f9404-114">Live synchronization for any table consistently throws a similar error when you create a row in a Finance and Operations app</span></span>

<span data-ttu-id="f9404-115">**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="f9404-115">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="f9404-116">Előfordulhat, hogy a következőhöz hasonló hibaüzenet jelenik meg minden alkalommal, amikor megpróbálja menteni a táblák adatait egy Finance and Operations alkalmazásban:</span><span class="sxs-lookup"><span data-stu-id="f9404-116">You might receive an error message like the following every time that you try to save table data in a Finance and Operations app:</span></span>

<span data-ttu-id="f9404-117">*A módosítások nem menthetők az adatbázisba. A munkaegység nem tudja véglegesíteni a tranzakciót. Nem lehet adatokat írni az entitás értékesítési mértékegységeibe. A UnitOfMeasureEntity írása hibaüzenettel megszakadt, nem lehet szinkronizálni az entitás értékesítési mértékegységeivel.*</span><span class="sxs-lookup"><span data-stu-id="f9404-117">*Cannot save the changes to the database. Unit of Work can not commit transaction. Unable to write data to entity uoms. Writes to UnitOfMeasureEntity failed with error message Unable to sync with entity uoms.*</span></span>

<span data-ttu-id="f9404-118">A hiba elhárítása érdekében gondoskodni kell arról, hogy az előfeltételnek számító hivatkozási adatok mind a Finance and Operations alkalmazásban, mind a Dataverse szolgáltatásban létezzenek.</span><span class="sxs-lookup"><span data-stu-id="f9404-118">To fix the issue, you must make sure that the prerequisite reference data exists in both the Finance and Operations app and Dataverse.</span></span> <span data-ttu-id="f9404-119">Ha például az Finance and Operations alkalmazásban lévő vevő egy adott vevőcsoport tagja, győződjön meg arról, hogy a vevő csoport létezik a Dataverse szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="f9404-119">For example, if the customer that you're in the Finance and Operations app belongs to a specific customer group, make sure that the customer group exists in Dataverse.</span></span>

<span data-ttu-id="f9404-120">Ha mindkét oldalon szerepel az adat, és megerősítette, hogy a probléma nem az adatokkal kapcsolatos kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f9404-120">If data exists on both sides, and you've confirmed that the issue isn't data-related, follow these steps.</span></span>

1. <span data-ttu-id="f9404-121">A kapcsolódó tábla leállítása.</span><span class="sxs-lookup"><span data-stu-id="f9404-121">Stop the related table.</span></span>
2. <span data-ttu-id="f9404-122">Jelentkezzen be az Finance and Operations alkalmazásba, és győződjön meg arról, hogy az DualWriteProjectConfiguration és a DualWriteProjectFieldConfiguration táblákban léteznek sorok a hibát jelző táblákhoz.</span><span class="sxs-lookup"><span data-stu-id="f9404-122">Sign in to the Finance and Operations app, and make sure that rows for the failing table exist in the DualWriteProjectConfiguration and DualWriteProjectFieldConfiguration tables.</span></span> <span data-ttu-id="f9404-123">Itt megtekintheti például, hogy a lekérdezés hogyan néz ki, ha a **Vevők** tábla hibás.</span><span class="sxs-lookup"><span data-stu-id="f9404-123">For example, here is what the query looks like if the **Customers** table is failing.</span></span>

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. <span data-ttu-id="f9404-124">Ha a táblahozzárendelés leállítása után is léteznek sorok a hibás táblához, akkor törölje a hibás táblához kapcsolódó sorokat.</span><span class="sxs-lookup"><span data-stu-id="f9404-124">If there are rows for the failing table even after you stop the table mapping, delete the rows that are related to the failing table.</span></span> <span data-ttu-id="f9404-125">Jegyezze fel a DualWriteProjectConfiguration tábla **projektnév** oszlopát, és kérje le a sort a DualWriteProjectFieldConfiguration táblában a projektnév használatával, a sor törléséhez.</span><span class="sxs-lookup"><span data-stu-id="f9404-125">Make a note of the **projectname** column in the DualWriteProjectConfiguration table, and fetch the row in the DualWriteProjectFieldConfiguration table by using the project name to delete the row.</span></span>
4. <span data-ttu-id="f9404-126">Indítsa el az tábla-hozzárendelést.</span><span class="sxs-lookup"><span data-stu-id="f9404-126">Start the table mapping.</span></span> <span data-ttu-id="f9404-127">Ellenőrizze, hogy az adatok szinkronizálása probléma nélkül történik-e.</span><span class="sxs-lookup"><span data-stu-id="f9404-127">Validate whether the data is synced without any issues.</span></span>

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a><span data-ttu-id="f9404-128">Olvasási vagy írási jogosultsági hibák adatok létrehozása során a Finance and Operations alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="f9404-128">Handle read or write privilege errors when you create data in a Finance and Operations app</span></span>

<span data-ttu-id="f9404-129">Előfordulhat, hogy a következő példához hasonló „Hibás kérés” hibaüzenet jelenik meg, amikor egy Finance and Operations alkalmazásban hoz létre adatokat.</span><span class="sxs-lookup"><span data-stu-id="f9404-129">You might receive a "Bad Request" error message that resembles the following example when you create data in a Finance and Operations app.</span></span>

![Példa a Hibás kérés hibaüzenetére](media/error_record_id_source.png)

<span data-ttu-id="f9404-131">A hiba elhárításához a hiányzó jogosultság engedélyezéséhez társítania kell a megfelelő biztonsági szerepkört a megfeleltetett Dynamics 365 Sales vagy Dynamics 365 Customer Service üzleti egység csapatához a hiányzó jogosultság engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="f9404-131">To fix the issue, you must assign the correct security role to the team of the mapped Dynamics 365 Sales or Dynamics 365 Customer Service business unit to enable the missing privilege.</span></span>

1. <span data-ttu-id="f9404-132">A Finance and Operations alkalmazásban keresse meg azt az üzleti egységet, amely hozzá van rendelve az Adatintegrációs csatlakozókészletben.</span><span class="sxs-lookup"><span data-stu-id="f9404-132">In the Finance and Operations app, find the business unit that is mapped in the Data Integration connection set.</span></span>

    ![Szervezet leképezése](media/mapped_business_unit.png)

2. <span data-ttu-id="f9404-134">Jelentkezzen be a környezetbe a modellvezérelt alkalmazásban s Dynamics 365-ban, nyissa meg a **Beállítások \> Biztonság** lehetőséget, és keresse meg a leképezett üzleti egység csapatát.</span><span class="sxs-lookup"><span data-stu-id="f9404-134">Sign in to the environment in the model-driven app in Dynamics 365, navigate to **Setting \> Security**, and find the team of the mapped business unit.</span></span>

    ![A hozzárendelt üzleti egység csapata](media/setting_security_page.png)

3. <span data-ttu-id="f9404-136">Nyissa meg a csapat lapját szerkesztésre, majd válassza a **Szerepkörök kezelése** parancsot, a **Csapat szerepköreinek kezelése** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f9404-136">Open the page for the team for editing, and then select **Manage roles** to open the **Manage Team Roles** dialog box.</span></span>

    ![Szerepkörök kezelése gomb](media/manage_team_roles.png)

4. <span data-ttu-id="f9404-138">Rendelje hozzá a megfelelő táblákhoz az olvasási/írási jogosultsággal rendelkező szerepkört, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f9404-138">Assign the role that has the read/write privilege for the relevant tables, and then select **OK**.</span></span>

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a><span data-ttu-id="f9404-139">A szinkronizálási problémák javítása egy környezetben egy közelmúltban módosított Dataverse környezetben</span><span class="sxs-lookup"><span data-stu-id="f9404-139">Fix synchronization issues in an environment that has a recently changed Dataverse environment</span></span>

<span data-ttu-id="f9404-140">**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="f9404-140">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="f9404-141">A következő hibaüzenet jelenhet meg, amikor adatot hoz létre a Finance and Operations alkalmazásban:</span><span class="sxs-lookup"><span data-stu-id="f9404-141">You might receive the following error message when you create data in a Finance and Operations app:</span></span>

<span data-ttu-id="f9404-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Nem sikerült adatcsomagot generálni az CustCustomerV3Entity entitáshoz**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Adatcsinag létrehozása sikertelen érvénytelen URI hibával: Az URI üres."}\],"isErrorCountUpdated":true}*</span><span class="sxs-lookup"><span data-stu-id="f9404-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable to generate payload for entity CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Payload creation failed with error Invalid URI: The URI is empty."}\],"isErrorCountUpdated":true}*</span></span>

<span data-ttu-id="f9404-143">Így néz ki a hiba a Dynamics 365 egy modellvezérelt alkalmazásában:</span><span class="sxs-lookup"><span data-stu-id="f9404-143">Here is what the error looks like in the model-driven app in Dynamics 365:</span></span>

<span data-ttu-id="f9404-144">*Váratlan hiba történt az ISV-kódból. (ErrorType = ClientError) Váratlan kivétel a bővítménytől (végrehajtás): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: nem sikerült feldolgozni az entitás fiókját (Egy kapcsolódási kísérlet nem sikerült, mert a kapcsolódó fél egy adott időt követően nem válaszolt helyesen, vagy a létrejött kapcsolat megszakadt, mert a csatlakoztatott állomás nem válaszolt*</span><span class="sxs-lookup"><span data-stu-id="f9404-144">*An unexpected error occurred from ISV code. (ErrorType = ClientError) Unexpected exception from plug-in (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: failed to process entity account - (A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond*</span></span>

<span data-ttu-id="f9404-145">Ez a hiba akkor fordul, ha a Dataverse környezet helytelenül van alaphelyzetbe állítva, amikor adatokat próbál létrehozni a Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="f9404-145">This error occurs when the Dataverse environment is incorrectly reset at the same time that you try to create data in the Finance and Operations app.</span></span>

<span data-ttu-id="f9404-146">Egy hiba javításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f9404-146">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="f9404-147">Jelentkezzen be a Finance and Operations virtuális gépére (VM), nyissa meg az SQL Server Management Studio (SSMS) szolgáltatást, és keressen sorokat a DUALWRITEPROJECTCONFIGURATIONENTITY táblában, ahol **internalentityname** egyenlő **Customers V3** és **externalentityname** egyenlő **accounts**.</span><span class="sxs-lookup"><span data-stu-id="f9404-147">Sign in to the Finance and Operations virtual machine (VM), open SQL Server Management Studio (SSMS), and look for rows in the DUALWRITEPROJECTCONFIGURATIONENTITY table where **internalentityname** equals **Customers V3** and **externalentityname** equals **accounts**.</span></span> <span data-ttu-id="f9404-148">A lekérdezés így néz ki.</span><span class="sxs-lookup"><span data-stu-id="f9404-148">Here is what the query looks like.</span></span>

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. <span data-ttu-id="f9404-149">A előző lekérdezés eredményéből származó projektnév használható a következő elkérdezés futtatásához.</span><span class="sxs-lookup"><span data-stu-id="f9404-149">Use the project name from the results of the previous query to run the following query.</span></span>

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. <span data-ttu-id="f9404-150">Ügyeljen arra, hogy az **externalenvironmentURL** oszlop helyes Dataverse vagy alkalmazás URL-címmel rendelkezzen.</span><span class="sxs-lookup"><span data-stu-id="f9404-150">Make sure that the **externalenvironmentURL** column has the correct Dataverse or app URL.</span></span> <span data-ttu-id="f9404-151">Törölje a megfelelő Dataverse URL-címre mutató ismétlődő sorokat.</span><span class="sxs-lookup"><span data-stu-id="f9404-151">Delete any duplicate rows that point to the wrong Dataverse URL.</span></span> <span data-ttu-id="f9404-152">Törölje a megfelelő sorokat a DUALWRITEPROJECTFIELDCONFIGURATION és DUALWRITEPROJECTCONFIGURATION táblákból.</span><span class="sxs-lookup"><span data-stu-id="f9404-152">Delete the corresponding rows in the DUALWRITEPROJECTFIELDCONFIGURATION and DUALWRITEPROJECTCONFIGURATION tables.</span></span>
4. <span data-ttu-id="f9404-153">Állítsa le az táblák hozzárendelését, majd indítsa újra</span><span class="sxs-lookup"><span data-stu-id="f9404-153">Stop the table mapping, and then restart it</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]