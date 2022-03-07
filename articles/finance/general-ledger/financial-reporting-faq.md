---
title: Pénzügyi jelentéskészítés – GYIK
description: Ez a témakör a pénzügyi jelentéskészítéssel kapcsolatos néhány gyakran ismételt kérdésre ad választ.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e1b67f86446403933005008a9a1e2cc6739dc516
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266633"
---
# <a name="financial-reporting-faq"></a>Pénzügyi jelentéskészítés – GYIK

Ez a témakör a pénzügyi jelentéskészítéssel kapcsolatos gyakran ismételt kérdésekre ad választ.

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a>Hogyan lehet korlátozni a jelentésekhez való hozzáférést a fa biztonsági beállítás használatával?

A következő példák bemutatják, hogyan lehet korlátozni a jelentésekhez való hozzáférést a fa biztonsági beállítás használatával.

Az USMF bemutatóvállalat **mérlegkimutatást** készít, amelyhez a pénzügyi jelentéskészítési funkció nem minden felhasználójának kellene hozzáférnie. A fa biztonsági beállítással korlátozhatja az adott jelentéshez való hozzáférést, amelyet így csak bizonyos felhasználók érhetnek el.

1. Bejelentkezés a Financial Reporter Report Designer alkalmazásba.
2. Válassza a **Fájl \> Új \> Fadefiníció** lehetőséget egy új fadefiníció létrehozásához.
3. Koppintson duplán (vagy kattintson duplán) az **Összegzés** sorra az **Egység biztonsága** oszlopban.
4. Válassza ki a **Felhasználók és csoportok** lehetőséget.
5. Válassza ki azokat a felhasználókat vagy csoportokat, amelyeknek hozzá kell férnie a jelentéshez.
6. Válassza a **Mentés** lehetőséget.
7. A jelentésdefinícióban adja meg az új fadefiníciót.
8. A fadefinícióban válassza ki a **Beállítások** lehetőséget. Majd a **Jelentési egység kiválasztása** pont alatt válassza az **Összes egységgel együtt** lehetőséget.

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a>Hogyan tudom meghatározni, hogy mely számlák nem egyeznek meg az egyenlegeimmel?

Ha a jelentés egyenlegei nem egyeznek meg, az alábbi eljárásokkal azonosíthatja a számlát és az eltérést.

### <a name="in-financial-reporter-report-designer"></a>Itt: Financial Reporter Report Designer

1. Hozzon létre egy új sordefiníciót.
2. Válassza ki a **Szerkesztés \> Sorok beszúrása dimenziókból** lehetőséget.
3. Válassza ki a **Főszámla** lehetőséget.
4. Válassza ki az **OK** lehetőséget.
5. Mentse a sordefiníciót.
6. Hozzon létre egy új oszlopdefiníciót.
7. Hozzon létre új jelentésdefiníciót.
8. Válassza ki a **Beállítások** lehetőséget és törölje az opció kijelölését.
9. Hozza létre a jelentést. 
10. Exportálja a jelentést a Microsoft Excel szoftverbe.

### <a name="in-dynamics-365-finance"></a>Itt: Dynamics 365 Finance

1. Lépjen a **Főkönyv \> Lekérdezések és jelentések \> Főkönyvi kivonat** lehetőségre.
2. Állítsa be a következő mezőket:

    - **Kezdő dátum** – Adja meg a pénzügyi év kezdő dátumát.
    - **Záró dátum** – Adja meg a dátumot, amelyhez létrehozza a jelentést.
    - **Pénzügyi dimenzió** – Állítsa ezt a mezőt a **Fő számlakészlet** lehetőségre.

3. Válassza ki a **Számítás** lehetőséget.
4. Exportálja a jelentést Excelbe.

Most már a **főkönyvi kivonati** jelentésbe másolhatja az Excelben létrehozott pénzügyi jelentést, hogy összehasonlítsa a **Záró egyenleg** oszlopokat.

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a>Amikor jelentést tervezek a Report Designerben, vagy amikor pénzügyi jelentést készítek, a következő üzenet jelenik meg: „A műveletet nem lehet végrehajtani az adatszolgáltató keretrendszerében fellépő probléma miatt.” Hogyan reagáljak rá?

Az üzenet azt jelzi, hogy hiba történt, amikor a rendszer megpróbálta lekérni a pénzügyi metaadatokat az adatpiacról a Pénzügyi jelentéskészítés használata közben. Erre a problémára kétféleképpen tud reagálni:

- Tekintse át az adatok integrációs állapotát a Report Designerben lévő **Eszközök \> Integráció állapota** segítségével. Ha az integráció még nem fejeződött be, várjon, amíg befejeződik. Ezután próbálja meg újra elvégezni azt, amit az üzenet megjelenésekor szeretett volna.
- Forduljon az ügyfélszolgálathoz a probléma azonosítása és megoldása érdekében. Inkonzisztens adatok lehetnek a rendszerben. A támogatási szakemberek segítséget tudnak nyújtani a kiszolgálón lévő probléma azonosításában, és a frissítéshez szükséges konkrét adatok megkeresésében.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
