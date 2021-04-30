---
title: Ügyfélportál testre szabása és használata
description: Ez a témakör azt mutatja be, hogyan lehet testreszabni a Ügyfélportált a rendszerhez történő hozzáadását követően.
author: dasani-madipalli
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 6d4cc52a90b25406080032c7a98caa59f53ce188
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909000"
---
# <a name="customize-and-use-the-customer-portal"></a><span data-ttu-id="bf4b5-103">Ügyfélportál testre szabása és használata</span><span class="sxs-lookup"><span data-stu-id="bf4b5-103">Customize and use the Customer portal</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="bf4b5-104">Ez a témakör bemutatja azokat a különböző lapokat, amelyek a Ügyfélportál modulban gyári kiépítésben elérhetők.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-104">This topic describes the different pages that available in the Customer portal out of the box.</span></span> <span data-ttu-id="bf4b5-105">Bemutatja, hogy mire képesek a lapok, illetve hogyan lehet ezeket testre szabni.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-105">It explains what the pages do and how you can customize them.</span></span>

<span data-ttu-id="bf4b5-106">A Ügyfélportál néhány weblapot és műveletet kínál már gyári állapotban is.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-106">The Customer portal offers a few webpages and actions out of the box.</span></span> <span data-ttu-id="bf4b5-107">A következő oldaltérkép áttekintést nyújt ezekről a weboldalakról és műveletekről, valamint a műveletek végrehajtására képes szerepkörökről.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-107">The following site map provides an overview of those webpages and actions, and the roles that can perform the actions.</span></span>

<span data-ttu-id="bf4b5-108">![Ügyfélportál oldaltérképe](media/customer-portal-site-map.png "Ügyfélportál oldaltérképe")</span><span class="sxs-lookup"><span data-stu-id="bf4b5-108">![Customer portal site map](media/customer-portal-site-map.png "Customer portal site map")</span></span>

## <a name="typical-customizations"></a><span data-ttu-id="bf4b5-109">Jellemző testreszabások</span><span class="sxs-lookup"><span data-stu-id="bf4b5-109">Typical customizations</span></span>

<span data-ttu-id="bf4b5-110">A következő témakörökben megismerkedhet a Power Apps portálok alapjaival és a portálok testreszabásával:</span><span class="sxs-lookup"><span data-stu-id="bf4b5-110">The following topics will help you learn the basics about Power Apps portals and how you can customize portals:</span></span>

