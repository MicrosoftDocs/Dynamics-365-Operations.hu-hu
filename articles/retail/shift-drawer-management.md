---
title: Műszak és pénztárgépfiók kezelése
description: Ez a témakör bemutatja, hogyan állíthatók be és használhatók a műszakok a kiskereskedelmi pénztár (POS) esetében.
author: jblucher
manager: AnnBe
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailHardwareProfile, RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e600e1d2bb4bc1a49d55fb58b3e74fa7e13fc2af
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2017897"
---
# <a name="shift-and-cash-drawer-management"></a>Műszak és pénztárgépfiók kezelése

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja, hogyan állíthatók be és használhatók a műszakok a kiskereskedelmi pénztár (POS) esetében.

A Dynamics 365 Retail esetében a *műszak* kifejezés a pénztár tranzakciós adatait és tevékenységeit írja le két időbeli pont között. Minden műszakhoz az összeget, amely várható, hasonlítja a megszámlált és deklarált összeggel.

A műszakok általában a munkanap kezdetekor vannak megnyitva. Ezen a ponton a felhasználó feltünteti a nyitó összeget, amelyet a pénztárfiók tartalmaz. A nap folyamán értékesítési tranzakciókat hajtanak végre. Végül a nap végén megszámolják a fiók tartalmát, és a záró összeget deklarálják. A műszak le van zárva, és Z-jelentés készül. A Z-jelentés azt jelzi, hogy van-e felesleg vagy hiány.

## <a name="typical-shift-scenarios"></a>Műszak jellemző esetek

Több beállítási lehetőség és POS-művelet áll rendelkezésre a Retail esetében sokféle napi záró üzleti folyamat támogatásához a pénztár esetében. Ez a témakör néhány jellemző műszak-forgatókönyvet ír le.

### <a name="fixed-till"></a>Rögzített kassza

Hagyományosan ez az eset használt a leggyakrabban. Továbbra is széles körben használatos. A „rögzített kassza” műszaknál a műszak és a kassza egy adott pénztárgéphez van társítva. Ezek nem áthelyezhetők egy pénztárgépből a másikba. A „rögzített kassza” műszak lehet egy felhasználó által használt vagy több felhasználó között megosztott. A „rögzített kassza” műszakokhoz nincs szükség speciális konfigurációra.

### <a name="floating-till"></a>Mozgó kassza

A „mozgó kassza„ műszaknál a műszak és a pénzfiók áthelyezhető egyik pénztárgépből a másikba. Annak ellenére, hogy egy pénztárgéphez csak egy aktív műszak tartozható pénzfiókonként, a műszak felfüggeszthető és később folytatható egy másik pénztárgépen.

Például egy boltnak két pénztárgépe van. Mindkét pénztárgép meg van nyitva a nap elején, amikor a pénztáros új műszakot indít és megadja a nyitó összeget. Amikor az egyik pénztáros elkészült, hogy szünetet tart, ez a pénztáros a műszakot felfüggeszti, és a kasszát eltávolítja a pénztárfiókból. Adott pénztárgép ekkor más a pénztárosok számára elérhetővé válik. A másik pénztáros is bejelentkezhet, és a pénztárgépen saját műszakot nyithat meg. Miután az első pénztáros szünete véget ért, a pénztáros a többi pénztárgép elérhetővé válása esetén folytathatja a műszakját. A „mozgó kassza” műszakokhoz nincs szükség speciális konfigurációra vagy engedélyre.

### <a name="single-user"></a>Egy felhasználó

Számos kiskereskedő szívesebben engedélyez műszakonként csak egy felhasználót, a pénztárfiókban levő készpénz magasabb szintű elszámoltathatóságának biztosítására. Ha csak egy felhasználó számára engedélyezett a kassza használata, amely a műszakhoz van társítva, a felhasználó visel kizárólagos felelősséget az esetleges eltérésekért. Ha egynél több felhasználó használ egy műszakot, nehéz meghatározni, ki követett el hibát, vagy ki próbált esetlegesen lopni a kasszából.

