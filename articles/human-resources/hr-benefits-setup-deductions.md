---
title: Levonások konfigurálása
description: A Microsoft Dynamics 365 Human Resources rendszerben levonásokat használhat annak meghatározására, hogy mennyit kell levonni (ha kell) az alkalmazottak fizetéséből az egyes juttatások esetében.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 46a37aebf99751d16952d3d7c07c538713377a67
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324873"
---
# <a name="configure-deductions"></a>Levonások konfigurálása


A Microsoft Dynamics 365 Human Resources rendszerben levonásokat használhat annak meghatározására, hogy mennyit kell levonni (ha kell) az alkalmazottak fizetéséből az egyes juttatások esetében. A levonásokhoz érvényességi dátum tartozik, így megőrizheti a levonási adatok előzményeinek nyilvántartását. 

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Levonások** elemet.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Levonás** | Egyedi azonosító, amely a juttatási levonás azonosítására szolgál. |
   | **Leírás** | A levonás leírása. |
   | **Hatályos** | A kezdő dátum. Az alapértelmezett érték az aktuális rendszerdátum. |
   | **Lejárat** | A záró dátum. Az alapértelmezett érték a 2154. 12. 31., ami a „soha” megfelelője. |
   | **Címsor** | A címsorkód abból a bérszámfejtő rendszerből, amelyet ez a levonás fog használni a levonás alkalmazotti részéhez a juttatások bérszámfejtési feldolgozásakor. Ezt akkor alkalmazza a rendszer, amikor külső bérszámfejtő szolgáltatót használ. |
   | **Alkalmazotti bérlistalevonási referencia** | A bérlistarendszerből származó levonási kód, amelyet ez a levonás alkalmazotti részéhez használ a juttatások bérlistában való feldolgozása során. |
   | **Összeg címsora** | A címsorkód abból a bérszámfejtő rendszerből, amelyet ez a levonási összeg fog használni a levonás alkalmazotti részéhez a juttatások bérszámfejtési feldolgozásakor. Ezt általában akkor alkalmazza a rendszer, amikor külső bérszámfejtő szolgáltatót használ. |
   | **Törölhető** | Megadja, hogy a Dynamics 365 Pénzügy alkalmazásból exportált érték esetén törlődhet-e az érték a bérrendszerből. |
   | **Párba állított oszlopok** | Megadja, hogy az exportálási címsor és a levonási összeg szomszédos oszlopokban, párosítva lesz-e exportálva a bérszámfejtő rendszerbe. |
   | **Módosítás érvénybe lépési dátuma** | Az a dátum, amikor a juttatás levonásának módosítása érvénybe lép. Ezen a napon a levonás megváltozik, és a levonáshoz kapcsolódó összes juttatási terv frissül, amennyiben lefuttatja a **Levonásváltozás frissítés** feldolgozása futtatást. |
   | **Levonás módosítása befejeződött** | A rendszer automatikusan bejelöli a **Levonás módosítása befejeződött** jelölőnégyzetet, amikor a levonásfrissítési módosítás feldolgozása végrehajtotta a juttatáslevonási módosításokat. |
   
4. A juttatásimérték-beállítások változásainak követéséhez és karbantartásához válassza a **Műveletek**, majd a **Verziók karbantartása** lehetőséget.

5. Válassza a **Mentés** lehetőséget. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]

