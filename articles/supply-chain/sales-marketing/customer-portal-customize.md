---
title: Ügyfélportál testre szabása és használata
description: Ez a témakör azt mutatja be, hogyan lehet testreszabni a Ügyfélportált a rendszerhez történő hozzáadását követően.
author: dasani-madipalli
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b285cefc35654695ee631cc73baa0ccc2c1b5ac9
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359885"
---
# <a name="customize-and-use-the-customer-portal"></a>Ügyfélportál testre szabása és használata

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör bemutatja azokat a különböző lapokat, amelyek a Ügyfélportál modulban gyári kiépítésben elérhetők. Bemutatja, hogy mire képesek a lapok, illetve hogyan lehet ezeket testre szabni.

A Ügyfélportál néhány weblapot és műveletet kínál már gyári állapotban is. A következő oldaltérkép áttekintést nyújt ezekről a weboldalakról és műveletekről, valamint a műveletek végrehajtására képes szerepkörökről.

![Ügyfélportál oldaltérképe.](media/customer-portal-site-map.png "Ügyfélportál oldaltérképe")

## <a name="typical-customizations"></a>Jellemző testreszabások

A következő témakörökben megismerkedhet a Power Apps portálok alapjaival és a portálok testreszabásával:

- [Sablonok használata](/powerapps/maker/portals/work-with-templates) – Ez a témakör általános áttekintést nyújt a Power Apps-portálok működéséről, valamint a portálok egyszerű testreszabásainak végrehajtásáról.
- [Portáltartalom kezelése](/dynamics365/portals/manage-portal-content) – Ez a témakör azt mutatja be, hogyan lehet kezelni és testreszabni a portál felületén található tartalmakat.
- [CSS-szerkesztés](/powerapps/maker/portals/edit-css) – Ez a témakör a portál felhasználói felületének (UI) bonyolultabb testreszabásához nyújt segítséget.
- [Téma létrehozás a portálhoz](/dynamics365/portals/create-theme) – Ez a témakör segít létrehozni egy UI-témát a portálhoz.
- [A portál tartalmának egyszerű létrehozása és közzététele](/dynamics365/portals/create-expose-portal-content) – Ez a témakör a portálon használt mögöttes adatok és táblák kezelését segíti.
- [A portálon használható kapcsolattartó konfigurálása](/powerapps/maker/portals/configure/configure-contacts) – Ez a témakör azt mutatja be, hogyan lehet létrehozni és testreszabni a felhasználói szerepköröket, valamint a biztonsági és a hitelesítés működését a Power Apps-portálokon.
- [A táblák űrlapjaihoz és a portálokon található webképernyőkhez tartozó megjegyzések konfigurálása](/powerapps/maker/portals/configure-notes) – Ez a témakör azt mutatja be, hogyan lehet dokumentumokat és további tárolóhelyeket hozzáadni a portálhoz.
- [Hibakezelés a portál webhelyéhez](/powerapps/maker/portals/admin/view-portal-error-log) – Ez a témakör azt mutatja be, hogyan lehet megtekinteni a portál hibanaplóit, és tárolni azokat a Microsoft Azure Blob tárolási fiókban.

## <a name="customize-the-order-creation-process"></a>A rendelés létrehozási folyamatának testreszabása

Amikor egy felhasználó a Ügyfélportál segítségével elküld egy rendelést, a program automatikusan szinkronizálja a rendelést a megfelelő Dynamics 365 Supply Chain Management-környezettel. Mivel a felhasználó külső vevő, néhány szükséges adatot szándékosan elrejtettek előle. Ezt az információt a program automatikusan kitölti az űrlap elküldésekor.

Ez a szakasz bemutatja, hogyan kell beállítani a kapcsolattartókat a hibák elkerülése érdekében. Ez a rész automatikusan beállított mezőket és a mezők értékének esetlegesen módosításának folyamatát írja le.

### <a name="the-out-of-box-order-creation-process"></a>A gyári rendelés létrehozási folyamat

Itt megtekintheti a rendelésnek az Ügyfélportálról történő elküldésére vonatkozó szokásos lépéseket.

