---
title: ER adatforrások paraméterezett hívásainak támogatása a Számított mezőtípusban
description: Ez a témakör azt mutatja be, hogyan kell használni a Számított mezőtípust ER-adatforrásokhoz.
author: NickSelin
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 897133a27f9d3da2f576ce675c0949f824cde881
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749489"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a><span data-ttu-id="83e1b-103">ER adatforrások paraméterezett hívásainak támogatása a Számított mezőtípusban</span><span class="sxs-lookup"><span data-stu-id="83e1b-103">Support parameterized calls of ER data sources of the Calculated field type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83e1b-104">Ez a témakör azt mutatja be, hogyan lehet az elektronikus jelentéskészítési (ER) adatforrást tervezni a **Számított mező** típusban.</span><span class="sxs-lookup"><span data-stu-id="83e1b-104">This topic explains how you can design an Electronic reporting (ER) data source by using the **Calculated field** type.</span></span> <span data-ttu-id="83e1b-105">Ez az adatforrás olyan ER-kifejezéseket tartalmazhat, amelyek a végrehajtás során paraméterargumentumok értékeivel vezérelhetők, amely egy hozzárendelésben konfigurálható, amely meghívja ezt az adatforrást.</span><span class="sxs-lookup"><span data-stu-id="83e1b-105">This data source may contain an ER expression that, when executed, can be controlled by the values of the parameter arguments that are configured in a binding that calls this data source.</span></span> <span data-ttu-id="83e1b-106">Egy ilyen adatforrás paraméterezett hívásának konfigurálásával több kötésben is felhasználható egyetlen adatforrás, ami csökkenti azoknak az adatforrásoknak a számát, amelyeket az ER-formátumok ER modell-leképezéseihez konfigurálni kell.</span><span class="sxs-lookup"><span data-stu-id="83e1b-106">By configuring parameterized calls of such a data source, you can reuse a single data source in many bindings, which reduces the total number of data sources that must be configured in ER model mappings or ER formats.</span></span> <span data-ttu-id="83e1b-107">Leegyszerűsíti a konfigurált ER-összetevőt is, amely csökkenti a karbantartási költségeket és a más felhasználók által felhasználás költségeit.</span><span class="sxs-lookup"><span data-stu-id="83e1b-107">It also simplifies the configured ER component, which reduces the maintenance costs and the cost of use by other consumers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="83e1b-108">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="83e1b-108">Prerequisites</span></span>
<span data-ttu-id="83e1b-109">A jelen témakörben szereplő példák elvégzéséhez a következő hozzáférésekkel kell rendelkeznie:</span><span class="sxs-lookup"><span data-stu-id="83e1b-109">To complete the examples in this topic, you must have the following access:</span></span>

- <span data-ttu-id="83e1b-110">Hozzáférés egy ilyen szerepkörhöz:</span><span class="sxs-lookup"><span data-stu-id="83e1b-110">Access to one of these roles:</span></span>

    - <span data-ttu-id="83e1b-111">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="83e1b-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="83e1b-112">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="83e1b-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="83e1b-113">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="83e1b-113">System administrator</span></span>

- <span data-ttu-id="83e1b-114">A Regulatory Configuration Services (RCS) szolgáltatáshoz való hozzáférés, ami ugyanattól a bérlőtől került szolgáltatásra, mint Finance and Operations Operations egyre vonatkozik az alábbi lépések közül:</span><span class="sxs-lookup"><span data-stu-id="83e1b-114">Access to Regulatory Configuration Services (RCS) that have been provisioned for the same tenant as Finance and Operations for one of the following roles:</span></span>

    - <span data-ttu-id="83e1b-115">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="83e1b-115">Electronic reporting developer</span></span>
    - <span data-ttu-id="83e1b-116">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="83e1b-116">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="83e1b-117">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="83e1b-117">System administrator</span></span>

<span data-ttu-id="83e1b-118">A következő fájlokat is le kell töltenie és helyben tárolnia.</span><span class="sxs-lookup"><span data-stu-id="83e1b-118">You must also download and locally store the following files.</span></span>

