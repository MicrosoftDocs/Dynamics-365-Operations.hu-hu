---
title: Tömeges felvételi projektek
description: Ez a témakör a tömeges felvételi projekteket írja le, amelyek segítségével az emberi erőforrások szakértői több beosztást hozhatnak létre, és a dolgozókat hatékonyan fel lehet venni erre a beosztásra.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMMassHireProject, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7481
ms.assetid: 5f5eb271-76eb-4305-bd1c-5d171dafccc9
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e0a8bba2227136995542d08f4b3f1e9d6d48ad5
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2021
ms.locfileid: "7728656"
---
# <a name="mass-hire-projects"></a>Tömeges felvételi projektek

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



A tömeges felvételi projektek lehetővé teszik az emberi erőforrások szakértőinek, hogy több beosztást hozzanak létre és hatékonyan vegyenek fel dolgozókat ezekbe a beosztásokba.

## <a name="overview"></a>Áttekintés

Ha egyszerre több alkalmazottat állít munkába, például egy szezonális igény kielégítése érdekében, érdemes lehet egy tömeges felvételi projektet létrehozni. A tömeges felvételi projekt létrehozása azért hasznos, mert egyszerre tud pozíciórekordokat, dolgozói rekordokat és dolgozói hozzárendeléseket létrehozni. Tömeges felvételi projekt létrehozásakor a következő adatokat határozhatja meg:

- A létrehozandó beosztások száma
- A beosztásokba felvenni kívánt alkalmazottak típusa
- A pozíciókhoz társított részleg és feladat
- A pozíció teljes munkaidős egyenértéke

## <a name="example"></a>Példa

Nyáron általában 15-20 részmunkaidős egyetemistát vesz fel, hogy kitöltse a vállalat gyakornoki helyeit. Ebben az évben fel szeretné venni öt könyvelőt, öt értékesítési munkatársat és öt pénztárost. Ahelyett, hogy minden egyes beosztást és alkalmazotti rekordot külön létrehozna, egyetlen tömeges felvételi projektet hoz létre „SummerInterns” néven. A projekt kezdő és záró dátumai megegyeznek a beosztások időszakának elejével és végével, amelyet a tömeges felvételi projektben létrehoz.

A Tömeges **felvételi projektek lapon jelölje ki a** **SummerInterns projektet, majd válassza a Projekt** **megnyitása lehetőséget**. A nyitott tömeges felvételi projektben válassza a Beosztások létrehozása lehetőséget, és adja meg a **·** könyvelői beosztásra vonatkozó adatokat. Jelezheti, hogy öt könyvelői pozíciót kell létrehozni, és mindegyikhez ugyanazt az információt kell használni. Majd kattintson az **OK** lehetőségre. Ismételje meg ezt a folyamatot a rendelésfeldolgozói és a pénztárosi beosztásokra is.

Miután kiválasztotta az új beosztásra való felvételi lehetőséget, minden egyes hallgató adatait beírja annak a beosztásnak a részleteibe, amelybe felveszi őket. Amikor megadta a beosztások összes adatát, válassza ki a beosztást a Tömeges felvételi projektek lapon, majd válassza a **·** Felvétel **·** lehetőséget. Minden egyes beosztáshoz létrejön egy beosztásrekord, és létrejön egy dolgozórekord, amely a megfelelő beosztáshoz kerül minden egyes alkalmazotthoz.

## <a name="mass-hire-project-statuses"></a>Tömeges felvételi projekt állapota

A tömeges felvételi projekt állapota a következők egyike lehet.

- Létrehozva
- Nyitva
- Zárt

A Tömeges felvételi projekt lapon válassza a Projekt megnyitása vagy a Projekt bezárása lehetőséget a tömeges felvételi projekt **·** **·** **·** állapotának a módosításahoz. A következő táblázatban látható, mit lehet tenni a projekt egyes állapotaiban.

<table>
<thead>
<tr>
<th>Állapot</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr>
<td>Létrehozva</td>
<td>Létre lehet hozni és módosítani lehet adatokat, de beosztásokat nem lehet létrehozni a projektben. Ez az új projektek alapértelmezett állapota.</td>
</tr>
<tr>
<td>Nyitva</td>
<td>Módosíthatja a projekt adatait, beosztásokat hozhat létre a tömeges felvételi projekthez, és embereket vehet fel a beosztásokba. Ez az aktív projektek állapota.</td>
</tr>
<tr>
<td>Lezárva</td>
<td><p>Nem adhat hozzá beosztásokat a projekthez. Ha beosztásokat kíván hozzáadni a tömeges felvételi projekthez, nyissa meg újra a projektet. Ez a befejezett projektek állapota.</p>
<p><strong>Megjegyzés: A tömeges felvételi projekteket csak akkor lehet lezárni, ha a projekt összes beosztása Létrehozva vagy Lezárva</strong><b></b><b></b> állapotú.</p>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
