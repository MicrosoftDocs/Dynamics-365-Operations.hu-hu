---
title: Megjegyzésintegráció
description: Ez a témakör a megjegyzésadatok integrációját ismerteti a kettős írásban.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c73da804d724ea75ae6ccd479d1b7f3cf02d48c4
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062775"
---
# <a name="note-integration"></a>Megjegyzésintegráció

[!include [banner](../../includes/banner.md)]



Az üzleti folyamatok során a Microsoft Dynamics 365 felhasználói gyakran gyűjtenek információkat a vevőikről. Ezt az információt tevékenységekként és megjegyzésekként rögzíti a rendszer. Ez a témakör a megjegyzésadatok integrációját ismerteti a kettős írásban.

A vevői adatok a következőképpen osztályozhatók:

+ **Egy Dynamics 365-felhasználó által a vevő nevében kezelhető információk** – például a Contoso (Dynamics 365-ös felhasználó) játékbemutatót vezet. A Contoso egyik ügyfele (egy vevő) részt szeretne venni a játékbemutatón. A vevő megkéri a Contoso egyik alkalmazottját, hogy foglaljon helyet neki a bemutatón. A foglalás a Contoso rendezvény résztvevőinek naptárában történik.
+ **A Dynamics 365 felhasználója esetében kezelhető adatok** – például egy olyan vevő, aki egy Felületi egységet vásárol, különleges utasításokat ad meg, amelyek azt jelzik, hogy az eszközt ajándékcsomagolással kell ellátni a szállítás előtt. Ezek az utasítások olyan kezelhető információkat tartalmaznak, amelyet a csomagolásért felelős Contoso alkalmazottnak kell kezelnie.
+ **Nem műveletre használható adatok** – például egy vevő felkeresi a Contoso üzletét, és az üzlet egyik munkatársával folytatott beszélgetés során kifejezi érdeklődését a *Halo* játék és különböző videojáték-kiegészítők iránt. Az üzlet munkatársa feljegyzi ezt az információt. A termékajánlási motor ezt arra használja, hogy ajánlatokat jelenítsen meg a vevőnek.

Általánosságban elmondható, hogy a cselekvésre alkalmas információkat úgy rögzítjük *tevékenységek* a Finance and Operations és az ügyfélelköteleződési alkalmazásokban. A nem végrehajtható információk rögzítése a következőként történik: *jegyzetek* a Finance and Operations alkalmazásokban, és mint *megjegyzések* az ügyfelek bevonására szolgáló alkalmazásokban.

> [!TIP]
> Bár a megjegyzések nem használható adatok, az alkalmazások nem akadályozzák meg abban, hogy ezeket az adatokat kezelhető információkként tárolj és kezelje, ha ezt szeretné.

A Microsoft jelenleg a megjegyzésintegrációs funkció kiadásán dolgozik. (A tevékenységintegrációs funkciók kiadása később következik.) A megjegyzésintegráció a vevőkhöz, szállítókhoz, értékesítési rendelésekhez és beszerzési rendelésekhez használható.

## <a name="create-a-note-in-a-customer-engagement-app"></a>Megjegyzés létrehozása egy ügyfélkapcsolati alkalmazásban

Ha feljegyzést szeretne létrehozni egy ügyfél-elköteleződési alkalmazásban, majd szinkronizálja azt egy Finance and Operations alkalmazással, kövesse az alábbi lépéseket.

1. Nyissa meg egy vevő számlarekordját az ügyfélkapcsolati alkalmazásban.
2. Az **Idősor** ablaktáblán válassza a pluszjelet (**+**), majd a **Megjegyzés** gombra kattintva hozzon létre egy megjegyzést.

    ![Megjegyzés létrehozása az ügyfélkapcsolati alkalmazásban.](media/notes-ce-1.png)

3. Írja be a kívánt címet és leírást, majd válassza a **Megjegyzés hozzáadása** lehetőséget.

    ![A kívánt cím és leírás megadása.](media/notes-ce-2.png)

    Az új megjegyzés hozzáadódik a vevői idősorhoz.

    ![Új megjegyzés a vevői idősoron.](media/notes-ce-3.png)

4. Jelentkezzen be a Finance and Operations alkalmazásba, és nyissa meg ugyanazt az ügyfélrekordot. Láthatja, hogy jobb felső sarokban látható **Mellékletek** gomb (gemkapocs szimbólum) jelzi, hogy a rekordhoz melléklet van csatolva.

    ![Értesítés mellékletről.](media/notes-ce-4.png)

