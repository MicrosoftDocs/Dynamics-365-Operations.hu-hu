---
title: Problémák elhárítása a kezdeti beállításkor
description: Ez a témakör olyan információkat tartalmaz, amelyek segítségével kijavíthatja azokat a problémákat, amelyek a kettős írásos integráció kezdeti beállításakor merülhetnek fel.
author: RamaKrishnamoorthy
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
ms.openlocfilehash: 9ffb1378eccf175fbb9bd84228f91ba606125a63
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753990"
---
# <a name="troubleshoot-issues-during-initial-setup"></a><span data-ttu-id="b28ef-103">Problémák elhárítása a kezdeti beállításkor</span><span class="sxs-lookup"><span data-stu-id="b28ef-103">Troubleshoot issues during initial setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="b28ef-104">Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="b28ef-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="b28ef-105">Ez a témakör pontosabban olyan információkat tartalmaz, amelyek segítségével kijavíthatja azokat a problémákat, amelyek a kettős írásos integráció kezdeti beállításakor merülhetnek fel.</span><span class="sxs-lookup"><span data-stu-id="b28ef-105">Specifically, it provides information that can help you fix issues that might occur during the initial setup of dual-write integration.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b28ef-106">Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik.</span><span class="sxs-lookup"><span data-stu-id="b28ef-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="b28ef-107">Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.</span><span class="sxs-lookup"><span data-stu-id="b28ef-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a><span data-ttu-id="b28ef-108">Egy Finance and Operations alkalmazás nem kapcsolható a Dataverse szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="b28ef-108">You can't link a Finance and Operations app to Dataverse</span></span>

<span data-ttu-id="b28ef-109">**Szükséges szerepkör a Kettős írás beállításához:** Rendszergazda a Finance and Operations alkalmazásokban és Dataverse alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="b28ef-109">**Required role to set up dual-write:** System administrator in Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="b28ef-110">A **Hivatkozás beállítása a Dataverse szolgáltatáshoz** oldal hibáit általában hiányos beállítás vagy jogosultsági problémák okozzák.</span><span class="sxs-lookup"><span data-stu-id="b28ef-110">Errors on the **Setup link to Dataverse** page are usually caused by incomplete setup or permissions issues.</span></span> <span data-ttu-id="b28ef-111">Győződjön meg arról, hogy a teljes állapot-ellenőrzés megfelelt-e a **Hivatkozás beállítása a Dataverse szolgáltatáshoz** oldalon, az alábbi ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="b28ef-111">Make sure that the whole health check passes on the **Setup link to Dataverse** page, as shown in the following illustration.</span></span> <span data-ttu-id="b28ef-112">A kettős írás nem kapcsolható össze, hacsak a teljes állapot-ellenőrzés meg nem felelt.</span><span class="sxs-lookup"><span data-stu-id="b28ef-112">You can't link dual-write unless the whole health check passes.</span></span>

![Sikeres állapot-ellenőrzés](media/health_check.png)

<span data-ttu-id="b28ef-114">A Finance and Operations és Dataverse környezetek összekapcsolásához Azure AD bérlői rendszergazdai hitelesítő adatok szükségesek.</span><span class="sxs-lookup"><span data-stu-id="b28ef-114">You must have Azure AD tenant admin credentials to link the Finance and Operations and Dataverse environments.</span></span> <span data-ttu-id="b28ef-115">A környezetek összekapcsolása után a felhasználók a saját fiókjaik hitelesítő adataival jelentkezhetnek be, és módosíthatják a meglévő táblák leképezését.</span><span class="sxs-lookup"><span data-stu-id="b28ef-115">After you link the environments, users can sign in by using their account credentials and update an existing table map.</span></span>

## <a name="error-when-you-open-the-link-to-dataverse-page"></a><span data-ttu-id="b28ef-116">Hiba a Hivatkozás a Dataverse szolgáltatáshoz lap megnyitásakor</span><span class="sxs-lookup"><span data-stu-id="b28ef-116">Error when you open the Link to Dataverse page</span></span>

<span data-ttu-id="b28ef-117">**A hiba javításához szükséges hitelesítő adatok:** Azure AD bérlői rendszergazda</span><span class="sxs-lookup"><span data-stu-id="b28ef-117">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="b28ef-118">A következő hibaüzenet jelenhet meg a **Hivatkozás a Dataverse szolgáltatáshoz** oldal megnyitásakor egy Finance and Operations alkalmazásban:</span><span class="sxs-lookup"><span data-stu-id="b28ef-118">You might receive the following error message when you open the **Link to Dataverse** page in a Finance and Operations app:</span></span>