- <span data-ttu-id="bf4b5-111">[Sablonok használata](/powerapps/maker/portals/work-with-templates) – Ez a témakör általános áttekintést nyújt a Power Apps-portálok működéséről, valamint a portálok egyszerű testreszabásainak végrehajtásáról.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-111">[Work with templates](/powerapps/maker/portals/work-with-templates) – This topic provides a general overview of how Power Apps portals works and how you can do simple customizations of portals.</span></span>
- <span data-ttu-id="bf4b5-112">[Portáltartalom kezelése](/dynamics365/portals/manage-portal-content) – Ez a témakör azt mutatja be, hogyan lehet kezelni és testreszabni a portál felületén található tartalmakat.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-112">[Manage portal content](/dynamics365/portals/manage-portal-content) – This topic explains how you can manage and customize the content that you surface in your portal.</span></span>
- <span data-ttu-id="bf4b5-113">[CSS-szerkesztés](/powerapps/maker/portals/edit-css) – Ez a témakör a portál felhasználói felületének (UI) bonyolultabb testreszabásához nyújt segítséget.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-113">[Edit CSS](/powerapps/maker/portals/edit-css) – This topic helps you make more complex customizations to the user interface (UI) of your portal.</span></span>
- <span data-ttu-id="bf4b5-114">[Téma létrehozás a portálhoz](/dynamics365/portals/create-theme) – Ez a témakör segít létrehozni egy UI-témát a portálhoz.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-114">[Create a theme for your portal](/dynamics365/portals/create-theme) – This topic helps you create a UI theme for your portal.</span></span>
- <span data-ttu-id="bf4b5-115">[A portál tartalmának egyszerű létrehozása és közzététele](/dynamics365/portals/create-expose-portal-content) – Ez a témakör a portálon használt mögöttes adatok és táblák kezelését segíti.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-115">[Create and expose portal content easily](/dynamics365/portals/create-expose-portal-content) – This topic helps you manage the underlying data and tables that you use for your portal.</span></span>
- <span data-ttu-id="bf4b5-116">[A portálon használható kapcsolattartó konfigurálása](/powerapps/maker/portals/configure/configure-contacts) – Ez a témakör azt mutatja be, hogyan lehet létrehozni és testreszabni a felhasználói szerepköröket, valamint a biztonsági és a hitelesítés működését a Power Apps-portálokon.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-116">[Configure a contact for use on a portal](/powerapps/maker/portals/configure/configure-contacts) – This topic explains how to create and customize user roles, and how security and authentication work in Power Apps portals.</span></span>
- <span data-ttu-id="bf4b5-117">[A táblák űrlapjaihoz és a portálokon található webképernyőkhez tartozó megjegyzések konfigurálása](/powerapps/maker/portals/configure-notes) – Ez a témakör azt mutatja be, hogyan lehet dokumentumokat és további tárolóhelyeket hozzáadni a portálhoz.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-117">[Configure notes for table forms and web forms on portals](/powerapps/maker/portals/configure-notes) – This topic explains how to add documents and additional storage to your portal.</span></span>
- <span data-ttu-id="bf4b5-118">[Hibakezelés a portál webhelyéhez](/powerapps/maker/portals/admin/view-portal-error-log) – Ez a témakör azt mutatja be, hogyan lehet megtekinteni a portál hibanaplóit, és tárolni azokat a Microsoft Azure Blob tárolási fiókban.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-118">[Error handling for portal website](/powerapps/maker/portals/admin/view-portal-error-log) – This topic explains how to view portal error logs and store them in your Microsoft Azure Blob storage account.</span></span>

## <a name="customize-the-order-creation-process"></a><span data-ttu-id="bf4b5-119">A rendelés létrehozási folyamatának testreszabása</span><span class="sxs-lookup"><span data-stu-id="bf4b5-119">Customize the order creation process</span></span>

<span data-ttu-id="bf4b5-120">Amikor egy felhasználó a Ügyfélportál segítségével elküld egy rendelést, a program automatikusan szinkronizálja a rendelést a megfelelő Dynamics 365 Supply Chain Management-környezettel.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-120">When a user submits an order by using the Customer portal, the order is automatically synced to the corresponding Dynamics 365 Supply Chain Management environment.</span></span> <span data-ttu-id="bf4b5-121">Mivel a felhasználó egy külső vevő, néhány szükséges adatot szándékosan elrejtettek előle.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-121">Because the user is an external customer, some required information is intentionally hidden from him or her.</span></span> <span data-ttu-id="bf4b5-122">Ezt az információt a program automatikusan kitölti az űrlap elküldésekor.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-122">This information will automatically be filled in when the form is submitted.</span></span>

<span data-ttu-id="bf4b5-123">Ez a szakasz bemutatja, hogyan kell beállítani a kapcsolattartókat a hibák elkerülése érdekében.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-123">This section shows how you should set up contacts to avoid errors.</span></span> <span data-ttu-id="bf4b5-124">Ez a rész automatikusan beállított mezőket és a mezők értékének esetlegesen módosításának folyamatát írja le.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-124">It explains fields that are automatically set and how you can modify the value of those fields if you must.</span></span>

### <a name="the-out-of-box-order-creation-process"></a><span data-ttu-id="bf4b5-125">A gyári rendelés létrehozási folyamat</span><span class="sxs-lookup"><span data-stu-id="bf4b5-125">The out-of-box order creation process</span></span>

