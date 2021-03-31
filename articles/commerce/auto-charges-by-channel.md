---
title: Automatikus költségek csatorna szerinti engedélyezése és konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet engedélyezni és konfigurálni az automatikus költségeket csatornánként a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: annbe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 834d90c8ec8515c6bced2d8a4fabc79b4e4e4c3e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211273"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a><span data-ttu-id="509be-103">Automatikus költségek csatorna szerinti engedélyezése és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="509be-103">Enable and configure auto charges by channel</span></span>

<span data-ttu-id="509be-104">Ez a témakör azt mutatja be, hogyan lehet engedélyezni és konfigurálni az automatikus költségeket (auto költségek) csatornánként a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="509be-104">This topic explains how to enable and configure automatic charges (auto charges) by channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="509be-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="509be-105">Overview</span></span>

<span data-ttu-id="509be-106">Előfordulhat, hogy olyan forgatókönyvei vannak amikor egy adott államban (például Kalifornia) egy vagy több üzletben értékesített termékek egy csoportjára vonatkozóan újrahasznosítási díjat vagy egyéb díjat kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="509be-106">You might have scenarios where recycling fees or other fees must be applied to a group of products that are sold in all or some stores in a specific state (for example, California).</span></span> <span data-ttu-id="509be-107">A **Az automatikus kötsége szűrésének engedélyezése csatornánként** funkcióval csatornánként határozhat meg automatikus költségeket (péládul egy adott fizikiai üzlet csatornához).</span><span class="sxs-lookup"><span data-stu-id="509be-107">The **Enable filter auto charges by channel** feature in Commerce lets you specify auto charges by channel (for example, a specific brick-and-mortar channel).</span></span> <span data-ttu-id="509be-108">Ez a funkció elérhető a Dynamics 365 Commerce alkalmazás 10.0.10 vagy újabb verziójában.</span><span class="sxs-lookup"><span data-stu-id="509be-108">This feature is available in Dynamics 365 Commerce version 10.0.10 and later.</span></span>

<span data-ttu-id="509be-109">Az automatikus költségek csatorna szerinti engedélyezéséhez és beállításához a következő feladatokat kell elvégeznie:</span><span class="sxs-lookup"><span data-stu-id="509be-109">To enable and configure auto charges by channel, you must complete the following tasks:</span></span>

- <span data-ttu-id="509be-110">Kapcsolja be az **Automatikus kötségek szűrésének engedélyezése csatornánként** funkciót.</span><span class="sxs-lookup"><span data-stu-id="509be-110">Turn on the **Enable filter auto charges by channel** feature.</span></span>
- <span data-ttu-id="509be-111">Konfigurálja a szervezeti hierarchia célját.</span><span class="sxs-lookup"><span data-stu-id="509be-111">Configure the organization hierarchy purpose.</span></span>
- <span data-ttu-id="509be-112">Automatikus költségek definiálása csatornánként.</span><span class="sxs-lookup"><span data-stu-id="509be-112">Define auto charges by channel.</span></span>