<span data-ttu-id="b28ef-119">*A válasz állapotkódja sikertelenséget jelez: 404 (Nem található).*</span><span class="sxs-lookup"><span data-stu-id="b28ef-119">*Response status code does not indicate success: 404 (Not Found).*</span></span>

<span data-ttu-id="b28ef-120">Ez a hiba akkor fordul elő, ha a hozzájárulási lépést nem hajtották végre.</span><span class="sxs-lookup"><span data-stu-id="b28ef-120">This error occurs when the consent step hasn't been completed.</span></span> <span data-ttu-id="b28ef-121">A hozzájárulási lépés végrehajtásának ellenőrzéséhez jelentkezzen be a portal.Azure.com oldalra az Azure AD bérlői rendszergazdai fiókkal, és megtekintheti, hogy a **33976c19-1db5-4c02-810e-c243db79efde** azonosítóval rendelkező külső alkalmazás megjelenik-e az Azure AD **Vállalati alkalmazások** listájában.</span><span class="sxs-lookup"><span data-stu-id="b28ef-121">To validate whether the consent step has been completed, sign in to portal.Azure.com by using the Azure AD tenant admin account, and see whether the third-party app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** appears in the Azure AD **Enterprise applications** list.</span></span> <span data-ttu-id="b28ef-122">Ha nem, akkor meg kell adnia az alkalmazás hozzájárulását.</span><span class="sxs-lookup"><span data-stu-id="b28ef-122">If it doesn't, you must provide app consent.</span></span>

<span data-ttu-id="b28ef-123">Az alkalmazás-hozzájárulás biztosításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b28ef-123">To provide app consent, follow these steps.</span></span>

1. <span data-ttu-id="b28ef-124">Nyissa meg a következő URL-címet a rendszergazdai jogosultságok segítségével.</span><span class="sxs-lookup"><span data-stu-id="b28ef-124">Open the following URL by using your admin credentials.</span></span> <span data-ttu-id="b28ef-125">Meg kell adni a jóváhagyást.</span><span class="sxs-lookup"><span data-stu-id="b28ef-125">You should be prompted for consent.</span></span>

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. <span data-ttu-id="b28ef-126">Válassza az **Elfogadás** lehetőséget, ha hozzájárulását szeretné adni az **33976c19-1db5-4c02-810e-c243db79efde** azonosítóval rendlekező alkalmazás telepítésére az Ön bérlőjébe.</span><span class="sxs-lookup"><span data-stu-id="b28ef-126">Select **Accept** to indicate that you're giving your consent to install the app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** in your tenant.</span></span>

    > [!TIP]
    > <span data-ttu-id="b28ef-127">Ez az alkalmazás szükséges a Dataverse és a Finance and Operations alkalmazások összekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="b28ef-127">This app is required to link Dataverse and Finance and Operations apps.</span></span> <span data-ttu-id="b28ef-128">Ha baj van ezzel a lépéssel, akkor nyissa meg a böngészőprogramot rejtett módban (a Google Chrome-ban) vagy az InPrivate-módban (a Microsoft Edge-ben).</span><span class="sxs-lookup"><span data-stu-id="b28ef-128">If you have trouble with this step, open your browser in incognito mode (in Google Chrome) or InPrivate mode (in Microsoft Edge).</span></span>

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a><span data-ttu-id="b28ef-129">Győződjön meg arról, hogy a vállalati adatokat és a kettős írású csapatokat az összekapcsolás során helyesen állították be</span><span class="sxs-lookup"><span data-stu-id="b28ef-129">Verify that company data and dual-write teams are set up correctly during linking</span></span>