<span data-ttu-id="bf4b5-126">Itt megtekintheti a rendelésnek az Ügyfélportálról történő elküldésére vonatkozó szokásos lépéseket.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-126">Here are the standard steps for submitting an order from the Customer portal.</span></span>

1. <span data-ttu-id="bf4b5-127">Válassza ki a Kezdőlap **Rendelés létrehozása** csempéjét a **Rendelés létrehozása** varázsló megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-127">On the home page, select the **Create order** tile to open the **Create Order** wizard.</span></span>
1. <span data-ttu-id="bf4b5-128">A **Rendelés adatai** lapon állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="bf4b5-128">On the **Order Information** page, set the following fields:</span></span>

    - <span data-ttu-id="bf4b5-129">**Kért átvételi dátum** – Adja meg a kiszállítás dátumát.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-129">**Requested receipt date** – Specify the date of delivery.</span></span>
    - <span data-ttu-id="bf4b5-130">**Szállítási cím** – Adja meg azt a címet, amelyre a rendelést kézbesíteni kell.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-130">**Delivery address** – Enter the address that the order should be delivered to.</span></span>
    - <span data-ttu-id="bf4b5-131">**Vállalat** – Válassza ki a vevő vállalatának nevét.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-131">**Company** – Select the name of the customer company.</span></span> <span data-ttu-id="bf4b5-132">Ez a mező automatikusan be van állítva a nem rendszergazdai felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-132">This field is automatically set for non-admin users.</span></span>
    - <span data-ttu-id="bf4b5-133">**Igénylés száma** – Adja meg a rendelés igénylési számát.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-133">**Requisition number** – Enter the requisition number of the order.</span></span> <span data-ttu-id="bf4b5-134">A mező kitöltése nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-134">This field isn't required.</span></span>
    - <span data-ttu-id="bf4b5-135">**Szállítás országa/régiója** – Adja meg azt az országot vagy régiót, ahová a cikkeket szállítani fogják.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-135">**Ship to country/region** – Enter the country or region that the items will be delivered to.</span></span> <span data-ttu-id="bf4b5-136">Ez a mező automatikusan be van állítva a nem rendszergazdai felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-136">This field is automatically set for non-admin users.</span></span>

    <span data-ttu-id="bf4b5-137">![Rendelés adatai lap](media/customer-portal-order-information.png "Rendelés adatai lap")</span><span class="sxs-lookup"><span data-stu-id="bf4b5-137">![Order Information page](media/customer-portal-order-information.png "Order Information page")</span></span>

1. <span data-ttu-id="bf4b5-138">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-138">Select **Next**.</span></span>
1. <span data-ttu-id="bf4b5-139">A **Cikkek** oldalon válassza a **Cikk hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-139">On the **Items** page, select **Add Item**.</span></span>

    <span data-ttu-id="bf4b5-140">![Cikkek oldal](media/customer-portal-items.png "Cikkek oldal")</span><span class="sxs-lookup"><span data-stu-id="bf4b5-140">![Items page](media/customer-portal-items.png "Items page")</span></span>

1. <span data-ttu-id="bf4b5-141">A **Cikkinformáció** párbeszédpanelen a következő mezőket állítsa be:</span><span class="sxs-lookup"><span data-stu-id="bf4b5-141">In the **Item Information** dialog box, set the following fields:</span></span>

    - <span data-ttu-id="bf4b5-142">**Terméknév** – A rendeléshez hozzáadandó termék keresése és kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-142">**Product Name** – Find and select a product to add to the order.</span></span>
    - <span data-ttu-id="bf4b5-143">**Mennyiség** – Adja meg a kiválasztott termék mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-143">**Quantity** – Enter the quantity of the selected product.</span></span>
    - <span data-ttu-id="bf4b5-144">**Egység** – Adja meg a mértékegységet (például **ea.**, **kg** vagy **doboz**).</span><span class="sxs-lookup"><span data-stu-id="bf4b5-144">**Unit** – Specify the unit of measure (for example, **ea.**, **kgs**, or **box**).</span></span>
    - <span data-ttu-id="bf4b5-145">**Becsült nettó összeg** – Az érték számítása a kiválasztott egységhez tartozó mennyiség × a cikk becsült ára alapján történik.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-145">**Estimated net amount** – The value is calculated as the estimated price of the item × the quantity for the selected unit.</span></span>

    <span data-ttu-id="bf4b5-146">![Cikkinformáció párbeszédpanel](media/customer-portal-item-information.png "Cikkinformáció párbeszédpanel")</span><span class="sxs-lookup"><span data-stu-id="bf4b5-146">![Item Information dialog box](media/customer-portal-item-information.png "Item Information dialog box")</span></span>

