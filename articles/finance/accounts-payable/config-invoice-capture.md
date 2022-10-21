---
title: A Számlarögzítési megoldás konfigurálása
description: Ez a cikk bemutatja a Számlarögzítési megoldás konfigurálját.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: e297dafc930368f14f2e68213ce4153ba792ef4d
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690983"
---
# <a name="configure-the-invoice-capture-solution"></a>A Számlarögzítési megoldás konfigurálása

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A Számlarögzítés megoldás telepítése után konfigurálni kell a környezetet. A folyamat a következő alapvető lépésekből áll.

1. **Kötelező:** Szinkronizálja a jogi személyeket a Microsoft Dynamics 365 Pénzügy rendszerből. Ezzel a lépéssel lehet beállítani a szervezeti struktúrát a Microsoft Power Platform.
2. **Kötelező:** Állítsa be a csatornákat a számlaképek importálásához. A megoldás a következő csatornákat támogatja:

    - Office 365 Outlook (alapértelmezett)
    - Outlook.com
    - OneDrive
    - SharePoint

3. **Választható:** Az optikai karakterfelismerési (OCR) szolgáltatás további konfigurációs csoportjait adhatja meg.
4. **Választható: Hozzárendelési** szabályok meghatározása a jogi személyhez, a szállítói számlához, a cikkhez és a beszerzés típushoz.

Ez a cikk a folyamat két szükséges lépését fókuszálja. A konfigurációs csoportokkal kapcsolatos további tudnivalókat lásd [a Számlarögzítési megoldás konfigurációs csoportjaiban](invoice-capture-config-group.md). A hozzárendelési szabályokkal kapcsolatos további tudnivalókat lásd [a Számlarögzítési megoldás hozzárendelési szabályaiban](invoice-capture-mapping-rules.md).

## <a name="manage-legal-entities"></a>Jogi személyek kezelése

A Pénzügy rendszer jogi személyekként határozza meg a jogi személyeket, amelyek a jogi hatóságokkal való regisztráción keresztül vannak meghatározva. Az üzleti tevékenységeket különböző jogi személyek végzik és rögzítik. Az Microsoft Power Platform üzleti egységeknél a biztonsági szerepkörök és a felhasználók a szerepkör-alapú biztonsági modellnek megfelelő módon kapcsolódnak egymáshoz.

Az üzleti egységeket a biztonsági szerepkörökkel együtt az adatelérés szabályozására használják. A felhasználók csak az adatokat látják, amelyekre szükség van a munkakörük ehhez. A Számlarögzítés megoldás konfigurációs helyet biztosít, ahol betölthetők a Pénzügyben található meglévő jogi személyek alapvető adatai, és kezelhetők a manuálisan létrehozott entitások. A jogi személyek a szállítói számlákon és a biztonsági ellenőrzésben használatosak.

Jogi személy létrehozásakor és listanézetben való megtekintésekor automatikusan létrejön egy azonos nevű alapértelmezett üzleti egység. A csoport a ap adminisztrátor biztonsági **szerepkört** kap. Jogi személyek importálásakor a Pénzügy alapadatok importálása történik meg. A jogi személy azonosítja a nem létező cikkeket, és hozzáadja őket a Számlarögzítési megoldáshoz. Az alapértelmezett konfigurációs csoport új jogi személyekhez van hozzárendelve.

### <a name="sync-legal-entities"></a>Jogi személyek szinkronizálása

Jogi személyeket nem lehet közvetlenül létrehozni. A jogi személyek azonban szinkronizálhatók a Pénzügy rendszerből. A jogi személyek szinkronizálását a következő lépések szerint hajtsa végre.

1. Ugrás a Jogi **személyek \> kezelése beállítási \> rendszer beállításához**.
2. Válassza a **Szinkronizálás jogi személyeket**, majd kattintson az **OK** gombra a megerősítő párbeszédpanelen.

A szinkronizálás befejezése után megjelenik az új jogi személyek száma. Az új jogi személyek jelennek meg a listanézetben. Az alapértelmezett konfigurációs csoport az új jogi személyekhez van hozzárendelve.

## <a name="configure-invoice-import-channels"></a>Számlaimport-importáló csatornák konfigurálása

A szállítók különböző formátumokban (papíron vagy képen) küldik a különböző csatornákból származó számlákat (e-mail, fájl munkaterülete vagy számlaportál). A Számlarögzítés megoldás kezelni tudja a különböző csatornákat és formátumokat. A következő típusok támogatottak:

- Office 365 Outlook
- Outlook.com
- SharePoint
- OneDrive

