---
title: A kelet-európai elszámolási tranzakciók megtekintése
description: Ez a cikk a vevők és szállítók kiegyenlítési tranzakciói lapról nyújt tájékoztatást.
author: EvgenyPopovMBS
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustVendTransPostingLog_RU
audience: Application User
ms.reviewer: kfend
ms.custom: 270544
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b45dc7a8213c753491c367cef36d7dc1111270c4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856548"
---
# <a name="view-transactions-on-settlement-for-eastern-europe"></a>A kelet-európai elszámolási tranzakciók megtekintése

[!include [banner](../includes/banner.md)]

Ez a cikk a vevők és szállítók kiegyenlítési tranzakciói lapról nyújt tájékoztatást.

Használja az **Elszámolási tranzakciók** lapot a vevők vagy szállítók összetett kiegyenlítési tranzakcióival kapcsolatos információk megtekintésére. Ez a funkció csak az olyan jogi személyek esetében működik, amelyeknek Litvániában, Lettországban, Észtországban, Csehországban, Magyarországon vagy Lengyelországban van az elsődleges címe. Az **Elszámolási tranzakciók** lapot az alábbi helyeken találja:

-   **Kötelezettségek** &gt; **Szállítók** &gt; **Minden szállító**. A **Szállító** lap műveletpaneljén kattintson a **Tranzakciók** &gt; **Tranzakciók** elemre. A **Szállítói tranzakciók** lapon válasszon ki egy tranzakciót, és kattintson az **Elszámolási tranzakciók** elemre.
-   **Kinnlevőségek** &gt; **Vevők** &gt; **Minden vevő**. A **Vevő** lap műveletpaneljén kattintson a **Tranzakciók** elemre. A **Vevői tranzakciók** lapon válasszon ki egy tranzakciót, és kattintson az **Elszámolási tranzakciók** elemre.

A rendszer rögzíti az elszámolással kapcsolatos információkat, amelyek megjeleníthetők az **Elszámolási tranzakciók** oldalon azon tranzakcióknál, amelyek a következő helyzetekben jöttek létre:

-   **Árfolyam-korrekció** - amikor egy számla kiegyenlítése és a fizetés realizált vagy nem realizált árfolyam-különbözetet okoz.
-   **Feladási profil módosítása** – Két bejegyzés, például egy számla és egy jóváírás, amelyeknél különböző feladási profilok vannak beállítva.
-   Az előlegfizetés fizetéssé vagy a fizetés előleggé van alakítva.
-   **Készpénzfizetési engedmény** - egy számla olyan fizetéssel való kiegyenlítése, amelyből levontak egy engedményösszeget.
-   **Filléreltérés** – Egy számla kiegyenlítése olyan fizetéssel történik, amely némileg eltérő összeget a számlán szereplőhöz képest.
-   **Feltételes adófeladás** - Egy számla olyan fizetéssel való kiegyenlítése, amelyre feltételes adó vonatkozik;
-   **Több vállalatot érintő kiegyenlítés** – Vállalatközi funkció, amely segítségével egy számla egy szervezettől eredő fizetéssel egyenlíthető ki.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]