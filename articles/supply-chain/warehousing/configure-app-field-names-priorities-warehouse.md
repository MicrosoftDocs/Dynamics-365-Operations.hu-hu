---
title: A Raktárkezelés mobilalkalmazás mezőinek konfigurálása
description: Ez a témakör ismerteti, hogyan történik a Raktárkezelés mobilalkalmazásban szereplő mezők neveinek és prioritásainak meghatározása és konfigurálása.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bc224d3fd6cf5b111f61066202090f10ba4a7e8a
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189250"
---
# <a name="configure-fields-for-the-warehouse-management-mobile-app"></a><span data-ttu-id="4df3b-103">A Raktárkezelés mobilalkalmazás mezőinek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="4df3b-103">Configure fields for the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4df3b-104">Ez a témakör ismerteti, hogyan történik a Raktárkezelés mobilalkalmazásban szereplő mezők neveinek és prioritásainak meghatározása és konfigurálása.</span><span class="sxs-lookup"><span data-stu-id="4df3b-104">This topic describes how to define and configure names and priorities of fields shown in the Warehouse Management mobile app.</span></span>

> [!NOTE]
> <span data-ttu-id="4df3b-105">Ez a témakör a Raktárkezelési szolgáltatásokra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="4df3b-105">This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="4df3b-106">A Készletkezelés funkciókra nem vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="4df3b-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="4df3b-107">A Raktárkezelés mobilalkalmazás egy raktározási feladatok végrehajtásához használt alkalmazás.</span><span class="sxs-lookup"><span data-stu-id="4df3b-107">The Warehouse Management mobile app is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="4df3b-108">Meghatározhatja és beállíthatja az alkalmazásban használt mezőneveket, és konfigurálhatja a prioritást, amelyhez a mezőneveket hozzá kell rendelni.</span><span class="sxs-lookup"><span data-stu-id="4df3b-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="4df3b-109">Ez a témakör ismerteti, hogyan történik a Raktárkezelés mobilalkalmazás ezen mezőneveinek és prioritásainak meghatározása és konfigurálása, továbbá használata.</span><span class="sxs-lookup"><span data-stu-id="4df3b-109">This topic explains how to define and configure these Warehouse Management mobile app field names and priorities, and how they are used.</span></span>

## <a name="configure-warehouse-app-field-names"></a><span data-ttu-id="4df3b-110">A raktári alkalmazáson belüli mezőnevek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="4df3b-110">Configure warehouse app field names</span></span>

