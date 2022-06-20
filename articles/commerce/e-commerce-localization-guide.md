---
title: Dynamics 365 Commerce e-commerce honosítási útmutató
description: Ez a témakör azt ismerteti, hogyan Microsoft Dynamics 365 Commerce lehet további nyelvekre honosítani egy e-commerce webhelyet, és konfigurálni azt, hogy több csatornát támogatjon.
author: bicyclingfool
ms.date: 04/29/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 955a85340f6d35f1e203d74920d07b5dc6ff8654
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873384"
---
# <a name="dynamics-365-commerce-e-commerce-localization-guide"></a>Dynamics 365 Commerce e-commerce honosítási útmutató

[!include [banner](includes/banner.md)]

Ez a témakör ismerteti Microsoft Dynamics 365 Commerce, hogyan lehet további nyelvekre honosítani egy e-commerce webhelyet, és konfigurálni azt, hogy több csatornát támogatjon, valamint leírja a folyamattal kapcsolatos fogalmakat és fogalmakat.

A meglévő e-commerce Dynamics 365 Commerce képességek lehetővé teszik az olyan online tapasztalatokat, amelyek meghatározott országokra és nyelvekre szabottak, ugyanakkor lehetővé teszik a sablonok, lapok, tartalom és média maximális újrahasználatát. Létre lehet hozni egy alapvető telephelyet is, majd az idő után további országok és nyelvek támogatásának hozzáadásával új piacokra lehet kibontni.

## <a name="definitions"></a>Definíciók

**Területi beállítás, területi beállítás azonosítója**: A területi beállítás (más néven területi beállítás azonosítója) az országhoz vagy területhez társított nyelvet határozza meg. Az "fr-ca" területi azonosító például a kanadai francia nyelvhez van társítva.

**Alapnyelv**: az a nyelv, amikor a webhely tartalmát honosításra exportálja.

**Csatorna, online áruház**: a csatorna (más néven online áruház) meghatározza egy online e-commerce üzlet fizetési módjait, árcsoportját, termékhierarchiáit, szortimentét és termékeit.

## <a name="concepts"></a>Koncepció

### <a name="url-driven-experience"></a>URL-vezérelt tapasztalat

Dynamics 365 Commerce Az e-commerce webhelyek egyedi, piacosított és honosított tapasztalatokat kínálnak a vevők számára a csatornákon és a területi azonosítókon keresztül. A csatornák a piac egyedi termékeit, kategóriáit, pénznemét és fizetési módjait határozzák meg, a területi azonosítók pedig a vevők által látható tartalom nyelvét határozzák meg. Az e-commerce webhely URL-címekkel megkülönbözteti a piaci és a honosított tapasztalatokat. Ezeknek az egyedi csatorna- és területi tapasztalatoknak a webhely URL-címeit a **\>** Dynamics 365 Commerce Webhely beállításai – Csatornák lapon határozzák meg a Webhelyszerkesztőben.

A webhelyszerkesztőben az URL-cím egy tartomány és egy elérési út kombinációja, amely meghatározza a csatorna és a területi beállítás egyedi kombinációjának belépési pontját. A következő példában egy kitalált online áruház, a Gyár Zrt. meghatározza a csatorna és a területi beállítások négy egyedi kombinációját, és minden egyes kombinációt egy egyedi URL-címhez leképez, amely a vevőknek való tartalmat szolgál.

| Tartomány                     |  Elérési út      | Csatorna       |   Területi beállítás     |
|------------------------|--------|--------------------------------|--------|
| `https://fabrikam.com` | /      | Gyár bővített online áruháza | hu  |
| `https://fabrikam.com` | /es    | Gyár bővített online áruháza | es     |
| `https://fabrikam.ca`  | /      | Contoso online áruház    | fr-ca  |
| `https://fabrikam.ca`  | /en-ca | Contoso online áruház    | en-ca  |

#### <a name="domain"></a>Tartomány

A tartományokat az e-commerce Microsoft Dynamics webhelynek a Lifecycle Services (LCS) szolgáltatásban való beállításakor kell létrehozni. Az e-commerce környezet létesítését követően szolgáltatáskérés megnyitásával további tartományokat adhat hozzá. Az e-commerce webhely tartományának beállítását a Következő helyen található [további tájékoztatás: Tartomány.Dynamics 365 Commerce](domains-commerce.md)