1. <span data-ttu-id="bf4b5-147">Az **Beküldés** gombot választva vegye fel a cikket a rendelésbe.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-147">Select **Submit** to add the item to the order.</span></span>
1. <span data-ttu-id="bf4b5-148">Ismételje meg a 4–6. lépést, amíg fel nem vette az összes megrendelni kívánt cikket.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-148">Repeat steps 4 through 6 until you've added all the items that you want to order.</span></span>
1. <span data-ttu-id="bf4b5-149">Amikor befejezte a cikkek hozzáadását, válassza a **Tovább** lehetőséget a **Cikkek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-149">When you've finished adding items, select **Next** on the **Items** page.</span></span>
1. <span data-ttu-id="bf4b5-150">A **Rendelés adatai** lap a rendelés összesítését tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-150">The **Order Information** page provides a summary of the order.</span></span> <span data-ttu-id="bf4b5-151">A rendelés tartalmának és a szállítási adatoknak az áttekintése.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-151">Review the order contents and delivery details.</span></span> <span data-ttu-id="bf4b5-152">Ha minden megfelelőnek látszik, akkor a rendelés elküldéséhez válassza az **Elküldés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-152">If everything looks correct, select **Submit** to submit the order.</span></span>

    <span data-ttu-id="bf4b5-153">![Rendelés adatai lap](media/customer-portal-order-submit.png "Rendelés adatai lap")</span><span class="sxs-lookup"><span data-stu-id="bf4b5-153">![Order Information page](media/customer-portal-order-submit.png "Order Information page")</span></span>

### <a name="standard-data-setup"></a><span data-ttu-id="bf4b5-154">Standard adatbeállítás</span><span class="sxs-lookup"><span data-stu-id="bf4b5-154">Standard data setup</span></span>

<span data-ttu-id="bf4b5-155">A zökkenőmentes felhasználói élmény biztosításához a Ügyfélportál automatikusan kitölti az értékeket több kötelező mező esetében.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-155">To help ensure a smooth user experience, the Customer portal automatically fills in values for several required fields.</span></span> <span data-ttu-id="bf4b5-156">Ezek az értékek a rendelést beküldő vevő kapcsolattartói rekordjának adatain alapulnak.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-156">These values are based on information in the contact record of the customer who is submitting the order.</span></span>

<span data-ttu-id="bf4b5-157">Minden olyan [kapcsolattartói sorhoz](/powerapps/maker/portals/configure/configure-contacts), amely egy olyan vevőhöz tartozik, és az Ügyfélportált a rendelések elküldésére fogja használni, meg kell adni értékeket a következő kötelező mezőkben.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-157">For each [contact row](/powerapps/maker/portals/configure/configure-contacts) that belongs to a customer who will use the Customer portal to submit orders, values must be specified for the following required fields.</span></span> <span data-ttu-id="bf4b5-158">Ellenkező esetben hibák lépnek fel.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-158">Otherwise, errors will occur.</span></span>