Amikor csatornát hoznak létre egy adott számlához, a rendszer egy előre meghatározott sablont is tartalmazó automatikus folyamat, amely a beérkezett üzenetek vagy fájlok bejövő e-mailjeinek vagy fájljainak a figyelése alapján jön létre. Bármely érvényes számlával rendelkező fájlt fel lehet ismerni és el lehet küldeni a számlázási területre, hogy a kötelezettségkezelő adminisztrátor által feldolgozható legyen. A mellékletnek PDF formátumban vagy képformátumban kell lennie. A számlák a csatorna-konfigurációnak megfelelően betölthetőek a Számlarögzítés megoldásba.

### <a name="create-a-channel"></a>Csatorna létrehozása

Ha importálta a további megoldáscsomagot (Dynamics 365 Számlarögzítés – Telepítési eszközök), Office 365 akkor az Outlook alapértelmezett kapcsolata készen áll a használatra. Ha több kapcsolatot szeretne létrehozni különböző e-mail fiókokhoz vagy más csatornatípusokhoz, akkor lásd [: További kapcsolatok létrehozása a csatornákhoz.](invoice-capture-advanced-settings.md#create-additional-connections-for-channels)

A csatorna létrehozásához kövesse az alábbi lépéseket.

1. Ugrás a Rendszerbeállítás **konfigurációs \>\> csatornái beállításához**
2. Válassza az **Új** lehetőséget.
3. Állítsa be a következő mezőket:

    - Csatorna neve
    - Leírás
    - Típus
    - Kapcsolat

Csak a következő feltételeknek megfelelő e-maileket vagy fájlokat lehet importálni a megoldásba.

| Típus               | Konfiguráció  | További információ |
|--------------------|----------------|------------------|
| Office 365 Outlook | Mappa         | Az e-mail mappának a gyökérkönyvtárban kell lennie. Alapértelmezés szerint a Beérkezett üzenetek mappát használja a program. Az almappa nem támogatott. |
|                    | Tárgyszűrő | (Nem kötelező) A tárgyban szerepeltető alhálózat. |
|                    | Forrás           | (Nem kötelező) A feladó vagy a feladó e-mail címe. Ha több címet ad meg, pontosvesszőt (;) elválasztóként. |
| SharePoint         | Telephely címe   | A webhely címének URL-címe. |
|                    | Mappa         | A webhely címében található mappa. |

### <a name="activate-the-channel"></a>A csatorna aktiválása

A folyamat mentésekor a mezők a csatorna állapotát és a csatorna létrehozási idejét mutatják. Kezdetben az Állapot **mező** beállítása **Inaktív**. Az **Állapot oka** mező jelzi, hogy a csatorna inicializálva van, és készen áll az aktiválásra.

A csatorna aktiválásához válassza az Aktiválás **lehetőséget**. A program **frissíti** az Állapot **és** az Állapot okmezőket.

Ha nincs szükség csatornára, inaktiválhatja. Csatorna inaktiválásához válassza az Inaktiválás **lehetőséget**. A program **frissíti** az Állapot **és** az Állapot okmezőket.

### <a name="manage-flows-in-flow-management"></a>Folyamatok kezelése - áramláskezelés

A csatornákat a Konfigurációs csatornák lapon **vagy** a folyamatkezelésben lehet megtekinteni.

A további részletekért kattintson az Admin system **\> Default Solution \> Felhőáramlások** megoldásra, és válassza ki a célfolyamatot. A megjelenő részletek között megjelennek a kapcsolt kapcsolatok, a tulajdonosok és a történetek futtatása.

Az állapot szinkronizálása a Csekk **kiválasztásával** erősítse meg, hogy a csatorna állapota megfelel a folyamat állapotának.

Bizonyos kivételkezelési esetek az Állapot ok **mezőben láthatók**:

- **Hiányzik Dataverse a kapcsolat** – az aktuális felhasználó nem hozott létre legalább egy kapcsolati **Microsoft Dataverse** hivatkozást.
- **Nem található** – a folyamatkezelésben törölve lett a csatornához kapcsolt folyamat. Új csatorna létrehozásához ismét menteni kell a csatornát.
- **Inaktiválva** a folyamatkezelésben – a folyamat inaktiválva lett a folyamatkezelésben, és a csatorna állapota eltér a folyamat állapotától.
- **Aktiválva a folyamatkezelésben** – a folyamat aktiválva lett a folyamatkezelésben, és a csatorna állapota eltér a folyamat állapotától.
- **Váratlan hiba történt** – a felhasználónak meg kell erősítenie, hogy a webhely "Kommunikációs webhely", illetve hogy a mappa "Dokumentumtár".
