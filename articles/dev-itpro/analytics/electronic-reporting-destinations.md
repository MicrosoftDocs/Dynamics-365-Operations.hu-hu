---
title: "Elektronikus jelentéskészítés (ER) céljai"
description: "Konfigurálhatja az egyes Elektronikus jelentés (ER) formátum konfigurációjához tartozó célt és annak kimeneti összetevőit (egy mappa vagy egy fájl). Megfelelő hozzáférési jogokkal rendelkező felhasználók módosíthatják a célbeállításokat futásidőben is. Ez a cikk ismerteti az ER célkezelés, a támogatott célok típusait és a biztonsági megfontolásokat."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: 301dccaf154c3c12bcc4d611a147cdef03b8f851
ms.contentlocale: hu-hu
ms.lasthandoff: 08/13/2018

---

# <a name="electronic-reporting-er-destinations"></a>Elektronikus jelentéskészítés (ER) céljai

[!include [banner](../includes/banner.md)]

Konfigurálhatja az egyes Elektronikus jelentés (ER) formátum konfigurációjához tartozó célt és annak kimeneti összetevőit (egy mappa vagy egy fájl). Megfelelő hozzáférési jogokkal rendelkező felhasználók módosíthatják a célbeállításokat futásidőben is. Ez a cikk ismerteti az ER célkezelés, a támogatott célok típusait és a biztonsági megfontolásokat.

Az elektronikus jelentési (ER) formátum konfigurációk általában tartalmaznak legalább egy kimeneti összetevőt: egy fájlt. A konfigurációk általában több, különböző típusú eredménykomponensből állnak (pl. XML, TXT, vagy XLSX), amik egy, vagy több mappában kerülnek csoportosításra. Az ER célkezeléssel előre konfigurálható, hogy mi történjen, mikor a komponenseket futtatja. Alapértelmezés szerint a konfiguráció futtatásakor megjelenik egy párbeszédpanel, aminek segítségével a felhasználó mentheti vagy megnyithatja a fájlt. Ugyanez a viselkedésforma használatos, amikor egy ER konfigurációt importál, de nem konfigurál hozzá meghatározott célt. Miután létrehozta a célt a fő kimeneti komponens részére, a létrehozott cél felülírja az alapértelmezett viselkedést, és a mappa vagy fájl a cél beállításainak megfelelően kerül kiküldésre.

## <a name="availability-and-general-prerequisites"></a>Elérhetőség és általános előfeltételek
Az ER célok funkció a Microsoft Dynamics AX 7.0-ban (2016. február) nem elérhető. Ezért telepítenie kell a Microsoft Dynamics 365 for Operations 1611-es verzióját (2016. novemberi kiadás) az ebben a témakörben leírt függvények használatához. Másik lehetőségként telepíthet egyet a következő előfeltételek közül: Azonban ne feledje, hogy ezek az alternatívák az Elektronikus jelentéstétel célok korlátozottabb használatát teszik lehetővé.

