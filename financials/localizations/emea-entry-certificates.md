---
title: "EU-s beérkezési igazolás"
description: "Ez a cikk az európai uniós (EU) beérkezési igazolásokról nyújt tájékoztatást."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustEntryCertificateJour_W, CustParameters, CustTable, SalesTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11464
ms.assetid: e2240f55-cc9a-4ba4-ad50-2d919bca3b7f
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: a951b1f0159ef61704fb772d81ab6a9bc1c80589
ms.lasthandoff: 03/31/2017


---

# <a name="eu-entry-certificates"></a>EU beérkezési igazolások

[!include[banner](../includes/banner.md)]


Ez a cikk az európai uniós (EU) beérkezési igazolásokról nyújt tájékoztatást.

Egy európai uniós (EU) beérkezési igazolással kapcsolatban a következő műveleteket hajthatja végre:

-   Cikkek vagy szolgáltatások EU-országokba/régiókba való szállításához EU-s beérkezési igazolás létrehozása és kibocsátása szállítólevéllel vagy vevői számlával együtt.
-   EU-vevő által aláírt EU-s beérkezési igazolás fogadása.
-   Olyan aláírt EU-s beérkezési igazolás feltöltése, amely vagy egy vevőtől vagy egy olyan harmadik féltől származik, amely felelős a cikkek kiszállításáért a vevő számára.
-   Feltöltött EU-s beérkezési igazolás társítása egy vevői számlához.
-   A feltöltött EU beérkezési igazolás státuszának frissítése.

## <a name="prerequisites"></a>Előfeltételek
Az alábbi táblázat bemutatja a munka megkezdése előtt biztosítandó előfeltételeket.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategória</th>
<th>Előfeltételek</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ország/régió</td>
<td>A jogi személy elsődleges címének egy EU tagállamban kell lennie.</td>
</tr>
<tr class="even">
<td>Kapcsolódó feladatok beállítása</td>
<td><ul>
<li>A <strong>Kinnlevőségek paraméterei</strong> képernyőn válassza ki a <strong>Beérkezési igazolások kezelésének engedélyezése</strong> és a <strong>Beérkezési igazolás kiállításának engedélyezése</strong> lehetőségeket.</li>
<li>Az <strong>Ügyfelek</strong> képernyőn, a <strong>Számlázás és szállítás</strong> gyorslapon válassza ki a <strong>Beérkezési igazolás szükséges</strong> lehetőséget, hogy megjelölje, ha EU-s beérkezési igazolás szükséges az ügyfél részére. Jelölje be a <strong>Beérkezési igazolás kiállítása</strong> jelölőnégyzetet a jogi személy EU-s beérkezési igazolásának kiadásához a vevő számára.</li>
<li>A <strong>Kinnlevőségek paraméterei</strong> képernyőn válassza ki a számsorozat kódját a <strong>Beérkezési igazolás</strong> hivatkozáshoz.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Kapcsolódó tranzakciók</td>
<td><ul>
<li>Vevői fiók létrehozása.</li>
<li>Hozzon létre egy értékesítési rendelést.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="creating-registering-and-uploading-an-eu-entry-certificate"></a>EU-s beérkezési igazolás létrehozása, regisztrációja és feltöltése
Beérkezési igazolás EU hozhat létre, automatikusan vagy kézzel történjen. Amikor egy csomagjegyzéket vagy számlát ad fel egy vevő részére a **Szállítólevél feladása** oldalt vagy a **Számla feladása** oldalt használva, létrejön és nyomtatásra kerül egy EU beérkezési igazolás. Az EU-s beérkezési igazolás kézi létrehozásához vagy újranyomtatásához egy vevői számla esetében használja a **Számlanapló** képernyőt. Ezenkívül megadhat információkat egy olyan EU beérkezési igazolással kapcsolatban, amelyet egy harmadik fél bocsátott ki a **Beérkezési igazolások naplója** képernyőn keresztül.

### <a name="creating-an-eu-entry-certificate-automatically-or-manually"></a>EU-s beérkezési igazolás automatikus vagy kézi létrehozása

Létrehozhat egy EU-s beérkezési igazolást automatikusan a szállítólevél használatával a **Minden értékesítési rendelés** képernyőn vagy az **Értékesítési rendelés** képernyőn található számla használatával. Az EUs- beérkezési igazolás kézi létrehozásához használhatja a **Számlanapló** képernyő egyik számláját. Mielőtt azonban manuális létrehozhatná az EU-s beérkezési igazolást, meg kell változtatnia egy számla igazolási státuszát.

### <a name="registering-an-eu-entry-certificate"></a>EU beérkezési igazolás regisztrálása

Ha regisztráció szükséges, regisztrálhat egy olyan EU beérkezési igazolást, amelyet egy harmadik fél bocsátott ki a** Beérkezési igazolások naplója** képernyőn keresztül.

### <a name="uploading-a-received-eu-entry-certificate"></a>Átvett EU-s beérkezési igazolás feltöltése

EU-vevő által aláírt, fogadott EU-s beérkezési igazolás feltöltéséhez használja a **Mellékletek** képernyőt. Miután az igazolás feltöltésre került, hozzátársíthatja egy számlához a cikkek leszállításának bizonyítékaként. Ez a bizonyíték szükséges, ha olyan számlát kell kiadnia, amely nem tartalmazza az áfát, és könyvvizsgálat során is használják.

### <a name="optional-updating-the-certification-status-and-printing-status-of-an-invoice"></a>Opcionális: A tanúsítvány állapotának és a számla nyomtatási állapotának frissítése

Frissítheti a beérkezési igazolás állapotát és a vevői számla nyomtatási állapotát a **Számlanapló** képernyő használatával.

## <a name="technical-information-for-system-administrators"></a>Technikai információk rendszergazdáknak.
Ha nincs hozzáférése a feladat végrehajtásához használt lapokhoz, akkor forduljon a rendszergazdához, és adja meg azokat az információkat, amelyek a következő táblázatban szerepelnek.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategória</th>
<th>Előfeltételek</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Biztonsági szerepkörök és feladatok</td>
<td>Ha EU-s beérkezési igazolást szeretne beállítani és létrehozni cikkek vagy szolgáltatások esetén, a következő feladatköröket tartalmazó biztonsági szerepkör tagjának kell lennie:
<ul>
<li><strong>Kinnlevőség-adminisztrátor</strong> (CustInvoiceAccountsReceivableClerk)</li>
<li><strong>Ügyfélszolgálati munkatárs</strong> (TradeCustomerServiceRepresentative)</li>
<li><strong>Értékesítési adminisztrátor</strong> (TradeSalesClerk)</li>
<li><strong>Szállítási adminisztrátor</strong> (InventShippingClerk)</li>
</ul></td>
</tr>
</tbody>
</table>