### <a name="multiple-users"></a>Több felhasználó

Egyes kiskereskedők hajlandóak feláldozni az egyfelhasználós műszakok biztosította elszámoltathatóság szintjét, és egynél több felhasználót engedélyezni műszakonkén. Ez a megközelítés akkor jellemző, ha a felhasználók száma meghaladja az elérhető pénztárgépek számát, és rugalmasság és sebesség szükségessége fontosabb, mint a lehetséges veszteség. Akkor is jellemző, ha az üzletvezetőknek nincs saját műszakjuk, de szükség szerint használhatják a műszakját a pénztárosok bármelyikének. A bejelentkezéshez egy másik felhasználó által megnyitott műszakba, és annak használatához, a felhasználónak rendelkeznie kell a **Több műszakba történő bejelentkezés engedélyezése** POS-engedéllyel.

### <a name="shared-shift"></a>Megosztott műszakok

A „megosztott műszak” konfigurációnál a kiskereskedőnek egyetlen műszakja lehet több pénztárra, pénztárgépfiókra és felhasználóra nézve. A megosztott műszak rendelkezik egy egyetlen kezdő és záró összeggel, amely minden pénztárgépfiókra összesített. Megosztott műszakok leggyakoribbak a mobileszközök használatakor. Ebben az esetben egy külön pénzfiók nem foglalt minden egyes pénztárgépnél. Ehelyett minden pénztárgép megoszt egy pénztárgépfiókot.

Az üzletekben megosztott műszak használatához a pénztárfiókot is be kell állítani „megosztott műszakúként” a **Kiskereskedelem \> Csatorna beállítása \> POS alkalmazás telepítése \> POS-profilok \> Hardverprofilok \> Fiók**. Emellett a felhasználóknak rendelkezniük kell egy vagy több megosztott műszak engedéllyel (Megosztott műszak kezelésének engedélyezése és Megosztott műszak használatának engedélyezése).

> [!NOTE]
> Csak egy megosztott műszak lehet nyitott egyidejűleg az egyes üzletekben. Megosztott műszakok és önálló műszakok ugyanabban az üzletben használhatók.

## <a name="shift-and-drawer-operations"></a>Fiók és műszak műveletek

Különféle műveletek hajthatók végre a műszak állapotának módosítására, vagy a pénzfiókban levő pénzösszeg növelésére vagy csökkentésére. Ez a szakasz bemutatja a műszakműveleteket a Retail Modern POS és a Cloud POS alkalmazásokban.

### <a name="open-shift"></a>Nyitott műszak

A pénztár megköveteli, hogy a felhasználók aktív, nyitott műszakban végezzék mindazon műveleteket, amelyek pénzügyi tranzakciót eredményeznek, például eladás, visszaváltás vagy vevői megrendelés.

Amikor a felhasználó bejelentkezik a POS-nál, a rendszer először ellenőrzi van-e aktív műszak az aktuális pénztárgépen a felhasználóhoz. Ha nincs aktív műszak, a felhasználó dönthet úgy, hogy megnyit egy új műszakot, folytat egy meglévő műszakot, vagy bejelentkezik „nem fiókos” üzemmódban, a rendszerkonfigurációtól és a felhasználói engedélyektől függően.

### <a name="declare-start-amount"></a>Nyitó összeg elszámolása

Ez a művelet gyakran az első, amelyet az újonnan megnyitott műszakokon végrehajtanak. A művelethez a felhasználók megadják a fiókban levő kezdő pénzösszeget a műszakra. Ez a művelet fontos, mert a kezdő összeget a rendszer figyelembe veszi a felesleg vagy hiány-számításhoz a műszak lezárásakor.

### <a name="float-entry"></a>Váltópénzbetét

A *váltópénzbetétek* olyan nem értékesítési tranzakciók, amelyeket az aktív műszakon lehet elvégezni, növelve a pénzfiókban a készpénz mennyiségét. A váltópénzbetét jellemző példája az a tranzakció, ha további aprót kíván betenni a fiókba, amikor kifogyóban van.