- <span data-ttu-id="bf4b5-159">**Vállalat** A jogi személyt, amelyhez a rendelés tartozik</span><span class="sxs-lookup"><span data-stu-id="bf4b5-159">**Company** – The legal entity that the order belongs to</span></span>
- <span data-ttu-id="bf4b5-160">**Potenciális vevő** – A rendeléshez kapcsolódó ügyfélfiók</span><span class="sxs-lookup"><span data-stu-id="bf4b5-160">**Potential customer** – The customer account that is associated with the order</span></span>
- <span data-ttu-id="bf4b5-161">**Árlista** – A vevő egyéni árlistája</span><span class="sxs-lookup"><span data-stu-id="bf4b5-161">**Price list** – The custom price list for the customer</span></span>
- <span data-ttu-id="bf4b5-162">**Pénznem** – Az ár pénzneme</span><span class="sxs-lookup"><span data-stu-id="bf4b5-162">**Currency** – The currency of the price</span></span>
- <span data-ttu-id="bf4b5-163">**Szállítás országa/régiója** – Az ország vagy régió, ahová a cikkeket szállítani fogják</span><span class="sxs-lookup"><span data-stu-id="bf4b5-163">**Ship to country/region** – The country or region that the items will be delivered to</span></span>

<span data-ttu-id="bf4b5-164">A program automatikusan beállítja a következő mezőket az értékesítési rendelés táblához:</span><span class="sxs-lookup"><span data-stu-id="bf4b5-164">The following fields are automatically set for the sales order table:</span></span>

