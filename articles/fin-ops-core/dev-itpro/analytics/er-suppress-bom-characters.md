---
title: ER-konfigurációk tervezése az előállított fájlokban található bájtsorrendjelző karakterek elrejtéséhez
description: Ez a témakör bemutatja, hogyan konfigurálhat elektronikus jelentés (ER) formátumot olyan jelentések létrehozásához, amelyek elrejtik a bájtsorrendjelző (BOM) karaktereket.
author: NickSelin
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9260db2edab75c9876ddf5af99bee4ff174c64e1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568973"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a><span data-ttu-id="037c7-103">ER-konfigurációk tervezése az előállított fájlokban található bájtsorrendjelző karakterek elrejtéséhez</span><span class="sxs-lookup"><span data-stu-id="037c7-103">Design ER configurations to suppress BOM characters in generated files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="037c7-104">[Elektronikus jelentési (ER)](general-electronic-reporting.md) [megoldást](er-quick-start1-new-solution.md) tervezhet kimenő dokumentumok készítéséhez.</span><span class="sxs-lookup"><span data-stu-id="037c7-104">You can design an [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md) to generate outgoing documents.</span></span> <span data-ttu-id="037c7-105">A dokumentumok szöveges vagy XML-fájlként való létrehozásához a megoldásnak tartalmaznia kell egy ER [konfigurációt](general-electronic-reporting.md#Configuration), amely tartalmaz egy [formátum](general-electronic-reporting.md#FormatComponentOutbound) összetevőt.</span><span class="sxs-lookup"><span data-stu-id="037c7-105">To generate the documents as text or XML files, the solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="037c7-106">A generált fájlokban szereplő karakterkészlet [karakterkódolásának](https://docs.microsoft.com/windows/win32/intl/character-sets) megadásához az ER-formátumnak tartalmaznia kell a **Közös\\Fájl** formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="037c7-106">To specify the [character encoding](https://docs.microsoft.com/windows/win32/intl/character-sets) that represents the set of characters in generated files, the ER format must contain the **Common\\File** format element.</span></span> <span data-ttu-id="037c7-107">Az ER-formátum összetevő konfigurálásakor meg kell nyitnia a létrehozott ER-konfiguráció [vázlat](general-electronic-reporting.md#component-versioning) verzióját az ER-formátumtervezőben, és hozzá kell adnia a **Közös\\Fájl** elemet.</span><span class="sxs-lookup"><span data-stu-id="037c7-107">To configure the ER format component, open the [draft](general-electronic-reporting.md#component-versioning) version of the ER configuration in the ER format designer, and add the **Common\\File** element.</span></span> <span data-ttu-id="037c7-108">A **Kódolás** mezőben adja meg a futásidőben generált kimenő fájlok kódolását ezzel az összetevővel.</span><span class="sxs-lookup"><span data-stu-id="037c7-108">In the **Encoding** field, specify the encoding of outbound files that are generated at runtime by using this component.</span></span>

> [!NOTE]
> <span data-ttu-id="037c7-109">Ha a formátum hibás kódolási nevet tartalmaz, akkor a rendszer hibát jelez, amikor menti a formátum beállításainak módosításait.</span><span class="sxs-lookup"><span data-stu-id="037c7-109">If the format contains an incorrect encoding name, an error is thrown when you save your changes to the format's settings.</span></span>

![Gyökérelem hozzáadása a Formátumtervező oldalon](./media/er-suppress-bom-characters-image1.gif)

