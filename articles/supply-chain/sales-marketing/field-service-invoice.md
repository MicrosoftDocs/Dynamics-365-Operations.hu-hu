---
title: Field Service megállapodási számlák szinkronizálása Supply Chain Management szabadszöveges számlákká
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Field Service szerződési számláinak a Dynamics 365 Supply Chain Management szolgáltatásban található szabadszöveges számláival történő szinkronizálására használatosak.
author: ChristianRytt
ms.date: 04/10/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: f3066741781bd9058e09d7f577a35df4c9b453d4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819208"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a><span data-ttu-id="9f9b7-103">Field Service megállapodási számlák szinkronizálása Supply Chain Management szabadszöveges számlákká</span><span class="sxs-lookup"><span data-stu-id="9f9b7-103">Synchronize agreement invoices in Field Service to free text invoices in Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="9f9b7-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Field Service szerződési számláinak a Dynamics 365 Supply Chain Management szolgáltatásban található szabadszöveges számláival történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-104">This topic discusses the templates and underlying tasks that are used to synchronize agreement invoices in Dynamics 365 Field Service to free text invoices in Dynamics 365 Supply Chain Management.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="9f9b7-105">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="9f9b7-105">Templates and tasks</span></span>

<span data-ttu-id="9f9b7-106">A következő sablon és a mögöttes feladatok használatosak a Field Service-ben lévő szerződéses számlák és a Supply Chain Management alkalmazásban lévő szabadszöveges számlák szinkronizálásához.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-106">The following template and underlying tasks are used to run synchronization of agreement invoices from Field Service to free text invoices in Supply Chain Management.</span></span>

