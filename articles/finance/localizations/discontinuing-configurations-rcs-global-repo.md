---
title: Konfigurációk megszüntetése az RCS Globális adattárban
description: Ez a témakör leírja, hogyan lehet megszüntetni a konfigurációkat az RCS Globális adattárban.
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 2bd22e991de376cfd93f75158f1f29716d2559e1
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018733"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a><span data-ttu-id="77c6a-103">Konfigurációk megszüntetése az RCS Globális adattárban</span><span class="sxs-lookup"><span data-stu-id="77c6a-103">Discontinue configurations in the RCS Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="77c6a-104">Ez a témakör leírja, hogyan lehet megszüntetni a konfigurációt az RCS Globális adattárban.</span><span class="sxs-lookup"><span data-stu-id="77c6a-104">This topic describes how to discontinue configuration in the RCS Global repository.</span></span> <span data-ttu-id="77c6a-105">Korábban csak olyan konfigurációk voltak törölhetők, amelyekre már nem volt szükség.</span><span class="sxs-lookup"><span data-stu-id="77c6a-105">Previously, it was possible only to delete configurations that were no longer required.</span></span> <span data-ttu-id="77c6a-106">Most azonban egy kiadott konfigurációt **Kifutott** állapotúként jelölhet meg az RCS Globális adattárban.</span><span class="sxs-lookup"><span data-stu-id="77c6a-106">However now you can mark a released configuration as **Discontinued** in the RCS Global repository.</span></span> <span data-ttu-id="77c6a-107">Ezzel a funkcióval a következőkre is lehetőség nyílik:</span><span class="sxs-lookup"><span data-stu-id="77c6a-107">With this functionality, you can also do the following:</span></span> 
 
 - <span data-ttu-id="77c6a-108">Előzetes értesítés biztosítása egy konfiguráció tervezett megszüntetése esetén.</span><span class="sxs-lookup"><span data-stu-id="77c6a-108">Provide up front notifications when a configuration is planned to be discontinued.</span></span>
 - <span data-ttu-id="77c6a-109">Adja hozzá a cserekonfigurációra vonatkozó részleteket.</span><span class="sxs-lookup"><span data-stu-id="77c6a-109">Include applicable details about the replacement configuration.</span></span>
 - <span data-ttu-id="77c6a-110">Állítsa be a **Támogatás határideje** dátumát az adott konfigurációnál, hogy tájékoztassa a felhasználót a konfiguráció megszűnéséről.</span><span class="sxs-lookup"><span data-stu-id="77c6a-110">Set a **Supported until** date for the specific configuration to inform the user when it will be discontinued.</span></span>

<span data-ttu-id="77c6a-111">Ha megszüntet egy konfigurációs verziót, a következő opcionális adatokat adhatja meg:</span><span class="sxs-lookup"><span data-stu-id="77c6a-111">When you discontinue a configuration version, you can specify the following optional information:</span></span>

  - <span data-ttu-id="77c6a-112">**Helyettesítés konfigurációja**</span><span class="sxs-lookup"><span data-stu-id="77c6a-112">**Replacement configuration**</span></span>
  - <span data-ttu-id="77c6a-113">**Cserekonfiguráció verziója**</span><span class="sxs-lookup"><span data-stu-id="77c6a-113">**Replacement configuration version**</span></span>
  - <span data-ttu-id="77c6a-114">**Szabadszöveges megjegyzés**: Ebben a mezőben dokumentációhivatkozásokat vagy referenciákat adhat meg.</span><span class="sxs-lookup"><span data-stu-id="77c6a-114">**Free text note**: Use this field to provide documentation links or references</span></span>
  - <span data-ttu-id="77c6a-115">**Támogatás határideje**: Ez a mező azt a javasolt dátumot jeleníti meg, ameddig az aktuális konfiguráció/verzió támogatott lesz.</span><span class="sxs-lookup"><span data-stu-id="77c6a-115">**Supported until**: This field provides the proposed date up to which the current configuration/version will be supported.</span></span> <span data-ttu-id="77c6a-116">Ezt a dátumot manuálisan kell frissíteni.</span><span class="sxs-lookup"><span data-stu-id="77c6a-116">This date must be updated manually.</span></span>
  
<span data-ttu-id="77c6a-117">A konfiguráció megszüntetéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="77c6a-117">To discontinue the configuration, complete the following steps.</span></span> 

