---
title: ER adatforrások paraméterezett hívásainak támogatása a Számított mezőtípusban
description: Ez a témakör azt mutatja be, hogyan kell használni a Számított mezőtípust ER-adatforrásokhoz.
author: NickSelin
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 86efa927fa97be0d54e965bf33b1a18519025c22
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248677"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a><span data-ttu-id="15715-103">ER adatforrások paraméterezett hívásainak támogatása a Számított mezőtípusban</span><span class="sxs-lookup"><span data-stu-id="15715-103">Support parameterized calls of ER data sources of the Calculated field type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="15715-104">Ez a témakör azt mutatja be, hogyan lehet az elektronikus jelentéskészítési (ER) adatforrást tervezni a **Számított mező** típusban.</span><span class="sxs-lookup"><span data-stu-id="15715-104">This topic explains how you can design an Electronic reporting (ER) data source by using the **Calculated field** type.</span></span> <span data-ttu-id="15715-105">Ez az adatforrás olyan ER-kifejezéseket tartalmazhat, amelyek a végrehajtás során paraméterargumentumok értékeivel vezérelhetők, amely egy hozzárendelésben konfigurálható, amely meghívja ezt az adatforrást.</span><span class="sxs-lookup"><span data-stu-id="15715-105">This data source may contain an ER expression that, when executed, can be controlled by the values of the parameter arguments that are configured in a binding that calls this data source.</span></span> <span data-ttu-id="15715-106">Egy ilyen adatforrás paraméterezett hívásának konfigurálásával több kötésben is felhasználható egyetlen adatforrás, ami csökkenti azoknak az adatforrásoknak a számát, amelyeket az ER-formátumok ER modell-leképezéseihez konfigurálni kell.</span><span class="sxs-lookup"><span data-stu-id="15715-106">By configuring parameterized calls of such a data source, you can reuse a single data source in many bindings, which reduces the total number of data sources that must be configured in ER model mappings or ER formats.</span></span> <span data-ttu-id="15715-107">Leegyszerűsíti a konfigurált ER-összetevőt is, amely csökkenti a karbantartási költségeket és a más felhasználók által felhasználás költségeit.</span><span class="sxs-lookup"><span data-stu-id="15715-107">It also simplifies the configured ER component, which reduces the maintenance costs and the cost of use by other consumers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15715-108">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="15715-108">Prerequisites</span></span>
<span data-ttu-id="15715-109">A jelen témakörben szereplő példák elvégzéséhez a következő hozzáférésekkel kell rendelkeznie:</span><span class="sxs-lookup"><span data-stu-id="15715-109">To complete the examples in this topic, you must have the following access:</span></span>

- <span data-ttu-id="15715-110">Hozzáférés egy ilyen szerepkörhöz:</span><span class="sxs-lookup"><span data-stu-id="15715-110">Access to one of these roles:</span></span>

    - <span data-ttu-id="15715-111">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="15715-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="15715-112">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="15715-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="15715-113">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="15715-113">System administrator</span></span>

- <span data-ttu-id="15715-114">Hozzáférés a Regulatory Configuration Service (RCS) szolgáltatáshoz, amelyet ugyanarra a bérlőre telepítettek, mint a Finance and Operations szolgáltatást, a következő szerepkörök egyikéhez:</span><span class="sxs-lookup"><span data-stu-id="15715-114">Access to Regulatory Configuration Services (RCS) that have been provisioned for the same tenant as Finance and Operations for one of the following roles:</span></span>

    - <span data-ttu-id="15715-115">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="15715-115">Electronic reporting developer</span></span>
    - <span data-ttu-id="15715-116">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="15715-116">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="15715-117">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="15715-117">System administrator</span></span>

