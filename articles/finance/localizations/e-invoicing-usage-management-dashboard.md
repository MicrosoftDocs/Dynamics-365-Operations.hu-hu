---
title: Használat kezelése irányítópult
description: Ez a témakör bemutatja, hogy hogyan lehet a Használatkezelés irányítópult segítségével figyelni az elektronikus számlázási szolgáltatás használatát, és megfelelni az előírásoknak.
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 35b50c8cb5c6ef72f466a4fb10c7af0e53afc3db5d1ef9e2b23d6049e24a70c3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776474"
---
# <a name="usage-management-dashboard"></a>Használat kezelése irányítópult

[!include [banner](../includes/banner.md)]

A **Használat kezelése** irányítópult segítségével nyomon követheti az Elektronikus számlázási szolgáltatás használatát, így szervezete a havi használat tekintetében is megfelel az előírásoknak. A megfelelés meghatározása a benyújtás mennyiségének kiszámításával és az fogadott mennyiség összehasonlításával határozza meg, hogy a beszerzett mennyiség és a felhasznált mennyiség között eltérés van-e.

A irányítópult a következő kijelzéseket tartalmazza:

- Egy költségmutató, amely a felhasználás nyomon követésére használható a licencelési megfelelés céljából:

    - Havi használat (export)

- Három működési mutató, amelyek az elektronikus számlázási szolgáltatás használatának nyomon követésére használhatók kezelési célokra:

    - Felhasználás funkció szerint
    - Felhasználás környezet szerint
    - Havi használat (import)

## <a name="measurement-scope"></a>A mérés hatálya

- Mértékegység: 

    A **Használatkezelés** irányítópult az üzleti dokumentumok és az importált elektronikus számlák benyújtását számolja meg.

- Szervezet: 

    A számítás összegzése szervezet bérlői azonosítója szerint történik, függetlenül attól, hogy hány példányban van engedélyezve a Microsoft Dynamics 365 Finance vagy Dynamics 365 Supply Chain Management, illetve, hogy hány jogi személynél van engedélyezve az Elektronikus számlázás szolgáltatás.


## <a name="indicator-usage-per-month-export"></a>Mutató: Havi használat (export)

Ez a mutató részletes adatokat nyújt az elektronikus számlákról, amelyek a szervezetnél egy adott időszakban ki lettek bocsátva.

### <a name="scope"></a>Hatókör
- A Supply Chain Management modulból az elektronikus számlázási szolgáltatásba elküldött üzleti dokumentumok száma, függetlenül attól, hogy az üzleti dokumentumok hány sort tartalmaznak.
- Az Elektronikus számlázási szolgáltatás által sikeresen feldolgozott elküldött üzleti dokumentumok száma. A dokumentum sikeresen feldolgozottnak minősül, amikor befejeződött a funkcióbeállításban meghatározott műveletek folyamata.

> [!NOTE]
> Amikor egy elektronikus számlát elküldnek egy külső webszolgáltatásnak, a számolás független a webszolgáltatás feldolgozásának eredményeitől (elfogadva, elutasítva vagy sémaérvényesítési hiba). Ha a webszolgáltatás az elektronikus számlázási szolgáltatás kérését megkapta és választ küldött, a beküldés érvényes mennyiségnek számít.

- **Kivétel:** Az üzleti dokumentumokat nem számolja a rendszer, ha újraküldik őket a Finance és a Supply Chain Management modulból az Elektronikus számlázási szolgáltatásba, például olyan helyzetekben, amikor ugyanannak az üzleti dokumentumnak az újraküldése szükséges az elektronikus számla állapotának a módosítása érdekében. Például egy brazil elektronikus számla (pénzügyi bizonylat) kiállítása érvényesnek számít, de az ahhoz érvénytelenítési kérelem nem számít.


### <a name="calculation"></a>Számítás

Az egyenleg számítása a következő módon történik:

Egyenleg = Ingyenes + Megvásárolt – Felhasznált

Ahol:

