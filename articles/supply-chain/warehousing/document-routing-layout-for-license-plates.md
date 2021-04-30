---
title: Dokumentumirányítás elrendezés azonosítótábla-címkékhez
description: Ez a témakör azt mutatja be, hogyan lehet használni a formázási metódusokat értékek nyomtatásához a címkékre.
author: perlynne
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 6b5bf6815f225dcca8f9e89e2c85942ce8a2ccd7
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907987"
---
# <a name="document-routing-layout-for-license-plate-labels"></a><span data-ttu-id="ad889-103">Dokumentumirányítás elrendezés azonosítótábla-címkékhez</span><span class="sxs-lookup"><span data-stu-id="ad889-103">Document routing layout for license plate labels</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ad889-104">A dokumentumirányítási elrendezés határozza meg az azonosítótábla-címkék elrendezését, valamint a rájuk nyomtatandó adatokat.</span><span class="sxs-lookup"><span data-stu-id="ad889-104">The document routing layout defines the layout of license plate labels, and the data that is printed on them.</span></span> <span data-ttu-id="ad889-105">A nyomtatási műveletek aktiválási pontjait a mobileszköz menüelemeiben és a munkasablonok modulban állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="ad889-105">You configure the printing trigger points when you set up mobile device menu items and work templates.</span></span>

<span data-ttu-id="ad889-106">Egy tipikus esetben a raktári befogadó adminisztrátorok közvetlenül a fogadó területre érkezett raklapok tartalmának rögzítése után azonnal kinyomtatják az azonosítótábla-címkéket.</span><span class="sxs-lookup"><span data-stu-id="ad889-106">In a typical scenario, warehouse receiving clerks print license plate labels immediately after they record the contents of pallets that arrive in the receiving area.</span></span> <span data-ttu-id="ad889-107">A fizikai címkék a raklapokra lesznek rögzítve.</span><span class="sxs-lookup"><span data-stu-id="ad889-107">The physical labels are applied to the pallets.</span></span> <span data-ttu-id="ad889-108">Ezt követően a következő betárolási műveletek során és a kimenő kitárolási műveletek során is használhatók ellenőrzéshez.</span><span class="sxs-lookup"><span data-stu-id="ad889-108">They can then be used for validation as part of the put-away process that follows and future outbound picking operations.</span></span>

<span data-ttu-id="ad889-109">Rendkívül összetett címkéket nyomtathat, feltéve, hogy a nyomtatóeszköz értelmezni tudja a ráküldött szöveget.</span><span class="sxs-lookup"><span data-stu-id="ad889-109">You can print highly complex labels, provided that the printing device can interpret the text that is sent to it.</span></span> <span data-ttu-id="ad889-110">Például a Zebra Programming Language (ZPL) egy vonalkódot tartalmazó elrendezése a következő példához hasonlíthat.</span><span class="sxs-lookup"><span data-stu-id="ad889-110">For example, a Zebra Programming Language (ZPL) layout that includes a bar code might resemble the following example.</span></span>

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

<span data-ttu-id="ad889-111">A címke nyomtatási folyamatának részeként a példa szövegét `$LicensePlateId$` egy adatértékkel helyettesíti a program.</span><span class="sxs-lookup"><span data-stu-id="ad889-111">As part of the label printing process, the text `$LicensePlateId$` in this example will be replaced with a data value.</span></span>

<span data-ttu-id="ad889-112">A kinyomtatni kívánt értékek megtekintéséhez nyissa meg a **Raktárkezelési \> Lekérdezéseket és a jelentések \> Azonosítótábla-címkék** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ad889-112">To see the values that will be printed, go to **Warehouse management \> Inquiries and reports \> License plate labels**.</span></span>

