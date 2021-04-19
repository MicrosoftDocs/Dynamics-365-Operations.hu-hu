---
title: Hullámlépéskódok
description: Ez a témakör áttekintést nyújt a hullámlépéskódokról és használatukról.
author: josaw1
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveStepCode, WHSReplenishmentTemplates, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f44d500d58dffb37b27d230b0633336eb87996a6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838058"
---
# <a name="wave-step-codes"></a>Hullámlépéskódok

[!include [banner](../includes/banner.md)]

A hullámlépcsőkódok olyan kódok, amelyeket a felhasználók úgy állíthatnak be és használhatnak, hogy azok a hullámmetódusok meghatározott példányait a megfelelő sablonhoz kapcsolja. A sablonok tartalmazzák a feltöltéshez, a tárolóra bontáshoz, a címkék nyomtatásához, a rakomány építéséhez és a sorba rendezéshez szükséges sablonokat.

Ha nem használja a hullámlépéskódokat, a felhasználóknak szabad szöveget kell beírniuk ahhoz, hogy a meghatározott sablonra hivatkozzanak a hullámmetódus-példányból. A szabad szövegben előfordulhatnak hibák, mivel a felhasználóknak ellenőrizniük kell, hogy a hullámlépés szövege, amelyet egy meghatározott hullámlépés-metódushoz a hullámsablonban hozzá akarnak adni, megegyezik a hullámlépés szövegével a célsablonban.

Az adott hullámlépéstípus hullámlépéskódjait külön oldalon állítják be. Egy hullámsablon minden egyes hullámlépésmetódus-példányához, amelyhez hullámlépéskód szükséges, egy legördülő listából kell kiválasztani a hullámlépéskódot. A legördülő listában szereplő választék helyettesíti a szabadszöveges bevitelt, így csökkenti az emberi hiba kockázatát és hatását. A beállítási kódok a hullámsablon hullámlépés-metódusának és a metódushoz tartozó célsablon összekapcsolására használatos.

> [!NOTE]
> A hullámlépéskódok funkció használata nem kötelező. A teljes szervezetben, minden jogalanynál engedélyezett.

## <a name="setup-demo"></a>Demo beállítása 

Ennél a bemutatónál a bemutatóadatokat kell telepíteni, és az **USMF** demó adatvállalatot kell használnia.

### <a name="enable-wave-step-codes"></a>Hullámlépéskódok engedélyezése

Hajtsa végre az alábbi lépéseket a hullámlépéskód-funkció bekapcsolásához.

1. Lépjen a **Funkciókezelés** lehetőségre.
2. Jelölje be a **Szervezet egészére kiterjedő hullámlépéskód** nevű szolgáltatást.

A program az új struktúrára frissíti az összes meglévő hullámlépés szabadszöveges bejegyzését minden jogi személyben. Miután a frissítés befejeződött minden jogi személynél, a szolgáltatás engedélyezve van. Ha a szolgáltatást nem lehet engedélyezni egy vagy több jogi személynél, akkor a szolgáltatás nincs engedélyezve semelyik jogi személyhez.

Az engedélyezés során az érvényesítés az adatfrissítés során történik meg. Ha a frissítés nem sikerül, hibaüzenet jelenik meg. Előfordulhat, hogy a frissítés a következő ütközések miatt nem sikerül:

- Ismétlődő hullámlépéshez tartozó szabad szövegek léteznek.
- Testreszabások találhatók.
- A hullámlépés szabadszövege, amely egy adott hullámlépésmetódus-példányhoz van társítva, nem egyezik meg az elvárt sablontípussal.

Miután feloldotta az ellenőrzések során azonosított ütközéseket, próbálja újra engedélyezni a funkciót.

Amikor a funkció engedélyezve van, elérhetővé válik a **Hullámlépéskódok** oldal (**Raktárkezelés \> Beállítás \> Hullámok \> Hullámlépéskódok**). Ez a lap felsorolja azokat a hullámlépéskódokat, amelyek a Szervezet egészére kiterjedő hullámlépéskód funkció bekapcsolásakor engedélyezve lettek.

### <a name="create-new-wave-step-codes"></a>Új hullámlépéskódok létrehozása

A **Hullámlépéskódok** lapon hozhat létre és törölhet hullámlépéskódokat.

Minden új hullámlépéskódnak és a hozzárendelt azonosítónak egyedinek kell lennie az összes hullámlépéstípus tekintetében, és egy meghatározott hullámlépéstípushoz kell megadni.

### <a name="apply-wave-step-codes"></a>Hullámlépéskódok alkalmazása

Miután definiálta a megfelelő hullámlépéskódokat, alkalmazhatók a hullámfeldolgozási módszerekre.

A hullámlépéskódok alkalmazása érdekében lépjen a megfelelő célsablonra. Itt találhatók a célsablonok, amelyre a tervezés alapján a hullámlépéskódokat irányítják:

- **Feltöltési sablonok:** Raktárkezelés \> Beállítás \> Feltöltés \> Feltöltési sablonok
- **Rakományépítési sablonok:** Raktárkezelés \> Beállítás \> Rakomány \> Rakományépítési sablonok
- **Rendezési sablonok:** Raktárkezelés \> Beállítás \> Csomagolás \> Kimenő rendezési sablonok
- **Tárolóra bontási sablonok:** Raktárkezelés \> Beállítás \> Tárolók \> Tárolóépítési sablonok
- **Címkenyomtatási sablonok:** Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímkesablonok

A listában szereplő sablonokat akkor alkalmazza a program, ha a hullámsablonban kiválasztott hullámfeldolgozási metódusból hivatkoznak rájuk. Ha a hullámsablon hullámfeldolgozási metódusán szereplő hullámlépéskód megegyezik az egyik sablontípuson található hullámlépéskóddal, akkor a rendszer alkalmazza a sablont.

### <a name="sample-scenario"></a>Mintaforgatókönyv

A következő eljárás segít annak biztosításában, hogy a létrehozott feltöltési sablont a rendszer alkalmazza a hullámsablonra.

1. Lépjen a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámlépéskódok** pontra, és hozzon létre egy hullámlépéskódot a **Feltöltés** típushoz.
2. Lépjen a **Raktárkezelés \> Beállítás \> Feltöltés \> Feltöltési sablonok** pontra, és hozzon létre egy feltöltési sablont.
3. A feltöltési sablonban válassza ki a **Feltöltés** típushoz létrehozott hullámlépés kódját.
4. Lépjen a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra, és hozza létre a használni kívánt hullámsablont.
5. A sablon **Metódusok** gyorslapján válassza a **Feltöltés** metódust.
6. A **Hullámlépéskód** mezőben válassza ki a feltöltési sablonban kiválasztott hullámlépéskódot.

Ezeket a lépéseket minden egyes jogi személynél végre kell hajtani.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]