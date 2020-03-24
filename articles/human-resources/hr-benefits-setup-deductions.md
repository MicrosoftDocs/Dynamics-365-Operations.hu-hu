---
title: Levonások konfigurálása
description: A Microsoft Dynamics 365 Human Resources rendszerben levonásokat használhat annak meghatározására, hogy mennyit kell levonni (ha kell) az alkalmazottak fizetéséből az egyes juttatások esetében.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a5287161f352b386ae4e13067f40228d7c1bce62
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092729"
---
# <a name="configure-deductions"></a>Levonások konfigurálása

[!include [banner](includes/preview-feature.md)]

A Microsoft Dynamics 365 Human Resources rendszerben levonásokat használhat annak meghatározására, hogy mennyit kell levonni (ha kell) az alkalmazottak fizetéséből az egyes juttatások esetében. A levonásokhoz érvényességi dátum tartozik, így megőrizheti a levonási adatok előzményeinek nyilvántartását. 

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Levonások** elemet.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | Levonás | Egyedi azonosító, amely a juttatási levonás azonosítására szolgál. |
   | Leírás | A levonás leírása. |
   | Hatályos | A kezdő dátum. Az alapértelmezett érték az aktuális rendszerdátum. |
   | Lejárat | A záró dátum. Az alapértelmezett érték a 2154. 12. 31., ami a „soha” megfelelője. |
   | Címsor | A címsorkód abból a bérszámfejtő rendszerből, amelyet ez a levonás fog használni a levonás alkalmazotti részéhez a juttatások bérszámfejtési feldolgozásakor. Ezt akkor alkalmazza a rendszer, amikor külső bérszámfejtő szolgáltatót használ. |
   | Alkalmazotti bérlistalevonási referencia | A bérlistarendszerből származó levonási kód, amelyet ez a levonás alkalmazotti részéhez használ a juttatások bérlistában való feldolgozása során. |
   | Összeg címsora | A címsorkód abból a bérszámfejtő rendszerből, amelyet ez a levonási összeg fog használni a levonás alkalmazotti részéhez a juttatások bérszámfejtési feldolgozásakor. Ezt általában akkor alkalmazza a rendszer, amikor külső bérszámfejtő szolgáltatót használ. |
   | Törölhető | Megadja, hogy a Dynamics 365 for Finance and Operations alkalmazásból exportált érték okozhatja-e az érték törlését a bérszámfejtő rendszerben. |
   | Párba állított oszlopok | Megadja, hogy az exportálási címsor és a levonási összeg szomszédos oszlopokban, párosítva lesz-e exportálva a bérszámfejtő rendszerbe. |
   | Módosítás érvénybe lépési dátuma | Az a dátum, amikor a juttatás levonásának módosítása érvénybe lép. Ezen a dátumon a rendszer automatikusan megváltoztatja a juttatás levonását, és frissíti az ehhez a levonáshoz kapcsolódó összes juttatási konstrukciót, amikor futtatja a levonás módosításának frissítési feldolgozását. |
   | Levonás módosítása befejeződött | A rendszer automatikusan bejelöli a Levonás módosítása befejeződött jelölőnégyzetet, amikor a levonásfrissítési módosítás feldolgozása végrehajtotta a juttatáslevonási módosításokat. |
   
4. A juttatásimérték-beállítások változásainak követéséhez és karbantartásához válassza a **Műveletek**, majd a **Verziók karbantartása** lehetőséget.

5. Válassza a **Mentés** lehetőséget. 
