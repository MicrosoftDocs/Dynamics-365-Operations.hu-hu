---
title: Alkalmazáson belüli mezőnevek konfigurálása a raktáralkalmazásban
description: Ez a témakör ismerteti, hogyan történik a raktári alkalmazás mezőneveinek és prioritásainak meghatározása és konfigurálása a Dynamics 365 Supply Chain Management alkalmazásban.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7a4cfe62aa50c423adfd116a81d7962c30b25fcf
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429441"
---
# <a name="configure-app-field-names-in-the-warehouse-app"></a><span data-ttu-id="24cb5-103">Alkalmazáson belüli mezőnevek konfigurálása a raktáralkalmazásban</span><span class="sxs-lookup"><span data-stu-id="24cb5-103">Configure app field names in the warehouse app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="24cb5-104">Ez a témakör ismerteti, hogyan történik a raktári alkalmazás mezőneveinek és prioritásainak meghatározása és konfigurálása a Dynamics 365 Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="24cb5-104">This topic describes how to define and configure warehouse app field names and priorities in Dynamics 365 Supply Chain Management.</span></span> 

> [!NOTE]
> <span data-ttu-id="24cb5-105">Ez a témakör a Raktárkezelési szolgáltatásokra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="24cb5-105">This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="24cb5-106">A Készletkezelés funkciókra nem vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="24cb5-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="24cb5-107">Warehousing egy raktározási feladatok végrehajtásához használt alkalmazás.</span><span class="sxs-lookup"><span data-stu-id="24cb5-107">Warehousing is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="24cb5-108">Meghatározhatja és beállíthatja az alkalmazásban használt mezőneveket, és konfigurálhatja a prioritást, amelyhez a mezőneveket hozzá kell rendelni.</span><span class="sxs-lookup"><span data-stu-id="24cb5-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="24cb5-109">Ez a témakör ismerteti, hogyan történik a raktári alkalmazás ezen mezőneveinek és prioritásainak meghatározása és konfigurálása, továbbá használata a Warehousing alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="24cb5-109">This topic explains how to define and configure these warehouse app field names and priorities, and how they are used in Warehousing.</span></span> <span data-ttu-id="24cb5-110">Az FWarehousing alkalmazáshoz való kapcsolódás konfigurálásának részletei a [Raktáralkalmazás telepítésének és konfigurálásának áttekintése](install-configure-warehousing-app.md) című oktatóanyagban találhatók.</span><span class="sxs-lookup"><span data-stu-id="24cb5-110">For detailed information about how to configure the connection to FWarehousing, refer to the tutorial [Install and configure the warehouse app overview](install-configure-warehousing-app.md).</span></span>

## <a name="configure-warehouse-app-field-names"></a><span data-ttu-id="24cb5-111">A raktári alkalmazáson belüli mezőnevek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="24cb5-111">Configure warehouse app field names</span></span>

