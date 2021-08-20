---
title: Az elektronikus számlázás beállítása
description: Ez a témakör bemutatja, hogyan tudja beállítani az elektronikus számlázást a Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásokban.
author: gionoder
ms.date: 03/29/2021
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
ms.openlocfilehash: cf8d16415968b73300ff7ccc99d57303e5e3687f4a501e87b407f7a9bc66e820
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776501"
---
# <a name="set-up-electronic-invoicing"></a>Az elektronikus számlázás beállítása

[!include [banner](../includes/banner.md)]


Az elektronikus számlázás funkció beállítása az a folyamat, amely során létrehozzák a szükséges konfigurációt a Regulatory Configuration Services (RCS) környezeten keresztül, valamint közzéteszik ezen konfigurációt az Elektronikus számlázás bővítményének kiszolgálójára. A beállítással olyan konfigurálható szabályokat is létrehozhat, amelyek lehetővé teszik, hogy az elektronikus számlázás biztonságos protokollt használjon az interneten keresztül a webszolgáltatásokon keresztül történő adatkommunikációhoz és a harmadik fél entitásokkal történő adatcseréhez.

A konfigurálhatóság az Elektronikus jelentéskészítés (ER) formátumú konfigurációra támaszkodik, illetve a digitális fájlokon keresztül küldött és fogadott tartalmakat hozza létre. A kommunikáció vezénylésére is támaszkodik, illetve a harmadik fél webszolgáltatásaitól érkező válaszok küldéséhez és fogadásához nem szükséges kódot írnia.

## <a name="overview"></a>Áttekintés

„Az elektronikus számlázás funkció” annak az erőforrásnak az általános neve, amely az Elektronikus számlázási bővítmény kiszolgáló felhasználásához van konfigurálva és közzétéve. A funkcióbeállítás többek között az ER-konfigurációs formátumok használatát egyesíti úgy, hogy konfigurálható export- és importfájlokat hozzanak létre, valamint elősegítsék a műveletek és műveletfolyamatok használatát, illetve lehetővé teszi a szükséges konfigurálható szabályok létrehozását a kérelmek küldéséhez, a válaszok importálásához és a válasz tartalmának elemzéséhez.

A következő ábra bemutatja az elektronikus számlázás funkció fő elemeit.

![Elektronikus számlázás funkció áttekintése.](media/e-Invoicing-services-feature-setup-Overview-e-Invoicing-feature.png)

A számla- és műveletsor-formátumok eltérései miatt a szolgáltatások beállításai az ország vagy régió, illetve az üzleti követelményei alapján változhatnak.

## <a name="set-up-the-electronic-invoicing-feature"></a>Az elektronikus számlázási funkció beállítása

A beállítási folyamatot az RCS-környezetben kell végrehajtani. A következő lépések végrehajtásával hozzon létre egy új Elektronikus számlázás funkciót.

1. Jelentkezzen be az RCS-környezetébe.
2. A **Globalizációs funkciók** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
3. Az **Elektronikus számlázás funkciók** lapon válassza az **Importálás** lehetőséget az ER-adatmodell-konfiguráció Globális adattárból való importálásához.
4. A **Hozzáadás** lehetőség kiválasztásával létrehozhatja az Elektronikus számlázás funkciót. Létrehozhatja a funkciót az alapoktól, vagy származtathatja egy létező elektronikus számlázás funkcióból.

    ![Elektronikus számlázás funkció hozzáadása.](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature.png)

> [!NOTE]
> Új Elektronikus számlázás funkció létrehozásakor verziószámmal rendelkezik, és az alapértelmezett állapot a **Piszkozat** értékre van állítva .

### <a name="configurations"></a>Konfigurációk

A konfigurációk rendelkeznek az átalakításokhoz szükséges ER-formátumkonfigurációkkal, és a harmadik fél webszolgáltatásaival folytatott kommunikáció során kicserélendő fájlok létrehozásához szükséges beállításokkal. Az Elektronikus számlázás funkciónak a webszolgáltató által biztosított integrációs technikai előírás alapján tetszőleges számú ER-fájlformátum-konfigurációja lehet.