- Microsoft Dynamics AX 7.0.1 alkalmazásverzió (2016 Május)
- ER célkezelési [alkalmazás gyorsjavítás](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

A célokat csak importált ER konfigurációkhoz, és csak az **Elektronikus jelentéskonfigurációk** oldalon elérhető formátumokban állíthatja be.

## <a name="overview"></a>Áttekintés
Az elektronikus jelentéstételi célkezelés funkció itt érhető el: **Szervezeti adminisztráció** &gt; **Elektronikus jelentés**. Itt felülírható egy adott konfigurációhoz alapbeállított viselkedés. Az importált konfigurációk az **Új** gombra kattintva, majd a **Hivatkozás** mezőben a létrehozandó célbeállításokhoz használni kívánt konfiguráció kiválasztásával jeleníthetők meg.

[![Konfiguráció kiválasztása a Hivatkozás mezőben](./media/ger-destinations-2-1611-1024x574.jpg)](./media/ger-destinations-2-1611.jpg)

Hivatkozás létrehozása után minden mappa vagy fájl részére megadhat egy elérési utat.

[![Fájlcél létrehozása](./media/ger-destinations-1611-1024x586.jpg)](./media/ger-destinations-1611.jpg)

> [!NOTE]
> Minden, azonos formátumú kimeneti összetevőhöz - például a **Fájl neve** mezőben kiválasztott mappához vagy fájlhoz - létrehozhat egy fájlelérési utat. Ezután be- és kikapcsolhatja a fájl egyes elérési útjait az **Elérési út beállításai** párbeszédpanelen. A **Beállítások** gombbal egy kiválasztott fájl elérési útjának minden célja vezérelhető. Az **Útvonalbeállítások** párbeszédpanelen minden elérési utat külön vezérelhet a **Bekapcsolva** opcióval.

[![Célhely beállításai párbeszédablak](./media/ger-destinations-settings-1611-1024x589.jpg)](./media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>Céltípusok
Célok széles választéka támogatott. Minden típust egyszerre kapcsolhat ki és be. Ezzel a módszerrel mindent úgy hagyhat, ahogy van, vagy elküldheti a komponenseket minden konfigurált célra. A következő részben leírja a támogatott célokat.

### <a name="email-destination"></a>E-mail célja

Állítsa a **Bekapcsolva** opciót **Igen** állapotra egy eredményfájl email-ben történő küldéséhez. Ezen beállítás engedélyezése után szerkesztheti az e-mail címzettjeit, tárgyát és szövegét. Beállíthat állandó szöveget az e-mail tárgyaként és szövegeként, illetve használhat ER-képleteket az e-mail szövegének dinamikus létrehozására. Elektronikus jelentéstételhez e-mail-címeket két módon konfigurálhat. A konfiguráció ugyanúgy hajtható végre, mint a Finance and Operations Nyomtatás kezelése funkciójánál. Azt is megteheti, hogy az elektronikus jelentéstételi konfigurációra mutató közvetlen hivatkozással, képlet használatával old fel egy e-mail-címet.

### <a name="email-address-types"></a>E-mail-címek típusai

Amikor a **Szerkesztés** elemre kattint a **Címzett** vagy **Másolatot kap** mezőnél, megjelenik az **E-mail címzettje** párbeszédpanel. Ezután kiválaszthatja a használandó e-mail-cím típusát.

[![E-mail címzettje párbeszédpanel](./media/ger-destinations-email-1-1611-1024x588.jpg)](./media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Nyomtatás kezelése

Ha bejelöli a **Nyomtatáskezelő e-mail** típust, fix e-mail-címeket adhat meg a **Címzett** mezőben. Nem rögzített email-cím használatához válassza ki az e-mail forrástípusát a fájlcélponthoz. A következő értékek használhatók: **Vevő**, **Szállító**, **Potenciális vevő**, **Kapcsolat**, **Versenytárs**, **Dolgozó**, **Kérelmező**, **Potenciális szállító** és **Nem engedélyezett szállító**. Miután kiválasztott egy e-mail-forrástípust, használja az **E-mail származási fiókja** mező melletti gombot a **Képletszerkesztő** képernyő megnyitásához. Ezen a képernyőn olyan képletet adhat hozzá, amely a kiválasztott fél fiókját jelöli az az e-mail címzettje vonatkozásában.

[![Nyomtatáskezelő e-mail-típusának beállítása](./media/ger-destinations-email-2-1611-1024x588.jpg)](./media/ger-destinations-email-2-1611.jpg)

Vegye figyelembe, hogy a receptúrák ER-konfigurációspecifikusak. A **Receptúra** mezőben adja meg a vevői vagy szállítói féltípusra történő dokumentumspecifikus hivatkozást. Gépelés helyett megkeresheti a vevőt vagy szállítót reprezentáló adatforrás-csomópontokat, és az **Adatforrás hozzáadása** gombra kattintva frissítheti a receptúrát Például, ha az ISO 20022 Jóváírás Átutalása konfigurációt használja, a szállító számláját reprezentáló csomópont a következő: **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID**. A receptúra egyébként bármely karakterlánc, mint pl. **DE-001** megadásával menthető.

[![Képletszerkesztő](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

Az **E-mail címzettje** párbeszédpanelen kattintson a szemeteskukára az **E-mail származási fiókja** mező mellett az e-mail-forrásfiókra vonatkozó képlet végleges törléséhez. Másik lehetőségként megnyithatja a képletszerkesztőt a korábban mentett képlet módosításához. E-mail-címek hozzárendeléséhez kattintson a **Szerkesztés** elemre az **E-mail-címek hozzárendelése** párbeszédpanel megnyitásához.

[![E-mail-címek hozzárendelése e-mail-célhelyhez](./media/ger-destinations-email-3-1611-1024x587.jpg)](./media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>Konfigurációs e-mail

Használja ezt az e-mail-típust, ha a használt konfiguráció tartalmaz egy e-mail-címet képviselő csomópontot az adatforrásokban. A Képletszerkesztő adatforrásainak és függvényeinek használatával helyesen formázott e-mail-címet állíthat elő.

[![E-mail-cím-adatforrás hozzárendelése e-mail-célhelyhez](./media/ger-destinations-email-4-1611-1024x587.jpg)](./media/ger-destinations-email-4-1611.jpg)

> [!NOTE]
> Az Egyszerű üzenetátviteli protokoll (Simple Mail Transfer Protocol - SMTP) kiszolgálónak konfiguráltnak és elérhetőnek kell lennie. Az SMTP-kiszolgálót megadhatja a Finance and Operations rendszerben itt: **Rendszeradminisztráció** &gt; **Beállítások** &gt; **E-mail** &gt; **E-mail-paraméterek**.

### <a name="archive-destination"></a>Archív cél

Ezen opcióval eredmény küldhető egy Microsoft SharePoint vagy Microsoft Azure Storage mappába. A kiválasztott dokumentumtípus által meghatározott célra történő eredményküldéshez állítsa a **Bekapcsolva** opciót **Igen** állapotba. Csak azok a dokumentumtípusok választhatók ki, amelyeknél a csoport beállítása **File**. A dokumentumtípusokat itt határozhatja meg: **Szervezetadminisztráció** &gt; **Dokumentumkezelés** &gt; **Dokumentumtípusok**. Az ER célok konfigurálásának folyamata megegyezik a dokumentumkezelő rendszer konfigurálásával.

[![Dokumentumtípusok lapja](./media/ger_documenttypefile-1024x542.jpg)](./media/ger_documenttypefile.jpg)

A hely határozza meg, hogy a file hol kerül tárolásra. Az **Archívum** cél engedélyezése után a konfiguráció végrehajtásának eredménye elmenthető a Feladatarchívumba. Az eredményeket a **Szervezeti adminisztráció** &gt; **Elektronikus jelentés** &gt; **Elektronikus jelentéskészítési archivált feladatok** elemnél tekintheti meg.

> [!NOTE]
> Megjegyzés: a Feladatarchívumhoz dokumentumtípus a Finance and Operations alkalmazásban a következő helyen választható ki: **Szervezeti adminisztráció** &gt; **Munkaterületek** &gt; **Elektronikus jelentés** &gt; **Elektronikus jelentéskészítés paraméterei**.

#### <a name="sharepoint"></a>SharePoint

A fájlt egy kijelölt SharePoint mappába is mentheti. Az alapértelmezett SharePoint kiszolgálót itt határozhatja meg: **Szervezeti adminisztráció** &gt; **Dokumentumkezelés** &gt; **Dokumentumkezelés paraméterei**, a **SharePoint** lapon. A SharePoint-mappa konfigurálása után a mappát kiválaszthatja azon mappaként, ahová az elektronikus jelentési eredmények mentésre kerülnek az adott dokumentumtípusnál.

[![SharePoint-mappa kiválasztása](./media/ger_sharepointfolderselection-1024x543.jpg)](./media/ger_sharepointfolderselection.jpg)

#### <a name="azure-storage"></a>Azure Storage

Ha a dokumentumtípus helye **Archív könyvtár**, a fájl menthető az Azure Storage-en.

### <a name="file-destination"></a>Fájl célja

A konfiguráció lefutása után a megnyitás/mentés párbeszédpanel megjelenítéséhez az **Engedélyezve** opciót állítsa **Igen** állapotba.

### <a name="screen-destination"></a>Célképernyő

Ha az **Engedélyezve** elem **Igen** értékre van állítva, létrejön a kimenet előnézete. Bizonyos fájltípusok, például XML, TXT vagy PDF, közvetlenül a böngésző ablakában tekinthető meg. Más fájltípusoknál, például Microsoft Excelnél vagy Wordnél, a Microsoft Office Online szolgáltatás használatos.

### <a name="power-bi-destination"></a>Power BI-célhely

Állítsa az **Engedélyezve** elemet **Igen** értékre ahhoz, hogy az elektronikus jelentési (ER) konfiguráció adatokat vigyen át a Finance and Operations alkalmazásból a Microsoft Power BI szolgáltatásokba. Az átvitt fájlok tárolása egy Microsoft SharePoint Server példányon történik, amelyet ennek a célnak megfelelően konfigurálni kell. További tájékoztatásért lásd: [Használja az elektronikus jelentési konfigurációt ahhoz, hogy a Finance and Operations adatait továbbítsa a Power BI-nak](general-electronic-reporting-report-configuration-get-data-powerbi.md).

> [!TIP]
> Az alapértelmezett viselkedés (vagyis a konfiguráció párbeszédpanelének) felülbírálásához létrehozhat egy célhivatkozást és fájlcélt a fő eredménykomponens részére, majd kikapcsolhatja az összes célt.

## <a name="security-considerations"></a>Biztonsági megfontolások
Az ER célokhoz kétféle jog és kötelezettség létezik. Az egyik típus felügyeli azon célok összességének karbantartását, melyek egy jogi személy számára lettek konfigurálva (vagyis vezérli az **Elektronikus jelentés céljai** oldalhoz való hozzáférést). A másik típus szabályozza az alkalmazás felhasználóját abban, hogy a futtatás során felülírja az ER-fejlesztők vagy ER-funkciótanácsadók által konfigurált célbeállításokat.

| Szerepkör (AOT-név)                     | Szerepkör neve                                  | Feladat (AOT-név)                     | Feladat neve                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Elektronikus jelentések fejlesztője             | ERFormatDestinationConfigure        | Elektronikus jelentéskészítési formátum céljának konfigurálása                |
| ERFunctionalConsultant              | Elektronikus jelentések funkcióival foglalkozó konzulens | ERFormatDestinationConfigure        | Elektronikus jelentéskészítési formátum céljának konfigurálása                |
| PaymAccountsPayablePaymentsClerk    | Kötelezettségkifizetési adminisztrátor            | ERFormatDestinationRuntimeConfigure | Elektronikus jelentéskészítési formátum céljának konfigurálása futásidőben |
| PaymAccountsReceivablePaymentsClerk | Kinnlevőség-kifizetési adminisztrátor         | ERFormatDestinationRuntimeConfigure | Elektronikus jelentéskészítési formátum céljának konfigurálása futásidőben |

> [!NOTE]
> A megelőző feladatokban két jogosultság kerül alkalmazásra. Ezeknek a jogosultságoknak a neve megegyezik a hozzájuk tartozó feladatokkal: **ERFormatDestinationConfigure** és **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Gyakori kérdések
### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>Rendelkezem importált elektronikus konfigurációkkal, és látom azokat az Elektronikus jelentési konfigurációk oldalon. De miért nem látom őket az Elektronikus jelentési célok oldalon?

Győződjön meg arról, hogy az **Új** gombra kattintott, majd kiválasztott egy konfigurációt a **Hivatkozás** mezőben. Az **Elektronikus jelentési célok** oldalon csak azokat a konfigurációkat láthatja, melyekhez a célok konfigurálva vannak.

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>Meg lehet határozni, hogy melyik Azure Storage-fiókot és Azure Blob-tárhelyet használja a rendszer?

Szám A dokumentumkezelőben meghatározott és használt, alapértelmezett Azure Blob-tárhely lesz használva.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Mi a célja a Fájl cél lehetőségnek a célbeállításoknál? Mire jó ez a beállítás?

A **Fájl** cél a párbeszédpanel irányítására szolgál. Ha bekapcsolja ezt a célt, vagy ha a konfigurációhoz nincs cél megadva, egy eredményfájl létrehozása után megjelenik a megnyitás vagy mentés párbeszédpanel.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Létezik példa egy olyan receptúrára, ami egy szállítói fiókra utaló receptúrát tartalmaz, ahová emaileket küldhetek?

A formula ER-konfigurációspecifikus. Például, ha az ISO 20022 Jóváírás Átutalása konfigurációt használja, használhatja az **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** vagy **model.Payments.Creditor.Identification.SourceID** karakterláncokat egy társított szállítói fiók eléréséhez.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Valamelyik formátumkonfigurációmban több fájl is van, melyek egy mappába lettek csoportosítva (Például Mappa1 tartalma Fájl1, Fájl2, és Fájl3). Hogyan állíthatom be úgy a célokat, hogy a Mappa1.zip ne legyen létrehozva, Fájl1 legyen emailben elküldve, Fájl2 legyen a SharePoint-ra küldve, és Fájl3-mat egyből a konfiguráció lefutása után megnyithassam?

Előfeltétel, hogy az Ön formátuma elérhető legyen az ER-konfigurációknál. Ha megvan a formátum, nyissa meg az **Elektronikus jelentés célja** oldalt, majd hozzon létre új hivatkozást erre a konfigurációra. Ekkor négy fájlcélra lesz szüksége, egyre mindegyik eredménykomponenshez. Hozza létre az első fájlcélt, nevezze el pl. úgy, hogy **Mappa**, majd válassza ki a fájlnevet, ami a konfigurációban a mappát reprezentálja. Kattintson a **Beállítások** gombra, és győződjön meg róla, hogy minden cél ki van kapcsolva. Ehhez a fájlcélhoz nem lesz mappa létrehozva. A fájlok és szülőmappák közötti hierarchikus viszonyok miatt alapértelmezés szerint a fájlok ugyanúgy fognak viselkedni. Más szóval nem lesznek sehová elküldve. Ezen alapértelmezett viselkedés felülbírálásához három másik fájlcélt kell létrehoznia, egyet mindegyik fájlhoz. Az egyes célbeállításoknál be kell kapcsolnia azt a célt, ahová a fájlt küldeni kívánja.

## <a name="additional-resources"></a>További erőforrások

[Az Elektronikus jelentéskészítés áttekintése](general-electronic-reporting.md)

