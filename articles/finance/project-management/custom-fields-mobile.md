---
title: Egyéni mezők megvalósítása a Microsoft Dynamics 365 Project Timesheet mobilalkalmazás számára iOS és Android rendszeren
description: Ez a témakör gyakori mintákat mutat be a bővítmények egyéni mezők megvalósításáról való használatával kapcsolatban.
author: KimANelson
manager: AnnBe
ms.date: 05/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: 10.0.3
ms.search.validFrom: 2019-05-29
ms.openlocfilehash: c0c578ca44919671b67daeea51a9ec7687f755c9
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773645"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a><span data-ttu-id="5a4d6-103">Egyéni mezők megvalósítása a Microsoft Dynamics 365 Project Timesheet mobilalkalmazás számára iOS és Android rendszeren</span><span class="sxs-lookup"><span data-stu-id="5a4d6-103">Implement custom fields for the Microsoft Dynamics 365 Project Timesheet mobile app on iOS and Android</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5a4d6-104">Ez a témakör gyakori mintákat mutat be a bővítmények egyéni mezők megvalósításáról való használatával kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-104">This topic provides common patterns for using extensions to implement custom fields.</span></span> <span data-ttu-id="5a4d6-105">A következő témaköröket fedi le:</span><span class="sxs-lookup"><span data-stu-id="5a4d6-105">The following topics are covered:</span></span>

- <span data-ttu-id="5a4d6-106">A különböző adattípusok, amelyeket az egyénimező-keretrendszer támogat</span><span class="sxs-lookup"><span data-stu-id="5a4d6-106">The various data types that the custom field framework supports</span></span>
- <span data-ttu-id="5a4d6-107">A munkaidő-nyilvántartási bejegyzések írásvédett vagy szerkeszthető mezőinek megjelenítése és a felhasználó által megadott értékek mentése az adatbázisba</span><span class="sxs-lookup"><span data-stu-id="5a4d6-107">How to show read-only or editable fields on timesheet entries, and save user-provided values back to the database</span></span>
- <span data-ttu-id="5a4d6-108">A munkaidő-nyilvántartás fejlécében szereplő írásvédett mezők megjelenítése</span><span class="sxs-lookup"><span data-stu-id="5a4d6-108">How to show read-only fields on the timesheet header</span></span>
- <span data-ttu-id="5a4d6-109">Egyéb egyéni üzleti logika integrálása az alapértelmezett értékek mezőkbe történő beírásához és a további ellenőrzés elvégzéséhez</span><span class="sxs-lookup"><span data-stu-id="5a4d6-109">How to integrate other custom business logic to enter default values in fields and do additional validation</span></span>

## <a name="audience"></a><span data-ttu-id="5a4d6-110">Közönség</span><span class="sxs-lookup"><span data-stu-id="5a4d6-110">Audience</span></span>

<span data-ttu-id="5a4d6-111">Ez a témakör azoknak a fejlesztőknek készült, akik egyéni mezőket integrálnak a Microsoft Dynamics 365 Project Timesheet mobilalkalmazásba, amely Apple iOS és Google Android rendszeren érhető el.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-111">This topic is intended for developers who are integrating their custom fields into the Microsoft Dynamics 365 Project Timesheet mobile application that is available for Apple iOS and Google Android.</span></span> <span data-ttu-id="5a4d6-112">A feltételezés az, hogy az olvasók ismerik az X++ fejlesztési és projekt-időnyilvántartási funkciókat.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-112">The assumption is that readers are familiar with X++ development and project timesheet functionality.</span></span>

## <a name="data-contract--tstimesheetcustomfield-x-class"></a><span data-ttu-id="5a4d6-113">Adatszerződés – TSTimesheetCustomField X++ osztály</span><span class="sxs-lookup"><span data-stu-id="5a4d6-113">Data contract – TSTimesheetCustomField X++ class</span></span>

<span data-ttu-id="5a4d6-114">A **TSTimesheetCustomField** osztály az X++ adatszerződés-osztály, amely a munkaidő-nyilvántartási funkció egyéni mezőjével kapcsolatos információkat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-114">The **TSTimesheetCustomField** class is the X++ data contract class that represents information about a custom field for timesheet functionality.</span></span> <span data-ttu-id="5a4d6-115">Az egyéni mezőobjektumok listái mind a TSTimesheetDetails-, mind a TSTimesheetEntry-adatszerződésben megjelennek a mobilalkalmazás egyéni mezőinek megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-115">Lists of the custom field objects are passed on both the TSTimesheetDetails data contract and the TSTimesheetEntry data contract to show custom fields in the mobile app.</span></span>

- <span data-ttu-id="5a4d6-116">**TSTimesheetDetails** – Az időnyilvántartás fejlécének szerződése.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-116">**TSTimesheetDetails** - The timesheet header contract.</span></span>
- <span data-ttu-id="5a4d6-117">**TSTimesheetEntry** – A munkaidő-nyilvántartási tranzakció szerződése.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-117">**TSTimesheetEntry** - The timesheet transaction contract.</span></span> <span data-ttu-id="5a4d6-118">Ezeknek az objektumoknak az a csoportja, amelyek ugyanazzal a projektadatokkal és **timesheetLineRecId** értékkel rendelkeznek, egy sort alkotnak.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-118">Groups of these objects that have the same project information and **timesheetLineRecId** value constitute a line.</span></span>

### <a name="fieldbasetype-types"></a><span data-ttu-id="5a4d6-119">fieldBaseType (Típusok)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-119">fieldBaseType (Types)</span></span>

<span data-ttu-id="5a4d6-120">A **TsTimesheetCustom** objektum **FieldBaseType** tulajdonsága meghatározza az alkalmazásban megjelenő mező típusát.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-120">The **FieldBaseType** property on the **TsTimesheetCustom** object determines the type of the field that appears in the app.</span></span> <span data-ttu-id="5a4d6-121">A következő **Típusok** értékek támogatottak.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-121">The following **Types** values that are supported.</span></span>

