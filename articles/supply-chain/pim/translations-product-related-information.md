---
title: Termékekkel kapcsolatos GYIK
description: Ez a témakör ismerteti, hogyan kell kezelni a termékek, termékdimenzió értékek és termékattribútumok fordításait.
author: cvocph
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysTranslationDetail, SysTranslationLanguage, SysTranslationList, EcoResProductListPage, EcoResProductVariants, EcoResProductDetailsExtended, EcoResProductCreate, EcoResProductDetails, RetailSizeGroupTable, RetailStyleGroupTable, RetailColorGroupTable, PCTranslationLanguageLookup, EcoResProductCategory
audience: Application User
ms.reviewer: kamaybac
ms.custom: 201853
ms.assetid: c0286bba-f54b-42de-904c-81fd796bdd1d
ms.search.region: global
ms.search.industry: Product information
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7dc7c681b86e34f59cbbc3c6231a36fe9ca5327a
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188886"
---
# <a name="product-related-translations-faq"></a>Termékekkel kapcsolatos GYIK

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti, hogyan kell kezelni a termékek, termékdimenzió értékek és termékattribútumok fordításait. 

## <a name="what-product-related-data-can-be-translated"></a>Milyen termékkel kapcsolatos adatokat lehet lefordítani?

Fordításokat hozhat létre a következő termékkel kapcsolatos információkra:
-   A termékek nevei és leírásai.
-   A termékattribútum-értékek leírása, könnyen megjegyezhető neve és súgószövege.
-   A termékdimenzió-értékek nevei és leírásai.

A termékkel kapcsolatos információkat bármely – a **Szöveg fordítása** lapon elérhető – nyelvre lefordíthatja. További tudnivalókért lásd a **Hogyan hozhatok létre fordítást termékkel kapcsolatos információból?** részt.

## <a name="where-can-i-view-the-translated-information"></a>Hol tekinthetem meg a lefordított információkat?
A termékkel kapcsolatos információk fordításait bármilyen külső forrásbizonylaton, például egy számlán megtekintheti, ami olyan nyelvet használ, amelyre rendelkezésre állnak fordítások.

## <a name="how-do-i-create-translations-for-product-related-information"></a>Hogyan hozható létre fordítás termékkel kapcsolatos információból?
A termék-fordítások létrehozásához tegye a következőket:
1.  Kattintson a **Termékinformációk kezelése** &gt; **Közös** &gt; **Kiadott termékek** lehetőségre.
2.  Válasszon ki egy terméket, majd a Műveleti ablaktáblapontban a **Nyelvek** csoportban kattintson a **Fordítások** lehetőségre.
3.  A **Szöveg fordítása** lapon a **Nyelv** mezőben válasszon egy nyelvet. További nyelvek hozzáadásához bontsa ki a **Nyelv** mezőt, majd kattintson az **OK** lehetőségre.
4.  A **Lefordított szöveg** csoportban adja meg a fordításokat a **Leírás** és a **Termék neve** mezőkben.

A termékattribútum-fordítások létrehozásához tegye a következőket:
1.  Kattintson a **Termékinformációk kezelése** &gt; **Közös** &gt; **Kiadott termékek** lehetőségre.
2.  A **Beállítás** pontban kattintson az **Attribútumok** lehetőségre, majd kattintson az **Attribútumok** pontra.
3.  A **Attribútumok** lapon kattintson a **Fordítás** lehetőségre.
4.  A **Szöveg fordítása** lapon a **Nyelv** mezőben válasszon egy nyelvet. További nyelvek hozzáadásához bontsa ki a **Nyelv** mezőt, majd kattintson az **OK** lehetőségre.
5.  A **Lefordított szöveg** csoportban adja meg a fordításokat a **Leírás**, a **Rövid név** és a **Súgószöveg** mezőkben.

Termékdimenzió-értékek létrehozásához tegye a következőket:
1.  Kattintson a **Termékinformációk kezelése** &gt; **Közös** &gt; **Kiadott termékek** lehetőségre.
2.  Válasszon ki egy terméket, majd kattintson a **Termékdimenziók** elemre.
3.  Válasszon egyet a termékdimenziók linkjei közül: **Konfigurációk**, **Méretek**, **Színek** vagy **Stílus**.
4.  Válasszon egy dimenzióértéket, majd kattintson a **Fordítás** elemre.
5.  A **Szöveg fordítása** lapon a **Nyelv** mezőben válasszon egy nyelvet. További nyelvek hozzáadásához bontsa ki a **Nyelv** mezőt, majd kattintson az **OK** lehetőségre.
6.  A **Lefordított szöveg** csoportban adja meg a fordításokat a **Név** és a **Leírás** mezőkben.

## <a name="can-the-names-of-product-variants-be-translated"></a>Le lehet fordítani termékváltozatok nevét?
Termékváltozatok egy kiadott termék dimenzióin alapulnak. A termékváltozatok nevei dimenzióértékek kombinációján alapulnak. Amikor a termékváltozattal társított dimenzióértékek le vannak fordítva, a termékváltozat neve megjelenik a lefordított változatban.  

