---
title: Veszélyes anyagok beállítása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a cikkek veszélyes anyagokként történő osztályozásához szükséges adatokat. Ha olyan értékesítési rendelést hoz létre, amelyben veszélyes anyagként minősített cikkek szerepelnek, akkor a rendszer az értékesítési rendeléshez tartozó veszélyes anyag-dokumentációt létrehozza a szállításkor.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: b049559b64045e80a40afd99bac30a9cfe1d0580
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429703"
---
# <a name="set-up-hazardous-materials"></a>Veszélyes anyagok beállítása

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A veszélyes anyagok funkció használatához először be kell állítani a cikkek veszélyes anyagokként való osztályozásához szükséges adatokat. Majd, ha olyan értékesítési rendelést hoz létre, amelyben veszélyes anyagként minősített cikkek szerepelnek, akkor a rendszer az értékesítési rendeléshez tartozó veszélyes anyag-dokumentációt létrehozza a szállításkor.

## <a name="turn-on-the-hazardous-materials-feature-for-your-system"></a>A veszélyes anyagok funkció bekapcsolása a rendszerben

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Termékinformáció-kezelés*
- **Szolgáltatás neve:** *Veszélyes anyagok termékinformációi és szállítási dokumentációja*

## <a name="hazardous-material-regulations"></a>Veszélyes anyagokra vonatkozó előírások

A veszélyes anyagok folyamatainak használatához először létre kell hozni egy előírást. Az előírások határozzák meg, hogy hogyan legyen nyomtatva a szállítási szöveg egy cikkhez. Meghatározza a társított szállítási módokat is.

Itt van talál néhány gyakori előírást:

- **ADR** – a veszélyes áruk nemzetközi közúti fuvarozásával kapcsolatos szabályozások
- **CFR 49** – szabályozások a veszélyes áruk Egyesült Államokban történő szállítására
- **IMDG** – a Veszélyes Áruk Nemzetközi Tengerészeti (IMDG) kódexe
- **IATA** – a Nemzetközi Légiforgalmi Szövetség (IATA) veszélyes árukra vonatkozó szabályozásai

Ezek az előírások segítenek meghatározni, hogy milyen adatok jelenjenek meg a cikkek szállítási szövegének nyomtatásakor. Meg lehet bármennyi előírást, amelyet be kell tartani.

> [!IMPORTANT]
> A veszélyes anyagokhoz kapcsolódó adatkódok beállítására szolgáló funkció nem biztosítja a vállalat jogszabályi megfelelőségét. Ez csak olyan eszköz, amely segít a vállalatok folyamatainak kiépítésében.

Egy előírás általában egy adott szállítási mód, például a tengeri fuvarozás, a közúti árufuvarozás vagy a légi fuvarozás esetében áll rendelkezésre. Ebből következően az egyes előírásokat egy szállítási móddal lehet társítani. A szállítási mód akkor használatos, ha az adott dokumentumokat a Raktárkezelésben nyomtatják ki. A Raktárkezelés modulban minden szállítmány egy szállítmányozóhoz és egy szállítmányozói szolgáltatáshoz kapcsolódik, amely a **Szállítás** modulban be van állítva. A szállítási mód a szállítmányozóhoz és szállítmányozói szolgáltatáshoz van társítva. A jelentések futtatásakor a szállítási mód a kiadott elemhez társított szállítási nyomtatandó szöveg megtalálására szolgál.

Ez a beállítási adat nem specifikus jogi személyekre (vállalat). Ennek megfelelően a jogi személyek között közösen használt veszélyes anyagokkal kapcsolatos adatokat lehet létrehozni.

Mindegyik előíráshoz meghatározhatja az anyagok listáját, és felhasználhatja a kiadott cikkekhez társított sablonként. Mindegyik előíráshoz meg lehet adni egy nyomtatási beállítást is. A nyomtatási beállítással megadhatja, hogy hogyan történjen legyen a cikkek szállítási szövege felépítve. A nyomtatási beállítással lehet kialakítani a kiadott cikkek szállítási nyomtatási szövegét.