<span data-ttu-id="24cb5-112">Amikor a Warehousing alkalmazást a mobileszközön használja, konfigurálható, hogyan jelenjenek meg az eszközön a metaadatok **A raktári alkalmazáson belüli mezőnevek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="24cb5-112">When you use Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="24cb5-113">Egy felvett új vállalatnál válassza az **Alapértelmezett beállítás létrehozása** elemet a raktármodul mobileszközön használt munkafolyamataiban használt összes mezőnév létrehozásához, majd rendeljen hozzájuk egy elsődleges beviteli módot és beviteltípust.</span><span class="sxs-lookup"><span data-stu-id="24cb5-113">In a new company, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="24cb5-114">Az összes mezőnév létrehozása után a következő beviteli beállításokat választhatja ki.</span><span class="sxs-lookup"><span data-stu-id="24cb5-114">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24cb5-115">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="24cb5-115">Option</span></span></th>
<th><span data-ttu-id="24cb5-116">Leírás</span><span class="sxs-lookup"><span data-stu-id="24cb5-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="24cb5-117">Preferált beviteli mód</span><span class="sxs-lookup"><span data-stu-id="24cb5-117">Preferred input mode</span></span></td>
<td><span data-ttu-id="24cb5-118">Ez a beállítás határozza meg, hogy egy keresési mező vagy egy kézi beviteli mező jelenjen-e meg a kijelölt mezőnévnél.</span><span class="sxs-lookup"><span data-stu-id="24cb5-118">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="24cb5-119">Ez a mezők vonalkódhasználaton alapuló megkülönböztetéséhez hasznos.</span><span class="sxs-lookup"><span data-stu-id="24cb5-119">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="24cb5-120"><strong>Megjegyzés:</strong> azon mezőneveknél, amelyeknél az elsődleges beviteli mód beállítása <strong>Beolvasás</strong>, adatokat manuálisan is megadhat, ha a vonalkód nem olvasható vagy sérült.</span><span class="sxs-lookup"><span data-stu-id="24cb5-120"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="24cb5-121">Beviteltípus</span><span class="sxs-lookup"><span data-stu-id="24cb5-121">Input type</span></span></td>
<td><span data-ttu-id="24cb5-122">Ez a beállítás határozza meg, milyen beviteli típus legyen használva a kiválasztott mezőnévnél.</span><span class="sxs-lookup"><span data-stu-id="24cb5-122">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="24cb5-123">Négy lehetőség érhető el:</span><span class="sxs-lookup"><span data-stu-id="24cb5-123">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="24cb5-124"><strong>Kiválasztás</strong> - választható lehetőségek listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="24cb5-124"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="24cb5-125">Ezzel a beállítással a mezőnevek nem szerkeszthetők.</span><span class="sxs-lookup"><span data-stu-id="24cb5-125">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="24cb5-126"><strong>Dátum</strong> - a dátumként megadott mezőnevek dátumformátumot jelenítenek meg a címkével.</span><span class="sxs-lookup"><span data-stu-id="24cb5-126"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="24cb5-127">Ez segít a raktárosoknak látni, milyen formátumban adják meg a dátumot.</span><span class="sxs-lookup"><span data-stu-id="24cb5-127">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="24cb5-128">Ezzel a beállítással a mezőnevek nem szerkeszthetők.</span><span class="sxs-lookup"><span data-stu-id="24cb5-128">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="24cb5-129"><strong>Alfa</strong> - kiválasztása esetén az eszköz billentyűzetén kell adatokat manuálisan bevinni az alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="24cb5-129"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="24cb5-130">A billentyűzet felülete módosítható a használt eszköztől függően.</span><span class="sxs-lookup"><span data-stu-id="24cb5-130">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="24cb5-131"><strong>Numerikus</strong> - a csak numerikus bevitelt használó mezőneveknél ennek a lehetőségnek a kiválasztásával egyéni számbillentyűzet jeleníthető meg a beviteli mezőnél az eszköz billentyűzete helyett.</span><span class="sxs-lookup"><span data-stu-id="24cb5-131"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="24cb5-132">A raktári alkalmazáson belüli mezőprioritások beállítása</span><span class="sxs-lookup"><span data-stu-id="24cb5-132">Configure warehouse app field priority</span></span>