### <a name="tender-removal"></a>Fizetőeszköz kivétele

A *fizetőeszköz-törlések* olyan nem értékesítési tranzakciók, amelyeket az aktív műszakon lehet elvégezni, csökkentve a pénzfiókban a készpénz mennyiségét. Ezt a műveletet leggyakrabban egy másik műszakbeli váltópénzbetéttel együtt használjuk. Például mivel az 1. pénztárban kevés az apró, ezért a 2. pénztár fizetőeszköz-eltávolítást hajt végre a pénzfiókjában lévő mennyiség csökkentésére. A felhasználó az 1. pénztárgépen végrehajtja a váltópénzbetétet a saját pénzfiókjában levő összeg növelése érdekében.

### <a name="suspend-shift"></a>Műszak felfüggesztése

A felhasználók felfüggeszthetik az aktív műszakjukat, hogy felszabadítsák az aktuális pénztárgépet egy másik felhasználó számára, vagy a műszakot áthelyezhetik egy másik pénztárgépre (ezt a műszakot gyakran „mozgó kassza” műszaknak nevezik).

A műszak felfüggesztése megakadályozza az új tranzakciókat vagy a műszak változtatásait, mindaddig, amíg a folytatást nem választja.

### <a name="resume-shift"></a>Műszak folytatása

Ez a művelet lehetővé teszi, hogy a felhasználó folytasson egy felfüggesztett műszakot egy olyan pénztárgépen, amelyiken még nincs aktív műszak.

### <a name="tender-declaration"></a>Fizetőeszköz-elszámolás

Ezt a műveletet a teljes összegnek, amely jelenleg a pénztárfiókban van, a meghatározásához hajtják végre. Felhasználók ezt a műveletet leggyakrabban a műszakzárás előtt hajtják végre. Ezt az összeget veti össze a rendszer a várt műszakösszeggel a többlet/hiány összeg kiszámításához.

### <a name="safe-drop"></a>Széfes befizetés

Széfes befizetések az aktív műszak alatt bármikor elvégezhetők. Ez a művelet eltávolítja a pénzt a készpénzfiókból, hogy biztonságosabb helyre legyen átvihető, például egy széfben a hátsó helyiségben. A széfes befizetésekhez rögzített teljes összeg továbbra is szerepel a műszak összegében, de nem kell feltétlenül beszámítani a fizetőeszköz-elszámolásba.

### <a name="bank-drop"></a>Banki befizetés

A széfes befizetésekhez hasonlóan a banki befizetések is az aktív műszakban futnak le. Ez a művelet eltávolítja a műszakból a pénz, előkészítve a banki letétre.

### <a name="blind-close-shift"></a>Műszakzárás számlálás nélkül

A *Számlálás nélkül lezárt műszakok* már nem aktívak, de még nem lettek teljesen lezárva. Felfüggesztett műszakokkal ellentétben a számlálás nélkül lezárt műszakok nem folytathatók. A műveletek azonban, például a Nyitó összeg elszámolása Fizetőeszköz-elszámolás, később, vagy egy másik pénztárgépen is végrehajthatók.

A számlálás nélkül lezárt műszakok gyakran használatosak pénztár új felhasználó vagy a műszak részére történő felszabadításához, anélkül, hogy előbb teljes mértékű számlálást, egyeztetést és zárást végeznénk ezen a műszakon.

### <a name="close-shift"></a>Műszakzárás

Ez a művelet számítja ki a műszak összegeit, a többlet/hiány összegeket, és ezután véglegesít egy aktív és számlálás nélkül lezárt műszakot. A felhasználói engedélyektől függően a Z-jelentés is kinyomtatódik a műszakról. A lezárt műszakok nem folytathatók és nem módosíthatók.

### <a name="print-x"></a>X nyomtatás

Ezzel a művelettel X-jelentést hoz létre nyomtat az aktuális aktív műszakhoz.

### <a name="reprint-z"></a>Z újranyomtatás

Ez a művelet újra kinyomtatja a legutóbbi Z-jelentést, amit a rendszer generált, amikor a műszak le lett zárva.

