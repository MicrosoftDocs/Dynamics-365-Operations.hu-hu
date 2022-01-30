---
title: Toborzási folyamatok kezelése
description: Ez a témakör azt a fogalmat írja le, amely szerint a toborzási folyamat lépéseit a toborzási folyamat során a toborzók nyomon követhetik.
author: andreabichsel
ms.date: 01/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: anbichse
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9a5e89e700858ed9e625fbdee630fa14ebea26e
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/12/2022
ms.locfileid: "7965064"
---
# <a name="manage-recruiting-processes"></a>Toborzási folyamatok kezelése

[!include [banner](../includes/banner.md)]

Ez a témakör egy olyan koncepciót ismertet, amellyel a toborzók követhetik a toborzási folyamat lépéseit, köztük a nyitott beosztások meghirdetését és a pályázók felvételét, követhetik a pályázók és pályázatok adatait, pályázókat interjúztathatnak, és kiválaszthatak egy vagy több jelöltet a szervezet nyitott beosztásainak betöltésére.

## <a name="overview"></a>Áttekintés

Toborzási projektek is megkönnyítik a lépéseket is hajtsa végre a jogi személyben nyitott pozíciók kitöltésekor. A pályázó olyan személy, aki állásra pályázik a vállalatnál. A pályázat a pályázó érdeklődésének kifejezése, amely szerint szeretne dolgozni egy vállalatnál; ez egy konkrét nyitott pozícióhoz kapcsolódó toborzási projekthez tartozhat. Egy pályázó több pályázatot is leadhat ugyanazon jogi személyhez, illetve több vállalathoz a szervezeten belül.

## <a name="recruitment-projects"></a>Toborzási projektek

A toborzási projektek lehetővé teszik a felvétellel foglalkozók számára egy vagy több nyitott pozíció betöltési folyamatának követését. A toborzási projekt azonosítja a részleget és a munkát, amelyre nézve egy vagy több beosztás nyitva van. Toborzási projektek is nyomon követhető következő nyitott pozíciók vonatkozó információkat:

- Nyitott pozíciók egyedi száma
- A felvételi vezető és a beosztás egy másodlagos kapcsolattartó
- A tranzakció jóváhagyásának dátuma
- Jelentkezési határidő
- Becsült kezdő dátum

A toborzási projekt tartalmazza az Alkalmazott önkiszolgáló oldalának álláshirdetési értékét a **nyitó** **álláshirdetés** hirdetésére. A nyitó érték csak akkor jeleníthető meg az alkalmazottak számára, ha a toborzási projekt állásdátummal rendelkezik, az alkalmazotti önkiszolgáló rendszer Megjelenítésének beállítása Igen, a Pályázat határideje mező jövőbeli dátumra van állítva, és a toborzási projekt Projekt **állapota** **·** **·** **·** **·** **Elindítva**. Az alábbi táblázat felsorolja toborzási projektek lehetséges állapotait és azok leírását.

| Állapot    | Értelmezés...                                                                         |
|-----------|-----------------------------------------------------------------------------------------|
| Ütemezve | Toborzás erőfeszítések előkészítés alatt. A toborzás még nem indult meg ennél a projektnél. |
| Elkezdve   | Alkalmazások most éppen elfogadható a betöltendő pozíciók ebbe a projektbe.                   |
| Befejezve  | Minden betöltendő pozíciók, a projekt ki van töltve.                                         |
| Érvénytelenítve  | A tábla szinkronizálása megszakadt.                                          |

Recruiters is lehet rögzíteni a **Media** hirdetése a nyitó külső értékesítési keresztül, valamint a nyomon követésére használt **Fejlesztések** a projekt vagy alkalmazások szemben.

## <a name="applicants"></a>Pályázók

A pályázó olyan személy, aki munkára pályázik a vállalatnál. A pályázók a szervezet összes jogi személye között meg vannak osztva. Ebből következően nagy mennyiségű adata van a kereséshez. Megadhat és karban tarthat személyes információkat, állásinterjú dátumokat és időpontokat, referenciákat, kompetenciákat és a pályázó kérvényeit. Ha létrehoz egy pályázói rekordot, egy személyes rekord jön létre a pályázószámára a globális címjegyzékben. Használhatja a **Jelentkező** lap frissítése a következő globális címjegyzék adatait a pályázók számára:

- Címadatok
- Kapcsolattartási adatok
- Azonosító adatok megtekintése
- Név részletei
- Személyes információk

