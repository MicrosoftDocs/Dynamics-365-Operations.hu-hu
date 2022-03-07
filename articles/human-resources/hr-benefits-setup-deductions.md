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
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a865f109379064ae8829532af9253238e203c322
ms.sourcegitcommit: 8592c661b41f9cef8b7ef2863a3b97bf49a4e6f9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/26/2021
ms.locfileid: "7423497"
---
# <a name="configure-deductions"></a>Levonások konfigurálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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
   | **Törölhető** | Megadja, hogy a Dynamics 365 for Finance and Operations alkalmazásból exportált érték okozhatja-e az érték törlését a bérszámfejtő rendszerben. |
   | **Párba állított oszlopok** | Megadja, hogy az exportálási címsor és a levonási összeg szomszédos oszlopokban, párosítva lesz-e exportálva a bérszámfejtő rendszerbe. |
   | **Módosítás érvénybe lépési dátuma** | Az a dátum, amikor a juttatás levonásának módosítása érvénybe lép. Ezen a napon a levonás megváltozik, és a levonáshoz kapcsolódó összes juttatási terv frissül, amennyiben lefuttatja a **Levonásváltozás frissítés** feldolgozása futtatást. |
   | **Levonás módosítása befejeződött** | A rendszer automatikusan bejelöli a **Levonás módosítása befejeződött** jelölőnégyzetet, amikor a levonásfrissítési módosítás feldolgozása végrehajtotta a juttatáslevonási módosításokat. |
   
4. A juttatásimérték-beállítások változásainak követéséhez és karbantartásához válassza a **Műveletek**, majd a **Verziók karbantartása** lehetőséget.

5. Válassza a **Mentés** lehetőséget. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
