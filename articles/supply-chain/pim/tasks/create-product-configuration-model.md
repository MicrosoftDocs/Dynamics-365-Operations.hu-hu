---
title: Termékkonfigurációs modell létrehozása
description: Ez az eljárás bemutatja, hogyan lehet egy termékkonfigurációs modellt létrehozni, és alapvető információkat megadni, például attribútumok és alösszetevők.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca99c0346a3f982164076167c3429587aac18be6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568424"
---
# <a name="create-a-product-configuration-model"></a>Termékkonfigurációs modell létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet egy termékkonfigurációs modellt létrehozni, és alapvető információkat megadni, például attribútumok és alösszetevők. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-a-product-model"></a>Termékmodell létrehozása

1. Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.
1. Válassza az **Új** lehetőséget.
1. Írjon be egy értéket a **Név** mezőbe.
1. Írjon egy értéket a **Leírás** mezőbe.
1. Válasszon ki egy lehetőséget a **Feloldóstratégia** mezőben.
    * A feloldási stratégia határozza meg, hogy hogyan kerülnek feldolgozásra egy megszorításon alapuló termékkonfigurációs modellben a megszorítások. Ez a választás hatással lehet a termékkonfigurációs modell teljesítményére.  
1. Írjon be egy értéket a **Név** mezőbe.
    * A legfelső szintű összetevő felel meg a termékkonfigurációs modellnek, de használható más termékmodellekben is.  
1. Válassza ki az **OK** lehetőséget.
1. Válasszon ki egy lehetőséget a **Konfigurációk újbóli felhasználása** mezőben.
    * Ha a konfigurációk újbóli használatához tartozó paraméter értéke Igen, a rendszer minden egyes konfigurációs munkamenet után ellenőrzi, hogy vannak-e azonos konfigurációk, és újrafelhasználást végez, ha pontos egyezést talál.  

## <a name="add-attributes"></a>Attribútumok hozzáadása

1. Bontsa ki az **Attribútumok** szakaszt.
2. Válassza a **Hozzáadás** lehetőséget.
3. A listában jelölje meg a kiválasztott sort.
4. Írjon be egy értéket a **Név** mezőbe.
5. Írjon be egy értéket a **Feloldónév** mezőbe.
    * A feloldónevet a termékkonfiguráló a megszorításfeloldója használja. Nem tartalmazhat szóközt vagy különleges karaktert kivéve: _(aláhúzás).  
6. Írjon egy értéket a **Leírás** mezőbe.
    * A leírószöveg megjelenik a konfiguráció felhasználója számára, és ezért segítségként alkalmazható a megfelelő attribútumérték kiválasztásához.  
7. Az **Attribútumtípus** mezőben adjon meg vagy válasszon ki egy értéket.
    * Az attribútum típusa határozza meg, hogy mely értékeket érhetők el az attribútum esetében.  
8. Jelölje be a **Felvétel az újrahasználhatók közé** jelölőnégyzetet.
    * Ez a lehetőség csak akkor érhető el, ha a Konfigurációk újbóli használata lehetőség ki van választva. Amennyiben az attribútumra vonatkozik az Újbóli használat jelölőnégyzet, az azt jelenti hogy a rendszer figyelembe veszi ezt az attribútumot, amikor pontos egyezést keres.  

## <a name="add-subcomponents"></a>Alösszetevők hozzáadása

1. Bontsa ki az **Alösszetevők** szakaszt.
2. Válassza a **Hozzáadás** lehetőséget.
3. A listában jelölje meg a kiválasztott sort.
4. Írjon be egy értéket a **Név** mezőbe.
5. Írjon be egy értéket a **Feloldónév** mezőbe.
6. Írjon egy értéket a **Leírás** mezőbe.
7. Az **Összetevő** mezőben adjon meg vagy válasszon ki egy értéket.
    * Minden alösszetevőnek hivatkoznia kell egy összetevő-definícióra. Ez a tervezés támogatja az újrafelhasználható összetevőket, és gondoskodik arról, hogy összetevő a definiálása után sok termékmodellekben alkalmazható legyen.  
8. Válassza a **Mentés** lehetőséget.
9. Válassza ki az **Anyagjegyzéksor részletei** lehetőséget.
    * Az Anyagjegyzéksor részletei űrlap lehetővé teszi, hogy a felhasználó kiválaszthassa az alösszetevő tulajdonságait. Minden tulajdonságnak lehet egy rögzített értéket adni, vagy hozzá lehet rendelni őket egy-egy attribútumhoz. Attribútumhoz rendeléskor az Anyagjegyzéksor tulajdonság értéke eltérő lesz a kiválasztott konfigurációtól függően.  
10. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.
    * Az egyes alösszetevők egy megszorításon alapuló konfigurációs technológiát használó konfigurálható alapterméket jelentenek. A hivatkozás a cikkszámon keresztül történik.  
11. Jelölje be a **Beállít** jelölőnégyzetet.
12. Válassza ki az **Igen** lehetőséget a **Számítás** mezőben.
    * A számítási beállítást megadva lehet biztosítani, hogy a rendszer figyelembe vegye a terméket, amikor a termék költségszámítását végzi.  
13. Válassza ki a **Beállítás** fület.
14. Jelölje be a **Beállít** jelölőnégyzetet.
15. Adjon meg egy számot a **Mennyiség** mezőben.
    * A mennyiség mező meghatározza, hogy ebből a termékből mennyi kerül felhasználásra a konfigurált termékben.  
16. Jelölje be a **Beállít** jelölőnégyzetet.
17. A **Sorozatonként** mezőben adjon meg egy számot.
18. Válassza ki az **OK** lehetőséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]