| <span data-ttu-id="83e1b-119">**Tartalom**</span><span class="sxs-lookup"><span data-stu-id="83e1b-119">**Content**</span></span>                           | <span data-ttu-id="83e1b-120">**Fájlnév**</span><span class="sxs-lookup"><span data-stu-id="83e1b-120">**File name**</span></span>                                        |
|---------------------------------------|------------------------------------------------------|
| <span data-ttu-id="83e1b-121">Minta ER-adatmodell konfigurációja</span><span class="sxs-lookup"><span data-stu-id="83e1b-121">Sample ER data model configuration</span></span>    | [<span data-ttu-id="83e1b-122">Model to learn parameterized calls.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="83e1b-122">Model to learn parameterized calls.version.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)     |
| <span data-ttu-id="83e1b-123">Minta ER-metaadat konfigurációja</span><span class="sxs-lookup"><span data-stu-id="83e1b-123">Sample ER metadata configuration</span></span>      | [<span data-ttu-id="83e1b-124">Metadata to learn parameterized calls.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="83e1b-124">Metadata to learn parameterized calls.version.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |
| <span data-ttu-id="83e1b-125">Minta ER-adatmodell leképezési konfigurációja</span><span class="sxs-lookup"><span data-stu-id="83e1b-125">Sample ER model mapping configuration</span></span> | [<span data-ttu-id="83e1b-126">Mapping to learn parameterized calls.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="83e1b-126">Mapping to learn parameterized calls.version.1.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="83e1b-127">Minta ER-formátum konfigurációja</span><span class="sxs-lookup"><span data-stu-id="83e1b-127">Sample ER format configuration</span></span>        | [<span data-ttu-id="83e1b-128">Format to learn parameterized calls.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="83e1b-128">Format to learn parameterized calls.version.1.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |

## <a name="sign-in-to-your-rcs-instance"></a><span data-ttu-id="83e1b-129">Jelentkezzen be a RCS-példányba</span><span class="sxs-lookup"><span data-stu-id="83e1b-129">Sign in to your RCS instance</span></span>
<span data-ttu-id="83e1b-130">Ebben a példában létrehozzuk egy konfigurációt a Litware, Inc. mintavállalatra vonatkozóan. A lépések végrehajtásához először a következő eljárás lépéseit kell végrehajtani az RCS-ben: [Konfigurációszolgáltatók létrehozása, és megjelölésük aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md):</span><span class="sxs-lookup"><span data-stu-id="83e1b-130">In this example, you will create a configuration for the sample company, Litware, Inc. First, in RCS, you must complete the steps in the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure:</span></span>

1. <span data-ttu-id="83e1b-131">Az alapértelmezett irányítópulton válassza az **Elektronikus jelentéskészítés** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-131">On the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="83e1b-132">Válassza a **Jelentéskészítési konfigurációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-132">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="83e1b-133">A letöltött konfigurációkat importálja a következő sorrendben az RCS-be: adatmodell, metaadatok, modell-leképezés, formátum.</span><span class="sxs-lookup"><span data-stu-id="83e1b-133">Import the downloaded configurations to RCS in the following sequence: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="83e1b-134">Hajtsa végre a következő lépéseket mindegyik ER-konfiguráció esetében:</span><span class="sxs-lookup"><span data-stu-id="83e1b-134">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="83e1b-135">Válassza az **Átváltás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-135">Select **Exchange.**</span></span>
    2. <span data-ttu-id="83e1b-136">Kattintson a **Betöltés XML-fájlból** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83e1b-136">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="83e1b-137">Kattintson a **Tallózás** gombra, majd válassza ki a megfelelő, XML-formátumú fájlt a szükséges ER-konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="83e1b-137">Select **Browse**, and then select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="83e1b-138">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-138">Select **OK.**</span></span>

## <a name="review-the-provided-er-solution"></a><span data-ttu-id="83e1b-139">A nyújtott ER-megoldás áttekintése</span><span class="sxs-lookup"><span data-stu-id="83e1b-139">Review the provided ER solution</span></span>

### <a name="review-model-mapping"></a><span data-ttu-id="83e1b-140">Modell-leképezés áttekintése</span><span class="sxs-lookup"><span data-stu-id="83e1b-140">Review model mapping</span></span>

1. <span data-ttu-id="83e1b-141">A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-141">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="83e1b-142">Válasza ki a **Leképezés paraméterezett hívások tanulásához elemet**.</span><span class="sxs-lookup"><span data-stu-id="83e1b-142">Select **Mapping to learn parameterized calls**.</span></span>
3. <span data-ttu-id="83e1b-143">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-143">Select **Designer**.</span></span>
4. <span data-ttu-id="83e1b-144">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-144">Select **Designer**.</span></span>  
   
    <span data-ttu-id="83e1b-145">Ez az ER-leképezés a következőkre képes:</span><span class="sxs-lookup"><span data-stu-id="83e1b-145">This ER model mapping is designed to do the following:</span></span>

    - <span data-ttu-id="83e1b-146">Lekéri az adókódok listáját (**Adó** adatforrás) amelyek a **TaxTable** táblában találhatók.</span><span class="sxs-lookup"><span data-stu-id="83e1b-146">Fetch the list of tax codes (**Tax** data source) residing in the **TaxTable** table.</span></span>
    - <span data-ttu-id="83e1b-147">Lekéri az adótranzakciók listáját (**Tranz** adatforrás) amelyek a **TaxTrans** táblában találhatók:</span><span class="sxs-lookup"><span data-stu-id="83e1b-147">Fetch the list of tax transactions (**Trans** data source) residing in the **TaxTrans** table:</span></span>
    
        - <span data-ttu-id="83e1b-148">A beolvasott tranzakciók (**Gr** -adatforrás) listájának csoportosítása adózási kód szerint.</span><span class="sxs-lookup"><span data-stu-id="83e1b-148">Group the list of fetched transactions (**Gr** data source) by tax code.</span></span>
        - <span data-ttu-id="83e1b-149">Kiszámítja a csoportosított tranzakciókat az adózási kód szerinti aggregált értékek szerint:</span><span class="sxs-lookup"><span data-stu-id="83e1b-149">Calculate for grouped transactions following aggregated values per tax code:</span></span>

            - <span data-ttu-id="83e1b-150">Adóalap-értékek összege.</span><span class="sxs-lookup"><span data-stu-id="83e1b-150">Sum of tax base values.</span></span>
            - <span data-ttu-id="83e1b-151">Adóértékek összege.</span><span class="sxs-lookup"><span data-stu-id="83e1b-151">Sum of tax values.</span></span>
            - <span data-ttu-id="83e1b-152">Az alkalmazott adómérték minimális értéke.</span><span class="sxs-lookup"><span data-stu-id="83e1b-152">Minimum value of applied tax rate.</span></span>

    <span data-ttu-id="83e1b-153">A modell-leképezés ebben a konfigurációban implementálása az alap adatmodellt bármely ER formátumhoz, amely ehhez a modellhez lett készítve és a Finance and Operations által lett végrehajtva.</span><span class="sxs-lookup"><span data-stu-id="83e1b-153">The model mapping in this configuration implements the base data model for any of the ER formats created for this model and executed in Finance and Operations.</span></span> <span data-ttu-id="83e1b-154">Ennek eredményeképpen az **Adó** és **Gr** -adatforrások tartalma ER-formátumoknak, például absztrakt adatforrásoknak van kitéve.</span><span class="sxs-lookup"><span data-stu-id="83e1b-154">As a result, the content of the **Tax** and **Gr** data sources is exposed for ER formats such as abstract data sources.</span></span>

    ![Modell-hozzárendelés tervező lapja au Adó és Gr adatforrásokat jeleníti meg.](media/er-calculated-field-type-01.png)

5.  <span data-ttu-id="83e1b-156">Zárja be a **Modell-hozzárendelési tervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="83e1b-156">Close the **Model mapping designer** page.</span></span>
6.  <span data-ttu-id="83e1b-157">Zárja be a **Modell-hozzárendelés** lapot.</span><span class="sxs-lookup"><span data-stu-id="83e1b-157">Close the **Model mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="83e1b-158">Formátum áttekintése</span><span class="sxs-lookup"><span data-stu-id="83e1b-158">Review format</span></span>

1. <span data-ttu-id="83e1b-159">A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-159">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="83e1b-160">Válasza ki a **Formátum paraméterezett hívások tanulásához elemet**.</span><span class="sxs-lookup"><span data-stu-id="83e1b-160">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="83e1b-161">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-161">Select **Designer**.</span></span> <span data-ttu-id="83e1b-162">Ez az ER-formátum a következőkre képes:</span><span class="sxs-lookup"><span data-stu-id="83e1b-162">This ER format is designed to do the following:</span></span>

    - <span data-ttu-id="83e1b-163">Adókimutatás létrehozása XML-formátumban.</span><span class="sxs-lookup"><span data-stu-id="83e1b-163">Generate a tax statement in XML format.</span></span>
    - <span data-ttu-id="83e1b-164">Az adóbevallásban a következő adómértékeket megjeleníti: normál, csökkentett és nincs.</span><span class="sxs-lookup"><span data-stu-id="83e1b-164">Present the following levels of taxation in the tax statement: regular, reduced, and none.</span></span>
    - <span data-ttu-id="83e1b-165">Minden adózási szinten több részletet mutat be, amelyek mindegyik szintjén különböző számú adat szerepel.</span><span class="sxs-lookup"><span data-stu-id="83e1b-165">Present multiple details at each taxation level, having a different number of details in each level.</span></span>

    ![Formátumtervező oldal](media/er-calculated-field-type-02.png)

4. <span data-ttu-id="83e1b-167">Válassza ki **Hozzárendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-167">Select **Mapping**.</span></span>
5. <span data-ttu-id="83e1b-168">Bontsa ki a **Modell**, **Adatok** és **Összegzés** elemeket.</span><span class="sxs-lookup"><span data-stu-id="83e1b-168">Expand the **Model**, **Data,** and **Summary** items.</span></span> 

    <span data-ttu-id="83e1b-169">A **Model.Data.Summary.Level** számított mező tartalmazza azt a kifejezést, amely az adózási szint kódját adja vissza (**Normál**, **Csökkenetett**, **Nincs** vagy **Egyéb**). szöveges értékként, amely lekérhető a **Model.Data.summary** adatforrásból futásidőben.</span><span class="sxs-lookup"><span data-stu-id="83e1b-169">The calculated field **Model.Data.Summary.Level** contains the expression that returns the code of the taxation level (**Regular**, **Reduced**, **None,** or **Other**) as a text value for any tax code that can be retrieved from the **Model.Data.Summary** data source at run time.</span></span>

    ![A Formátumtervező lap a paraméterezett hívások megtanulásához szükséges adatmodell részleteit jeleníti meg.](media/er-calculated-field-type-03.png)

6. <span data-ttu-id="83e1b-171">Bontsa ki a **Model**.**Data2** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-171">Expand the **Model**.**Data2** item.</span></span>
7. <span data-ttu-id="83e1b-172">Bontsa ki a **Model**.**Data2.Summary2** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-172">Expand the **Model**.**Data2.Summary2** item.</span></span>
   
    <span data-ttu-id="83e1b-173">A **Model**.**Data2.Summary2** adatforrás úgy van konfigurálva, hogy csoportba rendezze a **Model.Data.Summary** adatforrás tranzakcióadatait adózási szinten (ezt a **Model.Data.Summary.Level** számított mező adja vissza), és kiszámítsa az összesítéseket.</span><span class="sxs-lookup"><span data-stu-id="83e1b-173">The **Model**.**Data2.Summary2** data source is configured to group the **Model.Data.Summary** data source transaction details by taxation level (returned by the **Model.Data.Summary.Level** calculated field) and compute the aggregations.</span></span>

    ![A Formátumtervező lap a Model.Data2.Summary2 adatforrás részletes adatait jeleníti meg.](media/er-calculated-field-type-04.png)

8. <span data-ttu-id="83e1b-175">Tekintse át a **Model**.**Data2.Level1**, **Model**.**Data2.Level2** és **Model**.**Data2.Level3** számított mezőket.</span><span class="sxs-lookup"><span data-stu-id="83e1b-175">Review the calculated fields **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, and **Model**.**Data2.Level3.**</span></span> <span data-ttu-id="83e1b-176">Ezeket a számított mezőket a **Model**.**Data2.Summary2** rekordlista szűrésére használja a rendszer, és csak az adott adózási szintet képviselő rekordokat adja vissza.</span><span class="sxs-lookup"><span data-stu-id="83e1b-176">These calculated fields are used to filter the **Model**.**Data2.Summary2** records list and return only records that represent a particular taxation level.</span></span>
9. <span data-ttu-id="83e1b-177">Zárja be a **Formátumtervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="83e1b-177">Close the **Format designer** page.</span></span>

## <a name="create-a-derived-format"></a><span data-ttu-id="83e1b-178">Származtatott formátum létrehozása</span><span class="sxs-lookup"><span data-stu-id="83e1b-178">Create a derived format</span></span>
<span data-ttu-id="83e1b-179">A megadott formátumot úgy javíthatja, hogy egy számított mezőt ad hozzá a szükséges adózási szint szűréséhez, nem pedig a meglévő három mezőt használja: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** és **Model**.**Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="83e1b-179">You can improve the provided format by adding one calculated field to filter the required taxation level instead of using the existing three fields: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** and **Model**.**Data2.Level3**.</span></span> <span data-ttu-id="83e1b-180">A szükséges adózási szint meghatározható azon a helyen, ahol ennek az új számított mezőnek a meghívása történik.</span><span class="sxs-lookup"><span data-stu-id="83e1b-180">The required taxation level can be specified in the location where this new calculated field will be called.</span></span>

1. <span data-ttu-id="83e1b-181">A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-181">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="83e1b-182">Válasza ki a **Formátum paraméterezett hívások tanulásához elemet**.</span><span class="sxs-lookup"><span data-stu-id="83e1b-182">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="83e1b-183">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-183">Select **Create configuration**.</span></span>
4. <span data-ttu-id="83e1b-184">Válassza a **Származtatás névből: Formátum paraméterezett hívások tanulásához, Microsoft** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-184">Select **Derive from Name: Format to learn parameterized calls, Microsoft**.</span></span>
5. <span data-ttu-id="83e1b-185">A **Név** mezőbe írja be: **Paraméterezett hívások tanulási formátuma (egyéni)**.</span><span class="sxs-lookup"><span data-stu-id="83e1b-185">In the **Name** field, enter **Format to learn parameterized calls (custom)**.</span></span>
6. <span data-ttu-id="83e1b-186">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-186">Select **Create configuration.**</span></span>

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a><span data-ttu-id="83e1b-187">A rekordok listáját visszaadó paraméterezett számított mező konfigurálása</span><span class="sxs-lookup"><span data-stu-id="83e1b-187">Configure a parameterized calculated field that returns a list of records</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="83e1b-188">Kezdje el az új számított mező hozzáadását</span><span class="sxs-lookup"><span data-stu-id="83e1b-188">Start adding a new calculated field</span></span>

1. <span data-ttu-id="83e1b-189">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-189">Select **Designer**.</span></span>
2. <span data-ttu-id="83e1b-190">Válassza ki a **Kibontás/összecsukás** elemet az összes formátumelem kibontásához.</span><span class="sxs-lookup"><span data-stu-id="83e1b-190">Select **Expand/collapse** to expand all format items.</span></span>
3. <span data-ttu-id="83e1b-191">Válassza ki **Hozzárendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-191">Select **Mapping**.</span></span>
4. <span data-ttu-id="83e1b-192">Bontsa ki a **Modell** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-192">Expand the **Model** item.</span></span>
5. <span data-ttu-id="83e1b-193">Válassza ki a **Model.Data2** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-193">Select the **Model.Data2** item.</span></span>
6. <span data-ttu-id="83e1b-194">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-194">Select **Add**.</span></span>
7. <span data-ttu-id="83e1b-195">Válassa a **Függvények\\Számított mezőt**.</span><span class="sxs-lookup"><span data-stu-id="83e1b-195">Select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="83e1b-196">A **Név** mezőbe írja be a **szintek** szót.</span><span class="sxs-lookup"><span data-stu-id="83e1b-196">In the **Name** field, enter **Levels**.</span></span>
9. <span data-ttu-id="83e1b-197">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-197">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="83e1b-198">Paraméter definiálása számított mező hozzáadásához</span><span class="sxs-lookup"><span data-stu-id="83e1b-198">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="83e1b-199">Válassza ki a **Paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-199">Select **Parameters**.</span></span>
2. <span data-ttu-id="83e1b-200">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-200">Select **New**.</span></span>
3. <span data-ttu-id="83e1b-201">A **Név** mezőbe írja be a következőt: **Adózási szint**.</span><span class="sxs-lookup"><span data-stu-id="83e1b-201">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="83e1b-202">A **Típus** mezőben válassza ki a **Karakterlánc** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-202">In the **Type** field, select **String**.</span></span>

    <span data-ttu-id="83e1b-203">A paraméterek argumentumának típusát csak primitív adattípusokkal lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="83e1b-203">Only primitive data types can be used to specify the type of the parameter’s argument.</span></span> <span data-ttu-id="83e1b-204">Ezért a **Rekordlista**, **Rekord** és **Enum** típus nem használhatók erre a célra.</span><span class="sxs-lookup"><span data-stu-id="83e1b-204">Therefore, **Record list**, **Record**, and **Enum** types cannot be used for this purpose.</span></span>

    <span data-ttu-id="83e1b-205">Az egyetlen számított mezőhöz meghatározható paraméterek maximális száma 8.</span><span class="sxs-lookup"><span data-stu-id="83e1b-205">The maximum number of parameters that can be specified for a single calculated field is 8.</span></span>

    ![Paraméter adatforráslistája](media/er-calculated-field-type-05.png)

5. <span data-ttu-id="83e1b-207">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-207">Select **OK**.</span></span>

<span data-ttu-id="83e1b-208">Ennek a paraméternek a hozzáadásával megadhatja azt a feltételt, amely a kiszámított mező hívásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="83e1b-208">By adding this parameter, you specify the condition that must be in place to call this calculated field.</span></span> <span data-ttu-id="83e1b-209">Ha ezt a mezőt választja, akkor az **Adózási szint** paraméter argumentumát **Karakterlánc** formátumú értékként kell megadni.</span><span class="sxs-lookup"><span data-stu-id="83e1b-209">When you call this calculated field, you need to specify the argument of the **Taxation Level** parameter as a value with **String** format.</span></span>

   <span data-ttu-id="83e1b-210">Győződjön meg róla, hogy csak olyan számított mezőkhöz határoz meg paramétereket, amelyek egy tárolóban találhatók (tehát **Rekordlista**, **Rekord** vagy **Tároló**).</span><span class="sxs-lookup"><span data-stu-id="83e1b-210">Make sure that you define parameters only for those calculated fields that reside in a container (either **Record list**, **Record**, or **Container**).</span></span>

   <span data-ttu-id="83e1b-211">A konfigurált paraméter elérhető a számított mezőhöz tartozó adatforrásainak listáján.</span><span class="sxs-lookup"><span data-stu-id="83e1b-211">The configured parameter is available in the list of data sources for this calculated field.</span></span> <span data-ttu-id="83e1b-212">A konfigurált kifejezéshez úgy vehet fel paramétert, hogy az **Adatforrás hozzáadása** lehetőséget választja.</span><span class="sxs-lookup"><span data-stu-id="83e1b-212">You can add the parameter to the configured expression by selecting **Add data source**.</span></span>

   ![Adatforrásmezők](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="83e1b-214">Kifejezés definiálása számított mező hozzáadásához</span><span class="sxs-lookup"><span data-stu-id="83e1b-214">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="83e1b-215">A **Képlet** mezőben adja meg a következőt:</span><span class="sxs-lookup"><span data-stu-id="83e1b-215">In the **Formula** field, enter:</span></span> 

    <span data-ttu-id="83e1b-216">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span><span class="sxs-lookup"><span data-stu-id="83e1b-216">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span></span>
    
2. <span data-ttu-id="83e1b-217">Válassza ki az **Adózási szint** paramétert az adatforrások listáján.</span><span class="sxs-lookup"><span data-stu-id="83e1b-217">Select the **Taxation Level** parameter in the list of data sources.</span></span>
3. <span data-ttu-id="83e1b-218">**Adatforrás hozzáadása** lehetőség választása.</span><span class="sxs-lookup"><span data-stu-id="83e1b-218">Select **Add data source**.</span></span>
4. <span data-ttu-id="83e1b-219">A **Képlet** mezőben véglegesítse a kifejezést a következőképpen:</span><span class="sxs-lookup"><span data-stu-id="83e1b-219">In the **Formula** field, finalize the expression as:</span></span>  

    <span data-ttu-id="83e1b-220">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span><span class="sxs-lookup"><span data-stu-id="83e1b-220">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span></span>

5. <span data-ttu-id="83e1b-221">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-221">Select **Save**.</span></span>

    ![Adatforrás mező adatai](media/er-calculated-field-type-07.png)

6. <span data-ttu-id="83e1b-223">Zárja be a **Képlettervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="83e1b-223">Close the **Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="83e1b-224">Az új számított mező hozzáadásának befejezése</span><span class="sxs-lookup"><span data-stu-id="83e1b-224">Finish adding a new calculated field</span></span>

- <span data-ttu-id="83e1b-225">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-225">Select **OK**.</span></span>

<span data-ttu-id="83e1b-226">A **Formátumtervező** lapon a **Szintek** konfigurált paraméterezett számított mező **Karakterlánc** argumentumot igényel.</span><span class="sxs-lookup"><span data-stu-id="83e1b-226">On the **Format designer** page, the configured parameterized calculated field **Levels** requires a **String** argument.</span></span>

![Számított mezők szintjeinek kibontott listája](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a><span data-ttu-id="83e1b-228">A konfigurált számított mező használata formátumelemek kapcsolásához</span><span class="sxs-lookup"><span data-stu-id="83e1b-228">Use the configured calculated field for binding format elements</span></span>

1. <span data-ttu-id="83e1b-229">Válasza ki a **Model.Data2.Levels** a konfigurált számított mező kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="83e1b-229">Select **Model.Data2.Levels** to select the configured calculated field.</span></span>
2. <span data-ttu-id="83e1b-230">Válassza ki a **Statement.Taxation.Regulars** formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-230">Select the **Statement.Taxation.Regular** format element.</span></span>
3. <span data-ttu-id="83e1b-231">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-231">Select **Bind**.</span></span>
4. <span data-ttu-id="83e1b-232">Az **igen** gombra kattintva visszaigazolhatja az aktuálisan használt adatforrás ( **Level1**) lecserélését az új **Szintek** adatforrásra a kiválasztott formátumelem minden beágyazott formátumeleme tekintetében.</span><span class="sxs-lookup"><span data-stu-id="83e1b-232">Select **Yes** to confirm the replacement of the currently used data source, **Level1**, by the new data source, **Levels**, in all nested format elements of the selected format element.</span></span>

    <span data-ttu-id="83e1b-233">Az alkalmazott társítást a program a paraméterezett számított mező meghívásaként alakítja ki.</span><span class="sxs-lookup"><span data-stu-id="83e1b-233">Applied binding has been built as a call of the parameterized calculated field.</span></span> <span data-ttu-id="83e1b-234">Alapértelmezés szerint a társított formátumelem neve argumentumként használatos a paraméterezett számított mezőhöz a következő feltételek teljesülése esetén:</span><span class="sxs-lookup"><span data-stu-id="83e1b-234">By default, the name of the bound format element is used as an argument for parameterized calculated field under the following conditions:</span></span>

      - <span data-ttu-id="83e1b-235">A számított mező úgy van beállítva, hogy egyetlen paramétert használjon.</span><span class="sxs-lookup"><span data-stu-id="83e1b-235">The calculated field is configured to use a single parameter.</span></span>
      - <span data-ttu-id="83e1b-236">A paraméter adattípusa **Karakterláncként** van definiálva.</span><span class="sxs-lookup"><span data-stu-id="83e1b-236">The data type of this parameter is defined as **String**.</span></span>

    <span data-ttu-id="83e1b-237">Amikor a társított formátumelem neve üres, az elemhez tartozó adatforrásnév használatos az alkalmazott társításban.</span><span class="sxs-lookup"><span data-stu-id="83e1b-237">When the name of the bound format element is blank, the data source name of this element is used in applied binding.</span></span>

5. <span data-ttu-id="83e1b-238">Válassza ki a **Statement.Taxation.Reduced** formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-238">Select the **Statement.Taxation.Reduced** format element.</span></span>
6. <span data-ttu-id="83e1b-239">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-239">Select **Bind**.</span></span>
7. <span data-ttu-id="83e1b-240">Az **Igen** gombra kattintva visszaigazolhatja az aktuálisan használt adatforrás ( **Level2**) lecserélését az új **Szintek** adatforrásra a kiválasztott formátumelem minden beágyazott formátumeleme tekintetében.</span><span class="sxs-lookup"><span data-stu-id="83e1b-240">Select **Yes** to confirm the replacement of the currently used data source, **Level2**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>
8. <span data-ttu-id="83e1b-241">Válassza ki a **Statement.Taxation.None** formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-241">Select the **Statement.Taxation.None** format element.</span></span>
9. <span data-ttu-id="83e1b-242">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-242">Select **Bind**.</span></span>
10. <span data-ttu-id="83e1b-243">Az **Igen** gombra kattintva visszaigazolhatja az aktuálisan használt adatforrás ( **Level3**) lecserélését az új **Szintek** adatforrásra a kiválasztott formátumelem minden beágyazott formátumeleme tekintetében.</span><span class="sxs-lookup"><span data-stu-id="83e1b-243">Select **Yes** to confirm the replacement of the currently used data source, **Level3**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>

   <span data-ttu-id="83e1b-244">Ha megadja az adózási szintet képviselő XML-elem paraméterezett számított mezőjének argumentumát (például: **Model.Data2.Levels("Reduced")** szöveges értékként), akkor nem kell ugyanezt elvégeznie a beágyazott XML-attribútumok esetében – a kötések automatikusan öröklik a szülő szintjén megadott argumentum értékét (**Model.Data2.Levels.aggregated.Base** és nem **Model.Data2.Levels("Reduced").aggregated.Base**).</span><span class="sxs-lookup"><span data-stu-id="83e1b-244">When you specify the argument of the parameterized calculated field for the XML element representing taxation level (for example, **Model.Data2.Levels("Reduced")** as a text value), you don’t need to do the same for nested XML attributes—their bindings will automatically inherit the value of the argument defined on the parent level (**Model.Data2.Levels.aggregated.Base**, not **Model.Data2.Levels("Reduced").aggregated.Base**).</span></span>

<span data-ttu-id="83e1b-245">A paraméterezett számított mezők ismétlődő meghívása nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="83e1b-245">Recurrent calls of any parameterized calculated field are not supported.</span></span>

<span data-ttu-id="83e1b-246">Kiválaszthatja a **Képlet szerkesztése** elemet, és módosíthatja a paraméterezett számított mező alapértelmezetten alkalmazott argumentumát a kiválasztott társításhoz.</span><span class="sxs-lookup"><span data-stu-id="83e1b-246">You can select **Edit formula**, and change the applied-by-default argument of the parameterized calculated field in the selected binding.</span></span> <span data-ttu-id="83e1b-247">Ha hiányzik ez az argumentum, az futásidőben hibákat okozhat – a felhasználókat tájékoztatni kell erről a helyzetről, amikor az aktuális formátumot validálják.</span><span class="sxs-lookup"><span data-stu-id="83e1b-247">If this argument is missing, it can cause errors at run time — users are informed about such a situation when the current format is validated.</span></span>

![Ellenőrzési figyelmeztetés értesítése](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a><span data-ttu-id="83e1b-249">Rekordot visszaadó paraméterezett számított mező konfigurálása</span><span class="sxs-lookup"><span data-stu-id="83e1b-249">Configure a parameterized calculated field to return a record</span></span>
<span data-ttu-id="83e1b-250">Ha egy paraméterezett számított mező rekordot ad vissza, akkor támogatnia kell a rekord egyedi mezőinek társítását formátumelemekhez.</span><span class="sxs-lookup"><span data-stu-id="83e1b-250">When a parameterized calculated field returns a record, you need to support binding of individual fields of this record to format elements.</span></span> <span data-ttu-id="83e1b-251">Ilyen esetekben nem lesz olyan szülő társítás amely argumentum értékét tartalmazza egy paraméterezett számított mező meghívására – ezt az értéket egyetlen rekord mezőjének társítása során kell meghatározni.</span><span class="sxs-lookup"><span data-stu-id="83e1b-251">In such cases there will be no parent binding that contains the value of an argument to call a parameterized calculated field — this value must be defined in the binding of a single record’s field.</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="83e1b-252">Kezdje el az új számított mező hozzáadását</span><span class="sxs-lookup"><span data-stu-id="83e1b-252">Start adding a new calculated field</span></span>

1. <span data-ttu-id="83e1b-253">Válassza ki a **Model.Data2** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-253">Select the **Model.Data2** item.</span></span>
2. <span data-ttu-id="83e1b-254">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-254">Select **Add**.</span></span>
3. <span data-ttu-id="83e1b-255">Válassa a **Függvények\\Számított mezőt**.</span><span class="sxs-lookup"><span data-stu-id="83e1b-255">Select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="83e1b-256">A **Név** mezőbe írja be a **LevelRecord** értéket.</span><span class="sxs-lookup"><span data-stu-id="83e1b-256">In the **Name** field, enter **LevelRecord**.</span></span>
5. <span data-ttu-id="83e1b-257">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-257">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="83e1b-258">Paraméter definiálása számított mező hozzáadásához</span><span class="sxs-lookup"><span data-stu-id="83e1b-258">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="83e1b-259">Válassza ki a **Paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-259">Select **Parameters**.</span></span>
2. <span data-ttu-id="83e1b-260">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-260">Select **New**.</span></span>
3. <span data-ttu-id="83e1b-261">A **Név** mezőbe írja be a következőt: **Adózási szint**.</span><span class="sxs-lookup"><span data-stu-id="83e1b-261">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="83e1b-262">A **Típus** mezőben válassza ki a **Karakterlánc** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-262">In the **Type** field, select **String**.</span></span>
5. <span data-ttu-id="83e1b-263">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-263">Select **OK**.</span></span>

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="83e1b-264">Kifejezés definiálása számított mező hozzáadásához</span><span class="sxs-lookup"><span data-stu-id="83e1b-264">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="83e1b-265">A **Képlet** mezőben adja meg a következőt:</span><span class="sxs-lookup"><span data-stu-id="83e1b-265">In the **Formula** field, enter the following:</span></span>  
    
    <span data-ttu-id="83e1b-266">**FIRSTORNULL(\@.Levels(**</span><span class="sxs-lookup"><span data-stu-id="83e1b-266">**FIRSTORNULL(\@.Levels(**</span></span>

2. <span data-ttu-id="83e1b-267">Válassza ki az **Adózási szint** paramétert.</span><span class="sxs-lookup"><span data-stu-id="83e1b-267">Select the **Taxation Level** parameter.</span></span>
3. <span data-ttu-id="83e1b-268">**Adatforrás hozzáadása** lehetőség választása.</span><span class="sxs-lookup"><span data-stu-id="83e1b-268">Select **Add data source**.</span></span>
4. <span data-ttu-id="83e1b-269">A **Képlet** mezőbe írja fűzze hozzá a **"'Taxation Level'))** elemet ahhoz,amit megadott az 1. lépésben, hogy a következőképp véglegesítse a kifejezést:</span><span class="sxs-lookup"><span data-stu-id="83e1b-269">In the **Formula** field, append **'Taxation Level'))** to what you entered in Step 1 to finalize the expression to:</span></span>  
    
    <span data-ttu-id="83e1b-270">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span><span class="sxs-lookup"><span data-stu-id="83e1b-270">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span></span>

5. <span data-ttu-id="83e1b-271">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-271">Select **Save**.</span></span>
6. <span data-ttu-id="83e1b-272">Zárja be a **Képlettervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="83e1b-272">Close **the Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="83e1b-273">Az új számított mező hozzáadásának befejezése</span><span class="sxs-lookup"><span data-stu-id="83e1b-273">Finish adding a new calculated field</span></span>

-   <span data-ttu-id="83e1b-274">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-274">Select **OK**.</span></span>

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a><span data-ttu-id="83e1b-275">A konfigurált számított mező használata formátumelemek társításához</span><span class="sxs-lookup"><span data-stu-id="83e1b-275">Use the configured calculated field to bind format elements</span></span>

1. <span data-ttu-id="83e1b-276">Bontsa ki a **Model.Data2.LevelRecord** elemet a konfigurált számított mező kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="83e1b-276">Expand **Model.Data2.LevelRecord** to select the configured calculated field.</span></span>
2. <span data-ttu-id="83e1b-277">Bontsa ki a **Model.Data2.LevelRecord.aggregated** tárolóját a konfigurált számított mezőnek.</span><span class="sxs-lookup"><span data-stu-id="83e1b-277">Expand the **Model.Data2.LevelRecord.aggregated** container of the configured calculated field.</span></span>
3. <span data-ttu-id="83e1b-278">Válassza ki **Model.Data2.LevelRecord.aggregated.Base** mezőt.</span><span class="sxs-lookup"><span data-stu-id="83e1b-278">Select the **Model.Data2.LevelRecord.aggregated.Base** field.</span></span>
4. <span data-ttu-id="83e1b-279">Válassza ki a **Statement.Taxation.None** formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-279">Select the **Statement.Taxation.None** format element.</span></span>
5. <span data-ttu-id="83e1b-280">Válassza a **Kötés megszűntetése** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-280">Select **Unbind**.</span></span>
6. <span data-ttu-id="83e1b-281">Válassza ki a **Statement.Taxation.Base** formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-281">Select the **Statement.Taxation.None.Base** format element.</span></span>
7. <span data-ttu-id="83e1b-282">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-282">Select **Bind**.</span></span>
8. <span data-ttu-id="83e1b-283">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-283">Select **Edit formula**.</span></span>
9. <span data-ttu-id="83e1b-284">A kifejezés módosítása a következőre: **Model.Data2.LevelRecord("None").aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="83e1b-284">Change the expression to **Model.Data2.LevelRecord("None").aggregated.Base**.</span></span>

![Frissített kifejezés](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a><span data-ttu-id="83e1b-286">Nem használt számított mezők eltávolítása</span><span class="sxs-lookup"><span data-stu-id="83e1b-286">Remove calculated fields that are not used</span></span>

1. <span data-ttu-id="83e1b-287">Válassza a **Model.Data2.Level1** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-287">Select **Model.Data2.Level1**.</span></span>
2. <span data-ttu-id="83e1b-288">Válassza a **Törlés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-288">Select **Delete**.</span></span>
3. <span data-ttu-id="83e1b-289">Válassza a **Model.Data2.Level2** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-289">Select **Model.Data2.Level2**.</span></span>
4. <span data-ttu-id="83e1b-290">Válassza a **Törlés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-290">Select **Delete**.</span></span>
5. <span data-ttu-id="83e1b-291">Válassza a **Model.Data2.Level3** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-291">Select **Model.Data2.Level3**.</span></span>
6. <span data-ttu-id="83e1b-292">Válassza a **Törlés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-292">Select **Delete**.</span></span>
7. <span data-ttu-id="83e1b-293">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-293">Select **Save**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="83e1b-294">Ugyanezt a **Model.Data2.Levels** számított mezőt többször is felhasználhatja a formátumtársításokban.</span><span class="sxs-lookup"><span data-stu-id="83e1b-294">You reused the same calculated field **Model.Data2.Levels** several times in format bindings.</span></span> <span data-ttu-id="83e1b-295">Sokkal könnyebb használni és karbantartani egyetlen számított mezőt,mint ugyanezt megtenni több hasonló mező esetében.</span><span class="sxs-lookup"><span data-stu-id="83e1b-295">It is much easier to use and maintain a single calculated field instead of doing this for multiple similar fields.</span></span>

8. <span data-ttu-id="83e1b-296">Zárja be a **Formátumtervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="83e1b-296">Close the **Format designer** page.</span></span>

## <a name="complete-adjusted-version-of-a-derived-format"></a><span data-ttu-id="83e1b-297">Származtatott formátum korrigált változatának befejezése</span><span class="sxs-lookup"><span data-stu-id="83e1b-297">Complete adjusted version of a derived format</span></span>

1. <span data-ttu-id="83e1b-298">A **Verziók** gyorslapon válassza az **Állapot módosítása** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-298">In the **Versions** FastTab, select **Change status**.</span></span>
2. <span data-ttu-id="83e1b-299">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-299">Select **Complete**.</span></span>

## <a name="export-completed-version-of-a-derived-format"></a><span data-ttu-id="83e1b-300">Származtatott formátum korrigált változatának exportálása</span><span class="sxs-lookup"><span data-stu-id="83e1b-300">Export completed version of a derived format</span></span>

1. <span data-ttu-id="83e1b-301">Válassza a **Formátum tanulja meg a paraméterezett meghívásokat (egyén)** formátumot a konfigurációs fában.</span><span class="sxs-lookup"><span data-stu-id="83e1b-301">Select **Format to learn parameterized calls (custom)** format in the configurations tree.</span></span>
2. <span data-ttu-id="83e1b-302">A **Verziók** gyorslapon válassza ki a kész 1.1.1-es verziót.</span><span class="sxs-lookup"><span data-stu-id="83e1b-302">In the **Versions** FastTab, select the completed version 1.1.1.</span></span>
3. <span data-ttu-id="83e1b-303">**Árfolyam** kijelölése.</span><span class="sxs-lookup"><span data-stu-id="83e1b-303">Select **Exchange**.</span></span>
4. <span data-ttu-id="83e1b-304">Válassza ki az **Exportálás XML-fájlként** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-304">Select **Export as XML file**.</span></span>
5. <span data-ttu-id="83e1b-305">A letöltött konfiguráció tárolása helyben, XML-formátumban.</span><span class="sxs-lookup"><span data-stu-id="83e1b-305">Store the downloaded configuration locally, in XML format.</span></span>

## <a name="test-er-formats"></a><span data-ttu-id="83e1b-306">ER-formátumok tesztelése</span><span class="sxs-lookup"><span data-stu-id="83e1b-306">Test ER formats</span></span> 
<span data-ttu-id="83e1b-307">A kezdeti és a továbbfejlesztett ER formátumot futtathatja, hogy meggyőzpdjön arról, hogy a konfigurált paraméterezett számított mezők megfelelően működnek.</span><span class="sxs-lookup"><span data-stu-id="83e1b-307">You can run the initial and improved ER formats to make sure that configured parameterized calculated fields work properly.</span></span>

### <a name="import-er-configurations"></a><span data-ttu-id="83e1b-308">ER-konfigurációk importálása</span><span class="sxs-lookup"><span data-stu-id="83e1b-308">Import ER configurations</span></span>
<span data-ttu-id="83e1b-309">Az **RCS** típushoz tartozó ER-tároló használatával importálhatja az áttekintett konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="83e1b-309">You can import reviewed configurations from RCS by using the ER repository of the **RCS** type.</span></span> <span data-ttu-id="83e1b-310">Ha már elvégezte az [Elektronikus jelentéskészítési (ER) konfigurációkat importálása a Regulatory Configuration Service (RCS) szolgáltatásból](rcs-download-configurations.md) lépéseit, használja a konfigurált ER-tárolót, a korábban tárgyalt konfigurációk importálásához környezetébe.</span><span class="sxs-lookup"><span data-stu-id="83e1b-310">If you already went through the steps in the topic, [Import Electronic reporting (ER) configurations from Regulatory Configuration Services (RCS)](rcs-download-configurations.md), use the configured ER repository to import configurations discussed earlier in this topic to your environment.</span></span> <span data-ttu-id="83e1b-311">Máskülönben kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="83e1b-311">Otherwise, follow these steps:</span></span>

1. <span data-ttu-id="83e1b-312">Válassza ki a **DEMF** vállalatot és az alapértelmezett irányítópulton válassza az **Elektronikus jelentéskészítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-312">Select the **DEMF** company and on the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="83e1b-313">Válassza a **Jelentéskészítési konfigurációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-313">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="83e1b-314">A letöltött konfigurációkat importálja a Microsoft letöltőközpontból a sorrendben: adatmodell, metaadatok, modell-leképezés, formátum.</span><span class="sxs-lookup"><span data-stu-id="83e1b-314">Import the configurations from Microsoft Download Center in the following sequence: data model, model mapping, format.</span></span> <span data-ttu-id="83e1b-315">Hajtsa végre a következő lépéseket mindegyik ER-konfiguráció esetében:</span><span class="sxs-lookup"><span data-stu-id="83e1b-315">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="83e1b-316">Válassza az **Átváltás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-316">Select **Exchange.**</span></span>
    2. <span data-ttu-id="83e1b-317">Kattintson a **Betöltés XML-fájlból** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83e1b-317">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="83e1b-318">Kattintson a **Tallózás** gombra, a megfelelő, XML-formátumú fájl kiválasztásához a szükséges ER-konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="83e1b-318">Select **Browse** to select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="83e1b-319">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-319">Select **OK**.</span></span>

4. <span data-ttu-id="83e1b-320">Importálja az exportált RCS befejezett 1.1.1. verzióját a **Formátum tanulja meg a paraméterezett meghívásokat** formátumából:</span><span class="sxs-lookup"><span data-stu-id="83e1b-320">Import the exported from RCS completed version 1.1.1 of the **Format to learn parameterized calls (custom)** format:</span></span>

    1. <span data-ttu-id="83e1b-321">Válassza az **Átváltás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-321">Select **Exchange.**</span></span>
    2. <span data-ttu-id="83e1b-322">Kattintson a **Betöltés XML-fájlból** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83e1b-322">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="83e1b-323">A **Tallózás** gombra kattintva kiválaszthatja a **Paraméterezett hívások tanulási formátuma (egyéni)** fájlt XML-formátumban.</span><span class="sxs-lookup"><span data-stu-id="83e1b-323">Select **Browse** to select the locally stored **Format to learn parameterized calls (custom)** file in XML format.</span></span>
    4. <span data-ttu-id="83e1b-324">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83e1b-324">Select **OK**.</span></span>

### <a name="run-er-formats"></a><span data-ttu-id="83e1b-325">ER formátumok futtatása</span><span class="sxs-lookup"><span data-stu-id="83e1b-325">Run ER formats</span></span>

1. <span data-ttu-id="83e1b-326">A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-326">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="83e1b-327">Válasza ki a **Formátum paraméterezett hívások tanulásához elemet**.</span><span class="sxs-lookup"><span data-stu-id="83e1b-327">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="83e1b-328">Válassza a **Futtatás** parancsot a legfelső menüszalagon.</span><span class="sxs-lookup"><span data-stu-id="83e1b-328">Select **Run** on the top-most ribbon.</span></span>
4. <span data-ttu-id="83e1b-329">Mentse el a helyileg előállított kimenetet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-329">Save the locally generated output.</span></span>
5. <span data-ttu-id="83e1b-330">Válassza ki a **Paraméterezett hívások tanulási formátuma (egyéni)** elemet.</span><span class="sxs-lookup"><span data-stu-id="83e1b-330">Select the **Format to learn parameterized calls (custom)** item.</span></span>
6. <span data-ttu-id="83e1b-331">Válassza a **Futtatás** parancsot a legfelső menüszalagon.</span><span class="sxs-lookup"><span data-stu-id="83e1b-331">Select **Run** on the top-most ribbon.</span></span>
7. <span data-ttu-id="83e1b-332">Mentse el az előállított kimenetet helyben.</span><span class="sxs-lookup"><span data-stu-id="83e1b-332">Save the generated output locally.</span></span> 
8. <span data-ttu-id="83e1b-333">A generált kimenetek tartalmának összehasonlítása.</span><span class="sxs-lookup"><span data-stu-id="83e1b-333">Compare the contents of the generated outputs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="83e1b-334">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="83e1b-334">Additional resources</span></span>

- [<span data-ttu-id="83e1b-335">Képletszerkesztő elektronikus jelentésekhez (ER)</span><span class="sxs-lookup"><span data-stu-id="83e1b-335">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="83e1b-336">Az ER megoldások teljesítményének javítása a paraméterek SZÁMÍTOTT MEZŐ-adatforrások hozzáadásával</span><span class="sxs-lookup"><span data-stu-id="83e1b-336">Improve performance of ER solutions by adding parameterized CALCULATED FIELD data sources</span></span>](er-calculated-field-ds-performance.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]