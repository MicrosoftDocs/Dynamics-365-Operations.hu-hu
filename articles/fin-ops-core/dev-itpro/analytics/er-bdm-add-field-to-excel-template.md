---
title: Új mezők hozzáadása üzleti dokumentum-sablonhoz a Microsoft Excel szolgáltatásban
description: Ez a témakör azt mutatja be, hogyan lehet új mezőket felvenni egy üzleti dokumentumsablonba a Microsoft Excel programban az üzleti dokumentumkezelő funkció segítségével.
author: NickSelin
manager: AnnBe
ms.date: 11/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 8c3a905c90f5dd4ad3487f004a958c0dcd52115d
ms.sourcegitcommit: 71ec2f48185b8104ca52ff70df52263ce5f87f26
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/25/2020
ms.locfileid: "3893247"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a>Új mezők hozzáadása üzleti dokumentum-sablonhoz a Microsoft Excel szolgáltatásban

[!include[banner](../includes/banner.md)]

Új mezőket hozzáadhat egy sablonhoz, amely a következő Microsoft Excel formátumú üzleti dokumentumok létrehozásához használatos. Ezek a mezők olyan helyőrzőként adhatók hozzá, amelyekkel az alkalmazásból a létrehozott dokumentumokat a szükséges adatokkal ki lehet tölteni. Minden hozzáadott mező esetében megadhat egy kötést az adatforrásokhoz, amely meghatározza, hogy milyen alkalmazásadatok szerepeljenek a mezőben, ha a sablont az üzleti dokumentumok létrehozásához használják.

Ha további tájékoztatást szeretne erről a funkcióról, végezze el a példafeladatot ebben a témakörben. Ez a példa azt mutatja be, hogyan lehet módosítani egy sablont a létrejövő Szabadszöveges számlaűrlapok mezőinek kitöltéséhez.

## <a name="configure-business-document-management-to-edit-templates"></a>Az üzleti dokumentumkezelés modul konfigurálása sablonok szerkesztéséhez

Mivel az üzleti Dokumentumkezelés (BDM) az [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md) keretrendszerén alapul, konfigurálnia kell a szükséges ER és BDM paramétereket, mielőtt elkezdené a munkát a BDM-mel.

1.  Jelentkezzen be a Microsoft Dynamics 365 Finance példányára rendszeradminisztrátorként.
2.  Hajtsa végre a példa következő lépéseit az [üzleti Dokumentumkezelés – áttekintés](er-business-document-management.md) témakörben:

    1.  Konfigurálja az ER-paramétereket.
    2.  Kapcsolja be a BDM-et.

Most már elkezdheti használni a BDM-et az üzleti dokumentumok sablonjainak szerkesztéséhez.

## <a name="import-er-solutions-that-contain-a-template"></a>Sablont tartalmazó ER-megoldások importálása

Az ebben az eljárásban szereplő példa a hivatalosan közzétett ER megoldást használja. Az adott megoldás ER-konfigurációit importálnia kell a Finance aktuális példányába.

A megoldás **Szabadszöveges számla (Excel)** ER formátumkonfigurációja Excel-formátumban tartalmazza az üzletidokumentum-sablont, amelyet a BDM-mel szerkeszthet. Importálja az adott ER formátumkonfiguráció legújabb verzióját a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból. A program automatikusan importálja a megfelelő ER adatmodellt és az ER modell-leképezési konfigurációkat.

Az ER-konfigurációk importálásának módjával kapcsolatos további tudnivalókat lásd: [Elektronikus jelentéskészítési konfigurációk életciklusainak kezelése](general-electronic-reporting-manage-configuration-lifecycle.md).