**Példa**  

Az Ön terméke egy póló, amely különböző méretű és színű változatokban áll rendelkezésre, a változatok nevei a következő részleteken alapulnak:
-   Termékszám:\#3
-   Dimenziók: méret és szín
-   Méretdimenzió-értékek méret: kicsi, közepes, nagy
-   Színdimenzió-értékek: piros, zöld, fekete

A Kicsi és Piros dimenzióértékeken alapuló termékváltozat neve **\#3:Small:Red**.  

Ha a vevő meg kíván vásárolni néhány kis méretű, piros pólót, a póló nevének francia nyelven kell szerepelnie a számlán. A dimenzióértékeket – a Kicsit és a Pirosat – le kell fordítani franciára, a termékváltozat neve pedig **\#3:Petit:Rouge**.
<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tipp</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Az ügyfél által kívánt nyelv beállításához kövesse az alábbi lépéseket:
<ol><br/><li>Kattintson az <strong>Értékesítés és marketing</strong> &gt; <strong>Közös</strong> &gt; <strong>Vevők</strong> &gt; <strong>Minden</strong> <strong>vevő</strong> elemre.</li>
<li>A <strong>Vevők</strong> lap megnyitásához kattintson duplán egy vevőre. Az <strong>Általános</strong> lap <strong>Nyelv</strong> mezőjében válassza ki a <strong>nyelvet</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="what-happens-if-a-customer-has-a-preferred-language-for-which-no-translations-are-available"></a>Mi történjen, ha egy ügyfél olyan nyelvet kíván meg, amelyre vonatkozóan nem állnak rendelkezésre fordítások?
Ha az ügyfél által megkívánt nyelven nem érhetők el fordítások, a nevek és a leírások az Ön vállalata által használt világnyelven jelennek meg.

## <a name="can-i-manage-translations-for-a-series-of-dimension-values-at-the-same-time"></a>Van-e lehetőség dimenzióértékek sorozata fordításainak egyszerre történő kezelésére?
A dimenzióértékek termékspecifikusak, így minden egyes termék dimenzióértékeihez tartozó fordítást kezelhet. Bár, ha dimenzióérték-csoportot hoz létre és az értékcsoportban az értékekhez fordításokat rendel, könnyebben kezelheti a fordításokat.   

**Példa**  

Vállalata különböző stílusú pólókat gyárt, és minden stílus Kicsi, Közepes és Nagy méretben áll rendelkezésre. A méretek összegyűjtése egy dimenzióérték-csoportban történik. Új pólóstílus hozzáadásakor társíthatja azt a méretekhez használt dimenzióérték-csoporttal, hogy a termékhez minden méret elérhető legyen. A dimenzióérték-csoport méreteihez bármikor hozzáadhat fordításokat vagy módosíthatja azokat.  

Termékkel dimenzióváltozat-csoporton keresztül társított dimenzióértéket a termékváltozat-csoportban tud karbantartani.   
Dimenzióérték-csoport létrehozásához tegye a következőket:
1.  Kattintson a **Termékinformációk kezelése** &gt; **Beállítás** &gt; **Változatcsoportok** lehetőségre.
2.  Válasszon a **Méretcsoportok**, **Színcsoportok** vagy **Stíluscsoportok** közül.
3.  Kattintson az **Új** lehetőségre, és írjon be egy csoportnevet a **Méret** **csoport**, **Színcsoport** vagy **Stíluscsoport** mezőbe. Kattintson a **Méretek**, **Színek** vagy **Stílusok** lehetőségre sorok csoportokban történő létrehozásához.
4.  A **Méret** **csoport** sorok, **Szín** **csoport** **sorok** vagy **Stílus csoportsorok** lapon kattintson az **Új** lehetőségre, majd hozza létre a csoportokban használandó méreteket, színeket és a stílusokat.

Az értékek fordításainak dimenzióérték-csoportban történő kezeléséhez kövesse az alábbi lépéseket:
1.  Kövesse az előző – dimenzióérték-csoportot létrehozó – eljárás lépéseit a **Méretcsoportsorok**, a **Színcsoportsorok** vagy a **Stíluscsoportsorok** lap megnyitásához.
2.  Kattintson a **Szöveg fordítása** lehetőségre. A **Szöveg fordítása** lapon a **Lefordított szöveg** csoportban adja meg a fordításokat a **Név** és a **Leírás** mezőkben.

## <a name="when-can-translations-of-product-related-information-be-managed"></a>Mikor módosíthatók a termékkel kapcsolatos információk fordításai?
A termékkel kapcsolatos információk fordításai bármikor módosíthatók. Termékhez társított dimenzióérték fordításainak frissítésekor a termék-információ attól függetlenül frissül, hogy a termékhez tartoznak-e tranzakciók.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]