<span data-ttu-id="b28ef-130">A kettős írás helyes működésének biztosítása érdekében a konfiguráció során kiválasztott vállalatok a Dataverse-környezetben jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="b28ef-130">To ensure that dual-write works correctly, the companies that you select during configuration are created in the Dataverse environment.</span></span> <span data-ttu-id="b28ef-131">Alapértelmezés szerint ezek a vállalatok csak olvashatók, az **IsDualWriteEnable** tulajdonság pedig **igaz** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="b28ef-131">By default, these companies are read-only, and the **IsDualWriteEnable** property is set to **True**.</span></span> <span data-ttu-id="b28ef-132">Ezenkívül létrejön az alapértelmezett részleg tulajdonosa és csoportja, amely tartalmazza a vállalat nevét.</span><span class="sxs-lookup"><span data-stu-id="b28ef-132">In addition, the default owning business unit owner and team are created and include the company name.</span></span> <span data-ttu-id="b28ef-133">A leképezések engedélyezése előtt győződjön meg róla, hogy a csoport alapértelmezett tulajdonosa meg van adva.</span><span class="sxs-lookup"><span data-stu-id="b28ef-133">Before you enable the maps, verify that the default team owner is specified.</span></span> <span data-ttu-id="b28ef-134">A **Vállalatok (CDM\_vállalat)** tábla megkereséséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b28ef-134">To find the **Companies (CDM\_Company)** table, follow these steps.</span></span>

1. <span data-ttu-id="b28ef-135">A Dynamics 365 modellvezérelt alkalmazásában válassza ki a szűrőt a jobb felső sarokban.</span><span class="sxs-lookup"><span data-stu-id="b28ef-135">In the model-driven app in Dynamics 365, select the filter in the upper-right corner.</span></span>
2. <span data-ttu-id="b28ef-136">A legördülő listán válassza a **Vállalat** elemet.</span><span class="sxs-lookup"><span data-stu-id="b28ef-136">In the drop-down list, select **Company**.</span></span>
3. <span data-ttu-id="b28ef-137">Az eredmények megtekintéséhez válassza a **Futtatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="b28ef-137">Select **Run** to see the results.</span></span>
4. <span data-ttu-id="b28ef-138">Válassza ki azt a vállalatot, amely a kettős írás konfigurálása során összekapcsolódott.</span><span class="sxs-lookup"><span data-stu-id="b28ef-138">Select the company that was linked when you configured dual-write.</span></span>
5. <span data-ttu-id="b28ef-139">Győződjön meg arról, hogy az **Alapértelmezett tulajdonos csoport** oszlopban szerepel érték.</span><span class="sxs-lookup"><span data-stu-id="b28ef-139">Verify that the **Default owning team** column has a value.</span></span> <span data-ttu-id="b28ef-140">A következő ábrán az **Alapértelmezett tulajdonos csoport** oszlop értéke **USMF kettős írás**.</span><span class="sxs-lookup"><span data-stu-id="b28ef-140">In the following illustration, the **Default owning team** column is set to **USMF Dual Write**.</span></span>

    ![Az alapértelmezett tulajdonos csoport ellenőrzése](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a><span data-ttu-id="b28ef-142">A kettős íráshoz összekapcsolható táblák vagy vállalatok számához tartozó korlát megkeresése</span><span class="sxs-lookup"><span data-stu-id="b28ef-142">Find the limit on the number of legal tables or companies that can be linked for dual-write</span></span>

<span data-ttu-id="b28ef-143">A következő hibaüzenetek jelenhetnek meg a leképezések engedélyezésekor:</span><span class="sxs-lookup"><span data-stu-id="b28ef-143">You might receive the following error message when you try to enable maps:</span></span>

<span data-ttu-id="b28ef-144">*Kettős írási hiba - A beépülő modul regisztrációja sikertelen: \[(Nem sikerült a projekt DWM partícióleképezésének lekérése-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Hiba: Túllépte a DWM-leképezések maxiálisan megengedett partícióinak számár-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], Egy vagy több hiba történt.*</span><span class="sxs-lookup"><span data-stu-id="b28ef-144">*Dual write failure - Plugin registration failed: \[(Unable to get partition map for project DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Error Exceeds the maximum partitions allowed for mapping DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], One or more errors occurred.*</span></span>

<span data-ttu-id="b28ef-145">A környezetek összekapcsolásánál érvényes aktuális korlát körülbelül 40 jogi tábla.</span><span class="sxs-lookup"><span data-stu-id="b28ef-145">The current limit when you link the environments is approximately 40 legal tables.</span></span> <span data-ttu-id="b28ef-146">Ez a hiba akkor fordul elő, ha engedélyezi a leképezéseket, és több mint 40 jogi tábla kapcsolódik a környezethez.</span><span class="sxs-lookup"><span data-stu-id="b28ef-146">This error occurs if you try to enable maps, and more than 40 legal tables are linked between the environments.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]