A következő lépések végrehajtásával adjon hozzá ER-formátumokat az új Elektronikus számlázás funkcióhoz.

1. Az **Elektronikus számlázás funkciók** oldalon, a **Konfigurációk** lapon válassza ki a **Hozzáadás** lehetőséget az ER-fájlformátum-konfiguráció Elektronikus számlázás funkcióhoz való hozzáadásához.

    ![Elektronikus számlázás funkció konfigurációinak hozzáadása.](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > Amikor az alapoktól hozza létre az Elektronikus számlázás funkciót, akkor manuálisan kell hozzáadnia az összes ER-fájlformátum-konfigurációt. Ha egy meglévő funkcióból származtat egy Elektronikus számlázás funkciót, akkor a rendszer automatikusan létrehozza az ER-fájlformátum-konfigurációkat, mivel ezek az eredeti Elektronikus számlázás funkcióból öröklődnek.

2. Ha meg szeretné nyitni a **Formátumtervező** lapot, akkor válassza a **Szerkesztés** lehetőséget, ahol szerkesztheti az ER-fájlformátum-konfigurációt.

    ![Elektronikus számlázás funkció konfigurációinak szerkesztése.](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > Miközben szerkeszti a formátumot, a konfigurációverzió állapota **Piszkozat** értékre van állítva.

3. A fájlformátum-konfiguráció módosításához használja a **Formátumtervező** lapot. További információ: [Elektronikus dokumentum-konfigurációk létrehozása](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration.md).

    ![Formátumtervező oldal.](media/e-Invoicing-services-feature-setup-ER-Format-designer.png)

### <a name="feature-setups"></a>Funkcióbeállítások

A funkcióbeállítások a kommunikációra és a biztonságra vonatkozó szabályokat egy harmadik fél webszolgáltatásával ágyazzák be. Az Elektronikus számlázás funkció az elérni kívánt üzleti szabály alapján tetszőleges számú funkcióbeállítással rendelkezhet.

A következő lépések végrehajtásával adjon hozzá funkcióbeállításokat az új Elektronikus számlázás funkcióhoz.

1. Az **Elektronikus számlázás funkciók** oldalon, a **Beállítások** lapon válassza ki a **Hozzáadás** lehetőséget a funkcióbeállítások Elektronikus számlázás funkcióhoz való hozzáadásához.

    ![Elektronikus számlázás funkció beállításainak hozzáadása.](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Setups.png)

    > [!NOTE]
    > Amikor az alapoktól hozza létre az Elektronikus számlázás funkciót, akkor manuálisan kell hozzáadnia az összes kívánt funkcióbeállítást. Ha egy meglévő funkcióból származtat egy Elektronikus számlázás funkciót, akkor a rendszer automatikusan létrehozza az összes funkcióbeállítást, mivel ezek az eredeti Elektronikus számlázás funkcióból öröklődnek.

2. A funkcióverzió beállításainak szerkesztéséhez válassza a **Szerkesztés** parancsot.

    ![Elektronikus számlázás funkció beállításainak szerkesztése.](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Setups.png)

3. A **Funkcióverzió beállítása** lap a műveletek, az alkalmazhatósági szabályok és a változók konfigurálására használható.

    ![Műveletek, alkalmazhatósági szabályok és változók.](media/e-Invoicing-services-feature-setup-View-Actions-Applicability-Rules-Variables.png)

### <a name="actions"></a>Műveletek

A műveletek a sorrendben futtatott műveletek előre meghatározott listája. Ez a lista az Elektronikus számlázás funkció teljes végrehajtásához szükséges lépések tételes bemutatását tartalmazza. A műveletek mindkét irányba be tudják ágyazni a kommunikációt ugyanabba az Elektronikus számlázás funkcióba: egy úticél-kérelem küldése, valamint válasz fogadása és tartalmának elemzése.

Minden művelet tartalmaz egy előre meghatározott paramétert, amely a művelet céljának megvalósításához szükséges. A további paramétereket tetszés szerint lehet megadni.

#### <a name="actions-fasttab"></a>Műveletek Gyorslap

A **Funkcióverziók beállítása** oldalon, a **Műveletek** lapj **Műveletek** Gyorslapon hajtsa végre az egyik vagy mindkét lépést a műveletek kezeléséhez:

- Válassza ki az **Új** vagy **Törlés** lehetőséget az új műveletek hozzáadásához vagy a meglévő műveletek törléséhez.
- A **Fel** vagy **Le** lehetőséggel a kijelölt műveleteket a rácsban felfelé vagy lefelé mozgathatja, így megváltoztatva, hogy milyen sorrendben fussanak. A műveletek a rácsban megjelenő – fentről lefelé haladó – sorrendben futnak.

![Műveletek kezelése.](media/e-Invoicing-services-feature-setup-Manage-Actions.png)

Az alábbi táblázat bemutatja a **Műveletek** gyorslapon rendelkezésre álló mezőket.

| Mező        | Leírás |
|--------------|-------------|
| Művelet       | Nyolc előre definiált művelet van:<ul><li><strong>Dokumentum aláírása</strong></li><li><strong>FileStoreActionName</strong></li><li><strong>Dokumentum átalakítása</strong></li><li><strong>Folyamatválasz</strong></li><li><strong>REST-webszolgáltatás hívása</strong></li><li><strong>Mexikói PAC-szolgáltatás hívása</strong></li><li><strong>Brazil SEFAZ-szolgáltatás hívása</strong></li><li><strong>Olasz SDI-szolgáltatás hívása</strong></li></ul> |
| Művelet neve  | A művelet neve és a végrehajtás sorrendje. |
| Leírás  | A művelet leírása. |
| Újrapróbálkozás engedélyezése | A bejelölt négyzet azt jelzi, hogy a művelet újrapróbálható, ha az előző kísérlet sikertelen. |
| Újrapróbálkozási művelet | A művelet, amelytől az újrapróbálkozáskor elindult. Az újrapróbálkozás ekkor véget ér az aktuális műveleten (inkluzív újrapróbálkozás). Azon műveletek, amelyek rendelkeznek velük, a **Minimális visszavonási** és a **Maximális visszavonási** paraméterek határozzák meg az újrapróbálkozások minimális és maximális számát. |

#### <a name="parameters-fasttab"></a>Paraméterek gyorslap

A **Paraméterek** gyorslap felsorolja a **Műveletek** gyorslapon kiválasztott művelet paramétereit.

![Paraméterek gyorslap.](media/e-Invoicing-services-feature-setup-View-Actions-Parameters.png)

Az alábbi táblázat bemutatja a **Paraméterek** gyorslapon rendelkezésre álló mezőket.

| Mező       | Leírás |
|-------------|-------------|
| Név        | A paraméterek előre meghatározott listája. További információért tekintse át a [Műveletenkénti paraméterek listája](#list-of-parameters-by-action) szakaszt. |
| Leírás | A paraméter leírása. |
| Érték       | A paraméter értéke. |

#### <a name="list-of-parameters-by-action"></a>Műveletenkénti paraméterek listája

A választható paraméterek a **Műveletek** gyorslapon kiválasztott művelettől függően változnak.

###### <a name="action-sign-document"></a>Művelet: dokumentum aláírása

| Paraméter                             | Leírás |
|---------------------------------------|-------------|
| Bemeneti fájl                            | A bemeneti XML-dokumentumfájl, amelyet elektronikus aláírással kell aláírni. |
| Tanúsítvány neve                      | A tanúsítvány tárbeli neve. |
| Aláírás típusa                        | A használandó aláírás típusa. |
| Aláírási módszer neve                 | Az elektronikus aláírás létrehozásához használt aláírási módszer neve. |
| Kivonatolási módszer neve                    | A kivonatolási sztring digitális aláírásban történő létrehozásához használt kivonatolási módszer. |
| A kanonizációs módszer neve          | Az aláírási hasító kiszámítására használt kanonizációs módszer típusa. |
| Hivatkozási attribútum neve              | Az attribútum neve, amely azt jelzi, hogy hol kell beszúrni a hivatkozási azonosítót az aláírási elembe. |
| Aláírandó elem neve               | A dokumentumban lévő XML-elem neve, amelyet elektronikus aláírással kell aláírni. Ha nincs megadva elem, a dokumentum gyökere lesz aláírva. |
| Az aláírás beszúrására szolgáló elem neve   | Annak az XML-elemnek a neve, amelybe a létrejövő digitális aláírást be kell szúrni. Ha nincs megadva elem, az aláírást a dokumentum gyökerébe szúrják be. |
| XSLT-fájlt kivonatolási átalakítással       | A kivonatolási átalakítási szabályokat tartalmazó XSLT-fájl, amely az elektronikus aláíráshoz létrehozza a kivonatolási sztringet. |
| A kivonatolási sztring beszúrásának elérési útja          | Elérési út a következőben: **\<elementName\> .\<Attribute.Path\>** Annak a helynek a formátuma, ahova a létrejövő kivonatolási sztringet be kell szúrni. |
| A tanúsítványszám helye           | Annak az elemnek és attribútumnak a neve, ahová a tanúsítványszámot kell helyezni. |
| A tanúsítvány adatainak helye          | Annak az elemnek és attribútumnak a neve, ahová a tanúsítványadatokat (base64) kell beszúrni. |
| A tanúsítvány száma ASCII-formátumú | Az érték, amely meghatározza, hogy a tanúsítvány száma ASCII-formátumban legyen-e kódolva. |

###### <a name="action-filestoreactionname"></a>Művelet: FileStoreActionName

| Paraméter  | Leírás |
|------------|-------------|
| Bemeneti fájl | A tárolandó bemeneti fájl. |

###### <a name="action-transform-document"></a>Művelet: dokumentum átalakítása

| Paraméter                       | Leírás |
|---------------------------------|-------------|
| Bemeneti fájl                      | A művelethez futtatandó adatokat tartalmazó forrásfájl. |
| Irány                       | Érték, amely azt jelzi, hogy az importálási vagy az exportálási formátumot kell-e használni. |
| Konfigurációazonosító                | A futtatandó formátum. |
| Konfiguráció verziója           | Ha nincs megadva konfigurációverzió, akkor a legfrissebb verzió lesz használva. |
| Konfiguráció integrációs pontja | A jelentés futtatési idejének adatait tartalmazó forrásfájl. |

###### <a name="action-process-response"></a>Művelet: válasz feldolgozása

| Paraméter                    | Leírás |
|------------------------------|-------------|
| Bemeneti fájl                   | Az elemzésre adott válasz. |
| Jelentéskészítési konfigurációlista | A válaszok elemzésére használt konfigurációk listája. |

###### <a name="action-call-rest-web-service"></a>Művelet: REST-webszolgáltatás hívása

| Paraméter                   | Leírás |
|-----------------------------|-------------|
| Webszolgáltatás URL-címe             | A kérelmek küldéséhez használandó URL-cím. |
| Webes kérelem időtúllépése         | Maximális idő a webszolgáltatás válaszára (ezredmásodpercben). |
| Művelettípus kérelmezése      | A HTTP-kérési művelet típusa (például **MEGSZERZÉS**, **KÖZZÉTÉTEL** vagy **TÖRLÉS**). |
| Tanúsítvány nevei           | A tanúsítvány nevei. |
| Választörzs kódolása      | A HTTP-választörzs várt kódolása ahhoz, hogy megfelelően lehessen dekódolni. |
| HTTP-kérelem tartalomtípusa   | A HTTP-kérelem tartalomtípus fejlécének bemenete. |
| HTTP-kérelem tartalomtörzse   | A HTTP-kérelem törzse. (A törzs lehet üres.) |
| HTTP-paraméter lekérdezési értékei | Paraméter-lekérdezési értékek, amelyeket az URL-cím változó paraméterekkel történő kitöltéséhez használnak. |
| Kérelem útvonala               | A HTTP-kérelem útvonalának elérési útja. A változó paraméterek lehetnek **\{paramName\}** jelölve. Egy példa: **"api/{id}/submit"**. |
| Útvonal-paraméter lista        | A kulcsérték jelölésben lévő útvonal-paraméterek, amelyeket a változók útvonalba történő beszúrására használnak. |
| Egyéni HTTP-fejlécek         | A kérelembe behelyezendő egyéni HTTP-fejlécek. |
| HTTP-kérelem sütijei        | A kulcsérték jelölésben lévő sütik listája, amelyet a HTTP-sütik fejléckérelmébe kell helyezni. |
| Biztonsági protokoll           | A kiszolgálóval folytatott kommunikáció HTTP-kérelmeihez használt biztonsági protokoll. (Alapértelmezés szerint a Transport Layer Security \[TLS\] 1.2-es verziója használatos.) |

###### <a name="action-call-mexican-pac-service"></a>Művelet: Mexikói PAC-szolgáltatás hívása

| Paraméter                | Leírás |
|--------------------------|-------------|
| Bemeneti fájl               | Az XML-adatokat tartalmazó fájl, amelyet a webszolgáltatáshoz, mint bemeneti paraméter módszereként fognak küldeni. |
| URL cím              | A webszolgáltatás címe (végpont). |
| Webes módszer (művelet) neve | A futtatni kívánt webes módszer (művelet) neve. |
| Diplomák             | A webszolgáltatás által a vevőhitelesítéshez szükséges tanúsítványlánc. A vevőtanúsítványnak a lánc utolsó tanúsítványának kell lennie. A gyökér- és a közbenső tanúsítványoknak kell az elsőknek lenniük. |
| Webes kérelem időtúllépése      | Maximális idő a webszolgáltatás válaszára (ezredmásodpercben). |
| Újrapróbálkozási időköz           | A webszolgáltatástól érkező válasz hívási és fogadási kísérletei közötti időköz. Ha nincs megadva időköz, akkor ha az első hívás eredménytelen, akkor nem lesznek további újrapróbálkozások. |
| Újrapróbálkozások száma              | A webszolgáltatás válaszának hívási és fogadási újrapróbálkozásainak maximális száma. |
| Újrapróbálkozás eddig:               | Az újrapróbálkozási hívásokat maximum ennyi ideig (ezredmásodpercben) lehet folytatni. |
| Minimális visszavonás         | Az újrapróbálkozási időközök exponenciális számításához szükséges minimális visszavonási arány. |
| Maximális visszavonás         | Az újrapróbálkozási időközök exponenciális számításához szükséges maximális visszavonási arány. |
| Biztonsági protokoll        | A kiszolgálóval folytatott kommunikáció HTTP-kérelmeihez használt biztonsági protokoll. (Alapértelmezés szerint a TLS 1.2-es verziója használatos.) |

###### <a name="action-call-brazilian-sefaz-service"></a>Művelet: Brazil SEFAZ-szolgáltatás hívása

| Paraméter                | Leírás |
|--------------------------|-------------|
| Bemeneti fájl               | Az XML-adatokat tartalmazó fájl, amelyet a webszolgáltatáshoz, mint bemeneti paraméter módszereként fognak küldeni. |
| URL cím              | A webszolgáltatás címe (végpont). |
| Webes módszer (művelet) neve | A futtatni kívánt webes módszer (művelet) neve. |
| Diplomák             | A webszolgáltatás által a vevőhitelesítéshez szükséges tanúsítványlánc. A vevőtanúsítványnak a lánc utolsó tanúsítványának kell lennie. A gyökér- és a közbenső tanúsítványoknak kell az elsőknek lenniük. |
| Webes kérelem időtúllépése      | Maximális idő a webszolgáltatás válaszára (ezredmásodpercben). |
| Újrapróbálkozási időköz           | A webszolgáltatástól érkező válasz hívási és fogadási kísérletei közötti időköz. Ha nincs megadva időköz, akkor ha az első hívás eredménytelen, akkor nem lesznek további újrapróbálkozások. |
| Újrapróbálkozások száma              | A webszolgáltatás válaszának hívási és fogadási újrapróbálkozásainak maximális száma. |
| Újrapróbálkozás eddig:               | Az újrapróbálkozási hívásokat maximum ennyi ideig (ezredmásodpercben) lehet folytatni. |
| Minimális visszavonás         | Az újrapróbálkozási időközök exponenciális számításához szükséges minimális visszavonási arány. |
| Maximális visszavonás         | Az újrapróbálkozási időközök exponenciális számításához szükséges maximális visszavonási arány. |
| Biztonsági protokoll        | A kiszolgálóval folytatott kommunikáció HTTP-kérelmeihez használt biztonsági protokoll. (Alapértelmezés szerint a TLS 1.2-es verziója használatos.) |

###### <a name="action-call-italian-sdi-service"></a>Művelet: Olasz SDI-szolgáltatás hívása

| Paraméter                | Leírás |
|--------------------------|-------------|
| Bemeneti fájl               | Az XML-adatokat tartalmazó fájl, amelyet a webszolgáltatáshoz, mint bemeneti paraméter módszereként fognak küldeni. |
| URL cím              | A webszolgáltatás címe (végpont). |
| Webes módszer (művelet) neve | A futtatni kívánt webes módszer (művelet) neve. |
| Diplomák             | A webszolgáltatás által a vevőhitelesítéshez szükséges tanúsítványlánc. A vevőtanúsítványnak a lánc utolsó tanúsítványának kell lennie. A gyökér- és a közbenső tanúsítványoknak kell az elsőknek lenniük. |
| Webes kérelem időtúllépése      | Maximális idő a webszolgáltatás válaszára (ezredmásodpercben). |
| Újrapróbálkozási időköz           | A webszolgáltatástól érkező válasz hívási és fogadási kísérletei közötti időköz. Ha nincs megadva időköz, akkor ha az első hívás eredménytelen, akkor nem lesznek további újrapróbálkozások. |
| Újrapróbálkozások száma              | A webszolgáltatás válaszának hívási és fogadási újrapróbálkozásainak maximális száma. |
| Újrapróbálkozás eddig:               | Az újrapróbálkozási hívásokat maximum ennyi ideig (ezredmásodpercben) lehet folytatni. |
| Minimális visszavonás         | Az újrapróbálkozási időközök exponenciális számításához szükséges minimális visszavonási arány. |
| Maximális visszavonás         | Az újrapróbálkozási időközök exponenciális számításához szükséges maximális visszavonási arány. |
| Biztonsági protokoll        | A kiszolgálóval folytatott kommunikáció HTTP-kérelmeihez használt biztonsági protokoll. (Alapértelmezés szerint a TLS 1.2-es verziója használatos.) |

### <a name="applicability-rules"></a>Alkalmazhatósági szabályok

Az alkalmazhatósági szabályokkal olyan logikai szabályokat is létrehozhat, amelyek meghatározzák a funkció beállításainak használati környezetét. Így a feldolgozásra elküldött üzleti dokumentum által megadott környezet és az alkalmazhatósági szabály feltételeinek megfelelő egyeztetés határozza meg, hogy mely elektronikus számlázási funkciókat kell használni a beadvány feldolgozásához.

#### <a name="set-up-applicability-rules"></a>Alkalmazhatósági szabályok beállítása

1. A **Funkcióverzió beállításai** oldal **Alkalmazhatósági szabályok** lapján válassza az **Új** lehetőséget az alkalmazhatósági szabály hozzáadásához.

    ![Alkalmazhatósági szabályok kezelése.](media/e-Invoicing-services-feature-setup-Manage-Actions-Applicability-rules.png)

2. A rácsban válassza ki a csoportosítani kívánt feltételeket.
3. **Csoportfeltétel** kiválasztása.

    ![Csoportosítási feltételek.](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-clause.png)

    Ha a feltételek csoportosítva vannak, akkor új oszlop lesz hozzáadva a rácshoz. Ez az oszlop a csoportosított feltételek logikai operátorát határozza meg.

    ![A csoportosított feltételek logikai operátora.](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-criterias.png)

A feltételek csoportosításának szétválasztásához válassza ki a csoportosítot feltételeket, majd válassza a **Szétválasztás** elemet.

![Feltételek szétválasztása.](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-UnGroup-criterias.png)

> [!NOTE]
> Feltételek szétválasztásakor mindig a legbelső csoportosítási szinttől induljon el.

Az alábbi táblázat bemutatja az **Alkalmazhatósági szabályok** lapon rendelkezésre álló mezőket.

| Mező         | Leírás |
|---------------|-------------|
| És/vagy        | A logikai operátor. |
| Mező         | A szabály összeállítására használt mező. |
| Operátor típusa | Az operátor típusa:<ul><li>Egyenlő</li><li>Nem egyenlő</li><li>Nagyobb, mint/Kisebb, mint</li><li>Nagyobb, mint vagy egyenlő/Kisebb, mint vagy egyenlő</li><li>Tartalmazza</li><li>Kezdete:</li></ul> |
| Érték         | A szabály feltétele. |

### <a name="variables"></a>Változók

Létrehozhat változókat, majd ezeket egy adott művelet paraméterének bemeneti értékeként használhatja. Arra is használhatja őket, hogy az Elektronikus számlázás szolgáltatásai és a vevő között olyan információkat osszon meg, amelyek a beadványok folyamataként, egy konkrét művelet végrehajtásának eredményei.

#### <a name="set-up-variables"></a>Változók beállítása

- A **Funkcióverzió beállítása** oldal **Változók** lapján válassza az **Új** vagy a **Törlés** lehetőséget a változók kezeléséhez.

    ![Változók kezelése.](media/e-Invoicing-services-feature-setup-Manage-Variables.png)

Az alábbi táblázat bemutatja a **Változók** lapon rendelkezésre álló mezőket.

| Mező       | Leírás |
|-------------|-------------|
| Név        | A változó neve. |
| Leírás | A változó rövid leírása. |
| Típus        | A változó típusa:<ul><li><strong>Állandó</strong> – A változó tartalma rögzített.</li><li><strong>Vevőtől</strong> – A változó tartalmát a Microsoft Dynamics 365 vevőtől szerezték meg a küldési folyamat végrehajtása során.</li><li><strong>Vevőhöz</strong> – A változó tartalmát elérhetővé tették a Microsoft Dynamics 365 ügyfél számára a küldési folyamat végrehajtása során.</li></ul> |
| Adattípus   | A változó adattípusa:<ul><li>Logikai</li><li>Dátum</li><li>Szám</li><li>UUID</li><li>Karakterlánc</li><li>Fájl</li></ul> |
| Érték       | A változó értéke vagy azon művelet neve, amely a változó értékét határozza meg. |

### <a name="validate-the-feature-setup"></a>A funkció beállításának ellenőrzése

- A **Funkcióverzió beállítása** oldalon található Művelet ablaktáblán válassza az **Ellenőrzés** elemet a funkcióverzió beállításának jóváhagyásához.

   ![Az Ellenőrzés gomb kiválasztása.](media/e-Invoicing-services-feature-setup-Select-Validate-Button.png)

Az ellenőrzéssel a teljes konfiguráció konzisztenciáját vizsgálják. Ha például egy művelethez egy konkrét paraméter kötelező, de az értéke üres marad, akkor az ellenőrzés észleli ezt az inkonzisztenciát, és figyelmezteti Önt.

## <a name="environments"></a>Környezetek

Az Elektronikus számlázás környezethez társítani, és engedélyezni is kell az Elektronikus számlázás funkciót. Az Elektronikus számlázás környezeteket előzetesen létre kell hozni, és közzé kell tenni a szervezet RCS-fiókjának Globalizációs funkciók konfigurációján keresztül.

Az Elektronikus számlázásbővítmény környezet Elektronikus számlázás funkcióhoz való engedélyezéséhez kövesse az alábbi lépéseket.

1. Az **Elektronikus számlázás funkciók** oldalon, a **Környezetek** lapon válassza ki az **Engedélyezés** lehetőséget egy Elektronikus számlázási környezet hozzáadásához.
2. A **Hatálybalépés dátuma** mezőbe írja be azt a dátumot, amikortól az új környezet hatályossá válik.

![Az Elektronikus számlázás környezet engedélyezése.](media/e-Invoicing-services-feature-setup-Select-Enable-e-Invoicing-feature-Environment.png)

## <a name="organizations"></a>Szervezetek

Az Elektronikus számlázás funkció több szervezet között is megosztható.

- Az **Elektronikus számlázás funkciók** oldal **Szervezetek** lapján válassza ki a **Megosztás vele:** lehetőséget ahhoz, hogy hozzáadhassa azt a szervezetet, amellyel meg szeretné osztani az Elektronikus számlázás funkciót.

Ha nem szeretné többé megosztani a szervezettel az elektronikus számlázás funkciót, akkor válassza ki a **Megosztás visszavonása** lehetőséget.

## <a name="versions"></a>Verziók

A verziók a saját állapotuk kezelésével vezérlik az Elektronikus számlázás funkció életciklusát. Létrehozhatja egy létező Elektronikus számlázás funkció új verzióját, vagy ha az Elektronikus számlázás funkció minden konfigurációja be van töltve, akkor a funkció állapotát **Befejezett**, majd **Közzététel** értékre állíthatja.

### <a name="create-a-new-version-of-an-existing-electronic-invoicing-feature"></a>Létező Elektronikus számlázás funkció új verziójának létrehozása

1. Az **Elektronikus számlázás funkciók** oldalon, a bal oldali rácsban válassza ki az Elektronikus számlázás funkciót.
2. A **Verziók** lapon válassza az **Új** lehetőséget, ha új verziót szeretne hozzáadni az Elektronikus számlázás funkcióhoz.

### <a name="change-the-status-of-the-electronic-invoicing-feature"></a>Az Elektronikus számlázás funkció állapotának módosítása

A következő lépések végrehajtásával kezelheti az új Elektronikus számlázás funkció életciklusát.

1. Az **Elektronikus számlázás funkciók** oldalon, a bal oldali rácsban válassza ki az Elektronikus számlázás funkciót.
2. A **Verziók** lapon válassza ki az **Állapot módosítása** lehetőséget, majd a **Piszkozat** értékről állítsa **Befejezett** értékre az állapotot.
3. A program megkéri, hogy erősítse meg, hogy az Elektronikus számlázás funkciót és annak összes összetevőjét szeretné befejezni. A művelet megerősítéséhez válassza az **Igen** lehetőséget, a visszavonásához pedig a **Nem** lehetőséget.

    > [!NOTE]
    > Ha az **Igen** lehetőséget választja, akkor a konfigurációverziók állapota – amely az Elektronikus számlázás-funkció összetevője – automatikusan átvált a **Piszkozat** értékről **Befejezett** értékre.

4. Válassza ki az **Állapot módosítása** lehetőséget, majd a **Befejezett** értékről állítsa **Közzététel** értékre az állapotot.
5. A program megkéri, hogy erősítse meg, hogy az Elektronikus számlázás funkciót és annak összes összetevőjét szeretné közzétenni a Globális adattárban. A művelet megerősítéséhez válassza az **Igen** lehetőséget, a visszavonásához pedig a **Nem** lehetőséget.

    > [!NOTE]
    > Ha az **Igen** lehetőséget választja, akkor a konfigurációverziók állapota automatikusan átvált **Befejezett** értékről **Megosztott** értékre.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]