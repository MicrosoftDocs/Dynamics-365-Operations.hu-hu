---
title: Pénzügyi jelentéskészítés – GYIK
description: Ebben a témakörben más felhasználóknál a pénzügyi jelentéskészítéssel kapcsolatban felmerült kérdésekre adunk választ.
author: jiwo
manager: tfehr
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2d49213ea18e09f04b026559bdca49fee1de0ef7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249304"
---
# <a name="financial-reporting-faq"></a>Pénzügyi jelentéskészítés – GYIK 

Ebben a témakörben más felhasználóknál a pénzügyi jelentéskészítéssel kapcsolatban felmerült kérdésekre adunk választ. 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>Hogyan lehet korlátozni a jelentésekhez való hozzáférést a Fa biztonsági beállítással?

Eset: Az USMF bemutatóvállalat mérlegkimutatás készít, és nem szeretné, hogy a pénzügyi jelentéskészítési funkció minden felhasználója megtekinthesse a kimutatást a D365-ben. Megoldás: A Fa biztonsági beállítással korlátozhatja az adott jelentéshez való hozzáférést, amelyet így csak bizonyos felhasználók érhetnek el. 

1.  Jelentkezzen be a Pénzügyi jelentés – Jelentéstervező alkalmazásba.

2.  Hozzon létre egy új fadefiníciót (Fájl | Új | Fadefiníció). a.    Kattintson duplán az **Összegzés** sorra az **Egység biztonsága** oszlopban.
  i.    Kattintson a Felhasználók és csoportok elemre.  
          1. Válassza ki azokat a felhasználókat vagy csoportokat, amelyeknek szeretne hozzáférést adni a jelentéshez. 
          
[![felhasználói képernyő](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)

[![biztonsági képernyő](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)

  b.    Kattintson a **Mentés** gombra.
  
[![mentés gomb](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)

3.  A Jelentésdefiníció résznél adja meg az új fadefiníciót.

[![fadefiníció űrlapja](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)

A.  A fadefinícióban kattintson a Beállítás elemre, és a „Jelentési egység kiválasztása” résznél jelölje be „Az összes egységgel együtt” jelölőnégyzetet.

[![jelentési egység kiválasztása űrlap](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)

**Előtte:** [![előtte képernyőkép](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)

**Utána:** [![utána képernyőkép](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)

Megjegyzés: A fenti üzenet oka az, hogy a felhasználónak az Egység biztonsága alkalmazása után nincs hozzáférése a jelentéshez.



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a>Hogyan tudom meghatározni, hogy mely számlák nem egyeznek meg az egyenlegeimmel a D365-ben?

Ha a jelentés értékei nem egyeznek a D365-ben várt értékekkel, az alábbi lépésekkel azonosíthatja az ilyen számlákat, valamint az eltéréseket. 

### <a name="in-financial-reporter-report-designer"></a>A Pénzügyi jelentés – Jelentéstervező alkalmazásban

1.  Hozzon létre egy új sordefiníciót. a.    Kattintson a Szerkesztés | Sorok beszúrása dimenziókból lehetőségre. i.  Válassza a MainAccount lehetőséget [![Válassza a Főképernyő lehetőséget_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)
    
    ii. Kattintson az OK gombra. b.    Mentse a sordefiníciót.

2.  Hozzon létre új oszlopdefiníciót.     [![Hozzon létre új oszlopdefiníciót](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)

3.  Hozzon létre új jelentésdefiníciót. a.    Kattintson a Beállítások gombra, és törölje a következőt: [![Beállítási űrlap](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)
   
4.  Hozza létre a jelentést. 

5.  Exportálja a jelentést Excelbe.

### <a name="in-d365"></a>A D365-ben: 
1.  Kattintson a Főkönyv | Lekérdezések és jelentések | Főkönyvi kivonat lehetőségre. a.    Paraméterek. i.  Kezdő dátum: a pénzügyi év kezdete. ii. Záró dátum: a jelentés létrehozásának dátuma. iii.    Pénzügyi dimenziókészlet, „Fő számlakészet” [![Fő számla űrlapja](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)
      
  b.    Kattintson a Számítás lehetőségre.

2.  Exportálja a jelentést Excelbe.

Most már a D365 főkönyvi kivonati jelentésébe másolhatja az Excelben létrehozott pénzügyi jelentés, és összehasonlíthatja a „Záró egyenleg” oszlopokat.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]