## <a name="applications"></a>Alkalmazások

A megkapott alkalmazotti pályázatokból rögzíthet adatokat a **Jelentkezés** képernyőn. A pályázat a pályázó érdeklődését fejezi ki a szervezetben megnyílt valamilyen munka iránt. Pályázat létrehozásához a pályázónak már léteznie kell pályázóként vagy személyként a rendszerben.

Webes pályázó által beküldött alkalmazotti pályázatokat vagy kért azon alkalmazásai, amelyek egy Álláshirdetésre reagálva vittek be, illetve kéretlen pályázatok. A kért pályázatok automatikusan ahhoz a felvételi projekthez kerülnek, amelyikből a hirdetés létrejött. A toborzási projekt megadott kéretlen pályázatok tartoznak a **Toborzási** területe a **Emberierőforrás-paraméterek** oldalon.

### <a name="application-status"></a>Pályázat állapota

A pályázat állapota jelzi, hogy a pályázat hol áll a toborzási folyamatban. Az alábbi táblázat felsorolja a lehetséges toborzási projekt állapota, és azok leírását.

| Állapot    | Értelmezés...                                                                           |
|-----------|-------------------------------------------------------------------------------------------|
| Bevételezve  | Pályázat beérkezésének dátuma.                                                             |
| Visszaigazolva | A pályázónak egy értesítés lett elküldve a pályázat beérkezésének visszaigazolásáról.            |
| Interjú | A pályázónak egy interjúmeghívás lett elküldve.                                     |
| Elutasítás | A pályázónak egy elutasító levél lett elküldve.                                          |
| Érvénytelenítve  | A pályázónak egy visszavonási visszaigazolás lett elküldve. Ezt az értéket kézzel rendelik hozzá. |
| Alkalmazott  | A pályázónak egy felvételi ajánlat lett elküldve.                                         |

### <a name="correspondence-actions"></a>Levelezési tevékenységek

A pályázat levelezési művelete határozza meg azt a dokumentumot vagy e-mail sablont, amely a pályázatot beküldött jelentkezővel való kommunikációra használ. A pályázati könyvjelzők megfeleltetési tevékenységhez társításával a Pályázók, Pályázó, Interjú és Toborzás projektoldalak értékeit használhatja a pályázókkal **folytatott** **·** **·** **·** **kommunikációban**. A levelezési műveletek pályázat-e-mail sablonjainak létrehozásával gyorsan elküldheti e-maileket azoknak a pályázóknak, akiknek jelentkezése az állapot és a levelezési **művelet** meghatározott kombinációját tartalmazza. Küldhet például visszaigazoló e-mailt minden olyan pályázatnak, amely Beérkezett állapotú és Megfeleltetés művelet **értéke** **·** **·** **Beérkezett**. Az e-mail elküldése után lehetőség van a pályázatok automatikus frissítésére.

## <a name="application-routing"></a>Pályázat útválasztása

Ha egy pályázatot több alkalmazottnak is át kell néznie, akkor a folyamat kezeléséhez a **Pályázat útválasztása**  oldalon létrehozhat egy alkalmazotti terjesztési listát.

## <a name="interviews"></a>Interjúk

**Pályázói interjúk** a **Pályázatok** oldalon ütemezhetők. Használja az **Értekezlettel kapcsolatos információk küldése** gombot, ha naptárfájlt kíván küldeni az interjú ütemezésének adataival a pályázónak és az interjúztatónak.

## <a name="skill-mapping"></a>Szakértelem feltérképezése

**Szakértelem-feltérképezés** és **szakértelem-feltérképezési profilok** lehet egy nyitólap jó közelítést jelentkezőket azonosítására is használható.

## <a name="hiring-applicants"></a>Pályázók felvétele

Használja a **alkalmazások** pályázó lapra. Pályázó felvételekor az alkalmazás rekord állapotú lesz, **alkalmazott** és az új dolgozói rekordot a kérelmező személy globáliscímjegyzék rekordja kapcsolódik. A globális címjegyzék adatait az új dolgozó rekord módosításai is megjelennek a pályázó rekordját. Így kevesebb adatot kell bevinni, ha az új dolgozó valaha a vállalaton belüli más munkakörre adna be pályázatot. Meglévő dolgozó felvételéhez új beosztásba kattintson a **Pozíció módosítása** elemre a **Pályázat állapota** legördülő listában, és az átviteli folyamat megkezdődik.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