<span data-ttu-id="ad889-113">Számos széles körben elérhető címke-létrehozási eszköz segít a szöveg formázásában a címkék elrendezéséhez.</span><span class="sxs-lookup"><span data-stu-id="ad889-113">Several widely available label generation tools can help you format the text for the label layout.</span></span> <span data-ttu-id="ad889-114">Számos ilyen eszköz támogatja a `$FieldName$` formátumot.</span><span class="sxs-lookup"><span data-stu-id="ad889-114">Many of these tools support the `$FieldName$` format.</span></span> <span data-ttu-id="ad889-115">Mindemellett a Microsoft Dynamics 365 Supply Chain Management speciális formázási logikát használ a dokumentumirányítási elrendezés mező-hozzárendelésének részeként.</span><span class="sxs-lookup"><span data-stu-id="ad889-115">In addition, Microsoft Dynamics 365 Supply Chain Management uses special formatting logic as part of the field mapping for the document routing layout.</span></span>

## <a name="turn-on-this-feature-for-your-system"></a><span data-ttu-id="ad889-116">A funkció bekapcsolása a rendszerhez</span><span class="sxs-lookup"><span data-stu-id="ad889-116">Turn on this feature for your system</span></span>

<span data-ttu-id="ad889-117">Ha a rendszer még nem tartalmazza az ebben a témakörben leírt funkciókat, lépjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőségre, és a kapcsolja be az *Engedélyezett azonosítótáblacímke-elrendezések* funkciót.</span><span class="sxs-lookup"><span data-stu-id="ad889-117">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the *Enhanced license plate label layouts* feature.</span></span>

## <a name="custom-number-formats"></a><span data-ttu-id="ad889-118">Egyéni számformátumok</span><span class="sxs-lookup"><span data-stu-id="ad889-118">Custom number formats</span></span>

<span data-ttu-id="ad889-119">Testreszabhatja a numerikus mezőértékek formátumát, amely a következő formátumú kódokkal van kinyomtatva.</span><span class="sxs-lookup"><span data-stu-id="ad889-119">You can customize the formatting of numerical field values that are printed by using codes that have the following format.</span></span>

```dos
$FieldName:FormatString$
```

<span data-ttu-id="ad889-120">Itt találja a formátum magyarázatát:</span><span class="sxs-lookup"><span data-stu-id="ad889-120">Here is an explanation of this format:</span></span>

- <span data-ttu-id="ad889-121">`FieldName` az adatmező neve (például **Mennyiség**).</span><span class="sxs-lookup"><span data-stu-id="ad889-121">`FieldName` is the name of the data field (such as **Qty**).</span></span>
- <span data-ttu-id="ad889-122">`FormatString` azt határozza meg, hogy hogyan kell kinyomtatni az adatokat.</span><span class="sxs-lookup"><span data-stu-id="ad889-122">`FormatString` defines how the data must be printed.</span></span>

<span data-ttu-id="ad889-123">A következő példák azt mutatják be, hogyan lehet testreszabni a munkamennyiség (**Mennyiség**) mezőt:</span><span class="sxs-lookup"><span data-stu-id="ad889-123">The following examples show how you can customize the work quantity (**Qty**) field:</span></span>

- <span data-ttu-id="ad889-124">Ha azt szeretné, hogy a program mindig négy számjegyet jelenítse meg (nullák használatával helyőrzőként), használja `$Qty:0000$` értéket.</span><span class="sxs-lookup"><span data-stu-id="ad889-124">To always show four digits (by using zeros as placeholders), use `$Qty:0000$`.</span></span> <span data-ttu-id="ad889-125">Ha például a mennyiség 10, akkor a címkén „0010” jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="ad889-125">For example, if the quantity is 10, the label will show "0010."</span></span>
- <span data-ttu-id="ad889-126">Ha mindig két tizedesjegyet kíván megjeleníteni, használja a `$Qty:0.00$` értéket.</span><span class="sxs-lookup"><span data-stu-id="ad889-126">To always show two decimal places, use `$Qty:0.00$`.</span></span> <span data-ttu-id="ad889-127">Ha például a mennyiség 10, akkor a címkén „10.00” jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="ad889-127">For example, if the quantity is 10, the label will show "10.00."</span></span>

