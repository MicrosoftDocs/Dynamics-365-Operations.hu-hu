---
title: Útkövetési modul
description: Ez a témakör az útkövetési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1c6d846686e3214e976a55271694382d7c5973ed
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417392"
---
# <a name="breadcrumb-module"></a><span data-ttu-id="b5b01-103">Útkövetési modul</span><span class="sxs-lookup"><span data-stu-id="b5b01-103">Breadcrumb module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="b5b01-104">Ez a témakör az útkövetési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="b5b01-104">This topic covers breadcrumb modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b5b01-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b5b01-105">Overview</span></span>

<span data-ttu-id="b5b01-106">Az útkövetési modulok másodlagos navigálás biztosítására szolgálnak a webhelyoldalakon.</span><span class="sxs-lookup"><span data-stu-id="b5b01-106">Breadcrumb modules are used to provide secondary navigation on site pages.</span></span> <span data-ttu-id="b5b01-107">Általában a lap tetején láthatók, a fejléc alatt.</span><span class="sxs-lookup"><span data-stu-id="b5b01-107">They are typically shown at the top of a page, below the header.</span></span> <span data-ttu-id="b5b01-108">Bár az útkövetési modulok bármilyen lapra hozzáadhatók, leggyakrabban a termékrészletek oldalakon (PDP-k) vannak használatban, a termékkategóriák hierarchiáját megjelenítéséhez, és gyors mozgást biztosítanak az oldalon.</span><span class="sxs-lookup"><span data-stu-id="b5b01-108">Although breadcrumb modules can be added to any page, they are most often used on product details pages (PDPs), to show the product category hierarchy and provide a quick way to move around a site.</span></span> <span data-ttu-id="b5b01-109">Az útkövetési modul egy „Visszatérés az eredményekhez" hivatkozás megjelenítésére is használható, amikor a felhasználók megnyitnak egy PDP-t a keresési vagy listaoldalon.</span><span class="sxs-lookup"><span data-stu-id="b5b01-109">A breadcrumb module can also be used to show a "Back to results" link when users open a PDP from a search or list page.</span></span> <span data-ttu-id="b5b01-110">Ily módon a felhasználók gyorsan visszatérhetnek a szűrt listaoldalukra a vásárlás folytatásához.</span><span class="sxs-lookup"><span data-stu-id="b5b01-110">In this way, users can quickly return to their filtered list page to continue shopping.</span></span>

<span data-ttu-id="b5b01-111">A termékkategóriák környezetét tartalmazó lapokon, például a PDP-k és a kategóriaoldalakon az útkövetési modul a kategória-hierarchiát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b5b01-111">On pages that have product category context, such as PDPs and category pages, breadcrumb modules show the category hierarchy.</span></span> <span data-ttu-id="b5b01-112">A kategóriakörnyezettel nem rendelkező oldalaknál az útkövetési modul alapértelmezésben a **&lt;Webhely gyökere&gt; / &lt;Aktuális oldal&gt;** helyet jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b5b01-112">On pages that don't have category context, breadcrumb modules show **&lt;Site root&gt; / &lt;Current page&gt;** by default.</span></span> <span data-ttu-id="b5b01-113">Az útkövetési modulokat a webhely más típusú oldalain is lehet konfigurálni, hogy a webhely adott oldalaira mutató hivatkozásokat jelenítsen meg.</span><span class="sxs-lookup"><span data-stu-id="b5b01-113">Breadcrumb modules can also be manually configured on other types of site pages to show links to specific pages on the site.</span></span>

<span data-ttu-id="b5b01-114">A következő kép egy olyan útkövető modult mutat be, amely a kategóriahierarchiát jeleníti meg egy PDP-n.</span><span class="sxs-lookup"><span data-stu-id="b5b01-114">The following image shows an example of a breadcrumb module that shows the category hierarchy on a PDP.</span></span>

![Példa egy útkövető modulra](./media/ecommerce-breadcrumb.PNG)

## <a name="breadcrumb-module-settings"></a><span data-ttu-id="b5b01-116">Útkövetési modul beállításai</span><span class="sxs-lookup"><span data-stu-id="b5b01-116">Breadcrumb module settings</span></span>

<span data-ttu-id="b5b01-117">Az útkövetési modul az **Útkövető megjelenítési típus PDP** beállításon alapul, amely a webhelykészítő **Oldalbeállítások \> bővítmények** részében van konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="b5b01-117">The breadcrumb module relies on the **Breadcrumb display type on PDP** setting, which is defined at **Site Settings \> Extensions** in site builder.</span></span> <span data-ttu-id="b5b01-118">Ennek a beállításnak három lehetséges értéke van:</span><span class="sxs-lookup"><span data-stu-id="b5b01-118">This setting has three possible values:</span></span>