### <a name="manage-shifts"></a>Műszakok kezelése

A művelet segítségével a felhasználók megtekinthetik az üzlet aktív, felfüggesztett és számlálás nélkül lezárt műszakjait. Engedélyeiktől függően a felhasználók a végleges zárási eljárásaikat is végrehajthatják, például a fizetőeszköz-elszámolásokat és műszakzárás műveletet számlálás nélkül lezárt műszakok számára. Ez a művelet azt is lehetővé teszi a felhasználó számára, hogy megtekintsék és töröljék az érvénytelen műszakokat abban a ritka esetben, amikor a műszak az offline és online módok közötti átváltást követően hibás állapotban marad. Ezek az érvénytelen műszakok nem tartalmaznak az egyeztetéshez szükséges pénzügyi információkat vagy tranzakciós adatokat.

## <a name="shift-and-drawer-permissions"></a>Fiók és műszak engedélyei

A következő POS-engedélyek befolyásolják, hogy a felhasználó a különböző helyzetekben mit és mit nem hajthat végre:

- **Számlálás nélküli zárás engedélyezése**
- **X-jelentés nyomtatásának engedélyezése**
- **Z-jelentés nyomtatásának engedélyezése**
- **Fizetőeszköz-elszámolás engedélyezése**
- **Váltópénz-elszámolás engedélyezése**
- **Fiók kinyitása értékesítés nélkül**
- **Több műszakba történő bejelentkezés engedélyezése** Az engedéllyel a felhasználó bejelentkezhet egy másik felhasználó által megnyitott műszakba és használhatja. Az ezzel az engedéllyel nem rendelkező felhasználók csak az általuk megnyitott műszakokba jelentkezhetnek be, és csak ezeket használhatják.
- **Megosztott műszak kezelésének engedélyezése** – A felhasználóknak a megosztott műszak megnyitásához vagy zárásához ezzel az engedéllyel kell rendelkezniük.
- **Megosztott műszak használatának engedélyezése** – A felhasználóknak a megosztott műszakba való bejelentkezéshez és a használatához ezzel az engedéllyel kell rendelkezniük.

## <a name="back-office-end-of-day-considerations"></a>Háttérirodai napzárási szempontok

A műszakok és a készpénzfizetési fiók egyeztetésének használata a pénztárban eltér a tranzakcióadatok összesítésétől a kimutatásszámításában. Fontos megérteni ezt az eltérést. Attól függően, hogy mi a konfigurációja és az üzleti folyamatai, a műszakadatok a pénztárban (Z-jelentés), és a számított kimutatás a háttérirodában, eltérő eredményeket adhat. Ez a különbség nem feltétlenül jelenti azt, hogy a műszakadatok vagy a számított kimutatás helytelen, vagy hogy az adatokkal probléma van. Ez csak azt jelenti, hogy a megadott paraméterek több vagy kevesebb tranzakciót tartalmaznak, vagy a tranzakciók vannak összegezve másképp.

Annak ellenére, hogy minden kiskereskedő különböző üzleti követelményekkel rendelkezik, azt ajánljuk, hogy a rendszert a következő módon állítsa be, hogy elkerülje az ilyen típusú különbség előfordulását:

Ugrás ide: **Kiskereskedelem \> Csatornák \> Kiskereskedelmi egységek \> Minden kiskereskedelmi egység \> Kimutatás/zárás**, és minden egyes üzlethez, mind a **Kimutatás módszere** mezőt, mind a **Zárási mód** mezőt állítsa erre: **Műszak**.

Ez a beállítás segítségével garantálható, hogy a háttérirodai kimutatások ugyanazokat a tranzakciókat tartalmazzák, mint a műszakok a pénztárban, és hogy az adatokat összegzése műszak szerint történik.

Kimutatás és a záró módszerekkel kapcsolatos további tudnivalókat lásd: [Konfigurációk tárolása kiskereskedelmi kimutatásokhoz](https://docs.microsoft.com/dynamics365/unified-operations/retail/tasks/store-configurations-retail-statements).