- Ingyenes:
  
    A vevő által havonta elküldhető üzleti dokumentumok ingyenes mennyisége. Ez a csomag 100 üzleti dokumentumot tartalmaz, amelyek benyújthatóak az elektronikus számlázási szolgáltatásnak. Az ingyenes mennyiség nem kumulatív, és a fennmaradó egyenleg nem lesz átgördítve a következő időszakra.
  
- Megvásárolt:
  
    Egy csomag 1000 üzleti dokumentumot tartalmaz, amelyek benyújthatóak az elektronikus számlázási szolgáltatásnak. Ezt a csomagot havonta kell beszerezni az Ön szervezete számára. Az megvásárolt mennyiség nem kumulatív, és a fennmaradó egyenleg nem lesz átgördítve a következő időszakra.
  
- Felhasznált: 

    Az Elektronikus számlázási szolgáltatásba küldött üzleti dokumentumok száma a meghatározott feltételeknek megfelelően.
   
> [!IMPORTANT]
> Ha a szervezet tervezi, hogy meghaladja a havi 100 ingyenesen beküldhető mennyiséget, akkor a maximális mennyiség megvásárlásával gondoskodhat arról, hogy az elektronikus számlázási szolgáltatás Microsoft licencelési irányelveinek megfelelő maradjon.
>
> Jelenleg a megvásárolt mennyiséget manuálisan kell megadni a beszerzés dátumának megfelelően, 1000 beküldést tartalmazó csomagonként.

## <a name="indicator-usage-by-feature"></a>Mutató: Funkció szerint való felhasználás

Ez a mutató azt mutatja, hogy egy adott időszakban az elektronikus számlák kiállítása során az elektronikus számlázási funkciók használatát mutatja meg.

- Számítás:
  
    Felhasznált = Annak száma, hogy hányszor használta az egyes elektronikus számlázási funkciókat az üzleti dokumentumoknak az Elektronikus számlázási szolgáltatásba történő benyújtásakor.

## <a name="indicator-usage-by-environment"></a>Mutató: Környezet szerint való felhasználás

Ez a mutató az elektronikus számlázási szolgáltatási környezet használatát mutatja egy adott időszakban.

- Számítás:
    
    Felhasznált = Annak száma, hogy hányszor használta az egyes elektronikus számlázási szolgáltatási környezeteket az üzleti dokumentumoknak az Elektronikus számlázási szolgáltatásba történő benyújtásakor.

## <a name="indicator-usage-per-month-import"></a>Mutató: Havi használat (import)

Ez a mutató azt mutatja, hogy egy adott időszakban az elektronikus számlázási szolgáltatásból mennyi elektronikus számla lett importálva a Finance és a Supply Chain Management alkalmazásokba.

- Hatókör:

    A Finance és a Supply Chain Management alkalmazásokba importált elektronikus számlák, függetlenül attól, hogy hány sort tartalmaznak ezek az elektronikus számlák.

- Számítás:

    Beérkezett = Az importált elektronikus számlák száma a Finance és a Supply Chain Management alkalmazásokban.

## <a name="functions"></a>Funkciók
### <a name="purchase"></a>Beszerzés

Válassza a **Vásárlás** lehetőséget a **Havi használat (export)** lapon a beszerzett beküldések mennyiségének manuális regisztrálása érdekében.

Egy adott dátumhoz válassza az **Új** lehetőséget, és adja meg az adott napon beszerzett **Csomagok** számát.

A **Mennyiség** kiszámítása:

Mennyiség = Csomagok * 1000

A számított **Mennyiség** a **Havi használat (export)** mutató alapján **Megvásárolt** értéknek megfelelő.

### <a name="update"></a>Módosítás

A Műveleti panelen a **Frissítés** gombra kattintva frissítse a számítást, és frissítse a lapon és a diagramon megjelenő adatokat.

### <a name="reset-history-data"></a>Előzményadatok alaphelyzetbe állítása

A Műveleti panelen válassza az **Előzményadatok alaphelyzetbe állítása** lehetőséget annak az adatbázisnak a frissítéséhez, ahonnan a mutatók számítása történik.




> [!NOTE]
> A **Használat kezelése** irányítópultja nem mutat pénzösszegeket. Ehelyett csak a számolt beküldések és az importált dokumentumok mennyiségét jeleníti meg.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