- <span data-ttu-id="bf4b5-165">**Nyelv** – A rendelés nyelve (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).</span><span class="sxs-lookup"><span data-stu-id="bf4b5-165">**Language** – The language of the order (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bf4b5-166">**Szállítás országa/régiója** – Az az ország vagy régió, ahová a cikkeket kézbesítik (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).</span><span class="sxs-lookup"><span data-stu-id="bf4b5-166">**Ship to country/region** – The country or region that the items will be delivered to (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bf4b5-167">**Kapcsolattartó** – Az a felhasználó, akivel a megrendeléssel kapcsolatban fel lehet venni a kapcsolatot (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).</span><span class="sxs-lookup"><span data-stu-id="bf4b5-167">**Contact person** – The user who can be contacted for information about the order (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bf4b5-168">**Vállalat** – Az a jogi személy, amelyhez a rendelés tartozik (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).</span><span class="sxs-lookup"><span data-stu-id="bf4b5-168">**Company** – The legal entity that the order belongs to (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bf4b5-169">**Potenciális vevő** – A rendeléshez társított vevőfiók (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).</span><span class="sxs-lookup"><span data-stu-id="bf4b5-169">**Potential customer** – The customer account that is associated with the order (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bf4b5-170">**Számla vevője** – A rendeléshez társított számlázás (alapértelmezés szerint ez az érték a potenciális vevő a kapcsolattartói rekordból).</span><span class="sxs-lookup"><span data-stu-id="bf4b5-170">**Invoice customer** – The billing account of the order (The default value is the potential customer from the contact record.)</span></span>
- <span data-ttu-id="bf4b5-171">**Értékesítési rendelés neve** – Az értékesítési rendelés neve (az alapértelmezett érték az **értékesítési rendelés**).</span><span class="sxs-lookup"><span data-stu-id="bf4b5-171">**Sales order name** – The name of the sales order (The default value is **sales order**.)</span></span>
- <span data-ttu-id="bf4b5-172">**Pénznem** – Az ár pénzneme (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).</span><span class="sxs-lookup"><span data-stu-id="bf4b5-172">**Currency** – The currency of the price (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bf4b5-173">**Árlista** – A vevő egyéni árlistája (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).</span><span class="sxs-lookup"><span data-stu-id="bf4b5-173">**Price list** – The custom price list for the customer (By default, the value is taken from the contact record.)</span></span>
- <span data-ttu-id="bf4b5-174">**Szállítási cím leírása** – Az értékesítési rendelés szállítási címe (az alapértelmezett érték a **szállítási cím leírása**.)</span><span class="sxs-lookup"><span data-stu-id="bf4b5-174">**Delivery address description** – The delivery address of the sales order (The default value is **delivery address description**.)</span></span>

### <a name="modify-the-order-creation-process"></a><span data-ttu-id="bf4b5-175">A rendelés létrehozási folyamatának módosítása</span><span class="sxs-lookup"><span data-stu-id="bf4b5-175">Modify the order creation process</span></span>

<span data-ttu-id="bf4b5-176">Szabadon módosíthatja a Ügyfélportál megjelenését és kezelőfelületét, ha nem módosítja az alapvető rendelési létrehozási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-176">You can freely modify the appearance and UI of the Customer portal if you don't change the basic order creation process.</span></span> <span data-ttu-id="bf4b5-177">Ha módosítani szeretné a rendelés létrehozási folyamatát, akkor van néhány dolog, amelyet szem előtt kell tartania.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-177">If you want to change the order creation process, there are a few points that you must keep in mind.</span></span>

<span data-ttu-id="bf4b5-178">Ne távolítsa el a következő oszlopokat az értékesítési rendelés táblából Microsoft Dataverse-szolgáltatásban, mert ezek szükségesek egy értékesítési rendelés létrehozásához a kettős írásban:</span><span class="sxs-lookup"><span data-stu-id="bf4b5-178">Don't remove the following columns from the sales order table in Microsoft Dataverse, because they are required to create a sales order in dual-write:</span></span>

- <span data-ttu-id="bf4b5-179">**Vállalat** A jogi személyt, amelyhez a rendelés tartozik</span><span class="sxs-lookup"><span data-stu-id="bf4b5-179">**Company** – The legal entity that the order belongs to</span></span>
- <span data-ttu-id="bf4b5-180">**Név** – Az értékesítési rendelés neve</span><span class="sxs-lookup"><span data-stu-id="bf4b5-180">**Name** – The name of the sales order</span></span>
- <span data-ttu-id="bf4b5-181">**Pénznem** – Az ár pénzneme</span><span class="sxs-lookup"><span data-stu-id="bf4b5-181">**Currency** – The currency of the price</span></span>
- <span data-ttu-id="bf4b5-182">**Árlista** – A vevő egyéni árlistája</span><span class="sxs-lookup"><span data-stu-id="bf4b5-182">**Price list** – The custom price list for the customer</span></span>
- <span data-ttu-id="bf4b5-183">**Szállítás országa/régiója** – Az ország vagy régió, ahová a cikkeket szállítani fogják</span><span class="sxs-lookup"><span data-stu-id="bf4b5-183">**Ship to country/region** – The country or region that the items will be delivered to</span></span>
- <span data-ttu-id="bf4b5-184">**Potenciális vevő** – A rendeléshez kapcsolódó ügyfélfiók</span><span class="sxs-lookup"><span data-stu-id="bf4b5-184">**Potential customer** – The customer account that is associated with the order</span></span>
- <span data-ttu-id="bf4b5-185">**Nyelv** – A rendelés nyelve (általában ez a nyelv a potenciális vevő nyelve.)</span><span class="sxs-lookup"><span data-stu-id="bf4b5-185">**Language** – The language of the order (Typically, this language is the language of the potential customer.)</span></span>
- <span data-ttu-id="bf4b5-186">**Szállítási cím leírása** – Az értékesítési rendelés szállítási címe</span><span class="sxs-lookup"><span data-stu-id="bf4b5-186">**Delivery address description** – The delivery address of the sales order</span></span>

<span data-ttu-id="bf4b5-187">A cikkek esetében a következő oszlopok kötelezők:</span><span class="sxs-lookup"><span data-stu-id="bf4b5-187">For items, the following columns are required:</span></span>

- <span data-ttu-id="bf4b5-188">**Termék** – A megrendelendő termék</span><span class="sxs-lookup"><span data-stu-id="bf4b5-188">**Product** – The product to order</span></span>
- <span data-ttu-id="bf4b5-189">**Mennyiség** – A kiválasztott termék mennyisége</span><span class="sxs-lookup"><span data-stu-id="bf4b5-189">**Quantity** – The quantity of the selected product</span></span>
- <span data-ttu-id="bf4b5-190">**Egység** – A mértékegység (például **ea.**, **kg** vagy **doboz**)</span><span class="sxs-lookup"><span data-stu-id="bf4b5-190">**Unit** – The unit of measure (for example, **ea.**, **kgs**, or **box**)</span></span>
- <span data-ttu-id="bf4b5-191">**Szállítás országa/régiója** – A szállítás országa vagy régiója</span><span class="sxs-lookup"><span data-stu-id="bf4b5-191">**Ship to country/region** – The country or region of delivery</span></span>
- <span data-ttu-id="bf4b5-192">**Szállítási cím leírása** – A rendelés szállítási címe</span><span class="sxs-lookup"><span data-stu-id="bf4b5-192">**Delivery address description** – The delivery address of the order</span></span>

<span data-ttu-id="bf4b5-193">Győződjön meg róla, hogy a Ügyfélportálja valamilyen módon az összes oszlophoz elküld értékeket.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-193">You must make sure that your Customer portal somehow submits values for all these columns.</span></span>

<span data-ttu-id="bf4b5-194">Ha oszlopokat kíván felvenni a lapra, vagy el szeretné távolítani az oszlopokat, tekintse meg a következő témakört: [Gyors létrehozási űrlapok létrehozása vagy szerkesztése egyszerű adatbeviteli élményhez](/dynamics365/customerengagement/on-premises/customize/create-edit-quick-create-forms).</span><span class="sxs-lookup"><span data-stu-id="bf4b5-194">If you want to add columns to the page, or remove columns, see [Create or edit quick create forms for a streamlined data entry experience](/dynamics365/customerengagement/on-premises/customize/create-edit-quick-create-forms).</span></span>

<span data-ttu-id="bf4b5-195">Ha módosítani szeretné az oszlopok előbeállítását, és azt, hogy hogyan legyenek beállítva az értékek a lap mentésekor, tekintse át a következő információkat a Power Apps portálok dokumentációjában:</span><span class="sxs-lookup"><span data-stu-id="bf4b5-195">If you want to change how columns are preset and how values are set when the page is saved, see the following information in the Power Apps portals documentation:</span></span>

- [<span data-ttu-id="bf4b5-196">Mező előzetes kitöltése</span><span class="sxs-lookup"><span data-stu-id="bf4b5-196">Prepopulate field</span></span>](/powerapps/maker/portals/configure/configure-web-form-metadata#prepopulate-field)
- [<span data-ttu-id="bf4b5-197">Érték beállítása mentéskor</span><span class="sxs-lookup"><span data-stu-id="bf4b5-197">Set Value On Save</span></span>](/powerapps/maker/portals/configure/configure-web-form-metadata#set-value-on-save)

## <a name="customize-the-home-page"></a><span data-ttu-id="bf4b5-198">A kezdőlap testreszabása</span><span class="sxs-lookup"><span data-stu-id="bf4b5-198">Customize the home page</span></span>

<span data-ttu-id="bf4b5-199">A Ügyfélportál összes vezérlője beépített Power Apps portálvezérlő.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-199">All the controls in the Customer portal are built-in Power Apps portals controls.</span></span> <span data-ttu-id="bf4b5-200">Ezeket úgy szabhatja testre, ha követi a [Lap létrehozása](/powerapps/maker/portals/compose-page) szakasz lépéseit a Power Apps portálok dokumentációjában.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-200">You can customize them by following the steps in [Compose a page](/powerapps/maker/portals/compose-page) in the Power Apps portals documentation.</span></span>

<span data-ttu-id="bf4b5-201">Az Ügyfélportál sablonban szereplő egyetlen egyéni vezérlő a kezdőlapon lévő csempék létrehozásához használatos.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-201">The only custom control that is included in the Customer portal template is used to create the tiles on the home page.</span></span>

<span data-ttu-id="bf4b5-202">![A kezdőlap csempéi](media/customer-portal-home-page-tiles.png "A kezdőlap csempéi")</span><span class="sxs-lookup"><span data-stu-id="bf4b5-202">![Tiles on the home page](media/customer-portal-home-page-tiles.png "Tiles on the home page")</span></span>

<span data-ttu-id="bf4b5-203">A csempék módosításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-203">To modify the tiles, follow these steps.</span></span>

1. <span data-ttu-id="bf4b5-204">Nyissa meg a [Portálkezelő alkalmazást](/powerapps/maker/portals/configure/configure-portal).</span><span class="sxs-lookup"><span data-stu-id="bf4b5-204">Open the [Portal Management app](/powerapps/maker/portals/configure/configure-portal).</span></span>
1. <span data-ttu-id="bf4b5-205">A bal oldali navigációs ablakban válassza ki az **Oldalsablonok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-205">In the navigation pane on the left, select **Page Templates**.</span></span>

    <span data-ttu-id="bf4b5-206">![A portálkezelő navigációs panel](media/customer-portal-nav.png "A portálkezelő navigációs panel")</span><span class="sxs-lookup"><span data-stu-id="bf4b5-206">![Portal Management navigation pane](media/customer-portal-nav.png "Portal Management navigation pane")</span></span>

1. <span data-ttu-id="bf4b5-207">Válassza ki az **Otthon** nevű oldalsablont.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-207">Select the page template that is named **Home**.</span></span>
1. <span data-ttu-id="bf4b5-208">A **Webes sablon** mezőben válassza ki a **Kezdőlap** hivatkozását a lap forráskódjának megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-208">In the **Web Template** field, select the **Home** link to open the source code for that page.</span></span>

    <span data-ttu-id="bf4b5-209">![Webes sablon mező](media/customer-portal-web-template.png "Webes sablon mező")</span><span class="sxs-lookup"><span data-stu-id="bf4b5-209">![Web Template field](media/customer-portal-web-template.png "Web Template field")</span></span>

1. <span data-ttu-id="bf4b5-210">Most látja a kezdőlap összes forráskódját, és azt igény szerint módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="bf4b5-210">You should now see all the source code for the home page and can modify it as you require.</span></span>

## <a name="resources"></a><span data-ttu-id="bf4b5-211">Erőforrások</span><span class="sxs-lookup"><span data-stu-id="bf4b5-211">Resources</span></span>

<span data-ttu-id="bf4b5-212">A Ügyfélportál beállításával és testreszabásával kapcsolatos további tudnivalókat lásd a következő forrásokban:</span><span class="sxs-lookup"><span data-stu-id="bf4b5-212">To learn more about how you can set up and customize the Customer portal, see the following resources:</span></span>

- [<span data-ttu-id="bf4b5-213">Power Apps portálok dokumentációja</span><span class="sxs-lookup"><span data-stu-id="bf4b5-213">Power Apps portals documentation</span></span>](/powerapps/maker/portals/overview)
- [<span data-ttu-id="bf4b5-214">Kettős írás dokumentációja</span><span class="sxs-lookup"><span data-stu-id="bf4b5-214">Dual-write documentation</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)
- [<span data-ttu-id="bf4b5-215">A portál életciklusáról</span><span class="sxs-lookup"><span data-stu-id="bf4b5-215">About portal lifecycle</span></span>](/powerapps/maker/portals/admin/portal-lifecycle)
- [<span data-ttu-id="bf4b5-216">Portál frissítése</span><span class="sxs-lookup"><span data-stu-id="bf4b5-216">Upgrade a portal</span></span>](/powerapps/maker/portals/admin/upgrade-portal)
- [<span data-ttu-id="bf4b5-217">Portál konfigurációjának áttelepítése</span><span class="sxs-lookup"><span data-stu-id="bf4b5-217">Migrate portal configuration</span></span>](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [<span data-ttu-id="bf4b5-218">Megoldás életciklus-kezelése: Dynamics 365 for Customer Engagement alkalmazásokhoz</span><span class="sxs-lookup"><span data-stu-id="bf4b5-218">Solution Lifecycle Management: Dynamics 365 for Customer Engagement apps</span></span>](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]