| <span data-ttu-id="5a4d6-122">Típusok értéke</span><span class="sxs-lookup"><span data-stu-id="5a4d6-122">Types value</span></span> | <span data-ttu-id="5a4d6-123">Típus</span><span class="sxs-lookup"><span data-stu-id="5a4d6-123">Type</span></span>              | <span data-ttu-id="5a4d6-124">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5a4d6-124">Notes</span></span> |
|-------------|-------------------|-------|
| <span data-ttu-id="5a4d6-125">0</span><span class="sxs-lookup"><span data-stu-id="5a4d6-125">0</span></span>           | <span data-ttu-id="5a4d6-126">Karakterlánc (és felsorolás)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-126">String (and Enum)</span></span> | <span data-ttu-id="5a4d6-127">A mező szöveges mezőként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-127">The field appears as a text field.</span></span> |
| <span data-ttu-id="5a4d6-128">1</span><span class="sxs-lookup"><span data-stu-id="5a4d6-128">1</span></span>           | <span data-ttu-id="5a4d6-129">Egész</span><span class="sxs-lookup"><span data-stu-id="5a4d6-129">Integer</span></span>           | <span data-ttu-id="5a4d6-130">Az érték tizedesjegyek nélküli számként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-130">The value is shown as a number without decimal places.</span></span> |
| <span data-ttu-id="5a4d6-131">2</span><span class="sxs-lookup"><span data-stu-id="5a4d6-131">2</span></span>           | <span data-ttu-id="5a4d6-132">Valós</span><span class="sxs-lookup"><span data-stu-id="5a4d6-132">Real</span></span>              | <span data-ttu-id="5a4d6-133">Az érték tizedesjegyekkel megadott számként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-133">The value is shown as a number that has decimal places.</span></span><p><span data-ttu-id="5a4d6-134">Ha meg szeretné jeleníteni a tényleges értéket pénznemként az alkalmazásban, használja a **fieldExtenededType** tulajdonságot.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-134">To show the real value as a currency in the app, use the **fieldExtenededType** property.</span></span> <span data-ttu-id="5a4d6-135">A megjelenő tizedesjegyek számának megadására a **numberOfDecimals** tulajdonság használható.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-135">You can use the **numberOfDecimals** property to set the number of decimal places that are shown.</span></span></p> |
| <span data-ttu-id="5a4d6-136">3</span><span class="sxs-lookup"><span data-stu-id="5a4d6-136">3</span></span>           | <span data-ttu-id="5a4d6-137">Dátum</span><span class="sxs-lookup"><span data-stu-id="5a4d6-137">Date</span></span>              | <span data-ttu-id="5a4d6-138">A dátumformátum meghatározása a felhasználó által a felhasználó által megadott **Dátum-, idő- és számformátum** beállítás alapján történik, amelyet a **Felhasználói beállítások** **Nyelv- és ország/régiópreferencia** pontban lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-138">Date formats are determined by the user's **Date, times, and number format** setting that is specified under **Language and country/region preference** in **User options**.</span></span> |
| <span data-ttu-id="5a4d6-139">4</span><span class="sxs-lookup"><span data-stu-id="5a4d6-139">4</span></span>           | <span data-ttu-id="5a4d6-140">Logikai</span><span class="sxs-lookup"><span data-stu-id="5a4d6-140">Boolean</span></span>           | |
| <span data-ttu-id="5a4d6-141">15</span><span class="sxs-lookup"><span data-stu-id="5a4d6-141">15</span></span>          | <span data-ttu-id="5a4d6-142">GUID</span><span class="sxs-lookup"><span data-stu-id="5a4d6-142">GUID</span></span>              | |
| <span data-ttu-id="5a4d6-143">16</span><span class="sxs-lookup"><span data-stu-id="5a4d6-143">16</span></span>          | <span data-ttu-id="5a4d6-144">Int64</span><span class="sxs-lookup"><span data-stu-id="5a4d6-144">Int64</span></span>             | |

- <span data-ttu-id="5a4d6-145">Ha a **stringOptions** tulajdonság nem szerepel a **TSTimesheetCustomField** objektumban, a felhasználó számára egy szabad szöveges mezőt áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-145">If the **stringOptions** property isn't provided on the **TSTimesheetCustomField** object, a free-text field is provided to the user.</span></span>

    <span data-ttu-id="5a4d6-146">A **stringLength** tulajdonsággal beállítható a maximálisan megadható karakterlánc hossza.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-146">The **stringLength** property can be used to set the maximum string length that users can enter.</span></span>

- <span data-ttu-id="5a4d6-147">Ha a **stringOptions** tulajdonság szerepel a **TSTimesheetCustomField** objektumban, ezek a listaelemek az egyetlen értékek, amelyet a felhasználó a választási gombok (választógombok) használatával választhat ki.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-147">If the **stringOptions** property is provided on the **TSTimesheetCustomField** object, those list elements are the only values that users can select by using option buttons (radio buttons).</span></span>

    <span data-ttu-id="5a4d6-148">Ebben az esetben a karakterlánc-mező felsorolási értékként működhet a felhasználói bejegyzés céljához.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-148">In this case, the string field can act as an enum value for the purpose of user entry.</span></span> <span data-ttu-id="5a4d6-149">Ha az értéket felsorolásként szeretné menteni az adatbázisba, akkor az adatbázisba történő mentés előtt manuálisan hozzá kell rendelnie a karakterlánc értékét a felsorolás értékéhez (lásd: „Parancslánc használata a TSTimesheetEntryService osztályon az időnyilvántartás-bejegyzés alkalmazásból az adatbázisba való mentéséhez” szakaszt később ebben a témakörben példaként).</span><span class="sxs-lookup"><span data-stu-id="5a4d6-149">To save the value to the database as an enum, manually map the string value back to the enum value before you save to the database by using chain of command (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a><span data-ttu-id="5a4d6-150">fieldExtendedType (TSCustomFieldExtendedType)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-150">fieldExtendedType (TSCustomFieldExtendedType)</span></span>

<span data-ttu-id="5a4d6-151">Ez a tulajdonság a tényleges értékek pénznemként történő formázására használható.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-151">You can use this property to format real values as currency.</span></span> <span data-ttu-id="5a4d6-152">Ez a megközelítés csak akkor alkalmazható, ha a **fieldBaseType** értéke **Valódi**.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-152">This approach is applicable only when the **fieldBaseType** value is **Real**.</span></span>