<span data-ttu-id="037c7-111">Ha az **UTF-8**, **UTF-16** vagy **UTF-32** kódolást adja meg, elérhetővé válik az **Bájtsorrendjelző karakterek elrejtése** beállítás.</span><span class="sxs-lookup"><span data-stu-id="037c7-111">If you specify **UTF-8**, **UTF-16**, or **UTF-32** as the encoding, the **Suppress BOM characters** option becomes available.</span></span> <span data-ttu-id="037c7-112">A beállítást **Igen** értékre állítva elrejti a [bájtsorrendjelző (BOM) karaktereket](https://docs.microsoft.com/globalization/encoding/byte-order-mark) a kimenő fájlokban, amelyek futásidőben jönnek létre a szerkeszthető ER-formátum futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="037c7-112">Set this option to **Yes** to suppress [byte order mark (BOM) characters](https://docs.microsoft.com/globalization/encoding/byte-order-mark) in outbound files that are generated at runtime when the editable ER format is run.</span></span>

> [!NOTE]
> <span data-ttu-id="037c7-113">Ha üresen hagyja a **Kódolás** mezőt, az alapértelmezett **UTF-8** kódolás kerül használatra.</span><span class="sxs-lookup"><span data-stu-id="037c7-113">If you leave the **Encoding** field blank, the default **UTF-8** encoding is used.</span></span>

![A Bájtsorrendjelző karakterek elrejtése beállítás megadása a a Formátumtervező lapon](./media/er-suppress-bom-characters-image2.gif)

<span data-ttu-id="037c7-115">A funkció futásidőben való áttekintéséhez a megfelelő eljárást kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="037c7-115">To review the functionality at runtime, complete the appropriate procedure.</span></span> <span data-ttu-id="037c7-116">Például a következő témakör lépéseit kell végrehajtani: [Az XML-elemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-xml-element.md).</span><span class="sxs-lookup"><span data-stu-id="037c7-116">For example, complete the steps in the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic.</span></span> <span data-ttu-id="037c7-117">Miután befejezte a lépéseket a témakör [Módosítsa úgy a formátumot, hogy a számítás alapja a létrejövő kimenet legyen](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) szakaszában, kövesse ezeket a további lépéseket.</span><span class="sxs-lookup"><span data-stu-id="037c7-117">After you've completed the steps in the [Modify the format so that the calculation is based on generated output](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) section of that topic, follow these additional steps.</span></span>

1. <span data-ttu-id="037c7-118">Adja meg az UTF-kódolást:</span><span class="sxs-lookup"><span data-stu-id="037c7-118">Specify the UTF encoding:</span></span>

    1. <span data-ttu-id="037c7-119">Válassza a **Közös\\Fájl** típusú **Jelentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="037c7-119">Select the **Report** element of the **Common\\File** type.</span></span>
    2. <span data-ttu-id="037c7-120">A **Kódolás** mezőben adja meg az **UTF-8** kódolást.</span><span class="sxs-lookup"><span data-stu-id="037c7-120">In the **Encoding** field, specify the **UTF-8** encoding.</span></span>

2. <span data-ttu-id="037c7-121">BOM-karaktert tartalmazó XML-fájl létrehozása:</span><span class="sxs-lookup"><span data-stu-id="037c7-121">Generate an XML file that includes a BOM character:</span></span>

    1. <span data-ttu-id="037c7-122">Állítsa **Nem** értékre a **Bájtsorrendjelző karakterek elrejtése** beállítást a BOM-karakterek generált XML-fájlokban való szerepeltetéséhez.</span><span class="sxs-lookup"><span data-stu-id="037c7-122">Set the **Suppress BOM characters** option to **No** to include BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="037c7-123">Hajtsa végre a lépéseket [Az XML-elemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-xml-element.md) témakör [Az összesítő XML-elem végrehajtásának elhalasztása, hogy a kiszámított összeg használatban legyen](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) szakaszában, és mentse a generált fájlt **SampleXmlReport.xml** néven.</span><span class="sxs-lookup"><span data-stu-id="037c7-123">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport.xml**.</span></span>

3. <span data-ttu-id="037c7-124">BOM-karaktert nem tartalmazó XML-fájl létrehozása:</span><span class="sxs-lookup"><span data-stu-id="037c7-124">Generate an XML file that doesn't include a BOM character:</span></span>

    1. <span data-ttu-id="037c7-125">Állítsa **Igen** értékre a **Bájtsorrendjelző karakterek elrejtése** beállítást a BOM-karakterek generált XML-fájlokból való mellőzéséhez.</span><span class="sxs-lookup"><span data-stu-id="037c7-125">Set the **Suppress BOM characters** option to **Yes** to suppress BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="037c7-126">Hajtsa végre a lépéseket [Az XML-elemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-xml-element.md) témakör [Az összesítő XML-elem végrehajtásának elhalasztása, hogy a kiszámított összeg használatban legyen](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) szakaszában, és mentse a generált fájlt **SampleXmlReport (1).xml** néven.</span><span class="sxs-lookup"><span data-stu-id="037c7-126">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport (1).xml**.</span></span>

4. <span data-ttu-id="037c7-127">Hasonlítsa össze a generált fájlokat egy fájl-összehasonlítási segédprogramban.</span><span class="sxs-lookup"><span data-stu-id="037c7-127">In a file comparison utility, compare the generated files.</span></span>

    <span data-ttu-id="037c7-128">Az első eltérés, amit észre fog venni, a fájl fejlécében van.</span><span class="sxs-lookup"><span data-stu-id="037c7-128">The first difference that you will notice is in the file header.</span></span> <span data-ttu-id="037c7-129">A SampleXmlReport.xml fájl egy BOM-karaktert tartalmaz, míg a SampleXmlReport (1).xml fájl nem.</span><span class="sxs-lookup"><span data-stu-id="037c7-129">The SampleXmlReport.xml file contains a BOM character, where the SampleXmlReport (1).xml file doesn't.</span></span>

    ![Generált fájlok összehasonlítása egy fájl-összehasonlítási segédprogrammal](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a><span data-ttu-id="037c7-131">Lásd még</span><span class="sxs-lookup"><span data-stu-id="037c7-131">See also</span></span>

- [<span data-ttu-id="037c7-132">Az XML-elemek végrehajtásának elhalasztása az ER-formátumokban</span><span class="sxs-lookup"><span data-stu-id="037c7-132">Defer the execution of XML elements in ER formats</span></span>](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]