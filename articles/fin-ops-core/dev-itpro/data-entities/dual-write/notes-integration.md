---
title: Megjegyzésintegráció
description: Ez a témakör a megjegyzésadatok integrációját ismerteti a kettős írásban.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 3ff40011ac60c47f6ed667adfcf01bc727334f13
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358979"
---
# <a name="note-integration"></a>Megjegyzésintegráció

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Az üzleti folyamatok során a Microsoft Dynamics 365 felhasználói gyakran gyűjtenek információkat a vevőikről. Ezt az információt tevékenységekként és megjegyzésekként rögzíti a rendszer. Ez a témakör a megjegyzésadatok integrációját ismerteti a kettős írásban.

A vevői adatok a következőképpen osztályozhatók:

+ **Egy Dynamics 365-felhasználó által a vevő nevében kezelhető információk** – például a Contoso (Dynamics 365-ös felhasználó) játékbemutatót vezet. A Contoso egyik ügyfele (egy vevő) részt szeretne venni a játékbemutatón. A vevő megkéri a Contoso egyik alkalmazottját, hogy foglaljon helyet neki a bemutatón. A foglalás a Contoso rendezvény résztvevőinek naptárában történik.
+ **A Dynamics 365 felhasználója esetében kezelhető adatok** – például egy olyan vevő, aki egy Felületi egységet vásárol, különleges utasításokat ad meg, amelyek azt jelzik, hogy az eszközt ajándékcsomagolással kell ellátni a szállítás előtt. Ezek az utasítások olyan kezelhető információkat tartalmaznak, amelyet a csomagolásért felelős Contoso alkalmazottnak kell kezelnie.
+ **Nem használható adatok** – például egy vevő felkeresi a Contoso üzletét, és az üzlet egyik munkatársával folytatott beszélgetés során kifejezi érdeklődését a *Halo* játékok és különböző videojáték-kiegészítők iránt. Az üzlet munkatársa feljegyzi ezt az információt. A termékajánlási motor ezt arra használja, hogy ajánlatokat jelenítsen meg a vevőnek.

Általános szabály, hogy a használható adatok *tevékenységekként* vannak rögzítve a Finance and Operations alkalmazásokban és az ügyfélkapcsolati alkalmazásokban. A nem használható adatok *megjegyzésekként* vannak rögzítve a Finance and Operations alkalmazásokban és *jegyzetekként* az ügyfélkapcsolati alkalmazásokban.

> [!TIP]
> Bár a megjegyzések nem használható adatok, az alkalmazások nem akadályozzák meg abban, hogy ezeket az adatokat kezelhető információkként tárolj és kezelje, ha ezt szeretné.

A Microsoft jelenleg a megjegyzésintegrációs funkció kiadásán dolgozik. (A tevékenységintegrációs funkciók kiadása később következik.) A megjegyzésintegráció a vevőkhöz, szállítókhoz, értékesítési rendelésekhez és beszerzési rendelésekhez használható.

## <a name="create-a-note-in-a-customer-engagement-app"></a>Megjegyzés létrehozása egy ügyfélkapcsolati alkalmazásban

Ha megjegyzést szeretne létrehozni egy ügyfélkapcsolati alkalmazásban, majd szinkronizálni azt a Finance and Operations alkalmazással, kövesse az alábbi lépéseket.

1. Nyissa meg egy vevő számlarekordját az ügyfélkapcsolati alkalmazásban.
2. Az **Idősor** ablaktáblán válassza a pluszjelet (**+**), majd a **Megjegyzés** gombra kattintva hozzon létre egy megjegyzést.

    ![Megjegyzés létrehozása az ügyfélkapcsolati alkalmazásban.](media/notes-ce-1.png)

3. Írja be a kívánt címet és leírást, majd válassza a **Megjegyzés hozzáadása** lehetőséget.

    ![A kívánt cím és leírás megadása.](media/notes-ce-2.png)

    Az új megjegyzés hozzáadódik a vevői idősorhoz.

    ![Új megjegyzés a vevői idősoron.](media/notes-ce-3.png)

4. Jelentkezzen be a Finance and Operations alkalmazásba, és nyissa meg ugyanazt a vevői rekordot. Láthatja, hogy jobb felső sarokban látható **Mellékletek** gomb (gemkapocs szimbólum) jelzi, hogy a rekordhoz melléklet van csatolva.

    ![Értesítés mellékletről.](media/notes-ce-4.png)

5. Kattintson a **Mellékletek** gombra a **Mellékletek** oldal megnyitásához. Az ügyfélkapcsolati alkalmazásban meg kell találnia a létrehozott megjegyzést.

    ![Megjegyzés az ügyfélkapcsolati alkalmazásból.](media/notes-ce-5.png)

A megjegyzés frissítései oda-vissza szinkronizálódnak az alkalmazás és a Finance and Operations alkalmazás és az ügyfélkapcsolati alkalmazás között.

## <a name="create-a-note-in-a-finance-and-operations-app"></a>Megjegyzés létrehozása egy Finance and Operations alkalmazásban

Létrehozhat egy megjegyzést egy Finance and Operations alkalmazásban, majd szinkronizálhatja az ügyfélkapcsolati alkalmazással.

Ha megjegyzést szeretne létrehozni egy Finance and Operations alkalmazásban, majd szinkronizálni azt egy ügyfélkapcsolati alkalmazással, kövesse az alábbi lépéseket.

1. A Finance and Operations alkalmazásban a **Mellékletek** oldalon válassza az **Új** \> **Megjegyzés** lehetőséget.

    ![Megjegyzés létrehozása a Finance and Operations alkalmazásban.](media/notes-fo-1.png)

2. Adjon meg egy címet és egy rövid utasításkészletet, majd válassza a **Mentés** lehetőséget.

    ![A kívánt cím és az utasítások megadása.](media/notes-fo-2.png)

3. Frissítse a rekordot az ügyfélkapcsolati alkalmazásban. Az új megjegyzésnek az idősorban kell lennie.

    ![Új megjegyzés az ügyfélkapcsolati alkalmazás idősorán.](media/notes-fo-3.png)

A megjegyzéseket belsőként és külsőként is osztályozhatja.

- Nyissa meg a megjegyzést a Finance and Operations alkalmazásban a **Mellékletek** oldalon, majd a **Korlátozás** mezőben válassza a **Belső** vagy a **Külső** lehetőséget.

    ![Korlátozás mező.](media/notes-fo-4.png)

URL-címet is létrehozhat

1. A Finance and Operations alkalmazásban a **Mellékletek** oldalon válassza az **Új** \> **URL** lehetőséget.
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