![LCS Közös eszközök tára oldal](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a>Az ER megoldássablon szerkesztése

1.  Az **Üzleti dokumentum kezelése** munkaterületre való hozzáféréssel rendelkező felhasználóként jelentkezzen be.
2.  Nyissa meg az **Üzletidokumentum-kezelés** munkaterületet.

    ![Üzletidokumentum-kezelés munkaterület](./media/BDM-AddFldExcel-Workspace.png)

3.  A rácsban válassza ki a **Szabadszöveges számla (Excel)** sablonját.
4.  A jobb oldali ablakban válassza ki az **új sablon** elemet a kiválasztott sablonon alapuló új sablon létrehozásához.
5.  A **Cím** mezőbe írja be: **Szabadszöveges számla (Excel) Contoso** az új sablon címeként.
6.  A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.

Megjelenik a BDM sablonszerkesztő lap. A kiválasztott sablont a Microsoft 365 segítségével online szerkesztheti a beágyazott vezérlőben.

![BDM-sablonszerkesztő lapja](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a>Új mező címkéjének hozzáadása a sablonhoz

1.  A BDM-sablonszerkesztő lapon az Excel menüszalagjának **Nézet** lapján válassza a **Címsorok és rácsvonalak** jelölőnégyzeteket a szerkeszthető Excel-sablonnál.

    ![A címsorok és a rácsvonalak jelölőnégyzete be van jelölve.](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  Válassza a következő cellákat: **E8:F8**.
3.  Az Excel menüszalag **Kezdőlap** lapján jelölje be az **Egyesítés és középre igazítás** lehetőséget a kiválasztott cellák egyesítéséhez az új egyesített **E8:F8** cellába.
4.  Az egyesített **E8:F8** cellában adja meg: **URL**.
5.  Válassza ki az **E7:F7** egyesített cellát, válassza a **Formátummásolót**, majd válassza az egyesített **E8:F8** cellát, hogy ugyanúgy formázza, mint az egyesített **E7:F7** cellát.

    ![Új mező címkét hozzáadott a sablonhoz](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a>A sablon formázása egy új mező számára fenntartott hellyel

1.  A BDM sablonszerkesztő lapján válassza az egyesített **G8:H8** cellát.
2.  Az Excel menüszalag **Kezdőlap** lapján jelölje be az **Egyesítés és középre igazítás** lehetőséget a kiválasztott cellák egyesítéséhez az új egyesített **G8:H8** cellába.
3.  Válassza ki az **G7:H7** egyesített cellát, válassza a **Formátummásolót**, majd válassza az egyesített **G8:H8** cellát, hogy ugyanúgy formázza, mint az egyesített **G7:H7** cellát.

    ![Az új mező számára fenntartott hely](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  A **név** mezőben válassza ki: **CompanyInfo**.

    Az aktuális Excel-sablon **CompanyInfo**-tartománya minden olyan mezőt tartalmaz, amely a létrejövő Jelentés fejlécének kitöltéséhez használatos az aktuális vállalat, mint eladó fél adataival.

    ![Kijelölt CompanyInfo-tartomány](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a>Új mező hozzáadása a sablonhoz

1.  Válassza ki a **BDM sablonszerkesztő** lapján a művelet ablaktáblán a **formátum megjelenítése** elemet.
2.  Válassza a **Sablon szerkezete** ablaktábla **Hozzáadás** elemét.

    > [!NOTE]
    > Módosítania kell a sablonnak azt a szakaszát, amelyet új mezőként szeretne használni. Ezt a módosítást már elvégezte az egyesített cella formázásával: **G8:H8**.

    ![Új mező hozzáadása a sablonhoz](./media/BDM-AddFldExcel-AddCell.png)

3.  Az **Excel\Cella** kiválasztásával új mezőt adhat hozzá a sablonban szereplő cellaként.

    Az **Excel\Range** kiválasztásával a sablonhoz új tartományt szeretne adhat hozzá. A megadott tartomány több cellát is tartalmazhat. Ezek a cellák később is hozzáadhatók.
    
    Figyelje meg, hogy a **CompanyInfo** sablonösszetevője automatikusan be van jelölve a **sablon szerkezete** ablaktáblában, mert ez a legmegfelelőbb fölérendelt összetevő az aktuális sablonszerkezetben a hozzáadni kívánt mező számára.
    
4.  Az **Excel-tartomány** mezőbe írja be: **CompanyURL_Value**.
5.  Válassza ki az **OK** lehetőséget.

    ![A sablon struktúrájához hozzáadva a CompanyURL_Value mező](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  A **Sablon szerkezete** ablaktáblán válassza a három pont gombot (...), majd válassza a **kötések megjelenítése** lehetőséget.

    ![Kiválasztott kötések megjelenítése](./media/BDM-AddFldExcel-ShowBindings.png)

    A **sablon szerkezete** ablaktábla most megjeleníti azokat az adatforrásokat, amelyek elérhetők a mögöttes ER formátumában.

7.  Válassza ki a **CompanyInfo_Value** mezőt olyan mezőként, amelyet a mögöttes ER formátum adatforrásához kíván kötni.
8.  A **Sablon szerkezete** **Adatforrások** szakaszában bontsa ki a **Modell \> InvoiceBase \> CompanyInfo** elemet.
9.  A **CompanyInfo** területen válassza ki a **WebsiteURI** elemet.

    ![A WebsiteURI elem kiválasztva](./media/BDM-AddFldExcel-BindURL.png)

10. Válassza a **Bind** elemet.
11. Válassza a **Sablon szerkezete** ablaktáblában a **Mentés** elemet, majd zárja be a BDM-sablon szerkesztő lapját.

Az **üzleti Dokumentumkezelés** munkaterületen a **Sablon** lap jobb oldali ablaktáblájában látható a frissített sablon. A rácsban figyelje meg, hogy a szerkesztett sablon **állapot** mezője **Tervezet** állapotra módosult, és a **módosítás** mező már nem üres. Ezek a módosítások azt jelentik, hogy a sablon szerkesztésének folyamata elindult.

![Szerkesztett sablon az üzleti Dokumentumkezelés munkaterületen](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a>Vállalati beállítások felülvizsgálata

1.  Nyissa meg a következőt: **Szervezeti adminisztráció \> Szervezetek \> Jogi személyek**.
2.  A **kapcsolattartási adatok** gyorslapon győződjön meg arról, hogy a vállalat URL-címe meg van adva.

![A jogi személyek oldalon megadott vállalati URL-cím](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a>Üzleti dokumentumok létrehozása a frissített sablon teszteléséhez

1.  Az alkalmazásban változtassa meg a vállalatota **USMF** értékre, és lépjen a **Kinnlevőségek \> Számlák \> összes szabadszöveges számla** lehetőségre.
2.  Válassza ki az **FTI-00000002** számlát, majd válassza a **Nyomtatáskezelő**parancsot.
3.  A bal oldali ablaktáblán bontsa ki a **Modul – Kinnlevőségek \> dokumentumok \> szabadszöveges számla** elemet.
4.  A **Szabadszöveges számla** részben válassza az **Eredeti dokumentum** szintet a feldolgozáshoz szükséges számlahatókör megadásához.
5.  A jobb oldali ablakban a **jelentés formátuma** mezőben válassza ki a **Szabadszöveges számla (Excel) contoso** sablonját a megadott dokumentum szintjén.

    ![A Szabadszöveges számla (Excel) contoso sablon kiválasztva](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  Az **Esc** gombbal zárja be az aktuális lapot.
7.  Válassza a **Nyomtatás \> Kiválasztott** elemet.
8.  Töltse le a létrejövő dokumentumot, és nyissa meg az Excel alkalmazásban.

    ![Szabadszöveges számla Excelben](./media/BDM-AddFldExcel-PreviewReport.png)

A módosított sablon a szabadszöveges számlajelentés generálására szolgál a kiválasztott tételhez. Annak elemzéséhez, hogy milyen hatással vannak a sablonon végzett módosításai erre a jelentésre, futtassa ezt a jelentést azonnal egy alkalmazás-munkamenetben, közvetlenül azután, hogy módosította egy alkalmazásmunkamenetben.

## <a name="related-links"></a>Kapcsolódó hivatkozások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)

[Üzletidokumentum-kezelés – áttekintés](er-business-document-management.md)

[Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése](tasks/er-design-reports-openxml-2016-11.md)