<span data-ttu-id="ad889-128">A rendelkezésre álló számformátum-karakterláncok teljes listája az [Egyéni numerikus formátumú karakterláncok](/dotnet/standard/base-types/custom-numeric-format-strings) című témakörben olvasható.</span><span class="sxs-lookup"><span data-stu-id="ad889-128">For a complete list of the available number format strings, see [Custom numeric format strings](/dotnet/standard/base-types/custom-numeric-format-strings).</span></span>

## <a name="custom-string-formats"></a><span data-ttu-id="ad889-129">Egyéni karakterlánc-formátumok</span><span class="sxs-lookup"><span data-stu-id="ad889-129">Custom string formats</span></span>

<span data-ttu-id="ad889-130">A karakterlánc első karaktereit a következő mező és a formátumkód használatával lehet eltávolítani.</span><span class="sxs-lookup"><span data-stu-id="ad889-130">You can remove the first characters of a string by using the following field and format code.</span></span>

```dos
$FieldName:#..$
```

<span data-ttu-id="ad889-131">Itt a `#` a kihagyandó karakterek számár határozza meg.</span><span class="sxs-lookup"><span data-stu-id="ad889-131">Here, `#` specifies the number of characters to skip.</span></span> <span data-ttu-id="ad889-132">Például Konténer sorozatszámot (SSCC) szeretne nyomtatni, amely nem tartalmazza az első két karaktert, használja a `$LicensePlateId:2..$` értéket.</span><span class="sxs-lookup"><span data-stu-id="ad889-132">For example, to print a Serial Shipping Container Code (SSCC) license plate number that doesn't include the first two characters, use `$LicensePlateId:2..$`.</span></span> <span data-ttu-id="ad889-133">Ebben az esetben a 0011111111111222221 azonosítótábla-szám „11111111111222221” értékkel lesz nyomtatva.</span><span class="sxs-lookup"><span data-stu-id="ad889-133">In this case, the license plate number 0011111111111222221 will be printed as "11111111111222221."</span></span>

## <a name="custom-datetime-formats"></a><span data-ttu-id="ad889-134">Egyéni dátum-/időformátumok</span><span class="sxs-lookup"><span data-stu-id="ad889-134">Custom date/time formats</span></span>

<span data-ttu-id="ad889-135">A következő példa bemutatja, hogyan lehet szabályozni a dátumok nyomtatásához használt formátumot.</span><span class="sxs-lookup"><span data-stu-id="ad889-135">The following example shows how you can control the format that is used to print dates.</span></span>

```dos
$PrintedDate:dd-MM-yyyy$
```

<span data-ttu-id="ad889-136">Ebben a példában a 2020. április 30-i dátum „30-04-2020” értékkel lesz nyomtatva.</span><span class="sxs-lookup"><span data-stu-id="ad889-136">In this example, the date April 30, 2020, will be printed as "30-04-2020."</span></span>

<span data-ttu-id="ad889-137">A rendelkezésre álló dátum-/időformátumok teljes listája az [Egyéni dátum- és időformátum karakterláncok](/dotnet/standard/base-types/custom-date-and-time-format-strings) című témakörben olvasható.</span><span class="sxs-lookup"><span data-stu-id="ad889-137">For a complete list of the available date/time formats, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="print-individual-lines-from-multiline-data"></a><span data-ttu-id="ad889-138">Különálló sorok nyomtatása a többsoros adatokból</span><span class="sxs-lookup"><span data-stu-id="ad889-138">Print individual lines from multiline data</span></span>

<span data-ttu-id="ad889-139">Ha egy adatmező több sort tartalmaz (azaz a sortöréssel elválasztott sorokat), akkor a következő formátummal nyomtathat egy adott sort.</span><span class="sxs-lookup"><span data-stu-id="ad889-139">If a data field contains multiple lines (that is, lines that are separated by line breaks), you can print an individual line by using the following format.</span></span>

```dos
$FieldName[#]$
```

<span data-ttu-id="ad889-140">Itt `#` annak a sornak a száma, amelyet ki szeretne nyomtatni.</span><span class="sxs-lookup"><span data-stu-id="ad889-140">Here, `#` is the line number that you want to print.</span></span> <span data-ttu-id="ad889-141">(Az első sorhoz az 1 értéket használja)</span><span class="sxs-lookup"><span data-stu-id="ad889-141">(Use 1 for the first line.)</span></span>

