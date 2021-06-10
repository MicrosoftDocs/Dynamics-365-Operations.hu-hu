---
title: Tömeges felvételi projektek
description: A tömeges felvételi projektek lehetővé teszik az emberi erőforrások szakértőinek, hogy több beosztást hozzanak létre és hatékonyan vegyenek fel dolgozókat ezekbe a beosztásokba.
author: andreabichsel
ms.date: 06/20/2017
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
ms.openlocfilehash: b3d0747232ba4682afe4b28dc7d24ad2413448bb
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052842"
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

A **Tömeges felvételi projektek** oldalon válassza ki a „SummerInterns” projektet, majd kattitnson a **Projekt megnyitása** gombra. A megnyitott tömeges felvételi projektben kattintson a **Beosztások létrehozása** opcióra, és adja meg a könyvelő beosztással kapcsolatos információkat. Megadhatja, hogy öt könyvelői beosztást akar létrehozni, mindegyikhez ugyanazokkal az információkkal, majd kattintson az OK gombra. Ismételje meg ezt a folyamatot a rendelésfeldolgozói és a pénztárosi beosztásokra is.

Miután kiválasztotta a szakmai gyakorlathoz felvenni kívánt hallgatókat, az adataikat a **Beosztás részletei** oldalon adhatja meg a számukra kiválasztott beosztásra. Miután megadta a beosztások adatait, jelölje meg a pozíciót a Tömeges felvételi projektek lapon, és kattintson a **Felvételi** gombra. Egy beosztásrekord jön létre minden pozícióhoz, és egy dolgozói rekord kerül hozzárendelésre minden felvett dolgozóhoz.

## <a name="mass-hire-project-statuses"></a>Tömeges felvételi projekt állapota

A tömeges felvételi projekt állapota a következők egyike lehet.

- Létrehozva
- Nyitva
- Lezárva

A **Tömeges felvételi projekt** lapon kattintson a **Projekt megnyitása** vagy a **Projekt bezárása** elemre, ezzel változtathatja a tömeges felvételi projekt állapotát. A következő táblázatban látható, mit lehet tenni a projekt egyes állapotaiban.

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
<td>Nem adhat hozzá beosztásokat a projekthez. Ha beosztásokat kíván hozzáadni a tömeges felvételi projekthez, nyissa meg újra a projektet. Ez a befejezett projektek állapota.
<blockquote>[!NOTE] Tömeges alkalmazási projekt lezárása előtt a projekt összes beosztásának Létrehozva vagy Lezárva állapotúnak kell lennie.</blockquote>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../includes/footer-banner.md)]