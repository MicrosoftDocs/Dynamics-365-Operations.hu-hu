---
title: Elektronikus jelentésekben létrehozott nagyméretű dokumentumok tömörítése
description: Ez a témakör azt mutatja be, hogyan lehet tömöríteni olyan nagyméretű dokumentumokat, amelyeket Elektronikus jelentéskészítési (ER) formátumban hoztak létre.
author: NickSelin
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERFormatDestinationTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 7ef8f730f2e207a8fd28c2bf5167d14f57d6c607314bfc48d4358a59d3ef5c43
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718599"
---
# <a name="compress-large-documents-that-are-generated-in-electronic-reporting"></a>Elektronikus jelentésekben létrehozott nagyméretű dokumentumok tömörítése 

[!include [banner](../includes/banner.md)]

Az [Elektronikus jelentéskészítési (ER) keretrendszer](general-electronic-reporting.md) segítségével konfigurálhatja azt a megoldást, amely a tranzakciós adatokat a kimenő dokumentumok előállításához kérdezi le. Ez a létrehozott dokumentum elég nagy lehet. Ha ilyen típusú dokumentumot hoz létre, akkor azt az [Application Object Server (AOS)](../dev-tools/access-instances.md#location-of-packages-source-code-and-other-aos-configurations) kiszolgáló memóriájával tárolhatja. Valamikor le kell töltenie a dokumentumot a Microsoft Dynamics 365 Finance alkalmazásból. Jelenleg az ER-ben létrehozott dokumentum mérete legfeljebb 2 gigabájt (GB) lehet. Ezenkívül a Finance jelenleg 1 GB-ra [korlátozza](https://fix.lcs.dynamics.com/Issue/Details?kb=4569432&bugId=453907&dbType=3) a letöltött fájlok méretét. Éppen ezért konfigurálnia kell egy olyan ER-megoldást, amely csökkenti annak a valószínűségét, hogy túllépi ezeket a korlátozásokat, és hogy a **Adatfolyam túl hosszú volt** vagy **Az aritmetikai művelet kivétele során túlcsordulás vagy alulcsordulás következett be** kivételt kapjon.

Ha konfigurál egy megoldást, akkor úgy állíthatja be a saját ER-formátumát a Műveletek tervezőben, hogy hozzáadja a **Mappa** egy gyökérelemét, és tömöríti a saját beágyazott elemei által előállított valamelyik tartalmat. A tömörítés „pont időben” működik, így a csúcs memóriahasználat, és a letöltendő fájl mérete csökkenthető.

> [!NOTE]
> A fájltömörítés további CPU-százalékot vesz igénybe.

Ha további tájékoztatást szeretne erről a megközelítésről, végezze el a példafeladatot ebben a témakörben.

## <a name="example-compress-an-outbound-document"></a>Példa: Kimenő dokumentum tömörítése

Ez a példa azt mutatja be, hogyan tudja a **Rendszergazda** vagy az **Elektronikus jelentéskészítési funkcionális tanácsadó** szerepkörhöz rendelt felhasználó konfigurálni az ER-formátumot a létrejövő dokumentumok tömörítéséhez.

### <a name="prerequisites"></a>Előfeltételek

Mielőtt teljesítené az ebben a témakörben ismertetett eljárásokat, meg kell tennie a következő lépéseket:

1. [Konfigurációszolgáltató aktiválása](er-defer-xml-element.md#activate-a-configuration-provider).
2. [Minta ER-konfigurációk importálása](er-defer-xml-element.md#import-the-sample-er-configurations).
3. [Tekintse át az importált formátumot](er-defer-xml-element.md#review-the-imported-format).

> [!NOTE]
> A formátum szerkezete jelenleg a **Fájltípus** **Jelentés** elemével kezdődik, és XML-elemeket tartalmaz. Ezért a kimenő dokumentumok XML-formátumban jönnek létre, és a rendszer nem fogja őket tömöríteni.

### <a name="generate-an-er-format-to-get-an-uncompressed-document"></a>Hozzon létre egy ER-formátumot a tömörítetlen dokumentum beszerzéséhez

1. [Importált formátum futtatása](er-defer-xml-element.md#run-the-imported-format).
2. Figyelje meg, hogy a létrejövő XML-formátumú dokumentum mérete 3 kilobájt (KB).

    ![A tömörítetlen kimenő dokumentum előzetes verziója.](./media/er-compress-outbound-files1.png)

### <a name="modify-the-format-to-compress-the-generated-output"></a>A létrehozott kimenet tömörítéséhez használandó formátum módosítása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon található konfigurációk fájában bontsa ki a **Model to learn deferred elements** elemet.
3. Válassza ki **Format to learn deferred XML elements** konfigurációt.
4. A formátumszerkezet módosításához válassza a **Tervező** elemet.
5. A **Formátumtervező** oldal **Formátum** lapján válassza ki a **Gyökér hozzáadása** elemet a gyokérformátum hozzáadásához.
6. A **Hozzáadás** párbeszédpanelen válassza a **Közös \\Mappa** elemet.
7. Az új gyökérelem hozzáadásának jóváhagyásához kattintson az **OK** lehetőségre.
8. Válassza a **Mentés** lehetőséget.

> [!NOTE]
> A formátum szerkezete a **Mappa** típusának elemétől kezdődik. Ez az elem a kimenetet tömörített (zip) fájlként fogja létrehozni. Amikor egy **Jelentés** elemével létrehozott dokumentumot egy kimenő zip-fájlként helyezik el, majd tömörítik a tartalmát, hogy csökkentsék a kimenő fájl méretét.

### <a name="generate-an-er-format-to-get-a-compressed-document"></a>Hozzon létre egy ER-formátumot a tömörített dokumentum beszerzéséhez

1. A **Formátumtervező** oldalon válassza a **Futtatás** elemet.
2. Töltse le a webböngészőből a felkínált zip-fájlt, és nyissa meg ellenőrzésre.
3. Figyelje meg, hogy a létrejövő ZIP-formátumú dokumentum mérete 1 KB.

    > [!NOTE] 
    > A zip-fájl által birtokolt XML-fájl tömörítési aránya 87 százalék. A tömörítési arány a tömörített adatoktól függ.

    ![A tömörített kimenő dokumentum előzetes verziója.](./media/er-compress-outbound-files2.png)

> [!NOTE]
> Ha be van konfigurálva a kimeneti ER [cél](electronic-reporting-destinations.md) a kimenetet létrehozó formátumelemhez (ebben a példában a **Jelentés** elem), akkor kihagyják a kimenet tömörítését.

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)

[Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)

[Az XML-elemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]