- <span data-ttu-id="5a4d6-153">**TSCustomFieldExtendedType:Nincs** – Nincs formázás alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-153">**TSCustomFieldExtendedType:None** – No formatting is applied.</span></span>
- <span data-ttu-id="5a4d6-154">**TSCustomFieldExtendedType::Pénznem** – Az érték formázása fizetőeszközként.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-154">**TSCustomFieldExtendedType::Currency** – Format the value as currency.</span></span>

    <span data-ttu-id="5a4d6-155">Ha aktív a pénznem formázása, akkor a **stringValue** mező felhasználható az alkalmazásban megjelenítendő pénznemkód elküldéséhez.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-155">When currency formatting is active, the **stringValue** field can be used pass the currency code that should be shown in the app.</span></span> <span data-ttu-id="5a4d6-156">Az érték írásvédett érték.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-156">The value is a read-only value.</span></span>

    <span data-ttu-id="5a4d6-157">A **realValue** mező az adatbázisba mentendő pénzösszeget tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-157">The **realValue** field contains the money amount that should be saved to the database.</span></span>

### <a name="fieldsection-tscustomfieldsection"></a><span data-ttu-id="5a4d6-158">fieldSection (TSCustomFieldSection)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-158">fieldSection (TSCustomFieldSection)</span></span>

<span data-ttu-id="5a4d6-159">Ezt a tulajdonságot akkor kell megadni, ha az egyéni mezőnek meg kell jelennie az alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-159">You can use this property specify where the custom field should appear in the app.</span></span>

- <span data-ttu-id="5a4d6-160">**TSCustomFieldSection::Fejléc** – A mező az alkalmazás **További részletek megjelenítése** szakaszában fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-160">**TSCustomFieldSection::Header** – The field will appear in the **View more details** section in the app.</span></span> <span data-ttu-id="5a4d6-161">Mindkettő mező mindig csak olvasható mező.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-161">These fields are always read-only.</span></span>
- <span data-ttu-id="5a4d6-162">**TSCustomFieldSection::Sor** – A mező a munkaidő-nyilvántartási bejegyzések összes beépített sormezője után fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-162">**TSCustomFieldSection::Line** – The field will appear after all the out-of-box line fields on timesheet entries.</span></span> <span data-ttu-id="5a4d6-163">Ezek a mezők lehetnek szerkeszthetők és írásvédettek is.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-163">These fields can be either editable or read-only.</span></span>

### <a name="fieldname-fieldnameshort"></a><span data-ttu-id="5a4d6-164">fieldName (FieldNameShort)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-164">fieldName (FieldNameShort)</span></span>

<span data-ttu-id="5a4d6-165">Ez a tulajdonság azonosítja azt a mezőt, amikor az alkalmazás által biztosított értékeket visszamentették az adatbázisba.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-165">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="tablename-tablenameshort"></a><span data-ttu-id="5a4d6-166">tableName (TableNameShort)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-166">tableName (TableNameShort)</span></span>

<span data-ttu-id="5a4d6-167">Ez a tulajdonság azonosítja azt a mezőt, amikor az alkalmazás által biztosított értékeket visszamentették az adatbázisba.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-167">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="iseditable-noyes"></a><span data-ttu-id="5a4d6-168">isEditable (NoYes)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-168">isEditable (NoYes)</span></span>

<span data-ttu-id="5a4d6-169">Ennek a tulajdonságnak az **Igen** értékre állításával megadhatja, hogy az időnyilvántartás-bejegyzés szakasz mezőjét a felhasználók szerkeszthetik-e.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-169">Set this property to **Yes** to specify that the field in the timesheet entry section should be editable by users.</span></span> <span data-ttu-id="5a4d6-170">A tulajdonság **Nem** értékre állításával a mező írásvédett.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-170">Set the property to **No** to make the field read-only.</span></span>

### <a name="ismandatory-noyes"></a><span data-ttu-id="5a4d6-171">isMandatory (NoYes)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-171">isMandatory (NoYes)</span></span>

<span data-ttu-id="5a4d6-172">Ennek a tulajdonságnak az **Igen** értékre állításával megadhatja, hogy az időnyilvántartás-bejegyzés szakasz mezőjét kötelező-e megadni.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-172">Set this property to **Yes** to specify that the field in the timesheet entry section should be mandatory.</span></span>

### <a name="label-str"></a><span data-ttu-id="5a4d6-173">címke (str)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-173">label (str)</span></span>

<span data-ttu-id="5a4d6-174">Ez a tulajdonság azt a címkét határozza meg, amely az alkalmazásban a mező mellett látható.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-174">This property specifies the label that is shown next the field in the app.</span></span>

### <a name="stringoptions-list-of-strings"></a><span data-ttu-id="5a4d6-175">stringOptions (Karakterláncok listája)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-175">stringOptions (List of Strings)</span></span>

