---
title: Tanfolyamok – áttekintés
description: Ez a cikk bemutatja, hogy az emberi erőforrások rendszergazdái és vezetői hogyan használják a tanfolyamok funkcióit a dolgozók számára elérhető tanfolyamokra vonatkozó információk karbantartásához.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a1fd00fb9feea9ab426f67095770389696452215
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/25/2022
ms.locfileid: "9716283"
---
# <a name="courses-overview"></a>Tanfolyamok – áttekintés

A Microsoft Dynamics 365 Human Resources megoldást biztosít az Ön szervezetének oktatási szükségleteire. Ez a megoldás két tanfolyami útvonalat kínál: *virtuális* és *oktató által vezetett tanfolyamokat*.

*A virtuális* tanulás olyan oktatási tapasztalat, amely az online erőforrások révén tovább tökéletesedik. Az *oktatói képzés során* az oktató egy csoport dolgozó vagy oktató számára tart tanfolyamot.

A oktatási modulban az emberi erőforrásokkal dolgozó szakemberek, rendszergazdák, képzési vezetők és vezetők egyaránt létrehozhatnak, illetve hozzárendelhet oktatási útvonalakat a dolgozókhoz.

> [!NOTE]
> A virtuális tanfolyamok használatához engedélyeznie kell a **Funkciókezelés** Tanfolyam fokozása szolgáltatását.

## <a name="set-up-virtual-courses"></a>Virtuális tanfolyamok beállítása

A virtuális tanfolyamok konfigurálásában engedélyeznie kell **a** Funkciókezelés Tanfolyam-fejlesztés szolgáltatását. Menjen az Új tanfolyamok lehetőségre, és állítsa **a Virtuális \> lehetőséget Igen beállításra** **.** **·** A funkció engedélyezése után szükség van egy tanfolyam hivatkozásra. A **Tanfolyam állapota** mező Nyitott állapotúra **lesz állítva**. Az **Alkalmazott regisztrálásának** **engedélyezése** beállítás Igen, de Nem beállítással **is beállítható.**

Miután a Funkciókezelésben **engedélyezte** a Tanfolyam-fejlesztés funkciót, a következő változások lépnek fel:

- A tanfolyam-hozzárendeléshez meg kell határozni a határidő dátumát.
- Kötelező megadni a tanfolyam hivatkozását.
- **Az alkalmazotti önkiszolgáló** szolgáltatás egy alkalmazott áttekintését mutatja a **tanfolyamokon**. A felhasználó megtekintheti a késedelmes, hamarosan esedékes és hozzárendelt tanfolyamokat.
- A dolgozók virtuális tanfolyamokat fejezhet be, és ön is tanúsíthatja őket.

## <a name="set-up-instructor-led-courses"></a>Tanfolyamvezetők beállítása

Az oktató tanfolyamokat nem kell konfigurálni használat előtt.

A következő információkat nem kötelező megadni a tanfolyamokhoz. Ha ezek az adatok tanfolyamokhoz lesznek megadva, akkor a tanfolyamrekordok létrehozása előtt kell megadni őket:

- Tanfolyamtípus
- Oktatótermi csoportok
- Tanfolyami csoportok
- Tanfolyami helyszínek
- Oktatótermek
- Oktatók
- Tanfolyamtípusok

A tanfolyamtípusokkal *a* tanfolyamok szerkezetük és tartalmaik szerint kategorizálhatja a tanfolyamokat. A tanfolyamtípusokat a Tanfolyamtípusok **lapon hozhatja** létre.

A tanfolyamra regisztrálható résztvevők minimális és maximális számát a **** Tanfolyamok lap Általános gyorslapja határozza **** meg.

### <a name="course-setup-type"></a>Tanfolyamtípus - szakértelem 

*A beállítási* típusok határozzák meg a tanfolyam szerkezetét. A tanfolyamoknak három beállítási típusa van.

| Telepítés típusa | Leírás |
|------|--------|
| Normál | Az ilyen típusú tanfolyamoknak nincs napi napirendje. Ez az alapértelmezett beállítási típus új tanfolyam létrehozásakor. |
| Napirend | Akkor válassza ezt a beállítási típust, ha megterveheti egy több napon át történő tanfolyam egyes napjainak részleteit. |
| Munkamenet + Napirend | <p>Ezt a beállítási típust összetettebb tanfolyamokhoz választhatja ki. A tanfolyam napirendjét *például* szekciókra és munkamenetekre *oszthatja*:</p><ul><li>*A* sávok egy tanfolyam meghatározott tárgyterülete.</li><li>*A* munkamenetek felosztják a szekciókat, és segítik a szekciókhoz kapcsolódó folyamatok és módszerek azonosítását.</li></ul> |

### <a name="course-tasks"></a>Tanfolyami tevékenységek

Minden tanfolyamon a következő feladatokat kell elvégezni:

- Résztvevők regisztrálása.
- A regisztráció határidejének beállítása.
- A résztvevők minimális és maximális számának beállítása.
- A tanfolyam helyszínének és tantermének kiválasztása.
- Ajánlott szállodákból a tanfolyam résztvevőinek.
- Tanfolyam leírásának létrehozása, amely feladható az Alkalmazott önkiszolgáló **rendszer számára**.

> [!NOTE]
> Csak akkor törölhet egy tanfolyamot, ha nincs hozzá regisztráció.

### <a name="course-statuses"></a>Tanfolyam állapota

Az alábbi táblázat felsorolja a tanfolyami állapotokat és az egyes műveleteket.

| Állapot | Műveletek |
|------|--------|
| Létrehozva | <ul><li>Tanfolyami adatok megadása és szerkesztése.</li><li>A tanfolyam állapotának módosítása " **Nyitott" állapotúra**, hogy a dolgozók regisztrálják a tanfolyamot.</li></ul> | 
| Megnyitott | <ul><li>Résztvevő regisztrálása a tanfolyamra</li><li>A tanfolyam résztvevőinek eltávolítása.</li><li>Résztvevő regisztrálása a tanfolyamra</li><li>A Visszaigazolt állapotú ****  **** résztvevők tanfolyami állapotának Módosítása "Lezárva" vagy "Érvénytelenve" **állapotúra.**</li></ul>|
| Lezárt | A tanfolyam anyaga: |
| Törölve | A tanfolyam anyaga: |

### <a name="course-participants"></a>Tanfolyam résztvevői

*A tanfolyam résztvevői* olyan dolgozók, akik részt vesznek egy tanfolyamon vagy eseményen. Csak a nyitott tanfolyamokra regisztrálhat résztvevőket.

### <a name="workflow"></a>Munkafolyamat

Azok az alkalmazottak, akik az Alkalmazott **** önkiszolgáló lapon keresztül regisztrálnak egy tanfolyamra, a regisztrációt egy munkafolyamaton keresztül lehet jóváhagyásra átkedni. A munkafolyamatokat a **** Tanfolyamok lap Általános gyorslapján rendelheti hozzá egy tanfolyamhoz **** .