<span data-ttu-id="9f9b7-107">**A sablon neve az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="9f9b7-107">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="9f9b7-108">Szerződéses számlák (Field Service-ből Supply Chain Management szolgáltatásba)</span><span class="sxs-lookup"><span data-stu-id="9f9b7-108">Agreement invoices (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="9f9b7-109">**A feladatok nevei az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="9f9b7-109">**Names of the tasks in the Data integration project**</span></span>

- <span data-ttu-id="9f9b7-110">Számlafejlécek</span><span class="sxs-lookup"><span data-stu-id="9f9b7-110">Invoice headers</span></span>
- <span data-ttu-id="9f9b7-111">Számlasorok</span><span class="sxs-lookup"><span data-stu-id="9f9b7-111">Invoice lines</span></span>

<span data-ttu-id="9f9b7-112">A következő szinkronizálás kötelezőe, mielőtt a szerződéses számlák szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="9f9b7-112">The following synchronization is required before synchronization of agreement invoices can occur:</span></span>

- <span data-ttu-id="9f9b7-113">Ügyfelek (Sales – Supply Chain Management) – közvetlen</span><span class="sxs-lookup"><span data-stu-id="9f9b7-113">Accounts (Sales to Supply Chain Management) – Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="9f9b7-114">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="9f9b7-114">Entity set</span></span>

| <span data-ttu-id="9f9b7-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="9f9b7-115">Field Service</span></span>  | <span data-ttu-id="9f9b7-116">Ellátásilánc-kezelés</span><span class="sxs-lookup"><span data-stu-id="9f9b7-116">Supply Chain Management</span></span>                 |
|----------------|----------------------------------------|
| <span data-ttu-id="9f9b7-117">számlák</span><span class="sxs-lookup"><span data-stu-id="9f9b7-117">invoices</span></span>       | <span data-ttu-id="9f9b7-118">Dataverse vevői szabadszöveges számlafejlécek</span><span class="sxs-lookup"><span data-stu-id="9f9b7-118">Dataverse customer free text invoice headers</span></span> |
| <span data-ttu-id="9f9b7-119">invoicedetails</span><span class="sxs-lookup"><span data-stu-id="9f9b7-119">invoicedetails</span></span> | <span data-ttu-id="9f9b7-120">Dataverse vevői szabadszöveges számlasorok</span><span class="sxs-lookup"><span data-stu-id="9f9b7-120">Dataverse customer free text invoice lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="9f9b7-121">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="9f9b7-121">Entity flow</span></span>

<span data-ttu-id="9f9b7-122">A szerződésből a Field Service-ben létrehozott számlák a Microsoft Dataverse (CDS) adatintegrációs projekten keresztül szinkronizálhatók a Supply Chain Management szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-122">Invoices that are created from an agreement in Field Service can be synchronized to Supply Chain Management via a Microsoft Dataverse Data integration project.</span></span> <span data-ttu-id="9f9b7-123">E számlák frissítései a Supply Chain Management szabadszöveges számláira szinkronizálódnak, ha a szabadszöveges számlák könyvelési állapota **Folyamatban**.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-123">Updates to these invoices will be synchronized to the free text invoices in Supply Chain Management if the accounting status of the free text invoices is **In process**.</span></span> <span data-ttu-id="9f9b7-124">Miután a szabadszöveges számlák könyvelési állapota a Supply Chain Management szolgáltatásban történő feladása után **Kész** értékre frissül, többé már nem szinkronizálhatók frissítések a Field Service-ből.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-124">After the free text invoices are posted in Supply Chain Management, and the accounting status is updated to **Completed**, you can no longer synchronize updates from Field Service.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="9f9b7-125">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="9f9b7-125">Field Service CRM solution</span></span>

<span data-ttu-id="9f9b7-126">A **Sorokat tartalmaz a szerződés eredetével** oszlop hozzá lett adva a **Számla** táblához.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-126">The **Has Lines With Agreement Origin** column has been added to the **Invoice** table.</span></span> <span data-ttu-id="9f9b7-127">Ez az oszlop garantálja, hogy csak a szerződésből létrehozott számlák legyenek szinkronizálhatók.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-127">This column helps guarantee that only invoices that are created from an agreement are synchronized.</span></span> <span data-ttu-id="9f9b7-128">Az érték **igaz**, ha a számla tartalmaz legalább egy számlasort, amely szerződésből származik.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-128">The value is **true** if the invoice contains at least one invoice line that originates from an agreement.</span></span>

<span data-ttu-id="9f9b7-129">A **Szerződéses eredetet tartalmaz** oszlop hozzá lett adva a **Számlasor** táblához.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-129">The **Has Agreement Origin** column has been added to the **Invoice Line** table.</span></span> <span data-ttu-id="9f9b7-130">Ez az oszlop garantálja, hogy csak a szerződésből létrehozott számlasorok legyenek szinkronizálhatók.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-130">This column helps guarantee that only invoice lines that are created from an agreement are synchronized.</span></span> <span data-ttu-id="9f9b7-131">Az érték **igaz**, ha a számlasor szerződésből származik.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-131">The value is **true** if the invoice line originates from an agreement.</span></span>

<span data-ttu-id="9f9b7-132">A **Számla dátuma** kötelező mező a Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-132">**Invoice date** is a mandatory field in Supply Chain Management.</span></span> <span data-ttu-id="9f9b7-133">Ebből következően az oszlopnak értékkel kell rendelkeznie a Field Service szolgáltatásban a szinkronizálás előtt.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-133">Therefore, the column must have a value in Field Service before synchronization occurs.</span></span> <span data-ttu-id="9f9b7-134">E követelmény teljesítéséhez a következő logika került hozzáadásra:</span><span class="sxs-lookup"><span data-stu-id="9f9b7-134">To meet this requirement, the following logic is added:</span></span>

- <span data-ttu-id="9f9b7-135">Ha a **Számladátum** oszlop üres a **Számla** táblában (azaz nincs értéke), akkor szerződésből eredő számlasor hozzáadásánál az aktuális dátumra kerül beállításra.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-135">If the **Invoice Date** column is blank on the **Invoice** table (that is, if it has no value), it's set to the current date when an invoice line that originates from an agreement is added.</span></span>
- <span data-ttu-id="9f9b7-136">A felhasználó módosíthatja a **Számladátum** oszlopot.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-136">The user can change the **Invoice Date** column.</span></span> <span data-ttu-id="9f9b7-137">Ha azonban a felhasználó megpróbál egy szerződésből eredő számlát menteni, üzletifolyamat-hibát kap, ha a **Számladátum** oszlop üres a számlán.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-137">However, when the user tries to save an invoice that originates from an agreement, he or she receives a business process error if the **Invoice Date** column is blank on the invoice.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="9f9b7-138">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="9f9b7-138">Prerequisites and mapping setup</span></span>

### <a name="in-supply-chain-management"></a><span data-ttu-id="9f9b7-139">A Supply Chain Management alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="9f9b7-139">In Supply Chain Management</span></span>

<span data-ttu-id="9f9b7-140">Az integrációhoz számlázási eredetet kell beállítani, hogy megkülönböztessük a szabadszöveges számlákat a Supply Chain Management szolgáltatásban, amelyek a Field Service szolgáltatásban lévő szerződéses számlák alapján jöttek létre.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-140">An invoice origin must be set up for the integration, to distinguish the free text invoices in Supply Chain Management that are created from agreement invoices in Field Service.</span></span> <span data-ttu-id="9f9b7-141">Ha egy számla számlaeredete a **Szerződéses számla integrációja** típusú, akkor a **Külső számlaszám** mező megjelenik az **Értékesítési számla** fejlécében.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-141">When an invoice has an invoice origin of the **Agreement invoice integration** type, the **External invoice number** field is shown on the **Sales invoice** header.</span></span>

<span data-ttu-id="9f9b7-142">Amellett, hogy a számla fejlécében megjelenik, a **Külső számlaszám** az információ felhasználható annak biztosítására, hogy a Field Service szolgáltatásban lévő, szerződéses számlákból létrehozott számlák szűrésre kerüljenek a Supply Chain Management és a Field Service közötti számlaszinkronizálás során.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-142">Besides appearing on the invoice header, the **External invoice number** information can be used to help guarantee that invoices that are created from Field Service agreement invoices are filtered out during invoice synchronization from Supply Chain Management to Field Service.</span></span>

1. <span data-ttu-id="9f9b7-143">Ugorjon a **Kinnlevőségek** \> **Beállítás** \> **Számla forráskódjai** pontra.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-143">Go to **Accounts receivable** \> **Setup** \> **Invoice origin codes**.</span></span>
2. <span data-ttu-id="9f9b7-144">Válassza az **Új** elemet új számlaeredet létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-144">Select **New** to create a new invoice origin.</span></span>
3. <span data-ttu-id="9f9b7-145">A **Számla eredete** mezőbe írjon be egy nevet a számla eredetének, például **FS**.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-145">In the **Invoice origin** field, enter a name for the invoice origin, such as **FS**.</span></span>
4. <span data-ttu-id="9f9b7-146">A **Leírás** mezőben adjon meg egy leírást, például **Field Service szerződéses számla**.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-146">In the **Description** field, enter a description, such as **Field Service Agreement Invoice**.</span></span>
5. <span data-ttu-id="9f9b7-147">Jelölje be az **Eredettípus hozzárendelése** négyzetet.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-147">Select the **Origin type assignment** check box.</span></span>
6. <span data-ttu-id="9f9b7-148">Állítsa a **Számla eredettípusa** mezőt **Szerződéses számla integrációja** értékre.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-148">Set the **Invoice origin type** field to **Agreement invoice integration**.</span></span>
7. <span data-ttu-id="9f9b7-149">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-149">Select **Save**.</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="9f9b7-150">Az adatintegrációs projektben</span><span class="sxs-lookup"><span data-stu-id="9f9b7-150">In the Data Integration project</span></span>

<span data-ttu-id="9f9b7-151">Feladat: **Számlasorok**</span><span class="sxs-lookup"><span data-stu-id="9f9b7-151">Task: **Invoice lines**</span></span>  

<span data-ttu-id="9f9b7-152">Győződjön meg arról, hogy Supply Chain Management **Fő számla megjelenítendő értéke** mezője frissül, hogy megfeleljen a kívánt értéknek.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-152">Make sure that the default value for the Supply Chain Management field **Main Account Display Value** is updated to match the desired value.</span></span>

<span data-ttu-id="9f9b7-153">Az alapértelmezett sablonérték **401100**.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-153">The default template value is **401100**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="9f9b7-154">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="9f9b7-154">Template mapping in Data integration</span></span>

<span data-ttu-id="9f9b7-155">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="9f9b7-155">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a><span data-ttu-id="9f9b7-156">Szerződéses számlák (Field Service-ből Supply Chain Managementbe): Számlafejlécek</span><span class="sxs-lookup"><span data-stu-id="9f9b7-156">Agreement invoices (Field Service to Supply Chain Management): Invoice headers</span></span>

<span data-ttu-id="9f9b7-157">[![Sablonleképezés az adatintegrátorban](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span><span class="sxs-lookup"><span data-stu-id="9f9b7-157">[![Template mapping in Data integration](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a><span data-ttu-id="9f9b7-158">Szerződéses számlák (Field Service-ből Supply Chain Managementbe): Számlasorok</span><span class="sxs-lookup"><span data-stu-id="9f9b7-158">Agreement invoices (Field Service to Supply Chain Management): Invoice lines</span></span>

<span data-ttu-id="9f9b7-159">[![Sablonleképezés az adatintegrátorban](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span><span class="sxs-lookup"><span data-stu-id="9f9b7-159">[![Template mapping in Data integration](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]