#### <a name="path"></a>Elérési út

- Az elérési út egy olyan számsorozat, amely a tartománysal együttesen egy csatorna és egy területi érték egyedi kombinációjához van hozzárendelve. Az előző példában az elérési útként használt karakterlánc megegyezik azzal a területi azonosítóval, amelybe az elérési út van hozzárendelve. Használhatja azonban más megközelítést.
- Egy csatorna és egy területi érték kombinációja hozzárendelható egy tartományhoz és egy üres elérési úthoz ("/"). Az előző példában a `https://fabrikam.ca/` meglátogatott vevők a kanadai francia piac termékeit és szortimenteket kapják.
- A Commerce Site Builder megakadályozza egy tartomány és egy elérési út ismétlődő kombinációinak létrehozását. A csatornák és a területi értékek ismétlődő kombinációit azonban leképezheti a tartományok és útvonalak különböző kombinációira.

#### <a name="channel"></a>Csatorna

- A csatornák (más néven online áruházak) meghatározzák egy online e-kereskedelmi üzlet fizetési módjait, árcsoportját, termékhierarchiáit, szortimentét és termékeit.
- A csatornák meghatározása, konfigurálása és közzététele a központon Dynamics 365 Commerce keresztül történt.
- A webhelyszerkesztő észlelheti azokat az online áruházakat, amelyek a Commerce Headquarters alkalmazásban konfigurálva vannak, és a webhelyekhez hozzárendelhetőek.

A csatornákról a Csatornák áttekintése nyújt további [tájékoztatást](channels-overview.md). Az online csatornák beállításának [további tudnivalókat lásd: Online csatorna beállítása](channel-setup-online.md).

#### <a name="locale"></a>Területi beállítás

- A területi érték az XML honosítási fájlformátum (XLIFF) honosításra való kiszolgálásakor használt tényleges azonosító. A területi adatok a Commerce Headquarters minden csatornáján meg vannak határozva és közzé vannak adva. A webhelyszerkesztőben a nyelvek és csatornák konfigurálásának lépésekkel kapcsolatos tudnivalókat lásd a következő szakaszban.
- Ugyanaz a területi megegyezik a csatornáknál is. Így több piacon is kínálható közös nyelv.

## <a name="configure-languages-and-channels-for-your-e-commerce-site"></a>Az e-commerce webhely nyelvének és csatornáinak konfigurálása

A beállításon kívül minden Dynamics 365 Commerce e-commerce webhely úgy van beállítva, hogy egy online csatornát és egy nyelvet használjon, függetlenül attól, hogy a Gyár bemutatówebhelyével kezd, vagy teljesen új webhelyet hoz létre.

Ebben a konfigurációban a vevők és partnerek általában minden eszközt kialakítnak, amely ország- és nyelv szerint használható. Ezek közé tartoznak a sablonok, lapok, részletek, tartalom és adathordozók. A webhely minden tartalma a webhelyhez elsőként kiválasztott nyelven van fejlesztés alatt, vagy ha a Gyár bemutatówebhelyét használja, a webhely tartalma angol nyelven fog kifejlni.

![Nincs meg az Dynamics 365 Commerce e-commerce webhely a mezőben](media/loc-guide-1.png)