1. Válassza ki a Kezdőlap **Rendelés létrehozása** csempéjét a **Rendelés létrehozása** varázsló megnyitásához.
1. A **Rendelés adatai** lapon állítsa be a következő mezőket:

    - **Kért átvételi dátum** – Adja meg a kiszállítás dátumát.
    - **Szállítási cím** – Adja meg azt a címet, amelyre a rendelést kézbesíteni kell.
    - **Vállalat** – Válassza ki a vevő vállalatának nevét. Ez a mező automatikusan be van állítva a nem rendszergazdai felhasználók számára.
    - **Igénylés száma** – Adja meg a rendelés igénylési számát. A mező kitöltése nem kötelező.
    - **Szállítás országa/régiója** – Adja meg azt az országot vagy régiót, ahová a cikkeket szállítani fogják. Ez a mező automatikusan be van állítva a nem rendszergazdai felhasználók számára.

    ![Rendelés adatai lap.](media/customer-portal-order-information.png "Rendelés adatai lap")

1. Válassza ki **Következő** lehetőséget.
1. A **Cikkek** oldalon válassza a **Cikk hozzáadása** lehetőséget.

    ![Cikkek oldal.](media/customer-portal-items.png "Cikkek oldal")

1. A **Cikkinformáció** párbeszédpanelen a következő mezőket állítsa be:

    - **Terméknév** – A rendeléshez hozzáadandó termék keresése és kiválasztása.
    - **Mennyiség** – Adja meg a kiválasztott termék mennyiségét.
    - **Egység** – Adja meg a mértékegységet (például **ea.**, **kg** vagy **doboz**).
    - **Becsült nettó összeg** – Az érték számítása a kiválasztott egységhez tartozó mennyiség × a cikk becsült ára alapján történik.

    ![Cikkinformáció párbeszédpanel.](media/customer-portal-item-information.png "Cikkinformáció párbeszédpanel")

1. Az **Beküldés** gombot választva vegye fel a cikket a rendelésbe.
1. Ismételje meg a 4–6. lépést, amíg fel nem vette az összes megrendelni kívánt cikket.
1. Amikor befejezte a cikkek hozzáadását, válassza a **Tovább** lehetőséget a **Cikkek** oldalon.
1. A **Rendelés adatai** lap a rendelés összesítését tartalmazza. A rendelés tartalmának és a szállítási adatoknak az áttekintése. Ha minden megfelelőnek látszik, akkor a rendelés elküldéséhez válassza az **Elküldés** lehetőséget.

    ![Befejezett rendelés adatai lap.](media/customer-portal-order-submit.png "Befejezett rendelés adatai lap")

### <a name="standard-data-setup"></a>Standard adatbeállítás

A zökkenőmentes felhasználói élmény biztosításához a Ügyfélportál automatikusan kitölti az értékeket több kötelező mező esetében. Ezek az értékek a rendelést beküldő vevő kapcsolattartói rekordjának adatain alapulnak.

Minden olyan [kapcsolattartói sorhoz](/powerapps/maker/portals/configure/configure-contacts), amely egy olyan vevőhöz tartozik, és az Ügyfélportált a rendelések elküldésére fogja használni, meg kell adni értékeket a következő kötelező mezőkben. Ellenkező esetben hibák lépnek fel.

- **Vállalat** A jogi személyt, amelyhez a rendelés tartozik
- **Potenciális vevő** – A rendeléshez kapcsolódó ügyfélfiók
- **Árlista** – A vevő egyéni árlistája
- **Pénznem** – Az ár pénzneme
- **Szállítás országa/régiója** – Az ország vagy régió, ahová a cikkeket szállítani fogják

A program automatikusan beállítja a következő mezőket az értékesítési rendelés táblához:

- **Nyelv** – A rendelés nyelve (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).
- **Szállítás országa/régiója** – Az az ország vagy régió, ahová a cikkeket kézbesítik (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).
- **Kapcsolattartó** – Az a felhasználó, akivel a megrendeléssel kapcsolatban fel lehet venni a kapcsolatot (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).
- **Vállalat** – Az a jogi személy, amelyhez a rendelés tartozik (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).
- **Potenciális vevő** – A rendeléshez társított vevőfiók (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).
- **Számla vevője** – A rendeléshez társított számlázás (alapértelmezés szerint ez az érték a potenciális vevő a kapcsolattartói rekordból).
- **Értékesítési rendelés neve** – Az értékesítési rendelés neve (az alapértelmezett érték az **értékesítési rendelés**).
- **Pénznem** – Az ár pénzneme (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).
- **Árlista** – A vevő egyéni árlistája (alapértelmezés szerint az érték a kapcsolattartói rekordból származik).
- **Szállítási cím leírása** – Az értékesítési rendelés szállítási címe (az alapértelmezett érték a **szállítási cím leírása**.)

### <a name="modify-the-order-creation-process"></a>A rendelés létrehozási folyamatának módosítása

