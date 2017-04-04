---
title: "Nyugta minták és nyomtatás"
description: "Ez a cikk ismerteti, hogyan módosíthatja a képernyőelrendezések létrehozását, hogy irányíthassa a nyugták, számlák és egyéb dokumentumok nyomtatását. Microsoft Dynamics 365 - műveletekhez kiskereskedelmi tartalmaz, amelyek segítségével könnyen létre és módosíthatja a különféle képernyőelrendezések képernyőelrendezés-tervezője."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 57841
ms.assetid: e530dd8e-95e2-4021-90bd-ce1235f9e250
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fabaacbc7187b38a1745c2139a9eb7760f2be987
ms.lasthandoff: 03/31/2017


---

# <a name="receipt-templates-and-printing"></a>Nyugta minták és nyomtatás

Ez a cikk ismerteti, hogyan módosíthatja a képernyőelrendezések létrehozását, hogy irányíthassa a nyugták, számlák és egyéb dokumentumok nyomtatását. Microsoft Dynamics 365 - műveletekhez kiskereskedelmi tartalmaz, amelyek segítségével könnyen létre és módosíthatja a különféle képernyőelrendezések képernyőelrendezés-tervezője.

**Fontos:** kell képernyőelrendezéseinek beállítása és befizetési nyugtákat és egyéb bizonylatokat nyomtatási Modern Retail POS és felhő POS profilok. Nyugtaprofil több képernyőelrendezések is felvehet. Ezután hozzárendelheti a nyugta profilt egy nyomtatóhoz a hardver profil módosításával.

## <a name="set-up-a-receipt-format"></a>Nyugtaformátum beállítása
1.  Kattintson a **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**POS**&gt;**nyugta formátum**.
2.  A **Nyugta formátum** oldalon, kattintson az **Új** gombra, új űrlap elrendezés létrehozásához, vagy egy már létező kiválasztásához.
3.  Gépelje be a **Nyugta formátum** mezőbe egy űrlap elrendezés azonosítóját, majd válassza ki az ehhez az elrendezéshez használt nyugta típust. A nyugtához leírást és rövid nevet is megadhat a **Cím** mező segítségével.
4.  Az **Általános** gyorslapon, válasszon egy nyomtatási viselkedését meghatározó lehetőséget:
    -   **Mindig nyomtasson** – a program automatikusan kinyomtatja a nyugtát.
    -   **Ne nyomtasson** – Nem nyomtatja ki a nyugtát.
    -   **Felhasználó megkérdezése** – A felhasználónak engedélyeznie kell a nyugta nyomtatását.
    -   **Szükség szerint** – Ez a beállítás csak ajándéknyugták esetén használatos. Ha ez a beállítás be van jelölve, a felhasználó ajándéknyugtát nyomtathat a **Változtatás** oldalon.

## <a name="design-a-receipt-format"></a>Nyugtaformátum tervezése
A Képernyőelrendezés-tervező segítségével grafikusan hozhatja létre a képernyő-dokumentum elrendezését. A **Nyugtaformátum tervező** lap három részből áll: **Fejléc**, **Sorok**, és **Lábléc**. Bizonyos típusú űrlap-elrendezések mindhárom szakaszból használnak fel elemeket, míg más típusok csak egy vagy két szakasz elemeit hasznosítják. Az egyes részeknél használható elemek megtekintéséhez kattintson a megfelelő gombra a képernyő bal oldalán található navigációs ablakban.

1.  Kattintson a **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**POS**&gt;**nyugta formátum**.
2.  A **Nyugtaformátum** oldalon, válasszon egy űrlap elrendezést, majd kattintson **Tervező** opcióra.
3.  Kattintson a **Futtatás** gombra, hogy elindítsa a Kiskereskedelem tervező telepítését.
4.  Az Internet Explorer ablakának alján található Értesítés sávon kattintson a **Megnyitás** gombra, hogy elindítsa az egy-kattintás tervező telepítését. (Az értesítési sávra megjelenhet egy másik helyén más böngészők.) Folyamatjelző a telepítési folyamat előrehaladását mutatja.
5.  A telepítés befejezése után adja meg a Dynamics 365 műveletek felhasználónevet és jelszót, és kattintson a **be** a designer indítása.
6.  Miután a belépő adatai hitelesítésre kerültek és a tervező elindul, megkezdheti a nyugta formátum tervezését vagy a már meglevő módosítását.
7.  Az űrlap elemeinek létrehozásához válassza ki a **Fejléc**, a **Sorok** vagy a **Lábléc** szekciót, majd húzza a szekcióban található egyik elemet a munkaterületre. A legtöbb elem változókat tartalmaz, amelyekbe a program automatikusan beírja az adatbázis adatait. Más elemek – például a **Szöveg** elem – lehetővé teszik egyéni szöveg nyomtatását a nyugtára. **Megjegyzés:** A terület jobb alsó sarkában lévő szám módosításával meghatározhatja, hogy az adott szekció hány sorra terjedjen ki. Ha egyszerűbbé szeretné tenni a szekció módosítását, akkor növelje meg a szakasz méretét a szekció alján látható méretező sáv segítségével. A szekció munkaterületen látható magassága nem befolyásolja a sorok számát a tényleges nyugtán.
8.  Miután az elemet a munkaterületre húzta, adja meg a részre vonatkozó tulajdonságokat az oldal alján található **Objektumadatok **ablaktáblában. Adjon meg egyet vagy többet a következő beállítások közük:
    -   **Igazítás** – A mező igazításának beállítása **Balra** vagy **Jobbra**.
    -   **Kitöltő karakter** – Az üres hely karakter megadása. Alapértelmezés szerint a program üres szóközt használ, de bármilyen karaktert meg lehet adni.
    -   **Előtag** – A mező elején megjelenítendő értéket ide írhatja be. Ez a beállítás csak az elrendezés **Sorok **szekciójára vonatkozik.
    -   **Karakterek** – Adja meg a mezőbe írható karakterek maximum számát. Ha a mezőben a szöveg hosszabb, mint a megadott karakterek száma, a szöveg csonkul, hogy elférjen a mezőben.
    -   **Változó** – Ez a jelölőnégyzet automatikusan be van jelölve, ha az elem tartalmaz változót és nem testre szabható.
    -   **Betűtípus** – A betűk stílusának beállítása **Normál** vagy **Félkövér** lehet. A félkövér betűk kétszer annyi helyet foglalnak, mint a normál betűk. Ezért előfordulhat, hogy néhány karaktert levág a program.
    -   **Törlés** – erre a gombra kattintva eltávolíthatja a kijelölt részt a képernyőelrendezésből.

## <a name="assign-receipt-profiles"></a>Nyugtaprofilok hozzárendelése
A nyugtaprofilok közvetlenül a nyomtatókhoz vannak rendelve a hardver profilon keresztül.

1.  Megnyitásához kattintson a hardverprofil **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**POS profilok**&gt;**hardverprofil**.
2.  Válassza ki a nyomtatót, majd a **Nyugta profil ** mezőben rendelje hozzá a jegyzékben használandó nyugtaprofilt.

**Megjegyzés:** Két nyomtató használata esetén egy nyomtató használható standard 40-oszlopos hő-papiros nyugta nyomtatására. A második nyomtató általában a teljes oldalas, több információt leíró nyugta nyomtatására szolgál. Ezek a nyugta típusok vásárlói rendelés nyugtákat és vevői számlákat tartalmaznak.


