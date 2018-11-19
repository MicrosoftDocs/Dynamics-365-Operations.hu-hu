---
title: E-mail-sablonok
description: "Ez a témakör ismerteti a Microsoft Dynamics 365 for Talent - Attract e-mailsablonjait, amelyeket létrehozhat és használhat."
author: josaw
manager: AnnBe
ms.date: 10/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 85581968d9d242460117693174acbf906463997f
ms.contentlocale: hu-hu
ms.lasthandoff: 10/22/2018

---

# <a name="email-templates"></a>E-mail-sablonok
[!include[banner](../includes/banner.md)]

Az e-mail sablontár használatával a rendszergazdák egységes témát és márkázást hozhatnak létre minden e-mailhez, amelyeket a Microsoft Dynamics 365 for Talent: Attract használatával küldenek. A rendszergazdák karbantarthatják az e-mail tartalom sablonok gyűjteményét, amelyeket a felhasználók használhatnak. A felvételi csoport a sablonok használatával a munkafolyamatban hatékonyabban küldhet e-maileket. Az Attract egyes e-mailjei automatikus küldésre vannak beállítva, és a rendszergazda használhatja az e-mail sablontárat az e-mailek tartalmának testreszabására.

## <a name="global-template-configurations"></a>Globális sablonkonfigurációk

E-mail értesítések emblémájának konzisztens létrehozásához a rendszergazda először be kell vinni globális fejlécbe és láblécbe összes e-mail sablonokat. A felügyeleti központban a **E-mail sablon beállításai** lapon a **Fejléc** szakasz, az Adminisztráció feltöltheti minden e-mailek használni a fejlécben vagy transzparens kép. A kép lehet a vállalat emblémája, fejléce vagy bármelyik másik képe. Azt javasoljuk, hogy a szélesség 25 és 800 képpont közötti lehet, és a magassága 25 és 150 képpont között, mivel ezekre a dimenziókra a legtöbb e-mail ügyfél, például a Microsoft Outlook optimális. A képnek JPEG, JPG, PNG vagy SVG fájlnak kell lennie, és a fájl mérete kisebb, mint 1 megabájt (MB) kell lennie. Kép feltöltése után a fejléc előnézetét létrehozza és jelenik meg. Ha a fejléc képet el kell távolítani vagy ki kell cserélni, a rendszergazda használhatja az **Eltávolítás** elemet az előnézet lehetőség felett.

A **Lábléc** szakasz, az Adminisztráció teremthet kapcsolatot a cég adatvédelmi kommunikáció és a feltételek. Ezek a hivatkozások be vannak építve egy láblécbe, amely automatikusan létrejön. A lábléc előnézete akkor jelenik meg.

Ügyeljen arra, hogy mentse a módosításokat, mielőtt bezárja az Admin centert.

> [!NOTE] 
> Fejléc és lábléc globális minden e-mailek beállításhoz. Ezért megjelennek minden Attracton keresztül küldött e-mailben. Ha a beállítások nincsenek megadva, fejlécéből és láblécből kimaradnak minden e-mailben.

## <a name="email-template-library"></a>E-mail sablontár 

Miután a globális beállítások be vannak állítva, a rendszergazda létrehozhat és karbantarthat sablonokat az Attract alkalmazásból küldött összes e-mailhez. Az e-mail sablontár csak rendszergazdák számára érhető el. Válassza ki a könyvtár, a fő navigációs menü megnyitása a **E-mail sablonok** lapon. A könyvtár Attract küldött e-mailek kell, például az ütemezés, az értékelés, és a feladat létrehozása a különböző tevékenységekhez módszere. A rendszergazda választhat egy kategóriára, amelyek a tevékenységhez társított összes e-mail-típus megjelenítése. Kiválaszthatja például az **Ütemezés** elemet az ütemezési folyamat során különféle e-mailtípusok megtekintéséhez, és a különböző típusú e-mailekhez rendelkezésre álló összes sablon megtekintéséhez. Minden alszakasz a kategóriákban egy e-mailtípust jelöl.