> [!NOTE]
> A Gyár bemutatówebhelyét egy további nyelvre is be lehet állítani, hogy a tartalom fejlesztése ezen a nyelven legyen leállítva. Ha további tájékoztatást szeretne arról, hogyan adhat hozzá új nyelvet egy webhelyhez és csatornához, [akkor](#configure-an-additional-language-for-your-site) tekintse meg a webhely szakaszának további nyelvének konfigurálása című fejezetét.

Az e-commerce webhelyekhez készült tartalomkezelő rendszer (CMS) Dynamics 365 Commerce és oldalmodell azonban úgy van kialakítva, hogy lehetővé tegye az új piacok és területek bővítését. Ebből következően egyetlen e-commerce webhelyen kezelhetők egy több piacokra és nyelvekre is átfogják egy online áruház eszközeit.

![Dynamics 365 Commerce Több piacra és nyelvre is átfogja az e-commerce webhelyet.](media/loc-guide-2.png)

### <a name="configure-an-additional-language-for-your-site"></a>További nyelv konfigurálása a webhely számára

Az e-commerce webhelyek új nyelvének konfigurálása három lépésből áll.

#### <a name="step-1-add-the-language-to-your-channel-online-store-in-commerce-headquarters"></a>1. lépés: A nyelv hozzáadása a commerce headquarters csatornához (online áruházhoz)

1. A Commerce Headquarters bővítményben menjen arra a csatornára, amelybe az új nyelvet hozzá szeretné adni. A Commerce Headquarters **szolgáltatásban beállított csatornák listájának megkeresése a Retail and Commerce \> Channels \> Online áruházakban található**.
1. A webhelyhez hozzárendelt **online áruház megnyitása a kiskereskedelmi csatorna azonosítójának értékével**. A webhelyhez hozzárendelt online **áruház** ellenőrzéséhez megnyithatja a Commerce webhely beállítási lapját, és a Csatornák oszlopban ellenőrizheti az online **áruház** nevét. 
1. A **Nyelvek** gyorslapon válassza a **Hozzáadás** elemet. A Nyelv **mezőben** válassza ki az új nyelv területi beállításának kódját. Majd válassza a **Mentés** lehetőséget.
1. Menjen a **Retail and Commerce \> Retail and Commerce IT \> Distribution** ütemezéshez, **és futtassa a 1070-es csatornakonfigurációt**. Amikor befejeződött a feladat futtatása, továbbléphet a 2. lépésre, és a nyelvet hozzáadhatja egy csatornához a webhely webhelyére a Webhelyszerkesztőben.

![A Commerce Headquarters online áruházának Nyelvek gyorstára](media/loc-guide-3.png)

#### <a name="step-2-add-the-language-to-a-channel-in-site-builder"></a>2. lépés: A nyelv hozzáadása egy csatornához a webhelyszerkesztőben

A webhelyszerkesztő csatornáihoz a következő lépések szerint adhat hozzá nyelvet.

1. A Commerce webhelyszerkesztőben nyissa meg a webhelyet, majd nyissa meg a Webhely beállításai között **a Csatornák** lapot.
1. Válassza ki annak a csatornának a nevét, amelybe a nyelvet hozzá szeretné adni.
1. A jobb oldali ablakban válassza a Területi **beállítás hozzáadása lehetőséget**.
1. A Területi **beállítás hozzáadása** **párbeszédpanel Hely hozzáadása területén válassza ki a** Commerce Headquarters rendszerbeli csatornához korábban hozzáadott nyelv területi beállítását.
1. Annak a tartománynak és elérési útnak a kiválasztása, amelytől a vevők a webhely megtekintését kérik ezen a csatornán és nyelven.
1. Ha azt szeretné, hogy a nyelv legyen az alapértelmezett nyelv a webhelyszerkesztő lapjainak és a cikkrészleteknek a megtekintéséhez, létrehozásához és frissítéséhez, **jelölje be a Használat alapértelmezettként a** csatornanyelv alapján jelölőnégyzetet. 
    > [!NOTE]
    > Ez a beállítás csak a webhelyszerkesztőre van hatással. Ez nincs hatással a közzétett webhely felhasználói élményére.
1. Válassza ki az **OK** lehetőséget.
1. Válassza a **Mentés és közzététel** lehetőséget.

#### <a name="step-3-localize-your-site-content"></a>3. lépés: A webhely tartalmának honosizálása

Amikor visszatér a **Commerce** webhelyszerkesztő Oldal nézethez, az új nyelv elérhetővé válik a csatornában, és a jobb felső részén található területi beállítások kiválasztója látható. Most létrehozhatja a lapok honosított verzióit az alapnyelven.

A lapok tartalmának [és a cikkrészletek honosizálásának folyamatát a cikk későbbi, Az e-commerce](#localize-e-commerce-site-content) webhely honosítani szakasza tartalmaz.

### <a name="configure-a-new-channel-for-your-site"></a>Új csatorna konfigurálása a webhely számára

Dynamics 365 Commerce Az e-commerce webhelyek olyan tapasztalatokat szolgálnak, amelyek a Commerce Headquarters alkalmazáson keresztül több online csatornában vannak meghatározva. Egy hely több csatornát használ, hogy a vevők számára a fizetési módok, árcsoportok, termékhierarchiák, szortimentek és termékkészletek egyedi konfigurációját mutassa. A csatornák általában úgy konfigurálják ezeket a dimenziókat, hogy az megfeleljen az egyes országok tapasztalati követelményeinek és igényeinek. Ez a megközelítés azonban az ügyfél által hozott üzleti döntés. Nem követelmény.

A csatorna (online áruház) beállításához kapcsolódó előfeltételek és feladatok túllépik a dokumentum hatókörét. Az online csatornák Commerce Headquarters [alkalmazáson keresztüli beállításának további tudnivalókat lásd a Csatornabeállításokkal kapcsolatos alapismeretek között](channels-overview.md#channel-setup-basics). Az online csatornákra vonatkozó lépésekkel és követelményekkel kapcsolatos tudnivalókat lásd [: Online csatorna beállítása](channel-setup-online.md).

A webhelyszerkesztőben a következő lépésekkel adhat hozzá csatornát a webhelyhez.

1. A Commerce webhelyszerkesztőben kattintson a Webhely-beállítási **csatornák elemre \>**. 
1. Válassza **a Csatorna hozzáadása lehetőséget**.
1. A Csatorna **hozzáadása párbeszédpanel** **Csatorna** alatt válassza ki a hozzáadni kívánt csatornát. 
    > [!NOTE]
    > Csak olyan csatornákat adhat hozzá, amelyek még nincsenek hozzáadva a webhelyhez.
1. A csatorna alapértelmezett területi beállításának kiválasztása. Ha új nyelvet ad hozzá a csatornához, az alapértelmezett nyelvet módosíthatja valamelyikre.
1. Adja meg azt a tartományt és elérési utat, amely a csatorna és a nyelv ezen kombinációjához nyújt tartalmat és tapasztalatokat.
1. Válassza ki az **OK** lehetőséget.
1. Válassza a **Mentés és közzététel** lehetőséget.

## <a name="localize-e-commerce-site-content"></a>E-commerce webhely tartalmának honosizálása

### <a name="xliff-basics"></a>XLIFF-alapismeretek

Az XLIFF egy iparági szabványnak megfelelő fájlformátum, amely lehetővé válik a tartalomkezelési eszközök közötti honosított tartalom átadása. A Commerce Site Builder a XLIFF fájlformátum segítségével exportálja a lap, a részletek és a kép metaadatainak tartalmát, így honosizálható és újraimportálható.

Microsoft Dynamics az ügyfelek általában külső [fél](https://translated.com/welcome) honosítási szállítóival dolgoznak, például Translated.com, hogy xlIFF-fájljaikat a szükséges nyelvekre fordítják.

### <a name="localize-assets-in-site-builder"></a>Eszközök honosizálása a webhelyszerkesztőben

A webhelyszerkesztő a következő e-commerce webhely-eszközöket honoshatja:

- Oldalak
- Töredékek
- Médiaeszközök
- Modulok

Minden új oldal, részlet és médiaeszköz annak a csatornának és nyelvnek a kontextusában jön létre, amely ki van választva a csatornában és a területi beállításban. Ez a nyelv általában az alapnyelv, feltéve, hogy nem konfigurált további nyelveket vagy csatornákat. Olyan webhelyeken, ahol több csatorna és nyelv van konfigurálva, a csatorna határozza meg az " **alapnyelvet", és ez a beállítás van beállítva alapértelmezettként a Webhely beállításai között a Csatornák** lapon.

Hasonlóak a lapok, részletek és médiaeszközök tartalmának honosizálására vonatkozó lépések. A következő szakaszok kivételeket és eltéréseket mutatnak be. A modul tartalmának honosizálására vonatkozó lépések azonban eltérőek. A további tudnivalókat lásd [a](#localize-modules) cikk Honosítani moduljainak szakaszban.

#### <a name="step-1-export-an-xliff-file"></a>1. lépés: XLIFF-fájl exportálása

A következő lépések szerint exportálhatja egy lapra, részletre vagy képre vonatkozó XLIFF-fájlt a helyszerkesztőben.

1. Nyissa meg azt az eszközt, amely exportálni szeretné az alapnyelv tartalmát, hogy honosizálható legyen.
1. Válassza a parancssorból a Honosítás **\> exportálása XLIFF lehetőséget**.
    > [!NOTE]
    > A **honosítási** beállítás csak akkor látható, ha az eszköz Szerkesztés állapotban **van**.

A böngésző letöltési mappájába **\<assetname\> egy .xlf** nevű XLIFF-fájl lesz letöltve. Ez az XLIFF-fájl a honosító eszközre jellemző. Minden honosítani kívánt eszközre exportálni fog egy XLIFF-fájlt.

#### <a name="step-2-localize-the-xliff-file"></a>2. lépés: Az XLIFF-fájl honosítani kell.

A legtöbb esetben egy honosítási szállítóval kell lefordítani az XLIFF-fájlokat. Ha azonban az eszközöket belsőleg honosítással szeretné tesztelni, vagy csak tesztelni szeretné a honosítási folyamatot, a következő módosításokat kell végrehajtotta az XLIFF-fájlban:

- Célnyelv attribútum hozzáadása a /xliff/fájl elemhez, és az érték beállítása annak a nyelvnek a területi azonosítójában, amelybe honosítód. 
    > [!NOTE]
    > Ennek a területi beállításnak meg **kell egyeznie a webhely beállításai között a Csatornák** lap helyazonosítójának.
- Minden //forráselemhez adjon hozzá egy testvér célelemet, ahol a szövegérték az adott forráselem tartalmának honosított verziója.

Az XLIFF-fájlokat irányító sémával kapcsolatos tudnivalókat [lásd az XLIFF 1.2 specifikációban](http://docs.oasis-open.org/xliff/xliff-core/xliff-core.html).

> [!NOTE]
> Egy eszköz több nyelvre történő honosizálása előtt minden ilyen nyelvhez létre kell hoznia egy honosított XLIFF-fájlt.

#### <a name="step-3-import-the-localized-xliff-file"></a>3. lépés: A honosított XLIFF-fájl importálása

A tárgyi eszközök XLIFF-fájlját a következő lépések szerint importálhatja.

1. A Commerce webhelyszerkesztőben nyissa meg azt az eszközt, amelynek XLIFF-fájlt szeretne importálni.
1. A jobb felső csatorna- és területi beállításválasztóban válassza ki azt a csatornát és nyelvet, amelybe honosított tartalmat importál.
1. Válassza a parancssori import **XLIFF honosítási \> beállítását**. Ezután tallózással keresse meg és válassza ki a kiválasztott eszközre és nyelvre vonatkozó honosított XLIFF-fájlt.

Az XLIFF-fájl sikeres importálása után létrejön a lap, a részlet vagy az eszköz "változata". Ettől a ponttól kezdve a honosított változat minden változtatása csak erre a változatra lesz hatással. Ezek nem befolyásolják azt az alap eszközt, amelyből a változat származik. Hasonlóképpen az alapeszköz módosításai nem befolyásolják az eszközváltozatot. 

A lapok esetében azonban az egyes változatok módosítása a lapokhoz kötött sablon vagy elrendezés módosításával valósulhat meg. Hasonlóképpen a részlet módosításai hatással lesznek minden olyan lapra, amely az adott változattól függ.

### <a name="images"></a>Képek

A képek csak akkor jelennek meg egy oldalon vagy modulváltozatban, ha a képekhez társított tartalom-metaadatok honosítottak. A médiaeszköz következő metaadatai jelenleg honoshatók:

- Helyettesítő szöveg
- Leírás
- Beosztás

A digitális eszközök( például kép vagy video) bináris értékét jelenleg nem lehet honosítani. A Dynamics 365 Commerce termékcsoport jelenleg ezen a képességen dolgozik.

### <a name="localize-modules"></a>Modulok honosítani

A modul tartalmától elkülönítve honosított karakterláncok, amelyek magát a modult is részeiként jelennek meg (például "Előző" és "Tovább" a carousel modulban). Az útmutatás a modul [honosításában található](e-commerce-extensibility/localize-module.md).

## <a name="additional-resources"></a>További erőforrások

[Oldal modellszószedete](page-elements-overview.md)

[Csatornák közötti megosztás](cross-channel-sharing.md)

[Modul honosítása](e-commerce-extensibility/localize-module.md)

[Modul definíciós fájlja](e-commerce-extensibility/module-definition-file.md)

[Commerce-bővítmény erőforrásainak és címkefájljainak honosítása](dev-itpro/extension-resource-localization.md)

[Modulok globalizálása a CultureInfoFormatter osztály használatával](e-commerce-extensibility/globalize-modules.md)

[Alkalmazásbeállítások: Témák](e-commerce-extensibility/app-settings.md#themes-section)