<span data-ttu-id="24cb5-133">**A raktári alkalmazáson belüli mezőprioritás** oldalon a mezőneveket különböző prioritási csoportokba rendezheti.</span><span class="sxs-lookup"><span data-stu-id="24cb5-133">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="24cb5-134">Ez lehetővé teszi annak eldöntését, hogy milyen információk jelenjenek meg a fő feladatlapon, amikor a raktári dolgozók feladatokat végeznek az alkalmazás használatával.</span><span class="sxs-lookup"><span data-stu-id="24cb5-134">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="24cb5-135">Ha az **Alapértelmezett beállítás létrehozása** elemre kattint, létrejön az alapértelmezés szerinti prioritáscsoportok sorozata.</span><span class="sxs-lookup"><span data-stu-id="24cb5-135">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="24cb5-136">Szükség szerint tetszőleges számú prioritási csoport hozható létre, de a feladatlapon csak három prioritási csoport jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="24cb5-136">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="24cb5-137">Amikor a rendszer metaadatokat küld az alkalmazásnak, minden mezőhöz relatív prioritást rendel a prioritási csoportjától függően, és az alkalmazás a metaadatokban található első három prioritási csoportot jeleníti meg a feladatlapon.</span><span class="sxs-lookup"><span data-stu-id="24cb5-137">When the system sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="24cb5-138">Az ezen felüli metaadatok a másodlagos részletek lapon jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="24cb5-138">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="24cb5-139">A következő táblázat öt prioritási csoportra mutat példát.</span><span class="sxs-lookup"><span data-stu-id="24cb5-139">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24cb5-140">Prioritási csoport</span><span class="sxs-lookup"><span data-stu-id="24cb5-140">Priority group</span></span></th>
<th><span data-ttu-id="24cb5-141">Hozzárendelt mezők</span><span class="sxs-lookup"><span data-stu-id="24cb5-141">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="24cb5-142">10. prioritás</span><span class="sxs-lookup"><span data-stu-id="24cb5-142">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="24cb5-143">Tétel</span><span class="sxs-lookup"><span data-stu-id="24cb5-143">Item</span></span></li>
<li><span data-ttu-id="24cb5-144">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="24cb5-144">Quantity</span></span></li>
<li><span data-ttu-id="24cb5-145">Mértékegység</span><span class="sxs-lookup"><span data-stu-id="24cb5-145">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="24cb5-146">20. prioritás</span><span class="sxs-lookup"><span data-stu-id="24cb5-146">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="24cb5-147">Fürtpozíció</span><span class="sxs-lookup"><span data-stu-id="24cb5-147">Cluster position</span></span></li>
<li><span data-ttu-id="24cb5-148">Fürt</span><span class="sxs-lookup"><span data-stu-id="24cb5-148">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="24cb5-149">30. prioritás</span><span class="sxs-lookup"><span data-stu-id="24cb5-149">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="24cb5-150">Cikk leírása</span><span class="sxs-lookup"><span data-stu-id="24cb5-150">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="24cb5-151">40. prioritás</span><span class="sxs-lookup"><span data-stu-id="24cb5-151">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="24cb5-152">Konfiguráció</span><span class="sxs-lookup"><span data-stu-id="24cb5-152">Configuration</span></span></li>
<li><span data-ttu-id="24cb5-153">Szín</span><span class="sxs-lookup"><span data-stu-id="24cb5-153">Color</span></span></li>
<li><span data-ttu-id="24cb5-154">Méret</span><span class="sxs-lookup"><span data-stu-id="24cb5-154">Size</span></span></li>
<li><span data-ttu-id="24cb5-155">Stílus</span><span class="sxs-lookup"><span data-stu-id="24cb5-155">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="24cb5-156">50. prioritás</span><span class="sxs-lookup"><span data-stu-id="24cb5-156">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="24cb5-157">Tárolóhely</span><span class="sxs-lookup"><span data-stu-id="24cb5-157">Location</span></span></li>
<li><span data-ttu-id="24cb5-158">Azonosítótábla</span><span class="sxs-lookup"><span data-stu-id="24cb5-158">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="24cb5-159">Például amikor egy raktári dolgozó valamilyen műveletet hajt végre egy mobileszközön, ha az alkalmazásban megjelenő metaadatok a következő mezőkből állnak:</span><span class="sxs-lookup"><span data-stu-id="24cb5-159">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="24cb5-160">Tétel</span><span class="sxs-lookup"><span data-stu-id="24cb5-160">Item</span></span>
-   <span data-ttu-id="24cb5-161">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="24cb5-161">Quantity</span></span>
-   <span data-ttu-id="24cb5-162">Mértékegység</span><span class="sxs-lookup"><span data-stu-id="24cb5-162">Unit of measure</span></span>
-   <span data-ttu-id="24cb5-163">Cikk leírása</span><span class="sxs-lookup"><span data-stu-id="24cb5-163">Item description</span></span>
-   <span data-ttu-id="24cb5-164">Méret és hely</span><span class="sxs-lookup"><span data-stu-id="24cb5-164">Size and Location</span></span>

<span data-ttu-id="24cb5-165">A raktári alkalmazás a fenti táblában beállított mezőprioritásai alapján a következő 3 sor információ jelenik meg a feladatlapon:</span><span class="sxs-lookup"><span data-stu-id="24cb5-165">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="24cb5-166">1. sor: Elem, Mennyiség, Mértékegysége</span><span class="sxs-lookup"><span data-stu-id="24cb5-166">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="24cb5-167">2. sor: Elem leírása</span><span class="sxs-lookup"><span data-stu-id="24cb5-167">Row 2: Item description</span></span>
-   <span data-ttu-id="24cb5-168">3. sor: méret</span><span class="sxs-lookup"><span data-stu-id="24cb5-168">Row 3: Size</span></span>

<span data-ttu-id="24cb5-169">A fennmaradó metaadatok, például a Hely nem fog megjelenni a feladatlapon, de megjelenik a részletek lapon.</span><span class="sxs-lookup"><span data-stu-id="24cb5-169">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="24cb5-170">További információért és a felhasználói felülettel kapcsolatos példákért olvassa el [A Finance and Operations- Warehousing bejelentése](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/) blogbejegyzést.</span><span class="sxs-lookup"><span data-stu-id="24cb5-170">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

<a name="additional-resources"></a><span data-ttu-id="24cb5-171">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="24cb5-171">Additional resources</span></span>
--------

[<span data-ttu-id="24cb5-172">A raktáralkalmazás telepítésének és konfigurálásának áttekintése</span><span class="sxs-lookup"><span data-stu-id="24cb5-172">Install and configure the warehouse app overview</span></span>](install-configure-warehousing-app.md)
