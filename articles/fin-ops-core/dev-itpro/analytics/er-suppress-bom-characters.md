---
title: ER-konfigurációk tervezése az előállított fájlokban található bájtsorrendjelző karakterek elrejtéséhez
description: Ez a cikk bemutatja, hogyan kell konfigurálni egy elektronikus jelentési (ER) formátumot olyan jelentések létrehozásához, amelyek nem tartalmaznak bájtrendelési jelölést (AJ-) karaktereket.
author: kfend
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: EROperationDesigner
ms.openlocfilehash: a2ea132b51f2f451fbe81a9c7869bea84bf4017a
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324019"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a>ER-konfigurációk tervezése az előállított fájlokban található bájtsorrendjelző karakterek elrejtéséhez

[!include [banner](../includes/banner.md)]

[Elektronikus jelentési (ER)](general-electronic-reporting.md) [megoldást](er-quick-start1-new-solution.md) tervezhet kimenő dokumentumok készítéséhez. A dokumentumok szöveg- vagy XML-fájlként való létrehozásához a megoldásnak tartalmaznia [kell](general-electronic-reporting.md#Configuration) egy ER-formátumösszetevőt tartalmazó ER-konfigurációt. A generált fájlokban szereplő karakterkészlet [karakterkódolásának](/windows/win32/intl/character-sets) megadásához az ER-formátumnak tartalmaznia kell a **Közös\\Fájl** formátumelemet. Az ER-formátum összetevő konfigurálásán nyissa meg az ER-konfiguráció vázlatverzióját az ER-formátumtervezőben, és **adja hozzá a Közös\\ fájl** elemet. A **Kódolás** mezőben adja meg a futásidőben generált kimenő fájlok kódolását ezzel az összetevővel.

> [!NOTE]
> Ha a formátum hibás kódolási nevet tartalmaz, akkor a rendszer hibát jelez, amikor menti a formátum beállításainak módosításait.

![Gyökérelem hozzáadása a Formátumtervező oldalon.](./media/er-suppress-bom-characters-image1.gif)

Ha az **UTF-8**, **UTF-16** vagy **UTF-32** kódolást adja meg, elérhetővé válik az **Bájtsorrendjelző karakterek elrejtése** beállítás. A beállítást **Igen** értékre állítva elrejti a [bájtsorrendjelző (BOM) karaktereket](/globalization/encoding/byte-order-mark) a kimenő fájlokban, amelyek futásidőben jönnek létre a szerkeszthető ER-formátum futtatásakor.

> [!NOTE]
> Ha üresen hagyja a **Kódolás** mezőt, az alapértelmezett **UTF-8** kódolás kerül használatra.

![A Bájtsorrendjelző karakterek elrejtése beállítás megadása a Formátumtervező lapon.](./media/er-suppress-bom-characters-image2.gif)

A funkció futásidőben való áttekintéséhez a megfelelő eljárást kell végrehajtani. Például az ER formátumokban található [XML-elemek végrehajtásának elhalasztása cikk lépéseit kell](er-defer-xml-element.md) végrehajtani. Miután befejezte a lépéseket a [Formátum](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) módosítása szakaszban, hogy a számítás a cikk generált kimeneti szakaszán alapul, kövesse ezeket a további lépéseket.

1. Adja meg az UTF-kódolást:

    1. Válassza a **Közös\\Fájl** típusú **Jelentés** elemet.
    2. A **Kódolás** mezőben adja meg az **UTF-8** kódolást.

2. BOM-karaktert tartalmazó XML-fájl létrehozása:

    1. Állítsa **Nem** értékre a **Bájtsorrendjelző karakterek elrejtése** beállítást a BOM-karakterek generált XML-fájlokban való szerepeltetéséhez.
    2. Az összesítő XML-elem [halasztás](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) végrehajtása során a rendszer a kiszámított összesítést használja fel az XML-elemek ER-formátumban való végrehajtásának elhalasztása című [cikkében,](er-defer-xml-element.md) és mentse a generált fájlt MintaXmlReport.xml **fájlként.**

3. BOM-karaktert nem tartalmazó XML-fájl létrehozása:

    1. Állítsa **Igen** értékre a **Bájtsorrendjelző karakterek elrejtése** beállítást a BOM-karakterek generált XML-fájlokból való mellőzéséhez.
    2. [Az összesítő XML-elem](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used)[halasztás végrehajtása során kövesse el a lépéseket, hogy a kiszámított végösszeget használja a rendszer az XML-elemek ER-formátumban való végrehajtásának elhalasztása című](er-defer-xml-element.md) cikkben, **és mentse a generált fájlt SampleXmlReport (1.xml**) formátumban.

4. Hasonlítsa össze a generált fájlokat egy fájl-összehasonlítási segédprogramban.

    Az első eltérés, amit észre fog venni, a fájl fejlécében van. A SampleXmlReport.xml fájl egy BOM-karaktert tartalmaz, míg a SampleXmlReport (1).xml fájl nem.

    ![Generált fájlok összehasonlítása egy fájl-összehasonlítási segédprogrammal.](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a>Lásd még

- [Az XML-elemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