1. <span data-ttu-id="77c6a-118">Az **Összes verzió** **Igen** értékre állításával megadhatja, hogy egyetlen verzió vagy egy művelet összes azonos beállítású verziója megszűnjön-e.</span><span class="sxs-lookup"><span data-stu-id="77c6a-118">Select whether you want to discontinue a single version or all versions with the same settings in one operation by setting **All versions** to **Yes**.</span></span> 
2. <span data-ttu-id="77c6a-119">A **Megszüntetés** paramétert állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="77c6a-119">Set the **Discontinue** parameter to **Yes**.</span></span>
3. <span data-ttu-id="77c6a-120">A konfigurációk megszüntetéséhez kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="77c6a-120">Select **OK** to discontinue the configurations.</span></span> <span data-ttu-id="77c6a-121">A módosítások mentésekor a rendszer kitölti a **Megszüntetési dátum** mezőt.</span><span class="sxs-lookup"><span data-stu-id="77c6a-121">The **Discontinued date** field will be populated when you save the changes.</span></span>

![Konfigurációs adatok megszüntetése](media/Discontinue-details-2.png)
  
<span data-ttu-id="77c6a-123">A konfiguráció bármikor visszaállítható a **Megosztott** beállításra, illetve bármikor módosíthatja a megszüntetési adatokat.</span><span class="sxs-lookup"><span data-stu-id="77c6a-123">You can revert configuration back to **Shared** or adjust discontinuation information at any time.</span></span> <span data-ttu-id="77c6a-124">Ha közös konfigurációt oszt meg, adja meg a **Támogatás határideje** dátumát és a megszüntetéshez kapcsolódó összes egyéb információt, hogy jelezze a jövőbeli megszüntetésre vonatkozó terveit.</span><span class="sxs-lookup"><span data-stu-id="77c6a-124">If you share a configuration, specify the **Supported until** date and all other information related to the discontinuation to indicate your plans for future discontinuation.</span></span>

<span data-ttu-id="77c6a-125">Ha egy tervezett megszüntetésről szeretne információkat megosztani még a konfigurálás tényleges megszüntetése előtt, a felhasználó a cserével kapcsolatos összes mezőt előre kitöltheti, de a **Megszüntetés** paramétert **Nem** értéken hagyhatja.</span><span class="sxs-lookup"><span data-stu-id="77c6a-125">If you want to share information about a planned discontinuation, prior to actually discontinuing the configuration, user is able to prefill all fields related to replacement but leave the **Discontinue** parameter set to **No**.</span></span>

> [!NOTE]
> <span data-ttu-id="77c6a-126">A megszüntetés nem korlátozza a konfigurációkkal rendelkező műveleteket.</span><span class="sxs-lookup"><span data-stu-id="77c6a-126">Discontinuation doesn't limit operations with configurations.</span></span> <span data-ttu-id="77c6a-127">A konfigurációk importálását, futtatását és származtatását folytatni lehet – ezek a mezők csak tájékoztatásra valók.</span><span class="sxs-lookup"><span data-stu-id="77c6a-127">You can continue to import, run, or derive the configurations, these fields are informational.</span></span>

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a><span data-ttu-id="77c6a-128">A Finance rendszer támogatja ezen adatok megjelenítését a 10.0.14-es verziótól kezdve.</span><span class="sxs-lookup"><span data-stu-id="77c6a-128">Finance supports displaying this information starting in version 10.0.14</span></span>

<span data-ttu-id="77c6a-129">A Dynamics 365 Finance rendszer támogatja a megszüntetési adatok megjelenítését a 10.0.14-es verziótól kezdve.</span><span class="sxs-lookup"><span data-stu-id="77c6a-129">Starting in version 10.0.14, Dynamics 365 Finance supports displaying discontinuation information.</span></span> <span data-ttu-id="77c6a-130">A **Globális adattár** oldalon megtekintheti a megszüntetéshez kapcsolódó naprakész információkat.</span><span class="sxs-lookup"><span data-stu-id="77c6a-130">On the **Global repository** page, you can view up to date information related to discontinuation.</span></span> <span data-ttu-id="77c6a-131">Alapértelmezés szerint a már megszüntetett konfigurációkat kiszűri a rendszer.</span><span class="sxs-lookup"><span data-stu-id="77c6a-131">By default, configurations that are discontinued are filtered out.</span></span>
  
<span data-ttu-id="77c6a-132">Az **Importált konfigurációk** (ERSolutionTable) oldalon megjelennek az importáláskor már megszüntetett konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="77c6a-132">The **Imported configurations** (ERSolutionTable) page, shows configurations that were already discontinued when there were imported.</span></span> <span data-ttu-id="77c6a-133">Az importálás után megszüntetett konfigurációk esetén az importálás után megszüntetett adatokat az **Konfigurációfrissítések importálása** feladat futtatásával szinkronizálhatja.</span><span class="sxs-lookup"><span data-stu-id="77c6a-133">For those configurations that were discontinued after import, the discontinuation information can be synchronized by running the **Import configurations updates** job.</span></span>