A veszélyes anyagokra vonatkozó előírások beállításához Válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyagokra vonatkozó előírások** lehetőséget. A **Veszélyes anyagokra vonatkozó előírások** lapon tetszőleges számú előírást hozhat létre, és a következő alszakaszokban ismertetett mezők alapján konfigurálhatja azokat.

### <a name="hazardous-material-regulation-header"></a>Veszélyes anyagokra vonatkozó előírások fejléce

Mindegyik előírásnak van egy kódja és egy leírása. Az alábbi táblázat bemutatja a fejlécben rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Szabályozás kódja | A veszélyes anyagokra vonatkozó szabály rekordját azonosító kód megadása. |
| Leírás | Adja meg a veszélyesanyag-előírás leírását. |

### <a name="print-setup-fasttab"></a>Nyomtatási beállítások gyorslap

Mindegyik előíráshoz tetszőleges számú nyomtatási beállítás tartozhat. A nyomtatási beállításokat a **Nyomtatási beállítások** gyorslapon határozhatja meg. Az alábbi táblázat bemutatja az egyes nyomtatási beállításokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Sorrend | Annak a sorrendnek a megadása, amelyben a program a szállítási szövegben hivatkozik a mezőkre. |
| Mező nyomtatása | Válassza ki a szállítási szövegben szerepeltetendő mezőt. A veszélyes anyag mezőinek nem mindegyike áll rendelkezésre nyomtatáshoz. Csak a különböző előírások szállítási szövegének definiálására használt közös mezők lesznek elérhetők. Az első nyomtatandó mezőt mezőelválasztóként kell definiálni, amelynek **Sorozat** értéke *0* (nulla), így a többi mező között elválasztóként használható. Csak egy hivatkozás szükséges a mező elválasztóhoz.<p>A következő értékek állnak rendelkezésre:</p><ul></li><li>**Mezőelválasztó** – Ezt a nyomtatási mezőt használja a program a szöveg elválasztójaként. Csak egy mezőelválasztó szükséges a sorozatban. A nyomtatási mező **Sorozatát** általában *0* (nulla) értékre kell állítani. A rendszer megkeresi a mezőelválasztót, és a listában elsőként megtalált értéket fogja használni. A karakterláncban használt szöveges érték a **Nyomtatás utána** mezőből származik.</li><li>**Azonosító** – Ez a nyomtatási mező az [azonosítókódot és/vagy leírást](#identification) helyezi el a nyomtatott szövegbe.</li><li>**Osztály** – Ez a nyomtatási mező az [osztálykódot és/vagy leírást](#classes) helyezi el a nyomtatott szövegbe.</li><li>**Divízió** – Ez a nyomtatási mező a [divíziókódot és/vagy leírást](#divisions) helyezi el a nyomtatott szövegbe.</li><li>**Csomagolási csoport** – Ez a nyomtatási mező a [csomagolásicsoport-kódot és/vagy leírást](#packing-group) helyezi el a nyomtatott szövegbe.</li><li>**Alagútkód és/vagy leírás** – Ez a nyomtatási mező a [alagútkódot és/vagy leírást](#tunnel) helyezi a nyomtatott szövegbe.</li><li>**Megfelelő szállítási név** – Ez a nyomtatási mező a [megfelelő szállítási nevet](hazmat-items.md#hazmat-description) helyezi el a nyomtatott szövegbe.</li><li>**Műszaki név** – Ez a nyomtatási mező a [műszaki nevet és/vagy leírást](#technical-name) helyezi el a nyomtatott szövegbe.</li><li>**Szállítási kategória** – Ez a nyomtatási mező a [szállítási kategóriát és/vagy leírást](#transport-category) helyezi el a nyomtatott szövegbe.</li><li>**Rakodás** – Ez a nyomtatási mező a [rakodási kódot és/vagy leírást](#stowage) helyezi el a nyomtatott szövegbe.</li><li>**Rögzített szöveg** – Ez a nyomtatási mező a **Rögzített szöveg** mezőben megadott szöveget írja ebbe a sorba.</li><li>**Címkekód és/vagy leírás** – Ez a nyomtatási mező a [címkekódot és/vagy leírást](#label) helyezi a nyomtatott szövegbe.</li><li>**Csomagolás repülőre** – Ez a nyomtatási mező a [repülőre csomagolás kódját és/vagy leírást](#packing-instruction) helyezi el a nyomtatott szövegbe.</li><li>**Korlátozott mennyiség** – Ez a nyomtatási mező ellenőrzi, hogy a tétel [korlátozott mennyiségű tételként](hazmat-items.md#material-management) van-e megjelölve, és ha igen akkor a program a **Rögzített szöveg** mezőben megadott szöveget adja meg.</li><li>**Csaomagolási leírás** – Ez a nyomtatási mező a [csomagolási leírást](#packing-description) helyezi el a nyomtatott szövegbe.</li></ul> |
| Nyomtatás ez előtt: | Adja meg azt a szöveget, amelyet a **Nyomtatási mező** beállításban definiált tartalom előtt kell nyomtatni. |
| Nyomtatás ez után: | Adja meg azt a szöveget, amelyet a **Nyomtatási mező** beállításban definiált tartalom után kell nyomtatni. |
| Nyomtatás az előzővel | Ennek a jelölőnégyzetnek a bejelölésével megakadályozhatja, hogy előző mező és a mező között elválasztó legyen nyomtatva. Ennek a jelölőnégyzetnek a bejelölésével olyan mezőket lehet nyomtatni, amelyek opcionálisak, vagy egy másik nyomtatási mező tartalmazza azokat. |
| Rögzített szöveg | Ha a **Nyomtatási mező** mezőt **Rögzített szöveg** vagy **Korlátozott mennyiség** értékre állítja be, akkor írja be a nyomtatandó szöveget. |
| Felvétel nyomtatásba | Válassza ki, hogy melyik értéket vagy értékeket kell kinyomtatni a kiválasztott nyomtatási mezőből ehhez a sorhoz. Kinyomtathatja a kódot, a leírást, illetve a kódot és a leírást is. |

### <a name="mode-of-delivery-fasttab"></a>Szállítási mód gyorslap

Az előírás egy megosztott tábla, és nem az egyes jogi személyekre vonatkozik. A szállítási módok azonban jogi személyhez specifikusak. Ezért a szállítási mód beállításakor be kell jelölni az előírás, a jogi személy és a szállítási mód közötti kapcsolatot.

Az alábbi táblázat bemutatja a **Szállítási mód** gyorslapon rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Cég | Válassza ki azt a jogi személyt, amelyet társítani szeretne ehhez a rendelethez. |
| Szállítás módja | A kiválasztott jogi személy alapján válassza ki az előíráshoz társítani kívánt szállítási módot. |

### <a name="country-fasttab"></a>Ország gyorslap

Hivatkozás céljából listázhatja azokat az országokat vagy régiókat, amelyekre az előírás vonatkozik. A szállítási jelentések futtatásakor azonban csak a szállítási mód használható az előírás meghatározására. A raktári szállítmányok áttekintésekor nincs közvetlen kapcsolat a szállítási módhoz. A szállítmány egy szállítmányozóhoz és egy szállítmányozói szolgáltatáshoz lehet társítva. A szállítmányozói szolgáltatás definiálásakor egy szállítási móddal kell társítania. Ezt a kapcsolatot a szállítási jelentéseken – például a fuvarlevél – alapján kell használni a cikkek szállítási nyomtatási szövegének megtalálására.

Az alábbi táblázat bemutatja az **Ország** gyorslapon rendelkezésre álló mezőt.

| Mező | Leírás |
|---|---|
| Ország/régió | Jelölje ki az előíráshoz társítani kívánt országot/régiót. |

## <a name="material-codes"></a><a name="hazmat-codes"></a>Anyagkódok

Az anyagkódok olyan beállításokat határoznak meg, amelyek egy adott veszélyes összetevőhöz kötődnek, amely egy kiadott termékben jelen lehet. Minden anyagkód egy konkrét veszélyesanyag-előíráshoz tartozik, és definíciója meg kell feleljen annak az előírásnak. Amikor egy kibocsátott termékhez az **Anyagkód** mezővel egy anyagkódot alkalmaz, a program automatikusan a termékre alkalmazza az anyagkód összes veszélyesanyag-beállítását. Emiatt a kiadott termékek beállításának folyamata gyorsabb és kevesebb a hibalehetőség.

A veszélyes anyagok definícióinak kezeléséhez hajtsa végre az alábbi lépéseket.

1. Válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyagokra vonatkozó előírások** lehetőséget.
2. Válassza ki az előírást, amelyhez beállítja a veszélyes anyagok definícióját.
3. A Műveleti panel **Beállítások** lapján válassza a **Veszélyes anyagok** menüpontot.
4. Írja be az **Anyagkód** mezőbe a veszélyes anyag definícióját. Ez az érték akkor van kiválasztva, ha az anyagkódot egy kiadott termékre alkalmazza.

    Az **Előírás kódja** mező írásvédett, és a 2. lépésben kiválasztott előírást jeleníti meg.

5. A lap többi mezőjének használatával hozza létre és állítsa be a kiválasztott rendelethez tartozó veszélyes anyagokat. A rendelkezésre álló mezők a veszélyes anyagokat tartalmazó mezők egy részhalmaza, amelyek elérhetők egyedi kiadott termékekhez. További információ: [Termékekben, megrendelésekben, szállítmányokban és rakományokban lévő veszélyes anyagok](hazmat-items.md).

## <a name="hazardous-material-classification-groups"></a><a name="classification-groups"></a>Veszélyes anyagok osztályozási csoportjai

A veszélyes anyagok egyes osztályozási csoportjai olyan mezőértékek egy csoportját definiálják, amelyek egy sablont határoznak meg. Ezt a sablont később is használhatja, amikor egy kiadott cikkre vonatkozó veszélyes anyagok adatait állítja be.

Ha egy kiadott elemhez rendeli hozzá a veszélyes anyag osztályozási csoportjának kódját, akkor az adott osztályozási csoporthoz társított adatok a cikkek megfelelő mezőibe kerülnek. Ennek megfelelően a beállítási folyamatok egyszerűsítése érdekében gyakran együttesen használt mezőértékeket hozhat létre.

Ez a beállítási adat nem specifikus jogi személyekre. Ennek megfelelően a jogi személyek között közösen használt veszélyes anyagokkal kapcsolatos adatokat lehet létrehozni.

A veszélyes anyagok osztályozási csoportjainak beállításához Válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyagokra osztályozási csoportja** lehetőséget. A **Veszélyes anyagok osztályozási csoportja** lapon tetszőleges számú csoportot hozhat létre, és a következő alszakaszokban ismertetett táblázat alapján konfigurálhatja azokat.

| Mező | Leírás |
|---|---|
| Csoportkód | A csoport azonosítására szolgáló kód megadása. |
| Leírás | A csoport leírásának megadása. |
| Osztály kódja | Veszélyes anyag [osztálykódjának](#classes) társítása a csoporthoz. |
| Osztály kódja | Veszélyes anyag [divíziókódjának](#divisions) társítása a csoporthoz. |
| Csomagolási csoport kódja | [Csomagolási csoportkód](#packing-group) társítása a csoporthoz. |
| Szállítási kategória kódja | [Szállítási kategória kód](#transport-category) társítása a csoporthoz. |
| Szorzó | A kijelölt osztályra és a veszélyes anyagok felosztására vonatkozó veszélyes anyagok szorzója megadása a vonatkozó előírás alapján. Ez a szorzó a rakomány vagy szállítmány összes *veszélyesanyag-pontszámát* kiszámító képlet részeként használatos. A veszélyes anyagok pontszámaival és a szorzóval kapcsolatos további tudnivalókat lásd: [Anyagkezelés gyorslap](hazmat-items.md#material-management). |

## <a name="hazardous-material-classes"></a><a name="classes"></a>Veszélyesanyag-osztályok

A veszélyesanyagok-osztályt általában azon osztályok listájára kell leképezni, amelyek az előírásban szerepelnek, amelyet teljesít. Például a CFR 49 Amerikai Egyesült államokbeli rendelet a „3. osztályba” sorolja a gyúlékony és éghető folyadékokat. Be lehet állítani azokat az osztályokat, amelyek a besorolni kívánt anyagokhoz szükségesek.

Minden osztályt hozzá kell rendelni egy anyagbeállításhoz anyaglistában, amely a rendelethez kapcsolódik. Az előírásoknak megfelelően hozzárendel egy osztályt minden egyes kiadott cikkhez, amely leírja a veszélyes anyag természetét.

Ez a beállítási adat nem specifikus jogi személyekre. Ennek megfelelően a jogi személyek között közösen használt veszélyes anyagokkal kapcsolatos adatokat lehet létrehozni.

A veszélyesanyag-osztályok a következő használható együtt a részlegekkel, a csoportokkel és a kompatibilitási csoportokkal:

- Ha egy kiadott elemhez hozzárendel egy veszélyesanyag-osztályt, akkor egy [veszélyesanyag-dívíziót](#divisions) is társítania kell.
- A veszélyesanyag-osztályokat együtt használhatja a [veszélyes anyagok osztályozására szolgáló csoportokkal](#classification-groups) a cikkek beállításához használt kódsablonok létrehozásához.
- A [veszélyes anyagok kompatibilitási csoportjaival](#compatibility-groups) megadhatja, hogy mely veszélyesanyag-osztályokat és divíziókat lehet együtt szállítani.

A veszélyesanyag-osztályok beállításához Válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyesanyag-osztály** lehetőséget. A **Veszélyesanyag-osztályok** lapon tetszőleges számú osztályt hozhat létre, és a következő alszakaszokban ismertetett táblázat alapján konfigurálhatja azokat.

| Mező | Leírás |
|---|---|
| Osztály kódja | Az osztály azonosítására szolgáló kód megadása. Ezt a kódot definiálja a cikkhez. Ezt követően a rendszer a keresési listákban fogja használni, amikor veszélyesanyag-osztályt rendeli hozzá egy kiadott cikkhez. |
| Leírás | Adja meg az osztály leírását. |

## <a name="hazardous-material-divisions"></a><a name="divisions"></a>Veszélyesanyag-divíziók

A veszélyesanyag-divízió a veszélyesanyag-osztály egy részhalmaza. A veszélyes anyagokat tartalmazó összes termékhez társítani kell egy divíziót és egy osztályt.

Olyan osztályok esetében, amelyeknél nincs divízió, hozzon létre egy olyan divíziót, amelynek kódja *0*. Például az IATA-rendeletben a radioaktív anyagok 7-es osztályához nem tartoznak aldivíziók. Ebben az esetben hozzon létre egy *0* divíziót, amely a kiadott termékhez társítható, amikor osztályt rendel hozzá.

Ez a beállítási adat nem specifikus jogi személyekre. Ennek megfelelően a jogi személyek között közösen használt veszélyes anyagokkal kapcsolatos adatokat lehet létrehozni.

A veszélyesanyag-divíziók a következőm módon használható együtt az osztályokkal, a csoportokkal és a kompatibilitási csoportokkal:

- Ha egy kiadott elemhez hozzárendel egy veszélyesanyag-divíziót, akkor egy [veszélyesanyag-osztályt](#classes) is társítania kell.
- A veszélyesanyag-divíziókat együtt használhatja a [veszélyes anyagok osztályozására szolgáló csoportokkal](#classification-groups) a cikkek beállításához használt kódsablonok létrehozásához.
- A [veszélyes anyagok kompatibilitási csoportjaival](#compatibility-groups) megadhatja, hogy mely veszélyesanyag-osztályokat és divíziókat lehet együtt szállítani.

A veszélyesanyag-divíziók beállításához válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyesanyagok-divíziók** lehetőséget. A **Veszélyesanyag-divíziók** lapon tetszőleges számú divíziót hozhat létre, és a következő alszakaszokban ismertetett táblázat alapján konfigurálhatja azokat.

| Mező | Leírás |
|---|---|
| Osztály | Adja meg a divízió hivatkozási számához használandó kódot. |
| Leírás | Adja meg a divízió leírását. |
| Osztály | A divízióhoz tartozó osztály megkeresése és társítása. |

## <a name="hazardous-material-compatibility-groups"></a><a name="compatibility-groups"></a>Veszélyes anyagok kompatibilitási csoportjai

A veszélyes anyagok kompatibilitási csoportjai meghatározzák, hogy mely veszélyesanyag-osztályokat és divíziókat lehet együtt szállítani. Amikor a kezelők raktári rakományokat vagy szállítmányokat hoznak létre, akkor egy olyan kompatibilitási ellenőrzést futtathatnak, amely figyelmeztetést ad, ha a rakomány vagy a szállítmány olyan cikkeket tartalmaz, amelyek nem tartoznak ugyanahhoz a kompatibilitási csoporthoz.

Ez a beállítási adat nem specifikus jogi személyekre. Ennek megfelelően a jogi személyek között közösen használt veszélyes anyagokkal kapcsolatos adatokat lehet létrehozni.

A veszélyes anyagok kompatibilitási csoportjainak beállításához Válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyagok kompatibilitási csoportja** lehetőséget. A **Veszélyes anyagok kompatibilitási csoportja** lapon tetszőleges számú kompatibilitási csoportot hozhat létre, és a következő alszakaszokban ismertetettek alapján konfigurálhatja azokat.

### <a name="hazardous-material-compatibility-group-header"></a>Veszélyes anyagok kompatibilitási csoportjának fejléce

Minden kompatibilitási csoportnak van egy kódja és egy leírása. Az alábbi táblázat bemutatja a fejlécben rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Kompatibilitási csoport | A kompatibilitási csoport azonosítására szolgáló kód megadása |
| Leírás | Adja meg a kompatibilitási csoport leírását. |

### <a name="compatibility-group-details"></a>Kompatibilitási csoport részletei

Minden egyes kompatibilitási csoport meghatározza azon veszélyesanyag-osztályok és -divíziók listáját, amelyeket együtt lehet szállítani.

| Mező | Leírás |
|---|---|
| Osztály | Olyan veszélyes anyag osztály kiválasztása, amely kompatibilis a csoport minden más osztályával. |
| Osztály | Válasszon egy olyan veszélyesanyag-divíziót, amely a kiválasztott osztályhoz tartozik. |

## <a name="hazardous-material-specification-values"></a>Veszélyes anyagok specifikációs értékei

A Microsoft Dynamics 365 Supply Chain Management különböző típusú veszélyesanyag-specifikációkat tartalmaz. Mindegyik típushoz létre kell hoznia egy központosított értékhalmazt mindegyik fontos mező esetében. A felhasználók ezen az értékek közül választhatnak a veszélyes anyagok definíciói vagy a kiadott termékek definícióinak konfigurálásakor. Az Supply Chain Management olyan lapokat tartalmaz, amelyeken az értékek meghatározhatók. Mindegyik lap egy specifikációtípushoz van hozzárendelve. A rendelkezésre álló specifikációk leírását és a rendelkezésre álló értékek meghatározásával kapcsolatos tudnivalókat lásd a következő alszakaszokban.

A veszélyes anyagok specifikációjának egyik példája a _tárolási kód_, amely meghatározza, hogy egy adott anyag hogyan tárolható a szállítás során. Az ebben a szakaszban található információk alapján a tárolási kódok központi gyűjteményét fogja létrehozni. Ezt a gyűjteményt a rendszer legördülő listában jeleníti meg a felhasználók számára, amikor beállítják egy kiadott termék tárolási kódját.

Ezek a veszélyes anyagok előállítási értékei nem specifikusak az egyes jogi személyekre, ezért a jogi személyek között használható közös értékek használata lehetséges.

Az [anyagkódokat](#hazmat-codes) használva meghatározhatja az egyes specifikációk egy adott előírásra vonatkozó általános beállításait. Ezután a megfelelő kódot az egyes kiadott termékhez igény szerint alkalmazhatja. A veszélyes anyagok meghatározott kiadott termékre történő alkalmazásával és a termék egyéni beállításainak az itt ismertetett specifikációban történő beállításával kapcsolatos tudnivalókat lásd: [Veszélyes anyagok a termékekben, a rendelésekben, a szállítmányokban és a rakományokban](hazmat-items.md).

### <a name="hazardous-material-emergency-response"></a>Veszélyes anyagokkal kapcsolatos vészhelyzeti válasz

A *Veszélyes anyagokra vonatkozó vészhelyzeti válasz* specifikáció azt jelzi, hogy mit kell tenni, ha valamilyen probléma történt, miközben egy adott veszélyes anyagot tartalmazó termék szállítása folyamatban volt.

A specifikáció értékeinek beállításához válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyagokra vonatkozó vészhelyzeti válasz** lehetőséget. A **Veszélyes anyagokra vonatkozó vészhelyzeti válasz** oldalon tetszőleges számú értéket hozhat létre, és konfigurálhat mindegyikhez egy osztályozási kódot és egy rövid leírást.

### <a name="hazardous-material-identification"></a><a name="identification"></a>Veszélyes anyag azonosítója

A *veszélyes anyagok azonosítása* specifikáció a veszélyes anyagok osztályát vagy jellegét azonosítja. Az érték általában az Egyesült Nemzetek (ENSZ) szabványon alapuló kód. Mindegyik osztályt egy kód és egy leírás azonosítja, és a szállítási módokhoz korlátozás állítható be. A gyúlékony cikkek vagy anyagok azonosításához például egy veszélyes anyag osztályt kell létrehoznia, amely az *FL* kódot használja, és a leírás *Gyúlékony*. Azt is meghatározhatja, hogy az osztályt nem szabad légi úton szállítani.

A specifikáció értékeinek beállításához válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyagokra azonosítása** lehetőséget. A **Veszélyes anyagok azonosítása** lapon tetszőleges számú értéket hozhat létre, és a következő alszakaszokban ismertetett táblázat alapján konfigurálhatja azokat.

| Mező | Leírás |
|---|---|
| Azonosítás | Adja meg azt a kódot, amelyet hivatkozási számként kell használni a veszélyes anyag osztályának azonosítására. |
| Leírás | Adja meg az osztály leírását. |
| Letiltás légi szállításról | Ennek a jelölőnégyzetnek a bejelölésével jelezheti, hogy a veszélyes anyagoknak ezt az osztályát nem szabad légi úton szállítani. |
| Letiltás tengeri szállításról | Ennek a jelölőnégyzetnek a bejelölésével jelezheti, hogy a veszélyes anyagoknak ezt az osztályát nem szabad tengeren szállítani. |

### <a name="hazardous-material-label"></a><a name="label"></a>Veszélyes anyag címkéje

A *Veszélyesanyag-címke* specifikáció azonosítja azt a veszélyes árucikk-címkét, amelyet alkalmazni kell a kapcsolódó kiadott termékekhez. A címkék maguk leírják, hogyan kell kezelni a terméket. Például olyan termékkel rendelkezik, amely mérgező gázt tartalmaz. Ebben az esetben a mérgező gázt jelölő címke kódját kell beállítani. Az üzleti folyamatot úgy is létrehozhatja, hogy a termékek szállításakor ezt az értéket megkeresse.

A specifikáció értékeinek beállításához válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyesanyag-címke** lehetőséget. A **Veszélyesanyag-címke** oldalon tetszőleges számú címkét hozhat létre, és konfigurálhat mindegyikhez egy azonosító kódot és egy rövid leírást.

### <a name="hazardous-material-packing-descriptions"></a><a name="packing-description"></a>Veszélyes anyagok csomagolási leírásai

A *Veszélyes anyagok csomagolási leírásai* specifikáció határozza meg, hogyan kell egy veszélyes cikkeket csomagolni. Előfordulhat például, hogy egy bizonyos típusú acél dob vagy más speciális csomagolási típus szükséges.

A specifikáció értékeinek beállításához válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyagok csomagolási leírása** lehetőséget. A **Veszélyes anyagok csomagolási leírások** oldalon tetszőleges számú csomagolási leírást hozhat létre, és konfigurálhat mindegyikhez egy azonosító kódot és egy rövid leírást.

### <a name="hazardous-material-packing-group"></a><a name="packing-group"></a>Veszélyes anyagok csomagolási csoportja

A *Veszélyesanyag csomagolási csoportja* specifikáció azonosítja a veszélyes cikk csomagolási csoportját. A csomagolási csoport lehetővé teszi egy kód és a leírás meghatározását annak jelzésére, hogy hogyan kell a veszélyes anyagokat csomagolni a szállítás vagy szállítás során. A csomagolási csoport a **Cikkveszélyes anyagai** oldalon van hozzárendelve a cikkhez.

A specifikáció értékeinek beállításához válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyag csomagolási csoportja** lehetőséget. A **Veszélyesanyag csomagolási csoportja** oldalon tetszőleges számú csomagolási csoportot hozhat létre, és konfigurálhat mindegyikhez egy azonosító kódot és egy rövid leírást.

### <a name="hazardous-material-packing-instruction"></a><a name="packing-instruction"></a>Veszélyes anyagok csomagolási utasítása

A *Veszélyes anyag csomagolási utasítása* specifikáció azt a csomagolási utasítást azonosítja, amelyet követni kell, amikor egy adott veszélyes terméket légi szállításra készítenek össze.

A specifikáció értékeinek beállításához válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyag csomagolási utasítása** lehetőséget. A **Veszélyes anyag csomagolási utasítása** oldalon tetszőleges számú csomagolási utasításazonosítót hozhat létre, és konfigurálhat mindegyikhez egy azonosító kódot és egy rövid leírást.

### <a name="hazardous-material-stowage"></a><a name="stowage"></a>Veszélyes anyag rakodása

A *Veszélyes anyagok tárolása* specifikáció azt jelzi, hogy hogyan kell tárolni egy terméket egy hajón, amikor tengeri fuvarozással szállítják.

A specifikáció értékeinek beállításához válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyag tárolása** lehetőséget. A **Veszélyes anyag tárolása** oldalon tetszőleges számú tárolási azonosítót hozhat létre, és konfigurálhat mindegyikhez egy azonosító kódot és egy rövid leírást.

### <a name="hazardous-material-transport-category"></a><a name="transport-category"></a>Veszélyes anyagok szállítási kategóriája

A *Veszélyes anyag szállítási kategóriája* specifikáció általában a hasonló veszélyes termékek csoportosítására szolgál jelentéseken. Például a szállítási kategóriák a **Szállítmányösszesítés** jelentésében használatosak, amelyet a raktári szállítási rekordból lehet nyomtatni.

A specifikáció értékeinek beállításához válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyag szállítási kategóriája** lehetőséget. A **Veszélyes anyag szállítási kategóriája** oldalon tetszőleges számú szállítási kategóriát hozhat létre, és konfigurálhat mindegyikhez egy megjelenítendő nevet és egy rövid leírást.

### <a name="hazardous-material-technical-name"></a><a name="technical-name"></a>Veszélyes anyag műszaki neve

A *Veszélyes anyag műszaki neve* specifikációval létrehozható egy általánosan használt vagy belső vállalati név amely leírja az egyes anyagokat.

A specifikáció értékeinek beállításához válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyag műszaki neve** lehetőséget. A **Veszélyes anyag műszaki neve** oldalon tetszőleges számú műszaki nevet hozhat létre, és konfigurálhat mindegyikhez egy megjelenítendő nevet és egy rövid leírást.

### <a name="hazardous-material-tunnel"></a><a name="tunnel"></a>Veszélyes anyag alagútja

A *Veszélyes anyag alagút* specifikációja korlátozza, hogy milyen típusú alagutakon vihetők át a veszélyes anyagok a használandó alagutak típusának meghatározásával. Az alagútkategóriákat a veszélyes anyagok szállítására vonatkozó szabályok határozzák meg. Ez am specifikáció általában csak a közúti szállításra vonatkozik.

A specifikáció értékeinek beállításához válassza a **Termékinformáció-kezelés \> Beállítások \> Veszélyes anyagok szállítási dokumentációja \> Veszélyesanyag-alagút** lehetőséget. A **Veszélyesanyag-alagút** oldalon tetszőleges számú alagútazonosítót hozhat létre, és konfigurálhat mindegyikhez egy azonosító kódot és egy rövid leírást.
