---
title: ER-formátum megtervezése a sorok ugyanazon az Excel-lapon való együttes megtartására
description: Ez a cikk bemutatja, hogyan lehet olyan elektronikus jelentési (ER) formátumot tervezni, amely egy oldalon tartja a sorokat Microsoft Excel.
author: kfend
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2022-03-01
ms.dyn365.ops.version: Version 10.0.26
ms.custom: 220314
ms.assetid: ''
ms.search.form: EROperationDesigner
ms.openlocfilehash: 7ecc4358a0d4d9ae9e729393bd3ac4cefbf15ad2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287958"
---
# <a name="design-an-er-format-to-keep-rows-together-on-the-same-excel-page"></a>ER-formátum megtervezése a sorok ugyanazon az Excel-lapon való együttes megtartására

[!include [banner](../includes/banner.md)]


Ez a cikk bemutatja, hogy a rendszergazdai és elektronikus jelentéskészítő funkcionális tanácsadó szerepkörű felhasználók hogyan konfigurálhatnak egy elektronikus jelentésformátumot (ER), [...](general-electronic-reporting.md)[amely](er-overview-components.md#format-component) kimenő dokumentumokat generál és a dokumentumok számozását úgy kezeli, hogy a Microsoft Excel létrehozott sorok ugyanazon az oldalon maradnak.

Ebben a példában módosítani fogja a Microsoft által megadott ER-formátumot, amely a szabadszöveges számlák Excel programban való nyomtatására használható. A módosítások lehetővé teszi a létrehozott szabadszöveges számlajelentés oldalszámozásának kezelését, hogy egyetlen számlasor minden sora ugyanazon az oldalon maradjon, amikor lehetséges.

A cikk eljárásait az **USMF** vállalatnál lehet végrehajtani. Nincs szükség kódolásra.

Ebben a példában hozza létre a szükséges ER-konfigurációkat [a](general-electronic-reporting.md#Configuration) **Litware, Zrt. mintavállalat** számára. Győződjön meg róla **, hogy a Litware, Zrt.** (`http://www.litware.com`) mintavállalat konfigurációs szolgáltatója szerepel az ER keretrendszerben, és hogy Aktívként **van-e megjelölve**. Ha ez a konfigurációs szolgáltató nem szerepel a listán, **vagy** ha nem Aktív jelölésű, kövesse a Konfigurációszolgáltató létrehozása lépést, [és jelölje meg aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="enter-a-new-free-text-invoice"></a>Új szabadszöveges számla beírása

1. Szabadszöveges számla [hozzáadásához kövesse a Szabadszöveges](../../../finance/accounts-receivable/create-free-text-invoice-new.md#create-a-free-text-invoice-1) számla létrehozása lépést.

    1. Egyetlen sor hozzáadása a számlához.
    2. Öt megjegyzés hozzáadása a számlasorhoz.

    ![Számlasor megjegyzésének áttekintése a Mellékletek lapon.](./media/er-keep-excel-rows-together-notes.png)

2. A Sorok másolása [lépéseit](../../../finance/accounts-receivable/create-free-text-invoice-new.md#copy-lines) követve hozzon létre öt további számlasort, amelyek az előző lépésben hozzáadott számlasorokat másolják.

    ![Szabadszöveges számlasorok áttekintése a Szabadszöveges számla oldalon.](./media/er-keep-excel-rows-together-invoice.png)

## <a name="configure-the-er-framework"></a>ER-keretrendszer konfigurálása

Kövesse az [ER-keretrendszer konfigurálása](er-quick-start2-customize-report.md#ConfigureFramework) rész lépéseit az ER-paraméterek minimális készletének beállításához. Ezt a beállítást még az ER keretrendszer használata előtt el kell végeznie, hogy egy szabványos ER-formátum egyéni verzióját megtervezze.

## <a name="import-the-standard-er-format-configuration"></a>A szabvány ER-formátumkonfiguráció importálása

A Szabványos ER [formátumkonfiguráció](er-quick-start2-customize-report.md#ImportERSolution1) importálása lépéseit követve adja hozzá a normál ER-konfigurációkat a Dynamics 365 Pénzügy aktuális példányához. Importálja például **a szabadszöveges számla (Excel) formátumkonfiguráció 252.116-os** **verzióját**. A rendszer **a számlamodell alapkonfigurációjának 252-es** **·** **alapverzióját automatikusan importálja a tárházból a szükséges számlamodell-hozzárendelési konfigurációval** együtt.

## <a name="set-up-print-management-to-use-the-standard-er-format"></a>A nyomtatáskezelés beállítása a szabványos ER-formátum használatára

Hajtsa végre a [Nyomtatáskezelés](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement1)**beállítása** lépést a Kinnlevőségek modul nyomtatáskezelésének konfigurálása érdekében, hogy a szabványos ER-formátumban szabadszöveges számlákat nyomtassa ki a rendszer.

## <a name="configure-a-format-destination-for-the-standard-er-format"></a>A szabványos ER-formátum formátumának konfigurálása

[A Képernyő ER-céljához beállított szabványos ER-formátum](er-quick-start1-new-solution.md#ConfigureDestination)[konfigurálása](er-destination-type-screen.md) érdekében a létrehozott jelentések PDF-formátumúvá alakulnak, és előnézetben megjelenik egy új böngészőlap.

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a>Szabadszöveges számla nyomtatása a szabványos ER-formátum használatával

1. Kövesse a Szabadszöveges [számla nyomtatása lépést a](er-embed-images-header-footer-excel-reports.md#ProcessInvoice1) szabványos ER formátumban a szabadszöveges számla jelentésének Excel formátumú előállításához a hozzáadott számlához.
2. Töltse le a létrehozott Excel-munkafüzetet, és tekintse át az Excel asztali alkalmazásban.

    Ne figyelje meg, hogy a számla hatodik sora a jelentés első oldalán kezdődik, és a második oldalon folytatódik. Az utolsó megjegyzés megjelenik a második oldalon, és nem biztos, hogy a hatodik számlasorhoz tartozik. Emiatt a számlasor tartalmának középső részen az oldaltörés nehézvé teszi ezt a dokumentumot.

    ![A létrehozott szabadszöveges számla oldalszámozásának áttekintése az Excel asztali alkalmazásban.](./media/er-keep-excel-rows-together-invoice1.gif)

A cikk további eljárásai mutatják be, hogyan javítható a normál ER-formátum a számlajelentés jobb megjelenésének és olvashatóságának javítása érdekében azáltal, hogy ugyanazon az oldalon tart minden tartalmat egyetlen számlasoron.

## <a name="create-a-custom-format"></a>Egyéni formátum létrehozása

Hajtsa végre [az](er-embed-images-header-footer-excel-reports.md#DeriveProvidedFormat) Egyéni formátum létrehozása című lépést, ha az importált ER-formátumból **származtat egy formátumot, és hozzon létre egy szabadszöveges számla (Excel)** egyéni ER konfigurációt, amely szerkeszthető és szerkeszthető.

## <a name="edit-the-custom-format"></a>Egyéni formátum szerkesztése

1. Hajtsa végre az Egyéni formátum létrehozása [lépést a](er-embed-images-header-footer-excel-reports.md#ConfigureDerivedFormat) származtatott ER-formátum megnyitásához az ER formátumtervezőben való szerkesztéshez.
2. A Formátumtervező **lap** bal oldali összetevőfában bontsa **\>\> ki a Szabadszöveges számlalap Számlasorok** ágát, **és válassza ki InvoiceLines_Values** összetevőt.
3. A Formátum **lapon** állítsa **a Sorok egymáshoz megtartása lehetőséget** Igen **beállításra**.

    ![A Sorok egymáshoz megtartása beállítás beállítása a Szerkeszthető ER-formátumhoz a Formátumtervező lapon.](./media/er-keep-excel-rows-together-format.png)

4. Válassza a **Mentés** gombot, és zárja be az oldalt.

## <a name="mark-the-custom-format-as-runnable"></a>Egyéni formátum megjelölése futtathatóként

Az egyéni ER-formátum [módosított](er-embed-images-header-footer-excel-reports.md#MarkFormatRunnable) verziójának futtathatóként való megjelölése érdekében hajtsa végre az egyéni formátum megjelölése lépést.

## <a name="set-up-print-management-to-use-the-custom-er-format"></a>Nyomtatáskezelés beállítása az egyéni ER-formátum használatára

Hajtsa végre a [Nyomtatáskezelés](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement2)**beállítása** lépést a Kinnlevőségek modul nyomtatáskezelésének konfigurálása érdekében, hogy az egyéni ER-formátum szabadszöveges számlák nyomtatására használható.

## <a name="configure-a-format-destination-for-the-custom-er-format"></a>Az egyéni ER-formátum formátumának konfigurálása

[A Képernyőn megjelenő előnézet formátumcél konfigurálása lépéseit követve állítsa be az egyéni ER-formátumhoz a Képernyő ER-célt, hogy a generált jelentéseket PDF-formátumra konvertálja a](er-quick-start1-new-solution.md#ConfigureDestination)**rendszer**, és megtekinti az új böngészőlapon.

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a>Szabadszöveges számla nyomtatása egyéni ER-formátum használatával

1. Kövesse a Szabadszöveges [számla](er-embed-images-header-footer-excel-reports.md#ProcessInvoice2) nyomtatása lépést az egyéni ER formátum használatával a szabadszöveges számla jelentésének Excel formátumban való előállításához a hozzáadott számlához.
2. Töltse le a létrehozott Excel-munkafüzetet, és tekintse át az Excel asztali alkalmazásban.

    Ne figyelje meg, hogy a számla hatodik sora a második oldalon kezdődik, és ezen a lapon az adott számlasort képviselő összes Excel-sor együtt jelenik meg.

    ![A létrehozott szabadszöveges számla frissített oldalszámozásának áttekintése az Excel asztali alkalmazásban.](./media/er-keep-excel-rows-together-invoice2.gif)

## <a name="additional-resources"></a>További erőforrások

[Tervezzen konfigurációkat a kimenő dokumentumok Excel-formátumban történő létrehozásához](er-fillable-excel.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
