---
title: ER-konfigurációk tervezése az előállított fájlokban található bájtsorrendjelző karakterek elrejtéséhez
description: Ez a témakör bemutatja, hogyan konfigurálhat elektronikus jelentés (ER) formátumot olyan jelentések létrehozásához, amelyek elrejtik a bájtsorrendjelző (BOM) karaktereket.
author: NickSelin
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
ms.openlocfilehash: 9fabc308b1b0682c6fdce3e81e7335417846bebd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743533"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a>ER-konfigurációk tervezése az előállított fájlokban található bájtsorrendjelző karakterek elrejtéséhez

[!include [banner](../includes/banner.md)]

[Elektronikus jelentési (ER)](general-electronic-reporting.md) [megoldást](er-quick-start1-new-solution.md) tervezhet kimenő dokumentumok készítéséhez. A dokumentumok szöveges vagy XML-fájlként való létrehozásához a megoldásnak tartalmaznia kell egy ER [konfigurációt](general-electronic-reporting.md#Configuration), amely tartalmaz egy [formátum](general-electronic-reporting.md#FormatComponentOutbound) összetevőt. A generált fájlokban szereplő karakterkészlet [karakterkódolásának](https://docs.microsoft.com/windows/win32/intl/character-sets) megadásához az ER-formátumnak tartalmaznia kell a **Közös\\Fájl** formátumelemet. Az ER-formátum összetevő konfigurálásakor meg kell nyitnia a létrehozott ER-konfiguráció [vázlat](general-electronic-reporting.md#component-versioning) verzióját az ER-formátumtervezőben, és hozzá kell adnia a **Közös\\Fájl** elemet. A **Kódolás** mezőben adja meg a futásidőben generált kimenő fájlok kódolását ezzel az összetevővel.

> [!NOTE]
> Ha a formátum hibás kódolási nevet tartalmaz, akkor a rendszer hibát jelez, amikor menti a formátum beállításainak módosításait.

![Gyökérelem hozzáadása a Formátumtervező oldalon](./media/er-suppress-bom-characters-image1.gif)

Ha az **UTF-8**, **UTF-16** vagy **UTF-32** kódolást adja meg, elérhetővé válik az **Bájtsorrendjelző karakterek elrejtése** beállítás. A beállítást **Igen** értékre állítva elrejti a [bájtsorrendjelző (BOM) karaktereket](https://docs.microsoft.com/globalization/encoding/byte-order-mark) a kimenő fájlokban, amelyek futásidőben jönnek létre a szerkeszthető ER-formátum futtatásakor.

> [!NOTE]
> Ha üresen hagyja a **Kódolás** mezőt, az alapértelmezett **UTF-8** kódolás kerül használatra.

![A Bájtsorrendjelző karakterek elrejtése beállítás megadása a a Formátumtervező lapon](./media/er-suppress-bom-characters-image2.gif)

A funkció futásidőben való áttekintéséhez a megfelelő eljárást kell végrehajtani. Például a következő témakör lépéseit kell végrehajtani: [Az XML-elemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-xml-element.md). Miután befejezte a lépéseket a témakör [Módosítsa úgy a formátumot, hogy a számítás alapja a létrejövő kimenet legyen](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) szakaszában, kövesse ezeket a további lépéseket.

1. Adja meg az UTF-kódolást:

    1. Válassza a **Közös\\Fájl** típusú **Jelentés** elemet.
    2. A **Kódolás** mezőben adja meg az **UTF-8** kódolást.

2. BOM-karaktert tartalmazó XML-fájl létrehozása:

    1. Állítsa **Nem** értékre a **Bájtsorrendjelző karakterek elrejtése** beállítást a BOM-karakterek generált XML-fájlokban való szerepeltetéséhez.
    2. Hajtsa végre a lépéseket [Az XML-elemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-xml-element.md) témakör [Az összesítő XML-elem végrehajtásának elhalasztása, hogy a kiszámított összeg használatban legyen](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) szakaszában, és mentse a generált fájlt **SampleXmlReport.xml** néven.

3. BOM-karaktert nem tartalmazó XML-fájl létrehozása:

    1. Állítsa **Igen** értékre a **Bájtsorrendjelző karakterek elrejtése** beállítást a BOM-karakterek generált XML-fájlokból való mellőzéséhez.
    2. Hajtsa végre a lépéseket [Az XML-elemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-xml-element.md) témakör [Az összesítő XML-elem végrehajtásának elhalasztása, hogy a kiszámított összeg használatban legyen](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) szakaszában, és mentse a generált fájlt **SampleXmlReport (1).xml** néven.

4. Hasonlítsa össze a generált fájlokat egy fájl-összehasonlítási segédprogramban.

    Az első eltérés, amit észre fog venni, a fájl fejlécében van. A SampleXmlReport.xml fájl egy BOM-karaktert tartalmaz, míg a SampleXmlReport (1).xml fájl nem.

    ![Generált fájlok összehasonlítása egy fájl-összehasonlítási segédprogrammal](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a>Lásd még

- [Az XML-elemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]