<span data-ttu-id="4df3b-111">Amikor a Warehousing alkalmazást a mobileszközön használja, konfigurálható, hogyan jelenjenek meg az eszközön a metaadatok **A raktári alkalmazáson belüli mezőnevek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="4df3b-111">When you use Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="4df3b-112">Egy felvett új vállalatnál válassza az **Alapértelmezett beállítás létrehozása** elemet a raktármodul mobileszközön használt munkafolyamataiban használt összes mezőnév létrehozásához, majd rendeljen hozzájuk egy elsődleges beviteli módot és beviteltípust.</span><span class="sxs-lookup"><span data-stu-id="4df3b-112">In a new company, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="4df3b-113">Az összes mezőnév létrehozása után a következő beviteli beállításokat választhatja ki.</span><span class="sxs-lookup"><span data-stu-id="4df3b-113">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4df3b-114">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="4df3b-114">Option</span></span></th>
<th><span data-ttu-id="4df3b-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="4df3b-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4df3b-116">Preferált beviteli mód</span><span class="sxs-lookup"><span data-stu-id="4df3b-116">Preferred input mode</span></span></td>
<td><span data-ttu-id="4df3b-117">Ez a beállítás határozza meg, hogy egy keresési mező vagy egy kézi beviteli mező jelenjen-e meg a kijelölt mezőnévnél.</span><span class="sxs-lookup"><span data-stu-id="4df3b-117">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="4df3b-118">Ez a mezők vonalkódhasználaton alapuló megkülönböztetéséhez hasznos.</span><span class="sxs-lookup"><span data-stu-id="4df3b-118">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="4df3b-119"><strong>Megjegyzés:</strong> azon mezőneveknél, amelyeknél az elsődleges beviteli mód beállítása <strong>Beolvasás</strong>, adatokat manuálisan is megadhat, ha a vonalkód nem olvasható vagy sérült.</span><span class="sxs-lookup"><span data-stu-id="4df3b-119"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4df3b-120">Beviteltípus</span><span class="sxs-lookup"><span data-stu-id="4df3b-120">Input type</span></span></td>
<td><span data-ttu-id="4df3b-121">Ez a beállítás határozza meg, milyen beviteli típus legyen használva a kiválasztott mezőnévnél.</span><span class="sxs-lookup"><span data-stu-id="4df3b-121">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="4df3b-122">Négy lehetőség érhető el:</span><span class="sxs-lookup"><span data-stu-id="4df3b-122">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="4df3b-123"><strong>Kiválasztás</strong> - választható lehetőségek listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="4df3b-123"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="4df3b-124">Ezzel a beállítással a mezőnevek nem szerkeszthetők.</span><span class="sxs-lookup"><span data-stu-id="4df3b-124">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="4df3b-125"><strong>Dátum</strong> - a dátumként megadott mezőnevek dátumformátumot jelenítenek meg a címkével.</span><span class="sxs-lookup"><span data-stu-id="4df3b-125"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="4df3b-126">Ez segít a raktárosoknak látni, milyen formátumban adják meg a dátumot.</span><span class="sxs-lookup"><span data-stu-id="4df3b-126">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="4df3b-127">Ezzel a beállítással a mezőnevek nem szerkeszthetők.</span><span class="sxs-lookup"><span data-stu-id="4df3b-127">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="4df3b-128"><strong>Alfa</strong> - kiválasztása esetén az eszköz billentyűzetén kell adatokat manuálisan bevinni az alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="4df3b-128"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="4df3b-129">A billentyűzet felülete módosítható a használt eszköztől függően.</span><span class="sxs-lookup"><span data-stu-id="4df3b-129">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="4df3b-130"><strong>Numerikus</strong> - a csak numerikus bevitelt használó mezőneveknél ennek a lehetőségnek a kiválasztásával egyéni számbillentyűzet jeleníthető meg a beviteli mezőnél az eszköz billentyűzete helyett.</span><span class="sxs-lookup"><span data-stu-id="4df3b-130"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="4df3b-131">A raktári alkalmazáson belüli mezőprioritások beállítása</span><span class="sxs-lookup"><span data-stu-id="4df3b-131">Configure warehouse app field priority</span></span>

