---
title: Forrásnál levont indiai adó (TDS) áttekintése
description: Ez a témakör részletes információkat nyújt a forrásnál levont indiai adóról (TDS). A TDS dokumentáció lefedi ennek a képességnek a funkcionalitását.
author: kailiang
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 8064f10978712fc474dd72a5b5bdd9a445606d7a
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2021
ms.locfileid: "6337721"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a>Forrásnál levont indiai adó (TDS) áttekintése

[!include [banner](../includes/banner.md)]

Ez a témakör részletes információkat nyújt a forrásnál levont indiai adóról (TDS).

A TDS dokumentáció lefedi ennek a képességnek a funkcionalitását. Azt is elmagyarázza, hogyan kell elvégezni a TDS alapbeállítását, kiszámítani a TDS-t a tranzakciókon, befejezni a TDS-elszámolási folyamatot, rögzíteni a TDS-tanúsítványszámokat, és TDS-lekérdezéseket, TDS-kimutatásokat és TDS-tanúsítványokat generálni. A dokumentáció a következő témaköröket tartalmazza:

- [Az TDS alapbeállításai](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [A TDS kiszámításához használt képlettervező és küszöbértékkorlát funkció](apac-ind-TDS-Formula-designer.md)
- [TDS kiszámítása számlákon, kifizetéseken, kötelezvényeken és vállalatközi tranzakciókon](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [A TDS-adatok időszakos kiegyenlítési folyamata és elszámolása a TDS-hatóság szállítói számára](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [TDS-tanúsítványszámok és dátumok rögzítése és frissítése](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a>Bevezetés a TDS-be

A jövedelemadóról szóló 1961. évi törvény értelmében a jövedelemadót a szolgáltatás igénybevevője levonja a forrásnál az előlegfizetés vagy a jóváírás elkönyvelésekor, attól függően, hogy melyik következik be először. A fizetést végző személynek le kell vonnia az adó összegét, és csak a nettó egyenleget kell kifizetnie a szolgáltatónak. A TDS-t a kormány által meghatározott szolgáltatásokra alkalmazzák, és az adót a kormány által meghatározott adómértékek alkalmazásával vonják le egy időszakra. A levonás mértéke a kifizetést kapó vagy a szolgáltatást nyújtó entitás állapotán alapul. A státuszok közé tartozik az **Egyéni**, **Hindu osztatlan család** (**HUF**), **Vállalat**, **Cég**, **Személyügyi szövetség** (**AOP**), **Magánszemélyek testülete** (**BOI**) és az **Önkormányzat**.

A következő szakaszok felsorolják azokat a szolgáltatásokat, amelyeken a TDS-t alkalmazzák, az indiai kormány által meghatározottak szerint.

**Lakosok**

- Fizetésből származó jövedelem (192. szakasz szerint)
- Értékpapírkamatból származó jövedelem (193. szakasz szerint)
- Osztalékból származó jövedelem (194. szakasz szerint)
- Kamatból származó jövedelem (194A szakasz szerint)
- Lottóból vagy rejtvényekből származó jövedelem (194B szakasz szerint)
- Lóversenyek megnyerése stb. (194BB szakasz szerint)
- Vállalkozók és alvállalkozók (194C szakasz szerint)
- Biztosítási jutalék (194D szakasz szerint)
- A nemzeti megtakarítási rendszer keretében elhelyezett betétből származó jövedelem (194EE szakasz szerint)
- Befektetési alapból vagy UTI-ból származó jövedelem (194F szakasz szerint)
- Jutalék, díjazás, nyeremény stb., eladás vagy lottó (194G szakasz szerint)
- Jutalék vagy közvetítői kifizetés (a 194H szakasz szerint)
- Bérleti díj (194I szakasz szerint)
- Szakmai szolgáltatás (194J szakasz szerint)
- Egységekből származó jövedelem (194K szakasz szerint)
- Egyes ingatlanok megszerzéséért járó kártérítés kifizetése (194LA szakasz szerint)

**Nem rezidensek**

- Kifizetések nem rezidens sportolók vagy sportegyesületek részére (194E szakasz szerint)
- Egyéb összegek (195. szakasz szerint)
- A nem rezidensek egységeiből származó jövedelem (196A szakasz szerint)

    - Az Indiai Társaság devizakötvényeiből vagy részvényeiből származó jövedelem (196C szakasz szerint)
    - Külföldi intézményi befektetők értékpapírból származó jövedelmei (196D szakasz szerint)
    - Fizetés és minden egyéb pozitív jövedelem bármely jövedelem alatt (192. szakasz)
    - Értékpapírok kamata (193. szakasz)
    - Értékpapírok kamatán kívüli kamat (194A szakasz)
    - Vállalkozók és alvállalkozók kifizetései (194C szakasz)
    - Nyeremények lottóból vagy keresztrejtvényekből (194B szakasz)
    - Lóversenyek nyereményei (194BB szakasz)
    - Biztosítási Bizottság, amely fedezi a biztosítási tevékenység megszerzéséért járó összes kifizetést (194D szakasz)
    - A nem vállalati nem rezidensek vagy külföldi társaság részére fizetendő értékpapírok kamatán kívüli kamatok (195. szakasz)
    - Kifizetés nem rezidens sportolónak, beleértve a sportolót, a sportegyesületet vagy az intézményt. A nem rezidens sportoló esetében a kifizetések tekintetében hirdetések, valamint az indiai újságokban, magazinokban stb. megjelenő összes játék/sport cikk. szerepel (194E szakasz)
    - Kifizetés az NSS \[Nemzeti Megtakarítási Rendszer\] (194EE szakasz) szerinti betétek tekintetében
    - Kifizetés befektetési alapok, azaz UTI által történő visszavásárlás miatt (194F szakasz)
    - Jutalékért vagy közvetítésért járó kifizetés (194H szakasz)
    - Bérleti díj megfizetése (194I szakasz)
    - Szakmai vagy műszaki szolgáltatások díjának megfizetése (194J szakasz)
    - A lottójegy részvényesek, forgalmazók, vevők és eladók jutaléka, beleértve az ilyen jegyek fizetését vagy díját (194G szakasz)
    - Devizában vásárolt befektetési jegyekből származó jövedelem vagy a devizában vásárolt ilyen egységek átruházásából származó hosszú távú tőkenyereség (196B szakasz)
    - A nem rezidensek részére a kötvényekre és részvényekre vonatkozó kamat vagy osztalék tekintetében származó jövedelem kifizetése (196C szakasz)

A TDS kiszámítása a vásárlások, eladások, értékesítési hozamok, jóváírások, tárgyi eszközök beszerzései, előtörlesztések, előlegek, kötelezvények, munkák utáni adó és vállalatközi tranzakciók alapján történik.

> [!NOTE]
> A jelenlegi indiai adózási forgatókönyv szerint a TDS-t nem számítják ki az értékesítési tranzakciókra. A rendszer azonban tartalmaz egy rendelkezést az értékesítési tranzakciókra visszaigényelhető TDS kiszámítására, különösen a vállalatközi tranzakciók esetében.

A TDS kiszámítása mindig figyelembe veszi a TDS-összetevőre meghatározott küszöbértéket és kivételi küszöbértéket.

Az időszakos TDS-elszámolási folyamatot le kell futtatni, és a TDS-kifizetéseket el kell rendezni a TDS-hatóság szállítóinak.

A szállítóktól vagy ügyfelektől kapott TDS-tanúsítványok tanúsítványszámai és dátumai rögzíthetők és frissíthetők. Ezenkívül a Pénzügyekben a 26Q és a 27Q űrlap negyedéves kimutatásai, valamint a TDS 16A űrlapbizonyítványa is generálható.

## <a name="setting-up-and-working-with-tds"></a>A TDS beállítása és működése

Az alábbiakban áttekintést adunk a TDS beállításának és működésének folyamatáról:

1. **TDS-beállítás:**

    - Paraméterek beállítása:

        - A Főkönyvi paraméterekben aktiválja a TDS-hez kapcsolódó paramétereket.
        - A Főkönyvi paraméterekben állítsa be az adóelőleg-fizetések számsorozatát.
        - Paraméterek beállítása Kötelezettségek és Kinnlevőségek esetében.

    - Alapbeállítás:

        - TDS-regisztrációs számok beállítása egy vállalat, ügyfelek és szállítók számára.
        - TDS-összetevő csoportok beállítása.
        - TDS-összetevők beállítása, TDS-összetevők csoportjainak csatolása hozzájuk, és a küszöbérték és a kivételi küszöbérték meghatározása.
        - TDS-hatóságok felállítása.
        - TSD-elszámolási időszakok beállítása.
        - Állítsa be a TDS-adókódokat, és csatolja hozzájuk a TDS-összetevőket.
        - Állítsa be a TDS-adócsoportokat, és csatolja hozzájuk a TDS-adókódokat.
        - A képlettervezőben definiáljon egy képletet egy TDS-csoport TDS-ének kiszámításához.
        - TDS koncessziós tanúsítvány számának rögzítése.

    - Főkönyvi számlák és a vállalat beállítása:

        - TDS beállítása főkönyvi kötelezettségekhez és kinnlevőségekhez.
        - Hozzon létre egy adólevonási és beszedési számlaszámot (TAN) és egy levonó típuskategóriát a vállalat számára.

    - Egyéb beállítás:

        - Állítson be egy fizetési ütemezést, amely tartalmazza a TDS-felosztást.
        - Kifizetésidíj-típus beállítása a TDS-hatóságnak történő fizetések esetében.
        - A TDS-csoportokra, az állandó számlaszámokra (PAN-ok) és a szállítók és vevők TAN-jaira vonatkozó információk beállítása.

2. **TDS-számítás a tranzakciókban:**

    - Számlák és kifizetések
    - Kötelezvények
    - Előlegfizetések
    - Előlegek

3. **TDS-elszámolás:**

    - Időszakos TDS-elszámolási folyamat
    - TDS-kifizetések elszámolása TDS-hatósági szállítóknak és TDS-challan generálása

4. **TDS-vizsgálatok, nyilatkozatok és tanúsítványok:**

    - TDS-tanúsítványszámok és dátumok rögzítése és frissítése.
    - TDS-lekérdezés és kiküldött TDS-lekérdezés létrehozása.
    - A 27A, a 26Q űrlap és a 27Q TDS űrlap és az e-TDS negyedéves kimutatásainak létrehozása.
    - 16A űrlap TDS-tanúsítvány létrehozása.
