---
title: Egy bizonylat
description: "A pénzügyi naplók (főkönyvi napló, tárgyieszköz-napló, szállítói kifizetési napló és így tovább) Egy bizonylat funkciójának használatával bevihető több analitikusnapló-tranzakció egyetlen bizonylat keretein belül."
author: kweekley
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9f996131830f9bd4efd534143b3fb761c5ccc756
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="one-voucher"></a>Egy bizonylat

[!include [banner](../includes/banner.md)]

> [!NOTE]
>  Ez a funkció a Dynamics 365 for Finance and Operations 8.0 verziójában lesz elérhető, amely a 2018. tavaszi kiadásban jelenik meg.   

<a name="what-is-one-voucher"></a>Mi az az „Egy bizonylat”?
======================

A pénzügyi naplók (főkönyvi napló, tárgyieszköz-napló, szállítói kifizetési napló és így tovább) meglévő funkcióinak használatával bevihető több analitikusnapló-tranzakció egyetlen bizonylat keretein belül. Erre a funkció az „Egy bizonylat” megnevezéssel hivatkozunk. Egy bizonylatot az alábbi módszerek egyikével hozhat létre:

-   Állítsa be a napló nevét (**Főkönyv** \> **Naplóbeállítás** \> **Naplónevek**) úgy, hogy az **Új bizonylatot** mező értéke **Csak egy bizonylatszám** legyen. * Minden, a naplóhoz hozzáadott sor most ugyanarra a bizonylatra kerül. Mivel minden sor ugyanarra a bizonylatra kerül, a bizonylat többsoros bizonylatként is megadható, mint számla/ellenszámla ugyanazon a soron, vagy kombinációként.

[![Egy sor](./media/same-line.png)](./media/same-line.png)
 
> [!IMPORTANT] 
> *  Megjegyzés: az "Egy bizonylat" meghatározása nem tartalmazza azokat a naplónevet, amelynek csak **Egy bizonylatszámként** vannak beállítva, amit követően a felhasználó csak csak főkönyvi számlatípusokat tartalmazó bizonylatokat visz be.  A jelen dokumentumban az „Egy bizonylat” azt jelenti, hogy van egy bizonylat, amelyen egynél több szállító, vevő, bank, tárgyi eszköz vagy projekt szerepel. 

-   Adjon meg egy többsoros bizonylatot, ha nincs ellenszámla.

[![Többsoros bizonylat](./media/Multi-line.png)](./media/Multi-line.png)

-   Adjon meg egy bizonylatot, ha a számla és az ellenszámla is analitikus számlatípust tartalmaz – például a szállító/szállító, vevői/vevő, szállító/vevő vagy bank/bank.

[![Analitikus bizonylat](./media/subledger.png)](./media/subledger.png)

<a name="issues-with-one-voucher"></a>Problémák az Egy bizonylat funkcióval
=======================