> [!NOTE]
> <span data-ttu-id="509be-113">Az **Automatikus kötségek szűrésének engedélyezése csatornánként** funkció csak akkor működik, ha a speciális automatikus költségek funkció is be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="509be-113">The **Enable filter auto charges by channel** feature works only if the advanced auto charges feature is also turned on.</span></span> <span data-ttu-id="509be-114">A speciális automatikus költség funkció bekapcsolásával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Többcsatornás speciális automatikus költségek](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="509be-114">For information about how to turn on the advanced auto charges feature, see [Omni-channel advanced auto charges](omni-auto-charges.md).</span></span>

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a><span data-ttu-id="509be-115">Kapcsolja be az Automatikus kötségek szűrésének engedélyezése csatornánként funkciót</span><span class="sxs-lookup"><span data-stu-id="509be-115">Turn on the Enable filter auto charges by channel feature</span></span>

<span data-ttu-id="509be-116">A csatorna szerinti automatikus költségek engedélyezéséhez a Commerce alkalmazásban hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="509be-116">To enable auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="509be-117">Válassz a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** elemet.</span><span class="sxs-lookup"><span data-stu-id="509be-117">Go to **System administrator \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="509be-118">A **Nem engedélyezett** lapon a **Szolgáltatások neve** listáján keresse meg és válassza ki az **Automatikus kötségek szűrésének engedélyezése csatornánként** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="509be-118">On the **Not enabled** tab, in the **Feature name** list, find and select **Enable filter auto charges by channel**.</span></span>
1. <span data-ttu-id="509be-119">A jobb alsó sarokban válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="509be-119">In the lower-right corner, select **Enable now**.</span></span> <span data-ttu-id="509be-120">Miután a funkció be lett kapcsolva, az **Összes** lap listájában jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="509be-120">After the feature has been turned on, it will appear in the list on the **All** tab.</span></span>
1. <span data-ttu-id="509be-121">Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="509be-121">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="509be-122">A bal oldali ablaktáblában keresse meg és válassza ki a **1110** (**Globális konfiguráció**) feladatot.</span><span class="sxs-lookup"><span data-stu-id="509be-122">In the left pane, find and select the **1110** (**Global configuration**) job.</span></span>
1. <span data-ttu-id="509be-123">A Műveletek ablaktáblán válassza a **Futtatás most** parancsot a konfigurációs módosítások propagálásához.</span><span class="sxs-lookup"><span data-stu-id="509be-123">On the Action Pane, select **Run now** to propagate the configuration changes.</span></span>

> [!WARNING]
> <span data-ttu-id="509be-124">Ha kikapcsolja az **Automatikus kötségek szűrésének engedélyezése csatornánként** funkciót, miután már használta azt, akkor **Kiskereskedelmi csatorna kapcsolat** mező az **Automatikus költésgek** alatt nem fog megjelenni, és minden létező konfigurációt elveszik.</span><span class="sxs-lookup"><span data-stu-id="509be-124">If you turn off the **Enable filter auto charges by channel** feature after you've already used it, the **Retail channel relation** field under **Auto charges** will no longer appear, and you will lose all existing configurations.</span></span> <span data-ttu-id="509be-125">Ha a **Kiskereskedelmi csatorna kapcsolat** konfigurációk eltávolítása az automatikus költésgek szabályainak duplikálását okozná akkor nem fog sikerüni a funkció kikapcsolása.</span><span class="sxs-lookup"><span data-stu-id="509be-125">If removal of the **Retail channel relation** configurations will cause auto charges rules to be duplicated, an attempt to turn off the feature will fail.</span></span> <span data-ttu-id="509be-126">A funkció kikapcsolása előtt fontos, hogy minden automatikus költség-szabályt ellenőrizen, és végezze el a szükséges módosításokat.</span><span class="sxs-lookup"><span data-stu-id="509be-126">Before you turn off the feature, be sure to review all auto charges rules and make any required changes.</span></span>

## <a name="configure-the-organization-hierarchy-purpose"></a><span data-ttu-id="509be-127">Konfigurálja a szervezeti hierarchia célját</span><span class="sxs-lookup"><span data-stu-id="509be-127">Configure the organization hierarchy purpose</span></span>

<span data-ttu-id="509be-128">A program létrehozta a **Kiskereskedelmi automatikus költség** nevű új szervezeti hierarchiát, amely a csatorna szerinti automatikus díjak hierarchiájának kezelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="509be-128">A new organization hierarchy purpose that is named **Retail auto charge** has been created to manage the hierarchy for auto charges by channel.</span></span>

<span data-ttu-id="509be-129">Ha egy alapértelmezett hierarchiát szeretné társítani egy szervezeti hierarchiához a Commerce-ben, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="509be-129">To assign a default hierarchy to an organization hierarchy purpose in Commerce, follow these steps.</span></span>
        
1. <span data-ttu-id="509be-130">Ugrás a **Szervezet felügyelete \> Szervezetek \> Szervezeti hierarchiák céljai** menübe.</span><span class="sxs-lookup"><span data-stu-id="509be-130">Go to **Organization administration \> Organizations \> Organization hierarchy purposes**.</span></span>
1. <span data-ttu-id="509be-131">A bal oldali ablakban válassza ki a **Kiskereskedelmi automatikus költség** elemet.</span><span class="sxs-lookup"><span data-stu-id="509be-131">In the left pane, select **Retail auto charge**.</span></span>
1. <span data-ttu-id="509be-132">A **Hozzárendelt hierarchiák** területen válassza **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="509be-132">Under **Assigned hierarchies**, select **Add**.</span></span>
1. <span data-ttu-id="509be-133">A **Szervezeti hierarchiák** párbeszédpanelen válasszon egy szervezeti hierarchiát (például a **Kiskereskedelmi üzletek régiónként**), majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="509be-133">In the **Organization hierarchies** dialog box, select an organization hierarchy (for example, **Retail Stores by Region**), and then select **OK**.</span></span>
1. <span data-ttu-id="509be-134">A **Hozzárendelt hierarchiák** területen válassza **Beállítás alapértelmezettként** elemet.</span><span class="sxs-lookup"><span data-stu-id="509be-134">Under **Assigned hierarchies**, select **Set as default**.</span></span>
1. <span data-ttu-id="509be-135">Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="509be-135">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="509be-136">A bal oldali ablaktáblában keresse meg és válassza ki a **1040** (**Termékek**) feladatot.</span><span class="sxs-lookup"><span data-stu-id="509be-136">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="509be-137">A Műveleti ablaktáblán kattintson a **Futtatás most** elemre.</span><span class="sxs-lookup"><span data-stu-id="509be-137">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="509be-138">A **1070** (**Csatorna-konfigurációja**) és a **1110** (**Globális konfiguráció**) feladatok futtatásához ismételje meg az előző két lépést.</span><span class="sxs-lookup"><span data-stu-id="509be-138">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>

![A Kiskereskedelmi automatikus költség szervezeti hierarchia céljának konfigurálása](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a><span data-ttu-id="509be-140">Automatikus költségek definiálása csatornánként</span><span class="sxs-lookup"><span data-stu-id="509be-140">Define auto charges by channel</span></span>

<span data-ttu-id="509be-141">Miután bekapcsolta az **Automatikus kötségek szűrésének engedélyezése csatornánként** funkciót, és konfigurálta a **Kiskereskedelmi automatikus költség** szervezeti hierarchia célját, a csatorna szerinti automatikus költség definiálható a rendelés fejléc szintjén vagy a rendelési sor szintjén.</span><span class="sxs-lookup"><span data-stu-id="509be-141">After you've turned on the **Enable filter auto charges by channel** feature and configured the **Retail auto charge** organization hierarchy purpose, auto charges by channel can be defined at either the order header level or the order line level.</span></span>

<span data-ttu-id="509be-142">A csatorna szerinti automatikus költségek definiálásához a Commerce alkalmazásban hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="509be-142">To define auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="509be-143">Ugorjon a **Kinnlevőségek \> Költségek beállítása \> Automatikus költségek** pontra.</span><span class="sxs-lookup"><span data-stu-id="509be-143">Go to **Accounts receivable \> Charges setup \> Auto charges**.</span></span>
1. <span data-ttu-id="509be-144">A bal oldali ablak **Szint** mezőjében válassza a **Fejléc** vagy **Sor** beállítást az üzleti igényektől függően.</span><span class="sxs-lookup"><span data-stu-id="509be-144">In the left pane, in the **Level** field, select either **Header** or **Line**, depending on your business requirements.</span></span>
1. <span data-ttu-id="509be-145">A **Kiskereskedelmi csatorna kódja** mezőben válassza ki a megfelelő csatornakódot (például **Tábla** vagy **Csoport**).</span><span class="sxs-lookup"><span data-stu-id="509be-145">In the **Retail channel code** field, select the appropriate channel code (for example, **Table** or **Group**).</span></span> <span data-ttu-id="509be-146">Ha az alapértelmezett **Minden** beállítás van használatban, akkor minden csatornára alkalmazva lesznek a költségszabályok.</span><span class="sxs-lookup"><span data-stu-id="509be-146">If the default setting, **All**, is used, charge rules are applied to all channels.</span></span>

    - <span data-ttu-id="509be-147">Ha a **Csoport** lehetőséget választja, akkor győződjön meg róla, hogy kiskereskedelmi csatorna költésgcsoportja létre van hozva a **Kiskereskedelem és kereskedelem \> Csatorna beállításai \> Költésgek \> Kiskreskedelmi csatorna költségcsoportjai** menüben.</span><span class="sxs-lookup"><span data-stu-id="509be-147">If you select **Group**, make sure that a retail channel charges group is created at **Retail and Commerce \> Channel setup \> Charges \> Retail channel charge groups**.</span></span>
    - <span data-ttu-id="509be-148">Ha a **Tábla** lehetőséget választja, akkor a **Kiskereskedelmi csatorna kapcsolata** mezőben kiválaszthatja a kívánt csatornát (például **San Francisco**).</span><span class="sxs-lookup"><span data-stu-id="509be-148">If you select **Table**, you can select a specific channel (for example, **San Francisco**) in the **Retail channel relation** field.</span></span>

1. <span data-ttu-id="509be-149">Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="509be-149">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="509be-150">A bal oldali ablaktáblában keresse meg és válassza ki a **1040** (**Termékek**) feladatot.</span><span class="sxs-lookup"><span data-stu-id="509be-150">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="509be-151">A Műveleti ablaktáblán kattintson a **Futtatás most** elemre.</span><span class="sxs-lookup"><span data-stu-id="509be-151">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="509be-152">A **1070** (**Csatorna-konfigurációja**) és a **1110** (**Globális konfiguráció**) feladatok futtatásához ismételje meg az előző két lépést.</span><span class="sxs-lookup"><span data-stu-id="509be-152">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>
    
![Automatikus költségek csatornánként definiálva](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a><span data-ttu-id="509be-154">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="509be-154">Example scenario</span></span>

<span data-ttu-id="509be-155">A következő példa a termék konfigurálásához szükséges lépéseket írja le, hogy az újrafeldolgozási díjak fel legyenek számítva, amikor a terméket egy San Francisco-i fizikai üzletben értékesítik.</span><span class="sxs-lookup"><span data-stu-id="509be-155">The following example outlines the steps that are required to configure a product so that recycling fees are charged when the product is sold through a San Francisco brick-and-mortar channel.</span></span> <span data-ttu-id="509be-156">A példa azt is bemutatja, hogy hogyan jelenjenek meg az automatikus költségek a Commerce pénztár (POS) alkalmazásában.</span><span class="sxs-lookup"><span data-stu-id="509be-156">The example also shows how the auto charges appear in the Commerce point of sale (POS) application.</span></span>

<span data-ttu-id="509be-157">A szervezet definiál egy **ÚJRAHASZNOSÍTÁS** nevű költségkódot a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="509be-157">The organization defines a charges code that is named **RECYCLE**, as shown in the following illustration.</span></span>

![ÚJRAFELDOLGOZÁS költségkód](media/Auto-charges-charge-code.png)

<span data-ttu-id="509be-159">Az automatikus költséget a sor szintjén jön létre.</span><span class="sxs-lookup"><span data-stu-id="509be-159">An auto charge is created at the line level.</span></span> <span data-ttu-id="509be-160">Az alábbi konfiguráció jellemzi:</span><span class="sxs-lookup"><span data-stu-id="509be-160">It has the following configuration:</span></span>

- <span data-ttu-id="509be-161">A **Számlakód** mező be van állítva **Minden** értékre.</span><span class="sxs-lookup"><span data-stu-id="509be-161">The **Account code** field is set to **All**.</span></span>
- <span data-ttu-id="509be-162">A **Cikkkód** mező be van állítva **Tábla** értékre.</span><span class="sxs-lookup"><span data-stu-id="509be-162">The **Item code** field is set to **Table**.</span></span>
- <span data-ttu-id="509be-163">A **Cikk- kapcsolat** mező értéke a **91001** termékazonosító.</span><span class="sxs-lookup"><span data-stu-id="509be-163">The **Item relation** field is set to product ID **91001**.</span></span>
- <span data-ttu-id="509be-164">A **Szállítási mód** mező be van állítva **Minden** értékre.</span><span class="sxs-lookup"><span data-stu-id="509be-164">The **Mode of delivery code** field is set to **All**.</span></span>
- <span data-ttu-id="509be-165">A **Kiskereskedelmi csatorna kódja** mező be van állítva **Tábla** értékre.</span><span class="sxs-lookup"><span data-stu-id="509be-165">The **Retail channel code** field is set to **Table**.</span></span>
- <span data-ttu-id="509be-166">A **Kiskereskedelmi csatorna kapcsolata** mező értéke a **San Francisco** üzletre van állítva.</span><span class="sxs-lookup"><span data-stu-id="509be-166">The **Retail channel relation** field is set to the **San Francisco** store.</span></span>

<span data-ttu-id="509be-167">Létrejön egy automatikus költség sor.</span><span class="sxs-lookup"><span data-stu-id="509be-167">An auto charges line is created.</span></span> <span data-ttu-id="509be-168">Az alábbi konfiguráció jellemzi:</span><span class="sxs-lookup"><span data-stu-id="509be-168">It has the following configuration:</span></span>

- <span data-ttu-id="509be-169">A **Pénznem** mező beállítása **USD**.</span><span class="sxs-lookup"><span data-stu-id="509be-169">The **Currency** field is set to **USD**.</span></span>
- <span data-ttu-id="509be-170">A **Költségkód** mező be van állítva **ÚJRHASZNOSÍTÁS** értékre.</span><span class="sxs-lookup"><span data-stu-id="509be-170">The **Charges code** field is set to **RECYCLE**.</span></span>
- <span data-ttu-id="509be-171">A **Kategória** mező be van állítva **Rögzített** értékre.</span><span class="sxs-lookup"><span data-stu-id="509be-171">The **Category** field is set to **Fixed**.</span></span>
- <span data-ttu-id="509be-172">A **Költésgek** mező beállítása **6,25 USD**.</span><span class="sxs-lookup"><span data-stu-id="509be-172">The **Charges** field is set to **$6.25**.</span></span>

![A sor szintű automatikus költéségek és az automatikus költségek sora konfigurálása](media/Auto-charges-recyclingfee-line-fee.png)

<span data-ttu-id="509be-174">A pénztár alkalmazásban létrejön egy értékesítési rendelés a **San Franciscó** üzlet csatornájában.</span><span class="sxs-lookup"><span data-stu-id="509be-174">In the POS application, a sales order is created in the **San Francisco** store channel.</span></span> <span data-ttu-id="509be-175">A **Költségek** sor a **6,25 dolláros** újrahasznosítási díjat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="509be-175">The **Charges** line shows the recycling fee of **$6.25**.</span></span>

<span data-ttu-id="509be-176">Ha kiválasztja a **Tranzakcióbeállítások \> Költségék \> Költésgek kezelése** lehetőséget a POS-alkalmazásban, akkor megtekintheti az újrahasznosítási díj költségkódját és leírását.</span><span class="sxs-lookup"><span data-stu-id="509be-176">By selecting **Transaction options \> Charges \> Manage charges** in the POS application, you can view the charges code and description for the recycling fee.</span></span>

![Újrahasznosítási díj a pénztár alkalmazásban](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a><span data-ttu-id="509be-178">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="509be-178">Additional resources</span></span>

[<span data-ttu-id="509be-179">Többcsatornás speciális automatikus költségek</span><span class="sxs-lookup"><span data-stu-id="509be-179">Omni-channel advanced auto charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="509be-180">Fejlécköltségek arányosítása az egyező értékesítési sorokhoz</span><span class="sxs-lookup"><span data-stu-id="509be-180">Prorate header charges to matching sales lines</span></span>](pro-rate-charges-matching-lines.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]