Bizonyos típusú e-maileknek egynél több címzettje lehet. Például az **Ütemezés** kategóriában azokat az e-maileket, amelyeket akkor küldenek el, amikor az interjúütemezésések összegzésére van szükség, a jelöltnek, valamint az interjúbonyolítóknak is elküldik. Minden egyes szakasznak két fő oszlopa van: **Sablon címe** és **Címzett**. A szakasz minden sora egy sablon e-mail típust jelent. Először minden sablon sorában egy zár szimbólum fog megjelenni. Ez a szimbólum jelzi, hogy a sablon a szabványos, Attract alkalmazáshoz mellékelt sablon, és nem törölhető. Az adminisztrátor minden sablonnál használhatja a (**...**) gombot a sablon másolásához, beállításához alapértelmezett sablonként, vagy törléséhez. A sablon alapértelmezett sablonként beállításakor két viselkedés egyikére kerülhet sor. A viselkedés a sablon sorban megjelenő jelvényen vagy jelvényeken van megadva:

- **Alapértelmezett** – a jelvény azt jelzi, hogy a sablonban az alapértelmezett sablon az elküldött e-mailre, továbbá, hogy adatokat a program beírja, amikor egy felhasználó elküldi ezt a bizonyos típusú e-mailt.
- **Alapértelmezett** + **Automatikusan küldött** – a jelvények ezen kombinációja azt jelzi, hogy a sablon a rendszer által generált, automatikus küldött e-mailek aktív sablonja.

A sablon szerkesztéséhez jelölje ki a sort, és módosítsa a sablont.

> [!NOTE]
> Egy bizonyos típusú e-mail címzettjeinek mind alapértelmezett sablonja van. A szabványos Attract sablonok alapértelmezett sablonként be vannak állítva mindaddig, amíg a rendszergazda létre nem hoz egy új sablont egy bizonyos típusú e-mailhez, és alapértelmezett sablonként be nem állítja.

## <a name="create-a-template"></a>Sablon létrehozása

Sablon létrehozásához az e-mail sablontár jobb felső sarkában, jelölje be **+ új sablon** elemet. Az e-mailtípus kiválasztásához, amelyhez sablont hoz létre, jelölje be a címzettet, a folyamatot és az eseményt, amelyhez az e-mailt el kell küldeni. Ezután válassza a **Létrehozása** lehetőséget.

A sablon szerkesztési nézetben nyílik meg, és elnevezheti a sablont. Például, ha az Egyesült Államok egyetemeiről érkező pályázóknak készül a sablon, de franciául írták a tartalmat, akkor adja meg ez címként: **Egyetem\_Egyesült Államok\_Francia**. A cím, a tárgysor és az e-mail tartalma minden sablonnál támogat más nyelveket is az angolon kívül.

A **Címzett** mezője a sablonnak nem szerkeszthető, mivel már bejelölte a címzettet a sablon első létrehozásakor.

Felvehet szereplőket, például **Toborzó** vagy **Felvételi vezető**, a másolat (Cc) sorba. Az e-mail küldésekor a szerepköröket automatikusan felülírják a megfelelő felhasználók, az állás kontextusa alapján.

A tárgysor és a levél tartalma támogatja a helyőrzőket. Helyőrzőket a **\#** beírásával illeszthet be, majd válassza ki a megfelelő helyőrzőt az automatikus legördülő listában. Az elérhető helyőrzők listája megjelenik az oldal jobb oldalán. Az e-mail küldésekor a rendszer automatikusan felülírja a helyörzőket az állás kontextusa és a címzett alapján. Például a pályázónak küldött e-mail sablont tartalmaz ezt a helyőrzőt: \#{Candidate\_Name}. Az e-mail küldésekor a Cameron nevű pályázónak, a helyőrző helyére Cameron neve kerül.

Az e-mail tartalomának szerkesztője rich text szövegszerkesztő, amely lehetővé teszi a szöveg stílusának és formátumának megadását. Ezenkívül lehetővé teszi a hivatkozások és horgonyok beszúrását.

Egy bizonyos típusú e-mail sablon létrehozása után használja a (**...**) gombot a sablon sorában, és állítsa be az alapértelmezett sablonként.

## <a name="consume-templates"></a>Sablonok felhasználása

Amikor a felvételi csapat e-mailt küld, használhatja a rendszergazda által létrehozott a sablonokat. Ha több sablon lett létrehozva a felhasználó álta küldött e-mailhez, a legördülő lista megjelenik az e-mail felhasználása munkafolyamatban. Az alapértelmezett sablont a program automatikusan kitölti, de a felhasználó választhat másik sablont.

> [!NOTE] 
> Az automatikusan küldött e-mailekhez több sablon is létrehozható. Az aktív sablonként azonban csak egy sablon állítható be. Mivel ezt a folyamatot események váltják ki, csak a rendszergazda határozhatja meg, hogy melyik sablont kell használni, az **Alapértelmezett** és **Automatikusan küldött** jelvény kombinációja alapján a sablonkönyvtárban.