Az Egy bizonylat funkció problémákat okoz a kiegyenlítés, az adószámítás, egy analitikus napló egyeztetése a főkönyvbe, a pénzügyi beszámolók és egyebek egyeztetése során. (Például elszámolása közben előforduló hibákkal kapcsolatos további tudnivalókhoz lásd: [Egyetlen bizonylat több vevő- vagy szállítórekorddal](https://docs.microsoft.com/en-us/dynamics365/unified-operations/financials/accounts-payable/single-voucher-multiple-customer-vendor-records).) Ahhoz, hogy megfelelően működjenek és készítsenek jelentéseket, ezek a folyamatok és jelentések tranzakciós részleteket igényelnek. Bár egyes forgatókönyvek még mindig jól működhetnek, a szervezete beállításai alapján gyakoriak a problémák, ha több tranzakció kerül egy bizonylatra.

Például feladhatja az alábbi többsoros bizonylatot.

[![Példa](./media/example.png)](./media/example.png)

Ekkor létrehozza a **Szállítónkénti költségek** jelentést a **Pénzügyi információk** munkaterületen. A jelentés szállítócsoport és szállító szerint csoportosítja a költségszámla-egyenlegeket. A jelentés létrehozásakor a rendszer nem tudja megállapítani, melyik szállítói csoportok/szállítók esetében merült fel a 250,00 költség. Mivel a tranzakció részletei hiányoznak, a rendszer feltételezi, hogy az első bizonylaton található 250,00 összérték az első szállítónál merült fel. A 250,00, amely a 600120 fő számla egyenlegében szerepel, ekkor megjelenik a szállítói csoport vagy szállító alatt. Nagyon valószínű, hogy a bizonylaton szereplő első szállító nem a megfelelő szállító volt, így a jelentés nem megfelelő.

[![Kiadás](./media/expenses.png)](./media/expenses.png)

<a name="the-future-of-one-voucher"></a>Az Egy bizonylat jövője
=========================

A korábban jelzett problémák miatt az Egy bizonylat funkció elavulttá lesz nyilvánítva. Mivel azonban vannak ezen a funkción alapuló funkcionális hiányosságok, a funkció elavulása nem egy időben fog történni. Ehelyett a következő ütemezést használjuk: 

- **2018. tavaszi kiadás** – A funkcionalitás alapértelmezés szerint ki lesz kapcsolva egy Főkönyvi paraméter révén. Azonban bekapcsolhatja a funkciót, ha a szervezetének olyan helyzetet kell kezelnie, amely a témakörben később ismertetett, üzleti esetekkel kapcsolatos hiányok valamelyikének felel meg.

  -   Ha egy vevő üzleti helyzete olyan, hogy nincs szükség az Egy bizonylat funkcióra, ne kapcsolja be a funkciót. Nem javítjuk ki a „programhibákat”, amelyeket későbbi azonosítottak ebben a témakörben, ha annak ellenére használják ezt a funkciót, hogy létezik egy másik megoldás.

  -   Az Egy bizonylatot ne használja a Microsoft Dynamics 365 Finance and Operations integrációkhoz, kivéve, ha a funkció a működési rések egyikéhez szükséges.

- **2018 őszi és későbbi kiadások** – A funkcionális hiányosságok pótlása. A funkcionális hiányosságok pótlását követően az Egy bizonylat funkció véglegesen ki lesz kapcsolva.

- > [!IMPORTANT]
  > Ne feledje, hogy a **Csak egy bizonylatszám** beállítás NEM lett eltávolítva a naplónév-beállítások közül.  A funkció továbbra is támogatott, ha a bizonylat csak főkönyvi számlatípusokat tartalmaz.  A vevőknek körültekintően kell eljárniuk a beállítás használatakor, mert a bizonylat feladása nem történik meg, ha a **Csak egy bizonylatszám** funkciót használják, de aztán egynél több vevőt, szállítót, bankot, tárgyi eszközt vagy projektet adnak meg.  Ezenkívül a vevők továbbra is megadhatnak többfajta analitikus számlatípust, például egy kifizetést egyetlen bizonylaton, amely szállítói-banki számlatípusokat tartalmaz.  

<a name="why-use-one-voucher"></a>Miért használjon egy bizonylatot?
====================

Vevőkkel folytatott beszélgetések alapján összeállítottuk az alábbi forgatókönyvek listáját, ahol a vevők az Egy bizonylat funkciót használják, illetve a használatának okait adják meg. Egyes üzleti követelmények csak az egy bizonylat segítségével teljesíthetők. Sok esetben azonban alternatívák is megfelelhetnek ugyanazon üzleti követelményeknek.

<a name="scenarios-that-require-one-voucher"></a>Egy bizonylatot igénylő esetek
----------------------------------

A következő forgatókönyvek csak az Egy bizonylat funkció használatával végezhetők el. Ezeket a működési réseket más szolgáltatások fogják betölteni a 2018 őszi és a későbbi verziókban.

-   **Szállítói vagy vevői kifizetések feladása a bankszámlára összegző formában**

    -   A szervezet egy szállítókból és összegekből álló listát közöl a bankjával, és a bank ezt a listát használja a szervezet nevében a szállítók fizetésére. A bank a kifizetések összesített összegét egyetlen kivétkén könyveli el a bankszámlán.

>   A szállítói kifizetések összefoglalása csak az Egy bizonylaton keresztül támogatott. Minden szállító külön sorként kerül be az analitikus Kötelezettségek számlára az adatok nyilvántartásához, viszont az összes kifizetés teljes összege egyetlen sorral áll szemben a bankszámlán. Emiatt a visszavonás a banki analitikus naplóban egyetlen összesített összegként jelenik meg.

-   Egy szervezet betétek vevői kifizetéseket fizet be, vagy a bank helyez el vevői kifizetéseket a szervezet nevében, és a befizetés átalányösszegként szerepel a bankszámlán.

>   Vevői kifizetések összefoglalását általában a jóváírás funkció támogatja. Azonban ha „áthidalást” használ a fizetési módnál, ezt az esetet csak az Egy bizonylat funkció támogatja. A vevői kifizetések bevitele a szállítóikifizetés-összefoglalóban ismertetett módhoz hasonlóan történik.

-   **Mechanizmus tranzakciók csoportosítására egy üzleti eseményből**

    -   Egy szervezetnél egyetlen üzleti esemény történik, amely több tranzakciót vált ki. Azonban a számviteli osztály a könyvvizsgálati tételeket együtt szeretné látni a jobb auditálhatóság érdekében.

>   Ha egy szervezetnek egyben kell áttekitenie az egy üzleti eseményhez tartozó könyvelési tételek, használja az Egy bizonylat funkciót. 

- **Ország-/régiófüggő funkciók**

  -   Az egységes vámokmány (EV) funkció Lengyelország esetében jelenleg egyetlen bizonylat használatát igényli. Amíg a funkcióhoz nem érhető el csoportosítási beállítás, továbbra is az Egy bizonylat funkciót kell használni. Előfordulhat, hogy vannak további, a Egy bizonylat funkciót igénylő országspecifikus funkciók.

- **Vevői előlegkifizetési napló, amelynél több „soron” találhatók adók**

  -   A vevő előre fizet egy rendelésért, és a rendelés sorai különböző adókat tartalmaznak, amelyeket rögzíteni kell az előlegfizetéshez. Az előleg vevői kifizetés egy tranzakció, amely szimulálja a rendelés sorait, hogy a megfelelő adó rögzíthető legyen az összeghez, soronként.

Ebben az esetben az egyetlen bizonylaton szereplő vevők ugyanaz a vevő, mert a tranzakció a vevői rendelés sorait szimulálja. Az előleget egy bizonylaton kell bevinni, mert az adószámítást egy vevői kifizetés „sorain” kell végrehajtani.

-   **Tárgyi eszközök karbantartása: felzárkózó értékcsökkenés, felosztott eszköz, értékcsökkenés kiszámítása kivezetéskor**

A következő tárgyieszköz-tranzakciók szintén több tranzakciót hoznak létre egyetlen bizonylaton belül:
-   Egy eszközön további beszerzés történik, és „elmaradt” értékcsökkenés kiszámítására kerül sor.
-   Egy eszköz fel van osztva.
-   Engedélyezésre kerül az értékcsökkenés kivezetéskori kiszámítására használandó paraméter, és ezután a eszköz kivezetésre kerül.

<a name="scenarios-that-dont-require-one-voucher"></a>Egy bizonylatot nem igénylő esetek
----------------------------------------

A következő forgatókönyveket más módon is el lehet végezni, és nem szabad az Egy bizonylatot használni.

-   **Vevői kifizetések feladása a bankszámlára összegző formában**

Egy szervezet betétek vevői kifizetéseket fizet be, vagy a bank helyez el vevői kifizetéseket a szervezet nevében, és a befizetés átalányösszegként szerepel a bankszámlán.

A vevői kifizetések összefoglalását a jóváírás funkció támogatja, ha az áthidalást nem használják a fizetési módnál.

-   **Nettóérték-számítás**

Nettóérték-számításnál a szállító és a vevő egyenlegét egymás ellen számítjuk be, mivel a szállító és a vevő ugyanaz a fél. Ezzel a módszerrel minimálisra csökkenthető a szervezet és a vevő vagy szállító fél közötti pénzcsere.

Nettóérték-számítás végezhető úgy, hogy a növekedést és a csökkenést külön bizonylatokon visszük be, a különbözetet pedig feladjuk egy elszámoló főkönyvi számlára.

-   **Összegző feladás a főkönyvbe**

A szervezetek gyakran szeretnék az adatokat összegezve feladni a főkönyvbe, hogy minimalizálják az adatok mennyiségét. Azonban a szervezetek jellemzően továbbra is előírják a tranzakció részleteinek megőrzését. Ha a feladás összegzéssel történik egyetlen bizonylaton keresztül, a tranzakció részletei nem ismertek, és nem lehet karban tartani őket.

   -   Mivel a tranzakciós részleteket jelenleg nem lehet karbantartani, azt javasoljuk, hogy az Egy bizonylat funkciót ne használja összefoglaló feladásához.
   -   Az Egy bizonylat funkció támogatása megszűnése után a Forrásbizonylat és a Könyvelési keretrendszerek a naplókban valósíthatók meg. Ezek a keretrendszerek ezt követően karbantartják a tranzakció adatait, és a támogatják az összefoglaló beküldését a főkönyvbe.

-   **Több feladatlan kifizetés kiegyenlítése ugyanazon a számlán**

Ez a forgatókönyv általában a kiskereskedelmi szervezetekre jellemző, ahol a felhasználók többféle fizetési módot használhatnak a vásárlások kifizetésére. Ilyen esetben a szervezetnek több feladatlan kifizetést kell rögzítenie és rendeznie a vevői számla alapján.

A Microsoft Dynamics 365 for Operations 1611-es verziójához (2016. november) hozzáadott új funkció lehetővé teszi, hogy több fel nem adott kifizetést egyetlen számlával szemben rendezzen. Több vevői kifizetést már nem kell egyetlen bizonylaton megadni.

-   **Banki kivonatban szereplő tranzakciók importálása**

A bankok gyakran fizetnek és kapnak kifizetéseket egy szervezet nevében, és ezeket a tranzakciókat a Finance and Operations a banktól kapott fájlon keresztül rögzíti. A szervezetek gyakran szeretnék összevonni ezeket a tranzakciókat a banki kivonat számával a fájlban. Mivel az egyes tranzakciók részletesen szerepelnek a banki kivonaton, a banki naplóban nem szükséges összegzés.

A tranzakciókat a napló egyéb mezőinek segítségével lehet csoportosítani, például a napló kötegszáma vagy a dokumentumszám alapján.

-   **Egyenlegek átvitele**

Egy szervezetnek egy szállító egyenlegének átvitelére lehet szüksége egy másik szállítóhoz vagy hiba miatt, vagy mert egy másik szállító átvette a kötelezettséget. Ilyen típusú átutalások olyan számlatípusok esetében is előfordulnak, mint a vevők és bankszámlák.

Egyenlegátvitelek (szállítói, vevői, bankszámla stb.) egy számláról másik számlára külön bizonylatok révén kivitelezhető, és az ellenszámla elszámolási főkönyvi számlára adható fel.

-   **Nyitóegyenlegek megadása**

A szervezetek gyakran egy bizonylatos tranzakcióként adják meg az alszámlák (szállítók, vevők, tárgyi eszközök stb.) nyitóegyenlegét. Az egyes analitikus számlák nyitó egyenlegei külön bizonylatokként adhatók meg, az ellenszámla pedig elszámoló főkönyvi számla lehet.

-   **Feladott vevői vagy szállítói dokumentum könyvelési bejegyzésének kijavítása**

Egy szervezetnek a Kinnlevőségek vagy Kötelezettségek főkönyvi számla korrekciójára lehet szüksége egy könyvelt számla számlabejegyzéshez, de a számlát nem lehet sztornírozni vagy javítani másik mechanizmus révén.

Ha korrigálni kell a kinnlevőségek vagy a kötelezettségek főkönyvi számlát, a korrekciót közvetlenül a főkönyvi számlán kell elvégezni. A korrekció nem adható fel a vevőn vagy a szállítón keresztül. Ez a módszer azt igényli, hogy a korrekció „állásidő” alatt történjen meg, hogy a főkönyvi számla ideiglenesen engedélyezhesse a manuális bevitelt.

-   **„A rendszer lehetővé teszi”**

A szervezetek gyakran csak azért használják az Egy bizonylat funkciót,mert a rendszer lehetővé teszi számukra, és nem gondolnak bele a következményekbe.