5. Kattintson a **Mellékletek** gombra a **Mellékletek** oldal megnyitásához. Az ügyfélkapcsolati alkalmazásban meg kell találnia a létrehozott megjegyzést.

    ![Megjegyzés az ügyfélkapcsolati alkalmazásból.](media/notes-ce-5.png)

A feljegyzés minden frissítése oda-vissza szinkronizálódik a Finance and Operations alkalmazás és az ügyfél-elköteleződés alkalmazás között.

## <a name="create-a-note-in-a-finance-and-operations-app"></a>Jegyzet létrehozása a Finance and Operations alkalmazásban

A Finance and Operations alkalmazásban is létrehozhat jegyzetet, amely szinkronizálva lesz egy ügyfél-elköteleződési alkalmazással.

Ha feljegyzést szeretne létrehozni egy Finance and Operations alkalmazásban, majd szinkronizálja azt egy ügyfél-elköteleződési alkalmazással, kövesse az alábbi lépéseket.

1. A Finance and Operations alkalmazásban a **Mellékletek** oldal, válassza ki **Új** \> **jegyzet**.

    ![Jegyzet létrehozása a Finance and Operations alkalmazásban.](media/notes-fo-1.png)

2. Adjon meg egy címet és egy rövid utasításkészletet, majd válassza a **Mentés** lehetőséget.

    ![A kívánt cím és az utasítások megadása.](media/notes-fo-2.png)

3. Frissítse a rekordot az ügyfélkapcsolati alkalmazásban. Az új megjegyzésnek az idősorban kell lennie.

    ![Új megjegyzés az ügyfélkapcsolati alkalmazás idősorán.](media/notes-fo-3.png)

A megjegyzéseket belsőként és külsőként is osztályozhatja.

- A Finance and Operations alkalmazásban a **Mellékletek** oldalon nyissa meg a jegyzetet, majd a **Korlátozás** mezőben válassza ki **Belső** vagy **Külső**.

    ![Korlátozás mező.](media/notes-fo-4.png)

URL-címet is létrehozhat

1. A Finance and Operations alkalmazásban a **Mellékletek** oldal, válassza ki **Új** \> **URL**.
2. Adja meg a címet és az URL-t.
3. A **Korlátozás** mezőben válassza a **Belső** vagy a **Külső** lehetőséget.

    ![URL létrehozása a Finance and Operations alkalmazásban.](media/notes-fo-5.png)

4. Válassza a **Mentés** lehetőséget.

    Mivel az ügyfélkapcsolati alkalmazásoknak nincs URL-típusa, az URL-cím megjegyzésként kettős írással van integrálva.

    ![URL megjegyzésként jelenik meg az ügyfélkapcsolati alkalmazásban.](media/notes-ce-6.png)

> [!NOTE]
> A fájlmellékletek nem támogatottak.

## <a name="templates"></a>Sablonok

A megjegyzésintegráció tartalmazza azokat a táblaleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.

| Finance and Operations alkalmazás | Customer Engagement alkalmazás | Leírás |
|----------------------------|-------------------------|-------------|
| [Vevői mellékletek](mapping-reference.md#230) | Jegyzetek | Azon vállalatok, amelyek egyszerű szöveges és URL-címekkel rögzítik a vevőspecifikus információkat (szervezetek és személyek számára is). |
| [Szállítóidokumentum-mellékletek](mapping-reference.md#231) | Jegyzetek | Azon vállalatok, amelyek egyszerű szöveges és URL-címekkel rögzítik a szállítóspecifikus információkat (szervezetek és személyek számára is). |
| [Értékesítési rendelési fejléc bizonylatmellékletei](mapping-reference.md#229) | Jegyzetek | Azok a vállalatok, amelyek egyszerű szöveges és URL-címekkel rögzítik az értékesítési rendelésekre jellemző adatokat. |
| [Beszerzési rendelési fejléc bizonylatmellékletei](mapping-reference.md#232) | Jegyzetek | Azok a vállalatok, amelyek egyszerű szöveges és URL-címekkel rögzítik a beszerzési rendelésekre jellemző adatokat. |

## <a name="limitations"></a>Korlátozások

Ha már telepítette a megjegyzések megoldást, akkor azt nem lehet eltávolítani. 

További tájékoztatás: [Kettős írású leképezési hivatkozás](mapping-reference.md).