<span data-ttu-id="15715-118">A [Microsoft letöltőközpontból](https://go.microsoft.com/fwlink/?linkid=874684)töltse le a tömörített fájlt: **ER adatforrások paraméterezet hívásainak támogatása a Számított mezőtípusban**.</span><span class="sxs-lookup"><span data-stu-id="15715-118">From the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684), download the zipped (compressed) file **Support parameterized calls of ER data sources of Calculated field type**.</span></span> <span data-ttu-id="15715-119">A következő ER-konfigurációkat tartalmazza, amelyeket helyileg kell kibontani és tárolni.</span><span class="sxs-lookup"><span data-stu-id="15715-119">It contains the following ER configurations that must be extracted and stored locally.</span></span>

| <span data-ttu-id="15715-120">**Tartalom**</span><span class="sxs-lookup"><span data-stu-id="15715-120">**Content**</span></span>                           | <span data-ttu-id="15715-121">**Fájlnév**</span><span class="sxs-lookup"><span data-stu-id="15715-121">**File name**</span></span>                                        |
|---------------------------------------|------------------------------------------------------|
| <span data-ttu-id="15715-122">Minta ER-adatmodell konfigurációja</span><span class="sxs-lookup"><span data-stu-id="15715-122">Sample ER data model configuration</span></span>    | <span data-ttu-id="15715-123">Model to learn parameterized calls.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="15715-123">Model to learn parameterized calls.version.1.xml</span></span>     |
| <span data-ttu-id="15715-124">Minta ER-metaadat konfigurációja</span><span class="sxs-lookup"><span data-stu-id="15715-124">Sample ER metadata configuration</span></span>      | <span data-ttu-id="15715-125">Metadata to learn parameterized calls.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="15715-125">Metadata to learn parameterized calls.version.1.xml</span></span>  |
| <span data-ttu-id="15715-126">Minta ER-adatmodell leképezési konfigurációja</span><span class="sxs-lookup"><span data-stu-id="15715-126">Sample ER model mapping configuration</span></span> | <span data-ttu-id="15715-127">Mapping to learn parameterized calls.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="15715-127">Mapping to learn parameterized calls.version.1.1.xml</span></span> |
| <span data-ttu-id="15715-128">Minta ER-formátum konfigurációja</span><span class="sxs-lookup"><span data-stu-id="15715-128">Sample ER format configuration</span></span>        | <span data-ttu-id="15715-129">Format to learn parameterized calls.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="15715-129">Format to learn parameterized calls.version.1.1.xml</span></span>  |

## <a name="sign-in-to-your-rcs-instance"></a><span data-ttu-id="15715-130">Jelentkezzen be a RCS-példányba</span><span class="sxs-lookup"><span data-stu-id="15715-130">Sign in to your RCS instance</span></span>
<span data-ttu-id="15715-131">Ebben a példában létrehozzuk egy konfigurációt a Litware, Inc. mintavállalatra vonatkozóan. A lépések végrehajtásához először a következő eljárás lépéseit kell végrehajtani az RCS-ben: [ER – Konfigurációszolgáltató létrehozása, és megjelölés aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md):</span><span class="sxs-lookup"><span data-stu-id="15715-131">In this example, you will create a configuration for the sample company, Litware, Inc. First, in RCS, you must complete the steps in the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure:</span></span>

1. <span data-ttu-id="15715-132">Az alapértelmezett irányítópulton válassza az **Elektronikus jelentéskészítés**elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-132">On the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="15715-133">Válassza a **Jelentéskészítési konfigurációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-133">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="15715-134">A letöltött konfigurációkat importálja a következő sorrendben az RCS-be: adatmodell, metaadatok, modell-leképezés, formátum.</span><span class="sxs-lookup"><span data-stu-id="15715-134">Import the downloaded configurations to RCS in the following sequence: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="15715-135">Hajtsa végre a következő lépéseket mindegyik ER-konfiguráció esetében:</span><span class="sxs-lookup"><span data-stu-id="15715-135">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="15715-136">Válassza az **Átváltás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-136">Select **Exchange.**</span></span>
    2. <span data-ttu-id="15715-137">Kattintson a **Betöltés XML-fájlból** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="15715-137">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="15715-138">Kattintson a **Tallózás** gombra, majd válassza ki a megfelelő, XML-formátumú fájlt a szükséges ER-konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="15715-138">Select **Browse**, and then select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="15715-139">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-139">Select **OK.**</span></span>

## <a name="review-the-provided-er-solution"></a><span data-ttu-id="15715-140">A nyújtott ER-megoldás áttekintése</span><span class="sxs-lookup"><span data-stu-id="15715-140">Review the provided ER solution</span></span>

### <a name="review-model-mapping"></a><span data-ttu-id="15715-141">Modell-leképezés áttekintése</span><span class="sxs-lookup"><span data-stu-id="15715-141">Review model mapping</span></span>

1. <span data-ttu-id="15715-142">A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-142">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="15715-143">Válasza ki a **Leképezés paraméterezett hívások tanulásához elemet**.</span><span class="sxs-lookup"><span data-stu-id="15715-143">Select **Mapping to learn parameterized calls**.</span></span>
3. <span data-ttu-id="15715-144">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-144">Select **Designer**.</span></span>
4. <span data-ttu-id="15715-145">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-145">Select **Designer**.</span></span>  
   
<span data-ttu-id="15715-146">Ez az ER-leképezés a következőkre képes:</span><span class="sxs-lookup"><span data-stu-id="15715-146">This ER model mapping is designed to do the following:</span></span>

- <span data-ttu-id="15715-147">Lekéri az adókódok listáját (**Adó** adatforrás) amelyek a **TaxTable** táblában találhatók.</span><span class="sxs-lookup"><span data-stu-id="15715-147">Fetch the list of tax codes (**Tax** data source) residing in the   **TaxTable** table.</span></span>
- <span data-ttu-id="15715-148">Lekéri az adótranzakciók listáját (**Tranz** adatforrás) amelyek a **TaxTrans** táblában találhatók:</span><span class="sxs-lookup"><span data-stu-id="15715-148">Fetch the list of tax transactions (**Trans** data source) residing in the   **TaxTrans** table:</span></span>
    
    - <span data-ttu-id="15715-149">A beolvasott tranzakciók (**Gr** -adatforrás) listájának csoportosítása adózási kód szerint.</span><span class="sxs-lookup"><span data-stu-id="15715-149">Group the list of fetched transactions (**Gr** data source) by tax code.</span></span>
    - <span data-ttu-id="15715-150">Kiszámítja a csoportosított tranzakciókat az adózási kód szerinti aggregált értékek szerint:</span><span class="sxs-lookup"><span data-stu-id="15715-150">Calculate for grouped transactions following aggregated values per   tax code:</span></span>

        - <span data-ttu-id="15715-151">Adóalap-értékek összege.</span><span class="sxs-lookup"><span data-stu-id="15715-151">Sum of tax base values.</span></span>
        - <span data-ttu-id="15715-152">Adóértékek összege.</span><span class="sxs-lookup"><span data-stu-id="15715-152">Sum of tax values.</span></span>
        - <span data-ttu-id="15715-153">Az alkalmazott adómérték minimális értéke.</span><span class="sxs-lookup"><span data-stu-id="15715-153">Minimum value of applied tax rate.</span></span>

<span data-ttu-id="15715-154">Az ebben a konfigurációban szereplő modell-hozzárendelés az alapadatok modellt alkalmazza az ehhez a modellhez létrehozott, valamint a Finance and Operations megoldásban végrehajtott összes ER-formátum esetében.</span><span class="sxs-lookup"><span data-stu-id="15715-154">The model mapping in this configuration implements the base data model for any of the ER formats created for this model and executed in Finance and Operations.</span></span> <span data-ttu-id="15715-155">Ennek eredményeképpen az **Adó** és **Gr** -adatforrások tartalma ER-formátumoknak, például absztrakt adatforrásoknak van kitéve.</span><span class="sxs-lookup"><span data-stu-id="15715-155">As a result, the content of the **Tax** and **Gr** data sources is exposed for ER formats such as abstract data sources.</span></span>

  ![Modell-hozzárendelés tervező lapja au Adó és Gr adatforrásokat jeleníti meg.](media/er-calculated-field-type-01.png)

5.  <span data-ttu-id="15715-157">Zárja be a **Modell-hozzárendelési tervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="15715-157">Close the **Model mapping designer** page.</span></span>
6.  <span data-ttu-id="15715-158">Zárja be a **Modell-hozzárendelés** lapot.</span><span class="sxs-lookup"><span data-stu-id="15715-158">Close the **Model mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="15715-159">Formátum áttekintése</span><span class="sxs-lookup"><span data-stu-id="15715-159">Review format</span></span>

1. <span data-ttu-id="15715-160">A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-160">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="15715-161">Válasza ki a **Formátum paraméterezett hívások tanulásához elemet**.</span><span class="sxs-lookup"><span data-stu-id="15715-161">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="15715-162">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-162">Select **Designer**.</span></span> <span data-ttu-id="15715-163">Ez az ER-formátum a következőkre képes:</span><span class="sxs-lookup"><span data-stu-id="15715-163">This ER format is designed to do the following:</span></span>

  - <span data-ttu-id="15715-164">Adókimutatás létrehozása XML-formátumban.</span><span class="sxs-lookup"><span data-stu-id="15715-164">Generate a tax statement in XML format.</span></span>
  - <span data-ttu-id="15715-165">Az adóbevallásban a következő adómértékeket megjeleníti: normál, csökkentett és nincs.</span><span class="sxs-lookup"><span data-stu-id="15715-165">Present the following levels of taxation in the tax statement: regular, reduced, and none.</span></span>
  - <span data-ttu-id="15715-166">Minden adózási szinten több részletet mutat be, amelyek mindegyik szintjén különböző számú adat szerepel.</span><span class="sxs-lookup"><span data-stu-id="15715-166">Present multiple details at each taxation level, having a different number of details in each level.</span></span>

  ![Formátumtervező oldal](media/er-calculated-field-type-02.png)

4. <span data-ttu-id="15715-168">Válassza ki **Hozzárendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-168">Select **Mapping**.</span></span>
5. <span data-ttu-id="15715-169">Bontsa ki a **Modell**, **Adatok** és **Összegzés** elemeket.</span><span class="sxs-lookup"><span data-stu-id="15715-169">Expand the **Model**, **Data,** and **Summary** items.</span></span> 

   <span data-ttu-id="15715-170">A **Model.Data.Summary.Level** számított mező tartalmazza azt a kifejezést, amely az adózási szint kódját adja vissza (**Normál**, **Csökkenetett**, **Nincs** vagy **Egyéb**). szöveges értékként, amely lekérhető a **Model.Data.summary** adatforrásból futásidőben.</span><span class="sxs-lookup"><span data-stu-id="15715-170">The calculated field **Model.Data.Summary.Level** contains the expression that returns the code of the taxation level (**Regular**, **Reduced**, **None,** or **Other**) as a text value for any tax code that can be retrieved from the **Model.Data.Summary** data source at run time.</span></span>

  ![A Formátumtervező lap a paraméterezett hívások megtanulásához szükséges adatmodell részleteit jeleníti meg.](media/er-calculated-field-type-03.png)

6. <span data-ttu-id="15715-172">Bontsa ki a **Model**.**Data2** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-172">Expand the **Model**.**Data2** item.</span></span>
7. <span data-ttu-id="15715-173">Bontsa ki a **Model**.**Data2.Summary2** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-173">Expand the **Model**.**Data2.Summary2** item.</span></span>
   
   <span data-ttu-id="15715-174">A **Model**.**Data2.Summary2** adatforrás úgy van konfigurálva, hogy csoportba rendezze a **Model.Data.Summary** adatforrás tranzakcióadatait adózási szinten (ezt a **Model.Data.Summary.Level** számított mező adja vissza), és kiszámítsa az összesítéseket.</span><span class="sxs-lookup"><span data-stu-id="15715-174">The **Model**.**Data2.Summary2** data source is configured to group the **Model.Data.Summary** data source transaction details by taxation level (returned by the **Model.Data.Summary.Level** calculated field) and compute the aggregations.</span></span>

  ![A Formátumtervező lap a Model.Data2.Summary2 adatforrás részletes adatait jeleníti meg.](media/er-calculated-field-type-04.png)

8. <span data-ttu-id="15715-176">Tekintse át a **Model**.**Data2.Level1**, **Model**.**Data2.Level2** és **Model**.**Data2.Level3** számított mezőket.</span><span class="sxs-lookup"><span data-stu-id="15715-176">Review the calculated fields **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, and **Model**.**Data2.Level3.**</span></span> <span data-ttu-id="15715-177">Ezeket a számított mezőket a **Model**.**Data2.Summary2** rekordlista szűrésére használja a rendszer, és csak az adott adózási szintet képviselő rekordokat adja vissza.</span><span class="sxs-lookup"><span data-stu-id="15715-177">These calculated fields are used to filter the **Model**.**Data2.Summary2** records list and return only records that represent a particular taxation level.</span></span>
9. <span data-ttu-id="15715-178">Zárja be a **Formátumtervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="15715-178">Close the **Format designer** page.</span></span>

## <a name="create-a-derived-format"></a><span data-ttu-id="15715-179">Származtatott formátum létrehozása</span><span class="sxs-lookup"><span data-stu-id="15715-179">Create a derived format</span></span>
<span data-ttu-id="15715-180">A megadott formátumot úgy javíthatja, hogy egy számított mezőt ad hozzá a szükséges adózási szint szűréséhez, nem pedig a meglévő három mezőt használja: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** és **Model**.**Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="15715-180">You can improve the provided format by adding one calculated field to filter the required taxation level instead of using the existing three fields: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** and **Model**.**Data2.Level3**.</span></span> <span data-ttu-id="15715-181">A szükséges adózási szint meghatározható azon a helyen, ahol ennek az új számított mezőnek a meghívása történik.</span><span class="sxs-lookup"><span data-stu-id="15715-181">The required taxation level can be specified in the location where this new calculated field will be called.</span></span>

1. <span data-ttu-id="15715-182">A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-182">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="15715-183">Válasza ki a **Formátum paraméterezett hívások tanulásához elemet**.</span><span class="sxs-lookup"><span data-stu-id="15715-183">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="15715-184">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-184">Select **Create configuration**.</span></span>
4. <span data-ttu-id="15715-185">Válassza a **Származtatás névből: Formátum paraméterezett hívások tanulásához, Microsoft** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-185">Select **Derive from Name: Format to learn parameterized calls, Microsoft**.</span></span>
5. <span data-ttu-id="15715-186">A **Név** mezőbe írja be: **Paraméterezett hívások tanulási formátuma (egyéni)**.</span><span class="sxs-lookup"><span data-stu-id="15715-186">In the **Name** field, enter **Format to learn parameterized calls (custom)**.</span></span>
6. <span data-ttu-id="15715-187">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-187">Select **Create configuration.**</span></span>

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a><span data-ttu-id="15715-188">A rekordok listáját visszaadó paraméterezett számított mező konfigurálása</span><span class="sxs-lookup"><span data-stu-id="15715-188">Configure a parameterized calculated field that returns a list of records</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="15715-189">Kezdje el az új számított mező hozzáadását</span><span class="sxs-lookup"><span data-stu-id="15715-189">Start adding a new calculated field</span></span>

1. <span data-ttu-id="15715-190">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-190">Select **Designer**.</span></span>
2. <span data-ttu-id="15715-191">Válassza ki a **Kibontás/összecsukás** elemet az összes formátumelem kibontásához.</span><span class="sxs-lookup"><span data-stu-id="15715-191">Select **Expand/collapse** to expand all format items.</span></span>
3. <span data-ttu-id="15715-192">Válassza ki **Hozzárendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-192">Select **Mapping**.</span></span>
4. <span data-ttu-id="15715-193">Bontsa ki a **Modell** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-193">Expand the **Model** item.</span></span>
5. <span data-ttu-id="15715-194">Válassza ki a **Model.Data2** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-194">Select the **Model.Data2** item.</span></span>
6. <span data-ttu-id="15715-195">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-195">Select **Add**.</span></span>
7. <span data-ttu-id="15715-196">Válassa a **Függvények\\Számított mezőt**.</span><span class="sxs-lookup"><span data-stu-id="15715-196">Select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="15715-197">A **Név** mezőbe írja be a **szintek** szót.</span><span class="sxs-lookup"><span data-stu-id="15715-197">In the **Name** field, enter **Levels**.</span></span>
9. <span data-ttu-id="15715-198">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-198">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="15715-199">Paraméter definiálása számított mező hozzáadásához</span><span class="sxs-lookup"><span data-stu-id="15715-199">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="15715-200">Válassza ki a **Paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-200">Select **Parameters**.</span></span>
2. <span data-ttu-id="15715-201">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-201">Select **New**.</span></span>
3. <span data-ttu-id="15715-202">A **Név** mezőbe írja be a következőt: **Adózási szint**.</span><span class="sxs-lookup"><span data-stu-id="15715-202">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="15715-203">A **Típus** mezőben válassza ki a **Karakterlánc** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-203">In the **Type** field, select **String**.</span></span>

    <span data-ttu-id="15715-204">A paraméterek argumentumának típusát csak primitív adattípusokkal lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="15715-204">Only primitive data types can be used to specify the type of the parameter’s argument.</span></span> <span data-ttu-id="15715-205">Ezért a **Rekordlista**, **Rekord**és **Enum** típus nem használhatók erre a célra.</span><span class="sxs-lookup"><span data-stu-id="15715-205">Therefore, **Record list**, **Record**, and **Enum** types cannot be used for this purpose.</span></span>

    <span data-ttu-id="15715-206">Az egyetlen számított mezőhöz meghatározható paraméterek maximális száma 8.</span><span class="sxs-lookup"><span data-stu-id="15715-206">The maximum number of parameters that can be specified for a single calculated field is 8.</span></span>

    ![Paraméter adatforráslistája](media/er-calculated-field-type-05.png)

5. <span data-ttu-id="15715-208">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-208">Select **OK**.</span></span>

<span data-ttu-id="15715-209">Ennek a paraméternek a hozzáadásával megadhatja azt a feltételt, amely a kiszámított mező hívásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="15715-209">By adding this parameter, you specify the condition that must be in place to call this calculated field.</span></span> <span data-ttu-id="15715-210">Ha ezt a mezőt választja, akkor az **Adózási szint** paraméter argumentumát **Karakterlánc** formátumú értékként kell megadni.</span><span class="sxs-lookup"><span data-stu-id="15715-210">When you call this calculated field, you need to specify the argument of the **Taxation Level** parameter as a value with **String** format.</span></span>

   <span data-ttu-id="15715-211">Győződjön meg róla, hogy csak olyan számított mezőkhöz határoz meg paramétereket, amelyek egy tárolóban találhatók (tehát **Rekordlista**, **Rekord** vagy **Tároló**).</span><span class="sxs-lookup"><span data-stu-id="15715-211">Make sure that you define parameters only for those calculated fields that reside in a container (either **Record list**, **Record**, or **Container**).</span></span>

   <span data-ttu-id="15715-212">A konfigurált paraméter elérhető a számított mezőhöz tartozó adatforrásainak listáján.</span><span class="sxs-lookup"><span data-stu-id="15715-212">The configured parameter is available in the list of data sources for this calculated field.</span></span> <span data-ttu-id="15715-213">A konfigurált kifejezéshez úgy vehet fel paramétert, hogy az **Adatforrás hozzáadása** lehetőséget választja.</span><span class="sxs-lookup"><span data-stu-id="15715-213">You can add the parameter to the configured expression by selecting **Add data source**.</span></span>

   ![Adatforrásmezők](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="15715-215">Kifejezés definiálása számított mező hozzáadásához</span><span class="sxs-lookup"><span data-stu-id="15715-215">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="15715-216">A **Képlet** mezőben adja meg a következőt:</span><span class="sxs-lookup"><span data-stu-id="15715-216">In the **Formula** field, enter:</span></span> 

    <span data-ttu-id="15715-217">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span><span class="sxs-lookup"><span data-stu-id="15715-217">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span></span>
    
2. <span data-ttu-id="15715-218">Válassza ki az **Adózási szint** paramétert az adatforrások listáján.</span><span class="sxs-lookup"><span data-stu-id="15715-218">Select the **Taxation Level** parameter in the list of data sources.</span></span>
3. <span data-ttu-id="15715-219">**Adatforrás hozzáadása** lehetőség választása.</span><span class="sxs-lookup"><span data-stu-id="15715-219">Select **Add data source**.</span></span>
4. <span data-ttu-id="15715-220">A **Képlet** mezőben véglegesítse a kifejezést a következőképpen:</span><span class="sxs-lookup"><span data-stu-id="15715-220">In the **Formula** field, finalize the expression as:</span></span>  

    <span data-ttu-id="15715-221">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span><span class="sxs-lookup"><span data-stu-id="15715-221">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span></span>

5. <span data-ttu-id="15715-222">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-222">Select **Save**.</span></span>

    ![Adatforrás mező adatai](media/er-calculated-field-type-07.png)

6. <span data-ttu-id="15715-224">Zárja be a **Képlettervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="15715-224">Close the **Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="15715-225">Az új számított mező hozzáadásának befejezése</span><span class="sxs-lookup"><span data-stu-id="15715-225">Finish adding a new calculated field</span></span>

- <span data-ttu-id="15715-226">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-226">Select **OK**.</span></span>

<span data-ttu-id="15715-227">A **Formátumtervező** lapon a **Szintek** konfigurált paraméterezett számított mező **Karakterlánc** argumentumot igényel.</span><span class="sxs-lookup"><span data-stu-id="15715-227">On the **Format designer** page, the configured parameterized calculated field **Levels** requires a **String** argument.</span></span>

![Számított mezők szintjeinek kibontott listája](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a><span data-ttu-id="15715-229">A konfigurált számított mező használata formátumelemek kapcsolásához</span><span class="sxs-lookup"><span data-stu-id="15715-229">Use the configured calculated field for binding format elements</span></span>

1. <span data-ttu-id="15715-230">Válasza ki a **Model.Data2.Levels** a konfigurált számított mező kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="15715-230">Select **Model.Data2.Levels** to select the configured calculated field.</span></span>
2. <span data-ttu-id="15715-231">Válassza ki a **Statement.Taxation.Regulars** formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="15715-231">Select the **Statement.Taxation.Regular** format element.</span></span>
3. <span data-ttu-id="15715-232">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-232">Select **Bind**.</span></span>
4. <span data-ttu-id="15715-233">Az **igen** gombra kattintva visszaigazolhatja az aktuálisan használt adatforrás ( **Level1**) lecserélését az új **Szintek** adatforrásra a kiválasztott formátumelem minden beágyazott formátumeleme tekintetében.</span><span class="sxs-lookup"><span data-stu-id="15715-233">Select **Yes** to confirm the replacement of the currently used data source, **Level1**, by the new data source, **Levels**, in all nested format elements of the selected format element.</span></span>

    <span data-ttu-id="15715-234">Az alkalmazott társítást a program a paraméterezett számított mező meghívásaként alakítja ki.</span><span class="sxs-lookup"><span data-stu-id="15715-234">Applied binding has been built as a call of the parameterized calculated field.</span></span> <span data-ttu-id="15715-235">Alapértelmezés szerint a társított formátumelem neve argumentumként használatos a paraméterezett számított mezőhöz a következő feltételek teljesülése esetén:</span><span class="sxs-lookup"><span data-stu-id="15715-235">By default, the name of the bound format element is used as an argument for parameterized calculated field under the following conditions:</span></span>

      - <span data-ttu-id="15715-236">A számított mező úgy van beállítva, hogy egyetlen paramétert használjon.</span><span class="sxs-lookup"><span data-stu-id="15715-236">The calculated field is configured to use a single parameter.</span></span>
      - <span data-ttu-id="15715-237">A paraméter adattípusa **Karakterláncként** van definiálva.</span><span class="sxs-lookup"><span data-stu-id="15715-237">The data type of this parameter is defined as **String**.</span></span>

    <span data-ttu-id="15715-238">Amikor a társított formátumelem neve üres, az elemhez tartozó adatforrásnév használatos az alkalmazott társításban.</span><span class="sxs-lookup"><span data-stu-id="15715-238">When the name of the bound format element is blank, the data source name of this element is used in applied binding.</span></span>

5. <span data-ttu-id="15715-239">Válassza ki a **Statement.Taxation.Reduced** formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="15715-239">Select the **Statement.Taxation.Reduced** format element.</span></span>
6. <span data-ttu-id="15715-240">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-240">Select **Bind**.</span></span>
7. <span data-ttu-id="15715-241">Az **Igen** gombra kattintva visszaigazolhatja az aktuálisan használt adatforrás ( **Level2**) lecserélését az új **Szintek** adatforrásra a kiválasztott formátumelem minden beágyazott formátumeleme tekintetében.</span><span class="sxs-lookup"><span data-stu-id="15715-241">Select **Yes** to confirm the replacement of the currently used data source, **Level2**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>
8. <span data-ttu-id="15715-242">Válassza ki a **Statement.Taxation.None** formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="15715-242">Select the **Statement.Taxation.None** format element.</span></span>
9. <span data-ttu-id="15715-243">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-243">Select **Bind**.</span></span>
10. <span data-ttu-id="15715-244">Az **Igen** gombra kattintva visszaigazolhatja az aktuálisan használt adatforrás ( **Level3**) lecserélését az új **Szintek** adatforrásra a kiválasztott formátumelem minden beágyazott formátumeleme tekintetében.</span><span class="sxs-lookup"><span data-stu-id="15715-244">Select **Yes** to confirm the replacement of the currently used data source, **Level3**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>

   <span data-ttu-id="15715-245">Ha megadja az adózási szintet képviselő XML-elem paraméterezett számított mezőjének argumentumát (például: **Model.Data2.Levels("Reduced")** szöveges értékként), akkor nem kell ugyanezt elvégeznie a beágyazott XML-attribútumok esetében – a kötések automatikusan öröklik a szülő szintjén megadott argumentum értékét (**Model.Data2.Levels.aggregated.Base** és nem **Model.Data2.Levels("Reduced").aggregated.Base**).</span><span class="sxs-lookup"><span data-stu-id="15715-245">When you specify the argument of the parameterized calculated field for the XML element representing taxation level (for example, **Model.Data2.Levels("Reduced")** as a text value), you don’t need to do the same for nested XML attributes—their bindings will automatically inherit the value of the argument defined on the parent level (**Model.Data2.Levels.aggregated.Base**, not **Model.Data2.Levels("Reduced").aggregated.Base**).</span></span>

<span data-ttu-id="15715-246">A paraméterezett számított mezők ismétlődő meghívása nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="15715-246">Recurrent calls of any parameterized calculated field are not supported.</span></span>

<span data-ttu-id="15715-247">Kiválaszthatja a **Képlet szerkesztése** elemet, és módosíthatja a paraméterezett számított mező alapértelmezetten alkalmazott argumentumát a kiválasztott társításhoz.</span><span class="sxs-lookup"><span data-stu-id="15715-247">You can select **Edit formula**, and change the applied-by-default argument of the parameterized calculated field in the selected binding.</span></span> <span data-ttu-id="15715-248">Ha hiányzik ez az argumentum, az futásidőben hibákat okozhat – a felhasználókat tájékoztatni kell erről a helyzetről, amikor az aktuális formátumot validálják.</span><span class="sxs-lookup"><span data-stu-id="15715-248">If this argument is missing, it can cause errors at run time — users are informed about such a situation when the current format is validated.</span></span>

![Ellenőrzési figyelmeztetés értesítése](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a><span data-ttu-id="15715-250">Rekordot visszaadó paraméterezett számított mező konfigurálása</span><span class="sxs-lookup"><span data-stu-id="15715-250">Configure a parameterized calculated field to return a record</span></span>
<span data-ttu-id="15715-251">Ha egy paraméterezett számított mező rekordot ad vissza, akkor támogatnia kell a rekord egyedi mezőinek társítását formátumelemekhez.</span><span class="sxs-lookup"><span data-stu-id="15715-251">When a parameterized calculated field returns a record, you need to support binding of individual fields of this record to format elements.</span></span> <span data-ttu-id="15715-252">Ilyen esetekben nem lesz olyan szülő társítás amely argumentum értékét tartalmazza egy paraméterezett számított mező meghívására – ezt az értéket egyetlen rekord mezőjének társítása során kell meghatározni.</span><span class="sxs-lookup"><span data-stu-id="15715-252">In such cases there will be no parent binding that contains the value of an argument to call a parameterized calculated field — this value must be defined in the binding of a single record’s field.</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="15715-253">Kezdje el az új számított mező hozzáadását</span><span class="sxs-lookup"><span data-stu-id="15715-253">Start adding a new calculated field</span></span>

1. <span data-ttu-id="15715-254">Válassza ki a **Model.Data2** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-254">Select the **Model.Data2** item.</span></span>
2. <span data-ttu-id="15715-255">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-255">Select **Add**.</span></span>
3. <span data-ttu-id="15715-256">Válassa a **Függvények\\Számított mezőt**.</span><span class="sxs-lookup"><span data-stu-id="15715-256">Select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="15715-257">A **Név** mezőbe írja be a **LevelRecord** értéket.</span><span class="sxs-lookup"><span data-stu-id="15715-257">In the **Name** field, enter **LevelRecord**.</span></span>
5. <span data-ttu-id="15715-258">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-258">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="15715-259">Paraméter definiálása számított mező hozzáadásához</span><span class="sxs-lookup"><span data-stu-id="15715-259">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="15715-260">Válassza ki a **Paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-260">Select **Parameters**.</span></span>
2. <span data-ttu-id="15715-261">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-261">Select **New**.</span></span>
3. <span data-ttu-id="15715-262">A **Név** mezőbe írja be a következőt: **Adózási szint**.</span><span class="sxs-lookup"><span data-stu-id="15715-262">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="15715-263">A **Típus** mezőben válassza ki a **Karakterlánc** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-263">In the **Type** field, select **String**.</span></span>
5. <span data-ttu-id="15715-264">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-264">Select **OK**.</span></span>

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="15715-265">Kifejezés definiálása számított mező hozzáadásához</span><span class="sxs-lookup"><span data-stu-id="15715-265">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="15715-266">A **Képlet** mezőben adja meg a következőt:</span><span class="sxs-lookup"><span data-stu-id="15715-266">In the **Formula** field, enter the following:</span></span>  
    
    <span data-ttu-id="15715-267">**FIRSTORNULL(\@.Levels(**</span><span class="sxs-lookup"><span data-stu-id="15715-267">**FIRSTORNULL(\@.Levels(**</span></span>

2. <span data-ttu-id="15715-268">Válassza ki az **Adózási szint** paramétert.</span><span class="sxs-lookup"><span data-stu-id="15715-268">Select the **Taxation Level** parameter.</span></span>
3. <span data-ttu-id="15715-269">**Adatforrás hozzáadása** lehetőség választása.</span><span class="sxs-lookup"><span data-stu-id="15715-269">Select **Add data source**.</span></span>
4. <span data-ttu-id="15715-270">A **Képlet** mezőbe írja fűzze hozzá a **"'Taxation Level'))** elemet ahhoz,amit megadott az 1. lépésben, hogy a következőképp véglegesítse a kifejezést:</span><span class="sxs-lookup"><span data-stu-id="15715-270">In the **Formula** field, append **'Taxation Level'))** to what you entered in Step 1 to finalize the expression to:</span></span>  
    
    <span data-ttu-id="15715-271">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span><span class="sxs-lookup"><span data-stu-id="15715-271">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span></span>

5. <span data-ttu-id="15715-272">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-272">Select **Save**.</span></span>
6. <span data-ttu-id="15715-273">Zárja be a **Képlettervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="15715-273">Close **the Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="15715-274">Az új számított mező hozzáadásának befejezése</span><span class="sxs-lookup"><span data-stu-id="15715-274">Finish adding a new calculated field</span></span>

-   <span data-ttu-id="15715-275">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-275">Select **OK**.</span></span>

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a><span data-ttu-id="15715-276">A konfigurált számított mező használata formátumelemek társításához</span><span class="sxs-lookup"><span data-stu-id="15715-276">Use the configured calculated field to bind format elements</span></span>

1. <span data-ttu-id="15715-277">Bontsa ki a **Model.Data2.LevelRecord** elemet a konfigurált számított mező kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="15715-277">Expand **Model.Data2.LevelRecord** to select the configured calculated field.</span></span>
2. <span data-ttu-id="15715-278">Bontsa ki a **Model.Data2.LevelRecord.aggregated** tárolóját a konfigurált számított mezőnek.</span><span class="sxs-lookup"><span data-stu-id="15715-278">Expand the **Model.Data2.LevelRecord.aggregated** container of the configured calculated field.</span></span>
3. <span data-ttu-id="15715-279">Válassza ki **Model.Data2.LevelRecord.aggregated.Base** mezőt.</span><span class="sxs-lookup"><span data-stu-id="15715-279">Select the **Model.Data2.LevelRecord.aggregated.Base** field.</span></span>
4. <span data-ttu-id="15715-280">Válassza ki a **Statement.Taxation.None** formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="15715-280">Select the **Statement.Taxation.None** format element.</span></span>
5. <span data-ttu-id="15715-281">Válassza a **Kötés megszűntetése** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-281">Select **Unbind**.</span></span>
6. <span data-ttu-id="15715-282">Válassza ki a **Statement.Taxation.Base** formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="15715-282">Select the **Statement.Taxation.None.Base** format element.</span></span>
7. <span data-ttu-id="15715-283">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-283">Select **Bind**.</span></span>
8. <span data-ttu-id="15715-284">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-284">Select **Edit formula**.</span></span>
9. <span data-ttu-id="15715-285">A kifejezés módosítása a következőre: **Model.Data2.LevelRecord("None").aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="15715-285">Change the expression to **Model.Data2.LevelRecord("None").aggregated.Base**.</span></span>

![Frissített kifejezés](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a><span data-ttu-id="15715-287">Nem használt számított mezők eltávolítása</span><span class="sxs-lookup"><span data-stu-id="15715-287">Remove calculated fields that are not used</span></span>

1. <span data-ttu-id="15715-288">Válassza a **Model.Data2.Level1** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-288">Select **Model.Data2.Level1**.</span></span>
2. <span data-ttu-id="15715-289">Válassza a **Törlés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-289">Select **Delete**.</span></span>
3. <span data-ttu-id="15715-290">Válassza a **Model.Data2.Level2** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-290">Select **Model.Data2.Level2**.</span></span>
4. <span data-ttu-id="15715-291">Válassza a **Törlés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-291">Select **Delete**.</span></span>
5. <span data-ttu-id="15715-292">Válassza a **Model.Data2.Level3** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-292">Select **Model.Data2.Level3**.</span></span>
6. <span data-ttu-id="15715-293">Válassza a **Törlés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-293">Select **Delete**.</span></span>
7. <span data-ttu-id="15715-294">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-294">Select **Save**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="15715-295">Ugyanezt a **Model.Data2.Levels** számított mezőt többször is felhasználhatja a formátumtársításokban.</span><span class="sxs-lookup"><span data-stu-id="15715-295">You reused the same calculated field **Model.Data2.Levels** several times in format bindings.</span></span> <span data-ttu-id="15715-296">Sokkal könnyebb használni és karbantartani egyetlen számított mezőt,mint ugyanezt megtenni több hasonló mező esetében.</span><span class="sxs-lookup"><span data-stu-id="15715-296">It is much easier to use and maintain a single calculated field instead of doing this for multiple similar fields.</span></span>

8. <span data-ttu-id="15715-297">Zárja be a **Formátumtervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="15715-297">Close the **Format designer** page.</span></span>

## <a name="complete-adjusted-version-of-a-derived-format"></a><span data-ttu-id="15715-298">Származtatott formátum korrigált változatának befejezése</span><span class="sxs-lookup"><span data-stu-id="15715-298">Complete adjusted version of a derived format</span></span>

1. <span data-ttu-id="15715-299">A **Verziók** gyorslapon válassza az **Állapot módosítása** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-299">In the **Versions** FastTab, select **Change status**.</span></span>
2. <span data-ttu-id="15715-300">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-300">Select **Complete**.</span></span>

## <a name="export-completed-version-of-a-derived-format"></a><span data-ttu-id="15715-301">Származtatott formátum korrigált változatának exportálása</span><span class="sxs-lookup"><span data-stu-id="15715-301">Export completed version of a derived format</span></span>

1. <span data-ttu-id="15715-302">Válassza a **Formátum tanulja meg a paraméterezett meghívásokat (egyén)** formátumot a konfigurációs fában.</span><span class="sxs-lookup"><span data-stu-id="15715-302">Select **Format to learn parameterized calls (custom)** format in the configurations tree.</span></span>
2. <span data-ttu-id="15715-303">A **Verziók** gyorslapon válassza ki a kész 1.1.1-es verziót.</span><span class="sxs-lookup"><span data-stu-id="15715-303">In the **Versions** FastTab, select the completed version 1.1.1.</span></span>
3. <span data-ttu-id="15715-304">**Árfolyam** kijelölése.</span><span class="sxs-lookup"><span data-stu-id="15715-304">Select **Exchange**.</span></span>
4. <span data-ttu-id="15715-305">Válassza ki az **Exportálás XML-fájlként** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-305">Select **Export as XML file**.</span></span>
5. <span data-ttu-id="15715-306">A letöltött konfiguráció tárolása helyben, XML-formátumban.</span><span class="sxs-lookup"><span data-stu-id="15715-306">Store the downloaded configuration locally, in XML format.</span></span>

## <a name="test-er-formats"></a><span data-ttu-id="15715-307">ER-formátumok tesztelése</span><span class="sxs-lookup"><span data-stu-id="15715-307">Test ER formats</span></span> 
<span data-ttu-id="15715-308">A kezdeti és a továbbfejlesztett ER formátumot futtathatja, hogy meggyőzpdjön arról, hogy a konfigurált paraméterezett számított mezők megfelelően működnek.</span><span class="sxs-lookup"><span data-stu-id="15715-308">You can run the initial and improved ER formats to make sure that configured parameterized calculated fields work properly.</span></span>

### <a name="import-er-configurations"></a><span data-ttu-id="15715-309">ER-konfigurációk importálása</span><span class="sxs-lookup"><span data-stu-id="15715-309">Import ER configurations</span></span>
<span data-ttu-id="15715-310">Az **RCS** típushoz tartozó ER-tároló használatával importálhatja az áttekintett konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="15715-310">You can import reviewed configurations from RCS by using the ER repository of the **RCS** type.</span></span> <span data-ttu-id="15715-311">Ha már elvégezte az [Elektronikus jelentéskészítési konfigurációkat importálása a Regulatory Configuration Service szolgáltatásból](rcs-download-configurations.md) lépéseit, használja a konfigurált ER-tárolót, a korábban tárgyalt konfigurációk importálásához környezetébe.</span><span class="sxs-lookup"><span data-stu-id="15715-311">If you already went through the steps in the topic, [Import Electronic reporting configurations from Regulatory Configuration Services](rcs-download-configurations.md), use the configured ER repository to import configurations discussed earlier in this topic to your environment.</span></span> <span data-ttu-id="15715-312">Máskülönben kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="15715-312">Otherwise, follow these steps:</span></span>

1. <span data-ttu-id="15715-313">Válassza ki a **DEMF** vállalatot és az alapértelmezett irányítópulton válassza az **Elektronikus jelentéskészítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-313">Select the **DEMF** company and on the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="15715-314">Válassza a **Jelentéskészítési konfigurációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-314">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="15715-315">A letöltött konfigurációkat importálja a Microsoft letöltőközpontból a sorrendben: adatmodell, metaadatok, modell-leképezés, formátum.</span><span class="sxs-lookup"><span data-stu-id="15715-315">Import the configurations from Microsoft Download Center in the following sequence: data model, model mapping, format.</span></span> <span data-ttu-id="15715-316">Hajtsa végre a következő lépéseket mindegyik ER-konfiguráció esetében:</span><span class="sxs-lookup"><span data-stu-id="15715-316">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="15715-317">Válassza az **Átváltás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-317">Select **Exchange.**</span></span>
    2. <span data-ttu-id="15715-318">Kattintson a **Betöltés XML-fájlból** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="15715-318">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="15715-319">Kattintson a **Tallózás** gombra, a megfelelő, XML-formátumú fájl kiválasztásához a szükséges ER-konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="15715-319">Select **Browse** to select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="15715-320">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-320">Select **OK**.</span></span>

4. <span data-ttu-id="15715-321">Importálja az exportált RCS befejezett 1.1.1. verzióját a **Formátum tanulja meg a paraméterezett meghívásokat** formátumából:</span><span class="sxs-lookup"><span data-stu-id="15715-321">Import the exported from RCS completed version 1.1.1 of the **Format to learn parameterized calls (custom)** format:</span></span>

    1. <span data-ttu-id="15715-322">Válassza az **Átváltás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-322">Select **Exchange.**</span></span>
    2. <span data-ttu-id="15715-323">Kattintson a **Betöltés XML-fájlból** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="15715-323">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="15715-324">A **Tallózás** gombra kattintva kiválaszthatja a **Paraméterezett hívások tanulási formátuma (egyéni)** fájlt XML-formátumban.</span><span class="sxs-lookup"><span data-stu-id="15715-324">Select **Browse** to select the locally stored **Format to learn parameterized calls (custom)** file in XML format.</span></span>
    4. <span data-ttu-id="15715-325">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="15715-325">Select **OK**.</span></span>

### <a name="run-er-formats"></a><span data-ttu-id="15715-326">ER formátumok futtatása</span><span class="sxs-lookup"><span data-stu-id="15715-326">Run ER formats</span></span>

1. <span data-ttu-id="15715-327">A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-327">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="15715-328">Válasza ki a **Formátum paraméterezett hívások tanulásához elemet**.</span><span class="sxs-lookup"><span data-stu-id="15715-328">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="15715-329">Válassza a **Futtatás** parancsot a legfelső menüszalagon.</span><span class="sxs-lookup"><span data-stu-id="15715-329">Select **Run** on the top-most ribbon.</span></span>
4. <span data-ttu-id="15715-330">Mentse el a helyileg előállított kimenetet.</span><span class="sxs-lookup"><span data-stu-id="15715-330">Save the locally generated output.</span></span>
5. <span data-ttu-id="15715-331">Válassza ki a **Paraméterezett hívások tanulási formátuma (egyéni)** elemet.</span><span class="sxs-lookup"><span data-stu-id="15715-331">Select the **Format to learn parameterized calls (custom)** item.</span></span>
6. <span data-ttu-id="15715-332">Válassza a **Futtatás** parancsot a legfelső menüszalagon.</span><span class="sxs-lookup"><span data-stu-id="15715-332">Select **Run** on the top-most ribbon.</span></span>
7. <span data-ttu-id="15715-333">Mentse el az előállított kimenetet helyben.</span><span class="sxs-lookup"><span data-stu-id="15715-333">Save the generated output locally.</span></span> 
8. <span data-ttu-id="15715-334">A generált kimenetek tartalmának összehasonlítása.</span><span class="sxs-lookup"><span data-stu-id="15715-334">Compare the contents of the generated outputs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="15715-335">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="15715-335">Additional resources</span></span>
[<span data-ttu-id="15715-336">Képletszerkesztő az Elektronikus jelentéskészítésben</span><span class="sxs-lookup"><span data-stu-id="15715-336">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