<span data-ttu-id="4df3b-132">**A raktári alkalmazáson belüli mezőprioritás** oldalon a mezőneveket különböző prioritási csoportokba rendezheti.</span><span class="sxs-lookup"><span data-stu-id="4df3b-132">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="4df3b-133">Ez lehetővé teszi annak eldöntését, hogy milyen információk jelenjenek meg a fő feladatlapon, amikor a raktári dolgozók feladatokat végeznek az alkalmazás használatával.</span><span class="sxs-lookup"><span data-stu-id="4df3b-133">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="4df3b-134">Ha az **Alapértelmezett beállítás létrehozása** elemre kattint, létrejön az alapértelmezés szerinti prioritáscsoportok sorozata.</span><span class="sxs-lookup"><span data-stu-id="4df3b-134">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="4df3b-135">Szükség szerint tetszőleges számú prioritási csoport hozható létre, de a feladatlapon csak három prioritási csoport jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="4df3b-135">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="4df3b-136">Amikor a rendszer metaadatokat küld az alkalmazásnak, minden mezőhöz relatív prioritást rendel a prioritási csoportjától függően, és az alkalmazás a metaadatokban található első három prioritási csoportot jeleníti meg a feladatlapon.</span><span class="sxs-lookup"><span data-stu-id="4df3b-136">When the system sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="4df3b-137">Az ezen felüli metaadatok a másodlagos részletek lapon jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="4df3b-137">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="4df3b-138">A következő táblázat öt prioritási csoportra mutat példát.</span><span class="sxs-lookup"><span data-stu-id="4df3b-138">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4df3b-139">Prioritási csoport</span><span class="sxs-lookup"><span data-stu-id="4df3b-139">Priority group</span></span></th>
<th><span data-ttu-id="4df3b-140">Hozzárendelt mezők</span><span class="sxs-lookup"><span data-stu-id="4df3b-140">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="4df3b-141">10. prioritás</span><span class="sxs-lookup"><span data-stu-id="4df3b-141">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="4df3b-142">Tétel</span><span class="sxs-lookup"><span data-stu-id="4df3b-142">Item</span></span></li>
<li><span data-ttu-id="4df3b-143">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="4df3b-143">Quantity</span></span></li>
<li><span data-ttu-id="4df3b-144">Mértékegység</span><span class="sxs-lookup"><span data-stu-id="4df3b-144">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="4df3b-145">20. prioritás</span><span class="sxs-lookup"><span data-stu-id="4df3b-145">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="4df3b-146">Fürtpozíció</span><span class="sxs-lookup"><span data-stu-id="4df3b-146">Cluster position</span></span></li>
<li><span data-ttu-id="4df3b-147">Fürt</span><span class="sxs-lookup"><span data-stu-id="4df3b-147">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="4df3b-148">30. prioritás</span><span class="sxs-lookup"><span data-stu-id="4df3b-148">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="4df3b-149">Cikk leírása</span><span class="sxs-lookup"><span data-stu-id="4df3b-149">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="4df3b-150">40. prioritás</span><span class="sxs-lookup"><span data-stu-id="4df3b-150">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="4df3b-151">Konfiguráció</span><span class="sxs-lookup"><span data-stu-id="4df3b-151">Configuration</span></span></li>
<li><span data-ttu-id="4df3b-152">Szín</span><span class="sxs-lookup"><span data-stu-id="4df3b-152">Color</span></span></li>
<li><span data-ttu-id="4df3b-153">Méret</span><span class="sxs-lookup"><span data-stu-id="4df3b-153">Size</span></span></li>
<li><span data-ttu-id="4df3b-154">Stílus</span><span class="sxs-lookup"><span data-stu-id="4df3b-154">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="4df3b-155">50. prioritás</span><span class="sxs-lookup"><span data-stu-id="4df3b-155">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="4df3b-156">Tárolóhely</span><span class="sxs-lookup"><span data-stu-id="4df3b-156">Location</span></span></li>
<li><span data-ttu-id="4df3b-157">Azonosítótábla</span><span class="sxs-lookup"><span data-stu-id="4df3b-157">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df3b-158">Például amikor egy raktári dolgozó valamilyen műveletet hajt végre egy mobileszközön, ha az alkalmazásban megjelenő metaadatok a következő mezőkből állnak:</span><span class="sxs-lookup"><span data-stu-id="4df3b-158">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="4df3b-159">Tétel</span><span class="sxs-lookup"><span data-stu-id="4df3b-159">Item</span></span>
-   <span data-ttu-id="4df3b-160">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="4df3b-160">Quantity</span></span>
-   <span data-ttu-id="4df3b-161">Mértékegység</span><span class="sxs-lookup"><span data-stu-id="4df3b-161">Unit of measure</span></span>
-   <span data-ttu-id="4df3b-162">Cikk leírása</span><span class="sxs-lookup"><span data-stu-id="4df3b-162">Item description</span></span>
-   <span data-ttu-id="4df3b-163">Méret és hely</span><span class="sxs-lookup"><span data-stu-id="4df3b-163">Size and Location</span></span>

<span data-ttu-id="4df3b-164">A raktári alkalmazás a fenti táblában beállított mezőprioritásai alapján a következő 3 sor információ jelenik meg a feladatlapon:</span><span class="sxs-lookup"><span data-stu-id="4df3b-164">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="4df3b-165">1. sor: Elem, Mennyiség, Mértékegysége</span><span class="sxs-lookup"><span data-stu-id="4df3b-165">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="4df3b-166">2. sor: Elem leírása</span><span class="sxs-lookup"><span data-stu-id="4df3b-166">Row 2: Item description</span></span>
-   <span data-ttu-id="4df3b-167">3. sor: méret</span><span class="sxs-lookup"><span data-stu-id="4df3b-167">Row 3: Size</span></span>

<span data-ttu-id="4df3b-168">A fennmaradó metaadatok, például a Hely nem fog megjelenni a feladatlapon, de megjelenik a részletek lapon.</span><span class="sxs-lookup"><span data-stu-id="4df3b-168">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="4df3b-169">További információért és a felhasználói felülettel kapcsolatos példákért olvassa el [A Finance and Operations- Warehousing bejelentése](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/) blogbejegyzést.</span><span class="sxs-lookup"><span data-stu-id="4df3b-169">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4df3b-170">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="4df3b-170">Additional resources</span></span>

[<span data-ttu-id="4df3b-171">A Raktárkezelés mobilalkalmazás telepítése és csatlakoztatása</span><span class="sxs-lookup"><span data-stu-id="4df3b-171">Install and connect the Warehouse Management mobile app</span></span>](../warehousing/install-configure-warehouse-management-app.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]