Szabadon módosíthatja a Ügyfélportál megjelenését és kezelőfelületét, ha nem módosítja az alapvető rendelési létrehozási folyamatot. Ha módosítani szeretné a rendelés létrehozási folyamatát, akkor van néhány dolog, amelyet szem előtt kell tartania.

Ne távolítsa el a következő oszlopokat az értékesítési rendelés táblából Microsoft Dataverse-szolgáltatásban, mert ezek szükségesek egy értékesítési rendelés létrehozásához a kettős írásban:

- **Vállalat** A jogi személyt, amelyhez a rendelés tartozik
- **Név** – Az értékesítési rendelés neve
- **Pénznem** – Az ár pénzneme
- **Árlista** – A vevő egyéni árlistája
- **Szállítás országa/régiója** – Az ország vagy régió, ahová a cikkeket szállítani fogják
- **Potenciális vevő** – A rendeléshez kapcsolódó ügyfélfiók
- **Nyelv** – A rendelés nyelve (általában ez a nyelv a potenciális vevő nyelve.)
- **Szállítási cím leírása** – Az értékesítési rendelés szállítási címe

A cikkek esetében a következő oszlopok kötelezők:

- **Termék** – A megrendelendő termék
- **Mennyiség** – A kiválasztott termék mennyisége
- **Egység** – A mértékegység (például **ea.**, **kg** vagy **doboz**)
- **Szállítás országa/régiója** – A szállítás országa vagy régiója
- **Szállítási cím leírása** – A rendelés szállítási címe

Győződjön meg róla, hogy a Ügyfélportálja valamilyen módon az összes oszlophoz elküld értékeket.

Ha oszlopokat kíván felvenni a lapra, vagy el szeretné távolítani az oszlopokat, tekintse meg a következő témakört: [Gyors létrehozási űrlapok létrehozása vagy szerkesztése egyszerű adatbeviteli élményhez](/dynamics365/customerengagement/on-premises/customize/create-edit-quick-create-forms).

Ha módosítani szeretné az oszlopok előbeállítását, és azt, hogy hogyan legyenek beállítva az értékek a lap mentésekor, tekintse át a következő információkat a Power Apps portálok dokumentációjában:

- [Mező előzetes kitöltése](/powerapps/maker/portals/configure/configure-web-form-metadata#prepopulate-field)
- [Érték beállítása mentéskor](/powerapps/maker/portals/configure/configure-web-form-metadata#set-value-on-save)

## <a name="customize-the-home-page"></a>A kezdőlap testreszabása

A Ügyfélportál összes vezérlője beépített Power Apps portálvezérlő. Ezeket úgy szabhatja testre, ha követi a [Lap létrehozása](/powerapps/maker/portals/compose-page) szakasz lépéseit a Power Apps portálok dokumentációjában.

Az Ügyfélportál sablonban szereplő egyetlen egyéni vezérlő a kezdőlapon lévő csempék létrehozásához használatos.

![A kezdőlap csempéi.](media/customer-portal-home-page-tiles.png "A kezdőlap csempéi")

A csempék módosításához kövesse az alábbi lépéseket.

1. Nyissa meg a [Portálkezelő alkalmazást](/powerapps/maker/portals/configure/configure-portal).
1. A bal oldali navigációs ablakban válassza ki az **Oldalsablonok** lehetőséget.

    ![A portálkezelő navigációs panel.](media/customer-portal-nav.png "A portálkezelő navigációs panel")

1. Válassza ki az **Otthon** nevű oldalsablont.
1. A **Webes sablon** mezőben válassza ki a **Kezdőlap** hivatkozását a lap forráskódjának megnyitásához.

    ![Webes sablon mező.](media/customer-portal-web-template.png "Webes sablon mező")

1. Most látja a kezdőlap összes forráskódját, és azt igény szerint módosíthatja.

## <a name="resources"></a>Erőforrások

A Ügyfélportál beállításával és testreszabásával kapcsolatos további tudnivalókat lásd a következő forrásokban:

- [Power Apps portálok dokumentációja](/powerapps/maker/portals/overview)
- [Kettős írás dokumentációja](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)
- [A portál életciklusáról](/powerapps/maker/portals/admin/portal-lifecycle)
- [Portál frissítése](/powerapps/maker/portals/admin/upgrade-portal)
- [Portál konfigurációjának áttelepítése](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Megoldás életciklus-kezelése: Dynamics 365 for Customer Engagement alkalmazásokhoz](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]