<span data-ttu-id="5a4d6-176">Ez a tulajdonság csak akkor használható, ha a **fieldBaseType** értéke **Karakterlánc**.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-176">This property is applicable only when **fieldBaseType** is set to **String**.</span></span> <span data-ttu-id="5a4d6-177">Ha a **stringOptions** be van állítva, akkor a választógombokon keresztül választható karakterlánc-értékeket a lista karakterláncai határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-177">If **stringOptions** is set, the string values that are available for selection via option buttons (radio buttons) are specified by the strings in the list.</span></span> <span data-ttu-id="5a4d6-178">Ha nincsenek megadva karakterláncok, a karakterlánc mezőben szabad szöveges bejegyzés megengedett (lásd: „Parancslánc használata a TSTimesheetEntryService osztályon az időnyilvántartás-bejegyzés alkalmazásból az adatbázisba való mentéséhez” szakaszt később ebben a témakörben példaként).</span><span class="sxs-lookup"><span data-stu-id="5a4d6-178">If no strings are provided, free-text entry in the string field is allowed (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="stringlength-int"></a><span data-ttu-id="5a4d6-179">stringLength (int)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-179">stringLength (int)</span></span>

<span data-ttu-id="5a4d6-180">Ez a tulajdonság adja meg a karakterlánc-mező maximális hosszát.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-180">This property specifies the maximum length for a string field.</span></span> <span data-ttu-id="5a4d6-181">Csak akkor használható, ha a **fieldBaseType** értéke **Karakterlánc**.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-181">It's applicable only when **fieldBaseType** is set to **String**.</span></span>

### <a name="numberofdecimals-int"></a><span data-ttu-id="5a4d6-182">numberOfDecimals (int)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-182">numberOfDecimals (int)</span></span>

<span data-ttu-id="5a4d6-183">Ez a tulajdonság a valódi mezőhöz megjelenített tizedesjegyek számát határozza meg.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-183">This property specifies the number of decimal places that are shown for a real field.</span></span> <span data-ttu-id="5a4d6-184">Csak akkor használható, ha a **fieldBaseType** értéke **Valódi**.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-184">It's applicable only when **fieldBaseType** is set to **Real**.</span></span>

### <a name="ordersequence-int"></a><span data-ttu-id="5a4d6-185">orderSequence (int)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-185">orderSequence (int)</span></span>

<span data-ttu-id="5a4d6-186">Ez a tulajdonság határozza meg, hogy az egyéni mezők milyen sorrendben jelenjenek meg az alkalmazásban, ha egynél több egyéni mező van megadva.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-186">This property controls the order in which the custom fields are shown in the app when more than one custom field is specified.</span></span> <span data-ttu-id="5a4d6-187">A kisebb számú mezőket kell elsőként megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-187">Fields that have lower numbers are shown first.</span></span>

### <a name="booleanvalue-boolean"></a><span data-ttu-id="5a4d6-188">booleanValue (boolean)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-188">booleanValue (boolean)</span></span>

<span data-ttu-id="5a4d6-189">A **Logikai** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a mező logikai értékét adja át.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-189">For fields of the **Boolean** type, this property passes the Boolean value of the field between the server and the app.</span></span>

### <a name="guidvalue-guid"></a><span data-ttu-id="5a4d6-190">guidValue (guid)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-190">guidValue (guid)</span></span>

<span data-ttu-id="5a4d6-191">A **GUID** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a globális egyedi azonosító (GUID) értékét adja át.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-191">For fields of the **GUID** type, this property passes the globally unique identifier (GUID) value of the field between the server and the app.</span></span>

### <a name="int64value-int64"></a><span data-ttu-id="5a4d6-192">int64Value (int64)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-192">int64Value (int64)</span></span>

<span data-ttu-id="5a4d6-193">Az **Int64** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a mező int64 értékét adja át.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-193">For fields of the **Int64** type, this property passes the int64 value of the field between the server and the app.</span></span>

### <a name="intvalue-int"></a><span data-ttu-id="5a4d6-194">intValue (int)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-194">intValue (int)</span></span>

<span data-ttu-id="5a4d6-195">Az **Int** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a mező int értékét adja át.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-195">For fields of the **Int** type, this property passes the int value of the field between the server and the app.</span></span>

### <a name="realvalue-real"></a><span data-ttu-id="5a4d6-196">realValue (valódi)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-196">realValue (real)</span></span>

<span data-ttu-id="5a4d6-197">A **Valódi** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a mező valódi értékét adja át.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-197">For fields of the **Real** type, this property passes the real value of the field between the server and the app .</span></span>

### <a name="stringvalue-str"></a><span data-ttu-id="5a4d6-198">stringValue (str)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-198">stringValue (str)</span></span>

<span data-ttu-id="5a4d6-199">Az **Karakterlánc** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a mező karakterlánc-értékét adja át.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-199">For fields of the **String** type, this property passes the string value of the field between the server and the app.</span></span> <span data-ttu-id="5a4d6-200">Ez a pénznemként formázott **Valódi** típusú mezők esetében is használatos.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-200">It's also used for fields of the **Real** type that are formatted as currency.</span></span> <span data-ttu-id="5a4d6-201">Ezeknél a mezőknél a tulajdonság a pénznemkód az alkalmazásnak való átadására használatos.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-201">For those fields, the property is used to pass the currency code to the app.</span></span>

### <a name="datevalue-date"></a><span data-ttu-id="5a4d6-202">dateValue (dátum)</span><span class="sxs-lookup"><span data-stu-id="5a4d6-202">dateValue (date)</span></span>

<span data-ttu-id="5a4d6-203">A **Dátum** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a mező dátumértékét adja át.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-203">For fields of the **Date** type, this property passes the date value of the field between the server and the app.</span></span>

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a><span data-ttu-id="5a4d6-204">Egyéni mező megjelenítése és mentése a munkaidő-nyilvántartási bejegyzés szakaszban</span><span class="sxs-lookup"><span data-stu-id="5a4d6-204">Show and save a custom field in the timesheet entry section</span></span>

<span data-ttu-id="5a4d6-205">Alul látható egy képernyőkép az időnyilvántartás-bejegyzés létrehozásáról a mobilalkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-205">Below is a screenshot from the mobile app of a timesheet entry creation.</span></span> <span data-ttu-id="5a4d6-206">Ezen láthatók a beépített mezők és az egyéni mező az „Időbejegyzés” szakaszban „Tesztkarakterlánc” néven, beállított „Második lehetőség” felsorolási értékkel.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-206">It shows the out-of-box fields and a custom field in the "Time entry" section called "Test string" with an enum value of "Second option" already set.</span></span>

![Tesztkarakterlánc egyéni mezője az alkalmazásban](media/timesheet-entry.jpg)



<span data-ttu-id="5a4d6-208">Alul látható egy képernyőkép a mobilalkalmazásból, amelyen a felhasználó kiválasztja a „Tesztkarakterlánc” egyéni mezőkhöz rendelkezésre álló felsorolási lehetőségek egyikét.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-208">Below is a screenshot from the mobile app of the user selecting one of the enum options available for the "Test string" custom field.</span></span>  <span data-ttu-id="5a4d6-209">A két lehetőség az „Első lehetőség” és a „Második lehetőség” választógombként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-209">The two options are "First option" and "Second option" shown as radio buttons.</span></span> <span data-ttu-id="5a4d6-210">A második beállítás van jelenleg kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-210">The second option is currently selected.</span></span>

![Beállítógombok (választógombok) a tesztkarakterlánc egyéni mezőjéhez](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="5a4d6-212">A TSTimesheetLine táblájának bővítése, hogy egyéni mezőt tartalmazzon</span><span class="sxs-lookup"><span data-stu-id="5a4d6-212">Extend the TSTimesheetLine table so that it has a custom field</span></span>

<span data-ttu-id="5a4d6-213">A tipikus esetekben valószínű, hogy az időnyilvántartás-bejegyzési szakasz egyéni mezőjének adatait a TSTimesheetLine táblába menti a program.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-213">In typical scenarios, it's likely that the data for a custom field in the timesheet entry section will be saved to the TSTimesheetLine table.</span></span> <span data-ttu-id="5a4d6-214">Más táblákat lehet azonban használni, ha az adatok beolvasása a megadott TSTimesheetTrans-rekord alapján történik, vagy ha nem rendelkezik konkrét rekord környezettel (például ha a mező értéke írásvédett a projekt paraméterei között).</span><span class="sxs-lookup"><span data-stu-id="5a4d6-214">However, other tables can be used if the data can be retrieved based on a TSTimesheetTrans record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="5a4d6-215">Ne felejtse el, hogy az egyéni mezőknek nem kell biztonsági adatbázisrekordokkal rendelkezniük.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-215">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="5a4d6-216">Az X++ logika alapján dinamikusan generálhatók.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-216">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="5a4d6-217">Ez a megközelítés jól használható írásvédett helyzetekben (lásd: „Parancslánc használata a TSTimesheetDetails osztály buildCustomFieldListForHeader metódusán az időnyilvántartás-adatok kitöltésére” szakaszt a dinamikusan generált egyénimező-értékek példájaként).</span><span class="sxs-lookup"><span data-stu-id="5a4d6-217">This approach can be useful in read-only scenarios (see the “Use chain of command on the TSTimesheetDetails class, buildCustomFieldListForHeader method to fill in timesheet details” section for an example of dynamically generated custom field values.)</span></span>

<span data-ttu-id="5a4d6-218">Alul látható egy képernyőkép az Visual Studio alkalmazásobjektum-fáról.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-218">Below is a screenshot from Visual Studio of the Application Object Tree.</span></span> <span data-ttu-id="5a4d6-219">A TSTimesheetLine tábla bővítését jeleníti meg a TestLineString mezővel, amelyet egyéni mezőként adtak hozzá.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-219">It shows an extension of the TSTimesheetLine table with the TestLineString field added as a custom field.</span></span>

![Sor karakterlánca](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a><span data-ttu-id="5a4d6-221">A TSTimesheetSettings osztály buildCustomFieldList-metódusának parancsláncának használata az időnyilvántartás-bejegyzés szakasz mezőinek megjelenítésére</span><span class="sxs-lookup"><span data-stu-id="5a4d6-221">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the timesheet entry section</span></span>

<span data-ttu-id="5a4d6-222">Ez a kód az alkalmazásban a mező megjelenítési beállításait vezérli.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-222">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="5a4d6-223">Például a mező típusát, a címkét, hogy a mezőt kötelező-e megadni, és azt, hogy milyen szakaszban jelenik meg a mező.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-223">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="5a4d6-224">A következő példa egy karakterláncmezőt mutat be az időbejegyzéseken.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-224">The following example shows a string field on time entries.</span></span> <span data-ttu-id="5a4d6-225">Ennek a mezőnek két beállítása van, az **Első lehetőség** és a **Második lehetőség**, amely a beállításgombokon keresztül érhető el (választógombok).</span><span class="sxs-lookup"><span data-stu-id="5a4d6-225">This field has two options, **First option** and **Second option**, that are available via option buttons (radio buttons).</span></span> <span data-ttu-id="5a4d6-226">Az alkalmazás mezője az TSTimesheetLine táblához hozzáadott **TestLineString** mezőhöz van társítva.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-226">The field in the app is associated with the **TestLineString** field that is added to the TSTimesheetLine table.</span></span>

<span data-ttu-id="5a4d6-227">Vegye figyelembe a **TSTimesheetCustomField::newFromMetatdata()** metódus használatával a következő egyéni mezőtulajdonságok inicializálásának egyszerűsítése lehetséges: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength** és **numberOfDecimals**.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-227">Note the use of the **TSTimesheetCustomField::newFromMetatdata()** method to simplify the initialization of the custom field properties: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength**, and **numberOfDecimals**.</span></span> <span data-ttu-id="5a4d6-228">Ezeket a paramétereket kézzel is be lehet állítani, ahogy szeretné.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-228">You can also set these parameters manually, as you prefer.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('Second option');
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a><span data-ttu-id="5a4d6-229">A TSTimesheetEntry osztály buildCustomFieldListForEntry-metódusának parancsláncának használata az időnyilvántartás-bejegyzés adatainak megadására</span><span class="sxs-lookup"><span data-stu-id="5a4d6-229">Use chain of command on the buildCustomFieldListForEntry method of the TSTimesheetEntry class to enter values in a timesheet entry</span></span>

<span data-ttu-id="5a4d6-230">A **buildCustomFieldListForEntry** metódus a mobilalkalmazásban a mentett időnyilvántartás soraiban szereplő értékek megadására szolgál.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-230">The **buildCustomFieldListForEntry** method is used to enter values on the saved timesheet lines in the mobile app.</span></span> <span data-ttu-id="5a4d6-231">A TSTimesheetTrans-rekordot paraméterként veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-231">It takes a TSTimesheetTrans record as a parameter.</span></span> <span data-ttu-id="5a4d6-232">A rekord mezői felhasználhatók az alkalmazás egyéni mezőjéne értékének kitöltésére.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-232">Fields from that record can be used to fill in the custom field value in the app.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetEntry))]
final class TsTimesheetEntry_Extension
{
    protected List buildCustomFieldListForEntry(TSTimesheetTrans _tsTimesheetTrans)
    {
        List customFieldList = next buildCustomFieldListForEntry(_tsTimesheetTrans);
        TSTimesheetLine tsTimesheetLine = _tsTimesheetTrans.timesheetLine();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        tsTimesheetCustomField.parmStringValue(tsTimesheetLine.TestLineString);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('second option;);
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a><span data-ttu-id="5a4d6-233">A TSTimesheetEntryService osztályon parancslánc segítségével mentheti az alkalmazásból az adatbázisba a munkaidő-nyilvántartási bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-233">Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database</span></span>

<span data-ttu-id="5a4d6-234">Ha azt szeretné, hogy a szokásos használat során mentse az egyéni mezőt az adatbázisba, több metódust kell bővíteni:</span><span class="sxs-lookup"><span data-stu-id="5a4d6-234">To save a custom field back to the database in typical usage, you must extend multiple methods:</span></span>

- <span data-ttu-id="5a4d6-235">A **timesheetLineNeedsUpdating** metódus annak meghatározására szolgál, hogy az alkalmazásban a felhasználó módosította-e a sor rekordját, és az adatbázisba kell menteni.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-235">The **timesheetLineNeedsUpdating** method is used to determine whether the line record has been changed by the user in the app and must be saved to the database.</span></span> <span data-ttu-id="5a4d6-236">Ha a teljesítmény fontos, akkor ez a módszer egyszerűsíthető úgy, hogy mindig **igaz** értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-236">If performance isn't a concern, this method can be simplified so that it always returns **true**.</span></span>
- <span data-ttu-id="5a4d6-237">A **populateTimesheetLineFromEntryDuringCreate** és a **populateTimesheetLineFromEntryDuringUpdate** metódusok kiterjeszthetők úgy, hogy megadjanak értékeket a TSTimesheetLine adatbázisrekordban a megadott TSTimesheetEntry adatszerződés-rekordba.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-237">The **populateTimesheetLineFromEntryDuringCreate** and **populateTimesheetLineFromEntryDuringUpdate** methods can be extended so that they enter values in the TSTimesheetLine database record from the TSTimesheetEntry data contract record that is provided.</span></span> <span data-ttu-id="5a4d6-238">A következő példában figyelje meg, hogy az adatbázis-mező és a beviteli mező között manuálisan történik az X++ kód használatával a megfeleltetés.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-238">In the example that follows, notice how the mapping between the database field and the entry field is manually done via X++ code.</span></span>
- <span data-ttu-id="5a4d6-239">A **populateTimesheetWeekFromEntry** metódus is bővíthető, ha a **TSTimesheetEntry** objektumhoz rendelt egyéni mezőnek vissza kell írnia a TSTimesheetLineweek adatbázistáblájába.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-239">The **populateTimesheetWeekFromEntry** method can also be extended if the custom field that is mapped to the **TSTimesheetEntry** object must write back to the TSTimesheetLineweek database table.</span></span>

> [!NOTE]
> <span data-ttu-id="5a4d6-240">A következő példában a rendszer elmenti a **firstOption** vagy **secondOption** értéket, amelyet a felhasználó nyers karakterlánc-értékként választ az adatbázisra.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-240">The following example saves the **firstOption** or **secondOption** value that the user selects to the database as a raw string value.</span></span> <span data-ttu-id="5a4d6-241">Ha az adatbázis mező **Felsorolás** típusú mező, akkor ezek az értékek manuálisan is megfeleltethetők egy felsorolási értékre, majd az adatbázistábla felsorolási mezőjébe menthetők.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-241">If the database field is a field of the **Enum** type, those values can be manually mapped to an enum value and then saved to an enum field on the database table.</span></span>

```
...
[ExtensionOf(classStr(TSTimesheetEntryService))]
final class TSTimesheetEntryService_Extension
{
    protected boolean timesheetLineNeedsUpdating(TSTimesheetLine _tsTimesheetLine,
    TsTimesheetEntry _tsTimesheetEntry)
    {
        boolean ret = next timesheetLineNeedsUpdating(_tsTimesheetLine,
        _tsTimesheetEntry);
        if (!ret)
        {
            */ Loop through custom fields to see if value needs updating*/
            ListEnumerator enumerator =  _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    */ If Custom field value for TestLineString field has changed, We need to update the timesheet line.*/
                    if (_tsTimesheetLine.TestLineString != customField.parmStringValue())
                    {
                        ret = true;
                    }
                }
            }
        }
        return ret;
    }
    protected void populateTimesheetLineFromEntryDuringCreate(TSTimesheetLine
    _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
    {
        next populateTimesheetLineFromEntryDuringCreate(_tsTimesheetLine,
        _tsTimesheetEntry);
        this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
        _tsTimesheetEntry);
        }
        protected void populateTimesheetLineFromEntryDuringUpdate(TSTimesheetLine
        \_tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            next populateTimesheetLineFromEntryDuringUpdate(_tsTimesheetLine,
            _tsTimesheetEntry);
            this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
            _tsTimesheetEntry);
        }
        private void populateTimesheetLineFromCustomFields(TSTimesheetLine
        _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            ListEnumerator enumerator =
            _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    _tsTimesheetLine.TestLineString = customField.parmStringValue();
                }
            }
        }
    }
...
```

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a><span data-ttu-id="5a4d6-242">Egyéni mező megjelenítése a munkaidő-nyilvántartás fejlécébe szakasz</span><span class="sxs-lookup"><span data-stu-id="5a4d6-242">Show a custom field in the timesheet header section</span></span>

<span data-ttu-id="5a4d6-243">Alul látható egy képernyőkép a mobilalkalmazásból egy felhasználóról, aki időnyilvántartást tekint meg.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-243">Below is a screenshot from the mobile app of a user viewing a timesheet.</span></span> <span data-ttu-id="5a4d6-244">A jobb felső sarokban kiválasztotta a „További információ” gombot, hogy megjelenítse a "További részletek megtekintése" beállítást.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-244">The "More information" button has been selected in the upper-right corner to show the "View more details" option.</span></span>  

![További részletek megtekintése parancs](media/show-more.png)

<span data-ttu-id="5a4d6-246">Alul látható egy képernyőkép a mobilalkalmazásból az időnyilvántartás „Továbbiak” szakaszáról.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-246">Below is a screenshot from the mobile app showing the “More” section of a timesheet.</span></span> <span data-ttu-id="5a4d6-247">Az időnyilvántartás fejléc szakaszába hozzáadtak egy „Időnyilvántartás kihasználtsági rátája (számított egyéni mező)” egyéni mezőt.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-247">A custom field called “Utilization rate of this timesheet (computed custom field)” has been added to the timesheet header section.</span></span> <span data-ttu-id="5a4d6-248">Egy írásvédett "0,667" értékű érték van megadva az egyéni mezőben.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-248">A read-only value of "0.667" is set on the custom field.</span></span>

![Továbbiak szakasz](media/more-section.jpg)

### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="5a4d6-250">A TSTimesheetTable táblájának bővítése, hogy egyéni mezőt tartalmazzon</span><span class="sxs-lookup"><span data-stu-id="5a4d6-250">Extend the TSTimesheetTable table so that it has a custom field</span></span>

<span data-ttu-id="5a4d6-251">A tipikus esetekben valószínű, hogy a fejléc szakasz egyéni mezőjének adatait a TSTimesheetHeader táblából hívja le a program.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-251">In typical scenarios, it's likely that the data for a custom field in the header section will be pulled from the TSTimesheetHeader table.</span></span> <span data-ttu-id="5a4d6-252">Más táblákat lehet azonban használni, ha az adatok beolvasása a megadott TSTimesheetTable-rekord alapján történik, vagy ha nem rendelkezik konkrét rekord környezettel (például ha a mező értéke írásvédett a projekt paraméterei között).</span><span class="sxs-lookup"><span data-stu-id="5a4d6-252">However, other tables can be used if the data can be retrieved based on a TSTimesheetTable record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="5a4d6-253">Ne felejtse el, hogy az egyéni mezőknek nem kell biztonsági adatbázisrekordokkal rendelkezniük.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-253">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="5a4d6-254">Az X++ logika alapján dinamikusan generálhatók.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-254">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="5a4d6-255">A következő példa bemutatja ezt a megközelítést.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-255">The example that follows shows this approach.</span></span>

<span data-ttu-id="5a4d6-256">A fejléc szakasz mezői mindig csak olvashatók az alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-256">Fields in the header section are always read-only in the app.</span></span>

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a><span data-ttu-id="5a4d6-257">A TSTimesheetSettings osztály buildCustomFieldList-metódusának parancsláncának használata a fejléc szakasz mezőinek megjelenítésére</span><span class="sxs-lookup"><span data-stu-id="5a4d6-257">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the header section</span></span>

<span data-ttu-id="5a4d6-258">Ez a kód az alkalmazásban a mező megjelenítési beállításait vezérli.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-258">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="5a4d6-259">Például a mező típusát, a címkét, hogy a mezőt kötelező-e megadni, és azt, hogy milyen szakaszban jelenik meg a mező.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-259">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="5a4d6-260">A következő példa egy számított értéket mutat be az alkalmazás fejléc szakaszában.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-260">The following example shows a computed value in the header section in the app.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a><span data-ttu-id="5a4d6-261">A TSTimesheetDetails osztály buildCustomFieldListForHeader-metódusának parancsláncának használata az időnyilvántartás adatainak kitöltésére</span><span class="sxs-lookup"><span data-stu-id="5a4d6-261">Use chain of command on the buildCustomFieldListForHeader method of the TSTimesheetDetails class to fill in timesheet details</span></span>

<span data-ttu-id="5a4d6-262">A **buildCustomFieldListForHeader** metódus a mobilalkalmazásban az időnyilvántartás fejlécadatainak kitöltésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-262">The **buildCustomFieldListForHeader** method is used to fill in the timesheet header details in the mobile app.</span></span> <span data-ttu-id="5a4d6-263">A TSTimesheetTable-rekordot paraméterként veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-263">It takes a TSTimesheetTable record as a parameter.</span></span> <span data-ttu-id="5a4d6-264">A rekord mezői felhasználhatók az alkalmazás egyéni mezőjéne értékének kitöltésére.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-264">Fields from that record can be used to fill in the custom field value in the app.</span></span> <span data-ttu-id="5a4d6-265">A következő példa nem olvas le értéket az adatbázisból.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-265">The following example doesn't read any values from the database.</span></span> <span data-ttu-id="5a4d6-266">Helyette az X++ logikát használja egy számított érték előállítására, amelyet azután az alkalmazás megjelenít.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-266">Instead, it uses X++ logic to generate a computed value that is then shown in the app.</span></span>


```
...
[ExtensionOf(classStr(TSTimesheetDetails))]
final class TSTimesheetDetails_Extension
{
    protected List buildCustomFieldListForHeader(TSTimesheetTable
    _tsTimesheetTable)
    {
        List customFieldList = next buildCustomFieldListForHeader(_tsTimesheetTable);
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        real utilizationRate = 0;
        if (_tsTimesheetTable.totalHours() != 0)
        {
            utilizationRate = _tsTimesheetTable.totalHoursBillable() /
            _tsTimesheetTable.totalHours();
        }
        tsTimesheetCustomField.parmRealValue(utilizationRate);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

## <a name="other-configurabilityextensibility-opportunities"></a><span data-ttu-id="5a4d6-267">Egyéb konfigurálási és bővíthetőségi lehetőségek</span><span class="sxs-lookup"><span data-stu-id="5a4d6-267">Other configurability/extensibility opportunities</span></span>

### <a name="adding-additional-validation-for-the-app"></a><span data-ttu-id="5a4d6-268">További ellenőrzés hozzáadása az alkalmazáshoz</span><span class="sxs-lookup"><span data-stu-id="5a4d6-268">Adding additional validation for the app</span></span>

<span data-ttu-id="5a4d6-269">Az adatbázis szintjén a munkaidő-nyilvántartási funkció meglévő logikája továbbra is a várt módon fog működni.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-269">Existing logic for timesheet functionality at the database level will still work as expected.</span></span> <span data-ttu-id="5a4d6-270">Ha meg szeretné szakítani a mentés vagy küldés műveleteinek befejezését, és egy konkrét hibaüzenetet megjeleníteni, akkor a kódra vonatkozó parancslánc-kiterjesztéssel hozzáadhat egy **dobási hibát(„üzenet a felhasználónak”)**.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-270">To interrupt the completion of save or submit operations and show a specific error message, you can add **throw error("message to user")** to the code via a chain of command extension.</span></span> <span data-ttu-id="5a4d6-271">Az alábbiakban három példát talál a hasznos bővíthető metódusokra:</span><span class="sxs-lookup"><span data-stu-id="5a4d6-271">Here are three examples of useful extensible methods:</span></span>

- <span data-ttu-id="5a4d6-272">Ha a TSTimesheetLine tábla **validateWrite** tulajdonsága **hamis** értéket ad vissza egy időnyilvántartási sor mentési művelete során, akkor egy hibaüzenet jelenik meg a mobilalkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-272">If **validateWrite** on the TSTimesheetLine table returns **false** during a save operation for a timesheet line, an error message is shown in the mobile app.</span></span>
- <span data-ttu-id="5a4d6-273">Ha a TSTimesheetTable tábla **validateSubmit** tulajdonsága **hamis** értéket ad vissza egy időnyilvántartási elküldési művelete során az alkalmazásban, akkor egy hibaüzenet jelenik meg a felhasználónak.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-273">If **validateSubmit** on the TSTimesheetTable table returns **false** during timesheet submission in the app, an error message is shown to the user.</span></span>
- <span data-ttu-id="5a4d6-274">A program továbbra is futtatja a mezők kitöltésére szolgáló logikát (például **Sortulajdonság)** a TSTimesheetLine táblán a **beszúrás** metódus során.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-274">Logic that fills in fields (for example, **Line Property**) during the **insert** method on the TSTimesheetLine table will still run.</span></span>

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a><span data-ttu-id="5a4d6-275">Beépített mezők elrejtése és írásvédettként megjelenítése konfigurációval</span><span class="sxs-lookup"><span data-stu-id="5a4d6-275">Hiding and marking out-of-box fields as read-only via configuration</span></span>

<span data-ttu-id="5a4d6-276">A projekt paraméterei alapján a mobilalkalmazásban a beépített mezőket csak olvashatóvá vagy rejtetté teheti.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-276">From the project parameters, you can make out-of-box fields read-only or hidden in the mobile app.</span></span> <span data-ttu-id="5a4d6-277">Adja meg a **Projektkezelés és könyvelési paraméterek** oldal **Időnyilvántartás** lapjának **Mobil-időnyilvántartások** szakaszának beállításait.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-277">Set the options in the **Mobile timesheets** section on the **Timesheet** tab of the **Project management and accounting parameters** page.</span></span>

![Projekt paraméterei](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a><span data-ttu-id="5a4d6-279">A rendelkezésre álló tevékenységek módosítása a bővítményeken keresztül</span><span class="sxs-lookup"><span data-stu-id="5a4d6-279">Changing the activities that are available for selection via extensions</span></span>

<span data-ttu-id="5a4d6-280">A projekthez választható tevékenységek a **getActivitiesForProject()** és a **getActivityQuery()** metódusokon keresztül kerülnek kitöltésre a **TsTimesheetProjectService** osztályban.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-280">The activities that are available for selection for a project are filled in via the **getActivitiesForProject()** and **getActivityQuery()** methods in the **TsTimesheetProjectService** class.</span></span> <span data-ttu-id="5a4d6-281">A parancslánc használatával módosíthatja ezt a viselkedést, hogy megfeleljen az üzleti helyzetnek a tevékenységekhez, amelyek kiválaszthatók egy adott projekt esetében.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-281">You can use chain of command to change this behavior to match your business scenario for the activities that are available for selection for a specific project.</span></span>

### <a name="entering-a-default-project-category-on-timesheet-entries"></a><span data-ttu-id="5a4d6-282">Alapértelmezett projektkategória megadása a munkaidő-nyilvántartási bejegyzésekhez</span><span class="sxs-lookup"><span data-stu-id="5a4d6-282">Entering a default project category on timesheet entries</span></span>

<span data-ttu-id="5a4d6-283">Az időnyilvántartási bejegyzésekhez tartozó alapértelmezett projektkategória megadása három szinten történik.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-283">Entry of a default project category on timesheet entries occurs at three levels.</span></span> <span data-ttu-id="5a4d6-284">A parancslánc használatával bővítheti a viselkedést bármely vagy mind a három szinten a kívánt viselkedés eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-284">You can use chain of command to extend the behavior at any or all of these levels to achieve the desired behavior.</span></span> <span data-ttu-id="5a4d6-285">A rendszer a következő hierarchiát követi:</span><span class="sxs-lookup"><span data-stu-id="5a4d6-285">The following hierarchy is used:</span></span>

1. <span data-ttu-id="5a4d6-286">Az alkalmazás megpróbálja alkalmazni az alapértelmezett kategóriát a projekterőforrásból.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-286">The app tries to put the default category from the project resource.</span></span> <span data-ttu-id="5a4d6-287">Ez az alapértelmezett kategória a **getCurrentUserResource** és a **getDelegatedResourcesForCurrentUser** metódusokban van megadva a **TSTimesheetSettingsService** osztályban.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-287">This default category is set in the **getCurrentUserResource** and **getDelegatedResourcesForCurrentUser** methods in the **TSTimesheetSettingsService** class.</span></span>
2. <span data-ttu-id="5a4d6-288">Ha az alapértelmezett kategória nem szerepel a projekterőforrás szintjén, akkor az alkalmazás megpróbálja lehívni azt a projekt tevékenységéből.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-288">If the default category isn't provided at the project resource level, the app tries to pull it from the project activity.</span></span> <span data-ttu-id="5a4d6-289">Ez az alapértelmezett kategória a **TSTimesheetProjectService** osztály **getActivitiesForProject** metódusában van megadva.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-289">This default category is set in the **getActivitiesForProject** method in the **TSTimesheetProjectService** class.</span></span>
3. <span data-ttu-id="5a4d6-290">Ha az alapértelmezett kategória nem szerepel a projekttevékenység szintjén, akkor az alapértelmezett kategóriát alkalmazás megpróbálja lehívni azt a projekt paramétereiből.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-290">If the default category isn't provided at the project activity level, the default category it taken from the project parameters.</span></span> <span data-ttu-id="5a4d6-291">Ez az alapértelmezett kategória a **TSTimesheetProjectService** osztály **getProjectDetailsbyRule** metódusában van megadva.</span><span class="sxs-lookup"><span data-stu-id="5a4d6-291">This default category is set in the **getProjectDetailsbyRule** method in the **TSTimesheetProjectService** class.</span></span>