- <span data-ttu-id="b5b01-119">**Kategóriahierarchia megjelenítése** – Ha ez az érték van kiválasztva, akkor a útkövetési modul a PDP-ben megtekintett termék teljes kategóriahierarchiáját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b5b01-119">**Show category hierarchy** – When this value is selected, the breadcrumb module will show the full category hierarchy of the product that is viewed on the PDP.</span></span>
- <span data-ttu-id="b5b01-120">**Megjelenítés vissza az eredményekhez** – Ha ez az érték van kiválasztva, akkor a navigációs modul a PDP-ben egy „Visszatérés az eredményekhez” hivatkozást jelenít meg, ha a felhasználó egy olyan modulból nyitotta meg a PDP-t, amely lehetővé teszi a „Visszatérés az eredményekhez” linket.</span><span class="sxs-lookup"><span data-stu-id="b5b01-120">**Show back to results** – When this value is selected, the breadcrumb module will show a "Back to results" link on a PDP if the user opened the PDP from a module that allows for a "Back to results" link.</span></span> <span data-ttu-id="b5b01-121">Ez a funkció akkor érhető el, ha a felhasználók a kategória-, keresés-, lista-és ajánlás listaoldalakról navigálnak.</span><span class="sxs-lookup"><span data-stu-id="b5b01-121">This functionality is available when users navigate from category, search, list, and recommendation lists pages.</span></span> <span data-ttu-id="b5b01-122">Ennek a funkciónak a támogatásához a termékgyűjtemény és a keresési eredmények modulban van egy **Visszalépés engedélyezése az eredményekhez a PDP-ben** tulajdonság.</span><span class="sxs-lookup"><span data-stu-id="b5b01-122">To support this functionality, product collection and search results modules have a property that is named **Allow back to results on PDP**.</span></span> <span data-ttu-id="b5b01-123">Ez a tulajdonság biztosítja a rugalmasságot annak meghatározására, hogy mely modulok támogatják a „Visszatérés az eredményekhez” linket a PDP-ben.</span><span class="sxs-lookup"><span data-stu-id="b5b01-123">This property gives you the flexibility to define which modules should support the "Back to results" link functionality on the PDP.</span></span> <span data-ttu-id="b5b01-124">Ha például a **Megjelenítés vissza az eredményekhez** van kiválasztva az útkövető modul **Útkövető megjelenítési típus PDP-n** beállításban, és a **Visszalépés engedélyezése az eredményekhez a PDP-ben** ki van választva a keresési oldal találatok moduljában, a „Vissza az eredményekhez” hivatkozás meg lesz jelenítve, amikor a felhasználók a keresési oldalról a PDP-re navigálnak.</span><span class="sxs-lookup"><span data-stu-id="b5b01-124">For example, when **Show back to results** is selected for the **Breadcrumb display type on PDP** setting of the breadcrumb module, and **Allow back to results on PDP** is selected for the search page search results module, a "Back to results" link will be shown when users navigate from the search page to a PDP.</span></span>
- <span data-ttu-id="b5b01-125">**Kategóriahierarchia és visszatérés az eredményekhez megjelenítése** – Ez az érték az előző kettő kombinációja.</span><span class="sxs-lookup"><span data-stu-id="b5b01-125">**Show category hierarchy and back to results** – This value is a combination of the previous two.</span></span> <span data-ttu-id="b5b01-126">Ha ez az érték ki van választva, akkor a navigációs modul a teljes kategóriahierarchiát és a „Visszatérés az eredményekhez” hivatkozást is megjeleníti (ha be van állítva) egy PDP-ben.</span><span class="sxs-lookup"><span data-stu-id="b5b01-126">When this value is selected, the breadcrumb module will show both the full category hierarchy and a "Back to results" link (if it's configured) on a PDP.</span></span>

## <a name="breadcrumb-module-properties"></a><span data-ttu-id="b5b01-127">Útkövetési modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="b5b01-127">Breadcrumb module properties</span></span>

| <span data-ttu-id="b5b01-128">Tulajdonság neve</span><span class="sxs-lookup"><span data-stu-id="b5b01-128">Property name</span></span> | <span data-ttu-id="b5b01-129">Értékek</span><span class="sxs-lookup"><span data-stu-id="b5b01-129">Values</span></span> | <span data-ttu-id="b5b01-130">Leírás</span><span class="sxs-lookup"><span data-stu-id="b5b01-130">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="b5b01-131">Gyökér</span><span class="sxs-lookup"><span data-stu-id="b5b01-131">Root</span></span> | <span data-ttu-id="b5b01-132">Szöveg vagy hivatkozás</span><span class="sxs-lookup"><span data-stu-id="b5b01-132">Text or link</span></span>| <span data-ttu-id="b5b01-133">Ez a választható tulajdonság azt határozza meg a hivatkozás szövegét és a hivatkozás célját az ütkövető oldalgyökeréhez.</span><span class="sxs-lookup"><span data-stu-id="b5b01-133">This optional property specifies link text and a link target for the breadcrumb site root.</span></span> <span data-ttu-id="b5b01-134">Ha ez a tulajdonság nincs beállítva, akkor nem lesz gyökér meghatározva.</span><span class="sxs-lookup"><span data-stu-id="b5b01-134">If this property isn't configured, no root will be defined.</span></span> |
| <span data-ttu-id="b5b01-135">Útkövető hivatkozása</span><span class="sxs-lookup"><span data-stu-id="b5b01-135">Breadcrumb link</span></span> | <span data-ttu-id="b5b01-136">Összekapcsolás</span><span class="sxs-lookup"><span data-stu-id="b5b01-136">Link</span></span> | <span data-ttu-id="b5b01-137">Ez a választható tulajdonság határozza meg a manuálisan konfigurált útkövető hivatkozásait, ha szükség van ezekre a hivatkozásokra.</span><span class="sxs-lookup"><span data-stu-id="b5b01-137">This optional property specifies links for a manually configured breadcrumb, if these links are required.</span></span> <span data-ttu-id="b5b01-138">A hivatkozások a listán szereplő sorrendben jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="b5b01-138">Links appear in the order that they are listed in.</span></span> |

## <a name="add-a-breadcrumb-module-to-a-new-page"></a><span data-ttu-id="b5b01-139">Útkövető modul hozzáadása egy új oldalhoz</span><span class="sxs-lookup"><span data-stu-id="b5b01-139">Add a breadcrumb module to a new page</span></span>

<span data-ttu-id="b5b01-140">Egy útkövetési modul a PDP-re való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b5b01-140">To add a breadcrumb module to a PDP and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="b5b01-141">Nyissa meg a **Webhelybeállítások /> Bővítmények** elemet, majd az **Útkövető megjelenítési típus PDP-n** beállításnál válassza a **Kategória-hierarchia megjelenítése** parancsot.</span><span class="sxs-lookup"><span data-stu-id="b5b01-141">Go to **Site Settings /> Extensions**, and then, for the **Breadcrumb display type on PDP** setting, select **Show category hierarchy**.</span></span>
1. <span data-ttu-id="b5b01-142">Nyissa meg a **Sablonok** lehetőséget, és válassza ki a PDP-sablont.</span><span class="sxs-lookup"><span data-stu-id="b5b01-142">Go to **Templates**, and select the PDP template.</span></span>
1. <span data-ttu-id="b5b01-143">Válassza ki a három pont (**...**) elemet a **Tároló** helyén, amely tartalmazz a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b5b01-143">In the **Container** slot that contains the buy box module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b5b01-144">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Útkövetési** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b5b01-144">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b5b01-145">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="b5b01-145">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="b5b01-146">Ugorjon a **Lapok** lehetőségre, és nyissa meg a PDP-sablont használó PDP-t.</span><span class="sxs-lookup"><span data-stu-id="b5b01-146">Go to **Pages**, and open a PDP that uses the PDP template.</span></span> <span data-ttu-id="b5b01-147">Ha még nincs egy PDP sem, hozzon létre egyet.</span><span class="sxs-lookup"><span data-stu-id="b5b01-147">If a PDP doesn't yet exist, create one.</span></span>
1. <span data-ttu-id="b5b01-148">Válassza ki a három pont (**...**) elemet a **Tároló** helyén, amely tartalmazz a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b5b01-148">In the **Container** slot that contains the buy box module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b5b01-149">A **Modul hozzáadása** párbeszédpanelen válassza ki az **Útkövetési** modult, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b5b01-149">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b5b01-150">Az **Útkövető** hely tulajdonságok panelén a **Gyökér** alatt válassz a **Hivatkozás szövege** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b5b01-150">In the properties pane of the **Breadcrumb** slot, under **Root**, select **Link text**.</span></span>
1. <span data-ttu-id="b5b01-151">A **Hivatkozás szövege** párbeszédpanelen írja be a **Kezdőlap** kifejezést, majd a **Hivatkozás célja** területen válassza a **Hivatkozás hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b5b01-151">In the **Link text** dialog box, enter **Home**, and then, under **Link target**, select **Add a link**.</span></span>
1. <span data-ttu-id="b5b01-152">A **Hivatkozás hozzáadása** párbeszédpanelen jelölje ki az útkövető gyökerét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b5b01-152">In the **Add a link** dialog box, select a link for the breadcrumb root, and then select **OK**.</span></span>
1. <span data-ttu-id="b5b01-153">Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="b5b01-153">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="b5b01-154">Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="b5b01-154">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b5b01-155">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b5b01-155">Additional resources</span></span>

[<span data-ttu-id="b5b01-156">Kezdőcsomag áttekintése</span><span class="sxs-lookup"><span data-stu-id="b5b01-156">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b5b01-157">Az alapértelmezett kategória-céloldal és keresési találatoldal áttekintése</span><span class="sxs-lookup"><span data-stu-id="b5b01-157">Overview of default category landing page and search results page</span></span>](category-search-page-overview.md)

[<span data-ttu-id="b5b01-158">Termékgyűjtési modulok</span><span class="sxs-lookup"><span data-stu-id="b5b01-158">Product collection modules</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="b5b01-159">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="b5b01-159">Buy box module</span></span>](add-buy-box.md)