<span data-ttu-id="ad889-142">A rendszere például egy olyan `AdditionalAddress` mezőt tartalmaz, amely a következő többsoros címet tárolja:</span><span class="sxs-lookup"><span data-stu-id="ad889-142">For example, your system has an `AdditionalAddress` field that stores the following multiline address:</span></span>

<span data-ttu-id="ad889-143">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="ad889-143">Contoso Inc.</span></span>  
<span data-ttu-id="ad889-144">123 Utcanév</span><span class="sxs-lookup"><span data-stu-id="ad889-144">123 Street Name</span></span>  
<span data-ttu-id="ad889-145">Valamilyen város, Valamilyen állam</span><span class="sxs-lookup"><span data-stu-id="ad889-145">Some City, Some State</span></span>

<span data-ttu-id="ad889-146">Ezt a címet soronként a következő kódokat használva nyomtathatja ki.</span><span class="sxs-lookup"><span data-stu-id="ad889-146">You can print this address, one line at a time, by using the following codes.</span></span>

| <span data-ttu-id="ad889-147">Kód</span><span class="sxs-lookup"><span data-stu-id="ad889-147">Code</span></span> | <span data-ttu-id="ad889-148">A nyomtatott szöveg</span><span class="sxs-lookup"><span data-stu-id="ad889-148">Text that is printed</span></span> |
|---|---|
| `$AdditionalAddress[1]$` | <span data-ttu-id="ad889-149">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="ad889-149">Contoso Inc.</span></span> |
| `$AdditionalAddress[2]$` | <span data-ttu-id="ad889-150">123 Utcanév</span><span class="sxs-lookup"><span data-stu-id="ad889-150">123 Street Name</span></span> |
| `$AdditionalAddress[3]$` | <span data-ttu-id="ad889-151">Valamilyen város, Valamilyen állam</span><span class="sxs-lookup"><span data-stu-id="ad889-151">Some City, Some State</span></span> |

## <a name="print-and-format-from-a-display-method"></a><span data-ttu-id="ad889-152">Nyomtatás és formázás egy megjelenítési módból</span><span class="sxs-lookup"><span data-stu-id="ad889-152">Print and format from a display method</span></span>

<span data-ttu-id="ad889-153">A következő formátummal nyomtathat egy megjelenítési módból.</span><span class="sxs-lookup"><span data-stu-id="ad889-153">You can print from a display method by using the following format.</span></span>

```dos
$DisplayMethod()$
```

<span data-ttu-id="ad889-154">Ez a formátum kombinálható a témakör korábbi részében ismertetett egyéb típusokkal is.</span><span class="sxs-lookup"><span data-stu-id="ad889-154">You can combine this format with other types that were described earlier in this topic.</span></span> <span data-ttu-id="ad889-155">Például van egy `DisplayListOfItemsNumbers()` névvel ellátott megjelenítési módja, és ki szeretné nyomtatni a mód első cikkszámát.</span><span class="sxs-lookup"><span data-stu-id="ad889-155">For example, you have a display method that is named `DisplayListOfItemsNumbers()`, and you want to print the first item number of this method.</span></span> <span data-ttu-id="ad889-156">Ebben az esetben a következő kódot használhatja.</span><span class="sxs-lookup"><span data-stu-id="ad889-156">In this case, you can use the following code.</span></span>

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a><span data-ttu-id="ad889-157">A címkenyomtatással kapcsolatos további információk</span><span class="sxs-lookup"><span data-stu-id="ad889-157">More information about how to print labels</span></span>

<span data-ttu-id="ad889-158">A címkék beállításával és nyomtatásával kapcsolatos további tudnivalókat lásd az [Azonosítótábla-címke nyomtatásának engedélyezése](tasks/license-plate-label-printing.md) című témakört.</span><span class="sxs-lookup"><span data-stu-id="ad889-158">For more information about how to set up and print labels, see [Enable license plate label printing](tasks/license-plate-label-printing.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]