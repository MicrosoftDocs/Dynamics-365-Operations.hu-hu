---
title: "Elektronikus jelentéskészítés céljai"
description: "Konfigurálhatja az egyes Elektronikus jelentés (ER) formátum konfigurációjához tartozó célt és annak kimeneti összetevőit (egy mappa vagy egy fájl). Megfelelő hozzáférési jogokkal rendelkező felhasználók módosíthatják a célbeállításokat futásidőben is. Ez a cikk ismerteti az ER célkezelés, a támogatott célok típusait és a biztonsági megfontolásokat."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: d38d05fe445bf0326d408038dff84ccf8c0ff64c
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-reporting-destinations"></a>Elektronikus jelentéskészítés céljai

Konfigurálhatja az egyes Elektronikus jelentés (ER) formátum konfigurációjához tartozó célt és annak kimeneti összetevőit (egy mappa vagy egy fájl). Megfelelő hozzáférési jogokkal rendelkező felhasználók módosíthatják a célbeállításokat futásidőben is. Ez a cikk ismerteti az ER célkezelés, a támogatott célok típusait és a biztonsági megfontolásokat.

Az elektronikus jelentési (ER) formátum konfigurációk általában tartalmaznak legalább egy kimeneti összetevőt: egy fájlt. A konfigurációk általában több, különböző típusú eredménykomponensből állnak (pl. XML, TXT, vagy XLSX), amik egy, vagy több mappában kerülnek csoportosításra. Az ER célkezeléssel előre konfigurálható, hogy mi történjen, mikor a komponenseket futtatja. Alapértelmezés szerint egy konfigurációs futtatásakor egy párbeszédpanel jelenik meg, amely lehetővé teszi a felhasználó a fájlt megnyitni vagy menteni. Ugyanez a viselkedésforma használatos, amikor egy ER konfigurációt importál, de nem konfigurál hozzá meghatározott célt. Miután létrehozta a célt a fő kimeneti komponens részére, a létrehozott cél felülírja az alapértelmezett viselkedést, és a mappa vagy fájl a cél beállításainak megfelelően kerül kiküldésre.

## <a name="availability-and-general-prerequisites"></a>Elérhetőség és általános előfeltételek
ER célok működését nem érhető el a Microsoft Dynamics 365 műveletek 7.0 (2016. február) kiadáshoz. Ezért telepítenie kell a Microsoft Dynamics 365 műveletek (November 2016 kiadás) az ebben a témakörben leírt függvények használatához. Másik lehetőségként a következő előfeltételek egyike is telepítheti. Azonban ne feledje, hogy ezek helyett adja meg a korlátozottabb ER cél érdekében.

-   A Microsoft Dynamics 365 műveletek alkalmazás verzió 7.0.1 (2016. május)
-   ER célkezelési [alkalmazás gyorsjavítás](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

A célokat csak importált ER konfigurációkhoz, és csak az **Elektronikus jelentéskonfigurációk** oldalon elérhető formátumokban állíthatja be.

## <a name="overview"></a>Áttekintés
A cél ER kezelési funkciói érhető el: **szervezet felügyelete**&gt;**elektronikus jelentés**. Itt felülírható egy adott konfigurációhoz alapbeállított viselkedés. Az importált konfigurációk az **Új** gombra kattintva, majd a **Hivatkozás** mezőben a létrehozandó célbeállításokhoz használni kívánt konfiguráció kiválasztásával jeleníthetők meg.

[![A hivatkozás mezőben válassza a konfiguráció](./media/ger-destinations-2-1611-1024x574.jpg)](./media/ger-destinations-2-1611.jpg) 

Hivatkozás létrehozása után minden mappa és fájl fájl célt is létrehozhat. 

[![Egy fájl cél létrehozása](./media/ger-destinations-1611-1024x586.jpg)](./media/ger-destinations-1611.jpg)

**Megjegyzés:** Ugyanazon formátumú egyes eredménykomponensek számára csak egy elérési utat adhat meg, ami a **Fájlnév** mezőben kiválasztott fájl vagy mappa. Majd engedélyezheti és letilthatja a fájl célja az egyes célok a **beállításainak** párbeszédpanel. A **Beállítások** gombbal egy kiválasztott fájl elérési útjának minden célja vezérelhető. Az **Útvonalbeállítások** párbeszédpanelen minden elérési utat külön vezérelhet a **Bekapcsolva** opcióval.

[![Cél beállításai párbeszédpanel használata](./media/ger-destinations-settings-1611-1024x589.jpg)](./media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>Céltípusok
Célok széles választéka támogatott. Minden típust egyszerre kapcsolhat ki és be. Ezzel a módszerrel mindent úgy hagyhat, ahogy van, vagy elküldheti a komponenseket minden konfigurált célra. A következő részben leírja a támogatott célokat.

### <a name="email-destination"></a>E-mail célja

Állítsa a **Bekapcsolva **opciót **Igen** állapotra egy eredményfájl email-ben történő küldéséhez. Után ez a beállítás engedélyezve van, adja meg az e-mail címzettjeit, és szerkessze a tárgyat és az e-mail üzenet törzsében. Beállíthatja az e-mail tárgyát és szövegét változatlan szövegét, vagy ER képletek segítségével dinamikusan hozzák létre az e-mail szövegét. E-mail címek ER két módon konfigurálható. A konfigurációs műveletek Dynamics 365 nyomtatási szolgáltatása kitöltését ugyanúgy hajtható. Azt is megteheti oldhatja meg egy e-mail címet a ER konfiguráción keresztül egy képlet közvetlen hivatkozás segítségével.

### <a name="email-address-types"></a>E-mail cím típusa

Kattint **Szerkesztés** a a **,** vagy **Cc** mező, a **e-mail üzenet** párbeszédpanel jelenik meg. Ezután kiválaszthatja a használandó e-mail cím típusát.

[![E-mail üzenet párbeszédpanel](./media/ger-destinations-email-1-1611-1024x588.jpg)](./media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Nyomtatás kezelése

Ha bejelöli a **a Nyomtatáskezelő e-mail** típus, a rögzített e-mail címét adhatja a **,** mező. Nem javított e-mail címét használja, válassza a fájl cél e-mail forrástípus. A következő értékek használhatók: **vevő**, **szállító**, **potenciális**, **partner**, **versenytárs**, **dolgozó**, **kérelmező**, **potenciális szállító**, és **nem engedélyezett szállító**. Miután kiválasztott egy e-mail Forrástípus, használja a gomb mellett a **forrás fiók E-mail** mező megnyitásához a ** Képletszerkesztő ** képernyőn. Ezen a képernyőn olyan képletet, amely a kijelölt fél fiókot jelöli az e-mail címzettje csatolni.

[![A Nyomtatáskezelő e-mail típusának beállítása](./media/ger-destinations-email-2-1611-1024x588.jpg)](./media/ger-destinations-email-2-1611.jpg) 

Vegye figyelembe, hogy a receptúrák ER-konfigurációspecifikusak. A **Receptúra** mezőben adja meg a vevői vagy szállítói féltípusra történő dokumentumspecifikus hivatkozást. Gépelés helyett megkeresheti a vevőt vagy szállítót reprezentáló adatforrás-csomópontokat, és az **Adatforrás hozzáadása** gombra kattintva frissítheti a receptúrát Például, ha az ISO 20022 Jóváírás Átutalása konfigurációt használja, a szállító számláját reprezentáló csomópont a következő: **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID**. A receptúra egyébként bármely karakterlánc, mint pl. **DE-001** megadásával menthető.

[![Formula designer](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

A a **e-mail üzenet** párbeszédpanelen kattintson az újrahasznosítás bin tovább, a **forrás fiók E-mail** véglegesen törli a képletet a forrás e-mail fiók mezőben. Azt is megteheti nyissa meg a korábban mentett képlet módosítása Képletszerkesztő. E-mail címek hozzárendeléséhez kattintson a **Szerkesztés** megnyitása a **e-mail címek hozzárendelése** párbeszédpanel.

[![Az e-mail cél e-mail címek hozzárendelése](./media/ger-destinations-email-3-1611-1024x587.jpg)](./media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>Konfigurációs e-mail

E-mail ezt a típust akkor használja, ha a használt konfiguráció tartalmaz egy e-mail címet jelöl az adatforrások csomópontjában. Használhatja adatforrások és funkciók a Képletszerkesztő az egy helyesen formázott e-mail címét.

[![Az e-mail célja egy e-mail cím adatforrás hozzárendelése](./media/ger-destinations-email-4-1611-1024x587.jpg)](./media/ger-destinations-email-4-1611.jpg) 

**Megjegyzés:** Az Egyszerű üzenetátviteli protokoll (Simple Mail Transfer Protocol - SMTP) kiszolgálónak konfiguráltnak és elérhetőnek kell lennie. Az SMTP-kiszolgáló Dynamics 365 műveletek esetében megadhatja **rendszerfelügyelet**&gt;**a telepítő**&gt;**E-mail**&gt;**paramétereket Email**.

### <a name="archive-destination"></a>Archív cél

Ezen opcióval eredmény küldhető egy Microsoft SharePoint vagy Microsoft Azure Storage mappába. A kiválasztott dokumentumtípus által meghatározott célra történő eredményküldéshez állítsa a **Bekapcsolva** opciót **Igen **állapotba. Csak azok a dokumentumtípusok választhatók ki, amelyeknél a csoport beállítása **File**. Megadhatja a dokumentum típusok **szervezet felügyelete**&gt;**Dokumentumkezelés**&gt;**dokumentumtípusok**. Az ER célok konfigurálásának folyamata megegyezik a dokumentumkezelő rendszer konfigurálásával.

[![Dokumentum-típusok oldalon](./media/ger_documenttypefile-1024x542.jpg)](./media/ger_documenttypefile.jpg) 

A hely határozza meg, hogy a file hol kerül tárolásra. Után a **archívum** cél engedélyezve van, a konfigurációs végrehajtás eredményét a feladat archív menthetők. Megtekintheti az eredményeket a **szervezet felügyelete**&gt;**elektronikus jelentés**&gt;**elektronikus jelentési feladatok archivált**. **Megjegyzés:** kiválasztható egy bizonylattípust a feladat archív Dynamics 365 műveletekhez, **szervezet felügyelete**&gt;**munkaterületek**&gt;**elektronikus jelentés**&gt;**elektronikus jelentési paraméterek**.

#### <a name="sharepoint"></a>SharePoint

A fájlt egy kijelölt SharePoint mappába is mentheti. Megadhatja az alapértelmezett SharePoint-kiszolgáló, **szervezet felügyelete**&gt;**Dokumentumkezelés**&gt;**Dokumentumkezelés paraméterei**, a **SharePoint** fülre. A SharePoint-mappa beállítása után kiválaszthatja azt a mappát, ahová az ER kimeneti menti-e a dokumentumtípus. 

[![A SharePoint-mappa kijelölése](./media/ger_sharepointfolderselection-1024x543.jpg)](./media/ger_sharepointfolderselection.jpg) 

#### <a name="azure-storage"></a>Azure Storage

Ha a dokumentumtípus helye **Archív könyvtár**, a fájl menthető az Azure Storage-en.

### <a name="file-destination"></a>Fájl célja

Ha **engedélyezett** a **Igen**, a Megnyitás vagy Mentés párbeszédpanel jelenik meg, ha a konfigurációs futása befejeződött.

### <a name="screen-destination"></a>A cél képernyő

Ha **engedélyezett** a **Igen**, a Kimenet előnézete jön létre. Bizonyos fájltípusok, például XML, TXT vagy PDF, közvetlenül a böngésző ablakában tekintheti meg. Más fájltípusok, Microsoft Excel vagy a Word, a Microsoft Office Online szolgáltatás segítségével.

### <a name="power-bi-destination"></a>Kiemelt BI cél

Set **engedélyezett** a **Igen** ER konfigurációtól segítségével gondoskodik az adatok átvitelét a 365 Dynamics példány műveletek a Microsoft kiemelt BI szolgáltatások. Ebből a célból be kell állítani egy Microsoft SharePoint Server-példányt az átvitt fájlok tárolják. További tudnivalókért lásd: [egy elektronikus jelentési konfiguráció használata Dynamics 365 adatokkal kiemelt BI nyújt műveletek](general-electronic-reporting-report-configuration-get-data-powerbi.md). **Ötlet:** Az alapértelmezett viselkedés (vagyis a konfiguráció párbeszédpanelének) felülbírálásához létrehozhat egy célhivatkozást és fájlcélt a fő eredménykomponens részére, majd kikapcsolhatja az összes célt.

## <a name="security-considerations"></a>Biztonsági megfontolások
Az ER célokhoz kétféle jog és kötelezettség létezik. Egyféle lehetőségeit szabályozza, amely a jogi személy átfogó célok karbantartása (Ez azt jelenti, hogy szabályozza a hozzáférést a **célok jelentés elektronikus** lap). A másik típus szabályozza az alkalmazás felhasználóját abban, hogy a futtatás során felülírja az ER-fejlesztők vagy ER-funkciótanácsadók által konfigurált célbeállításokat.

| Szerepkör (AOT-név)                     | Szerepkör neve                                  | Feladat (AOT-név)                     | Feladat neve                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Elektronikus jelentések fejlesztője             | ERFormatDestinationConfigure        | Elektronikus jelentéskészítési formátum céljának konfigurálása                |
| ERFunctionalConsultant              | Elektronikus jelentések funkcióival foglalkozó konzulens | ERFormatDestinationConfigure        | Elektronikus jelentéskészítési formátum céljának konfigurálása                |
| PaymAccountsPayablePaymentsClerk    | Kötelezettségkifizetési adminisztrátor            | ERFormatDestinationRuntimeConfigure | Elektronikus jelentéskészítési formátum céljának konfigurálása futásidőben |
| PaymAccountsReceivablePaymentsClerk | Kinnlevőség-kifizetési adminisztrátor         | ERFormatDestinationRuntimeConfigure | Elektronikus jelentéskészítési formátum céljának konfigurálása futásidőben |

**Megjegyzés:** A fenti kötelezettségek teljesítésekor két jogosultság használatos. Ezeknek a jogosultságoknak a neve megegyezik a hozzájuk tartozó feladatokkal: **ERFormatDestinationConfigure** és **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Gyakori kérdések
### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>Rendelkezem importált elektronikus konfigurációkkal, és látom azokat az Elektronikus jelentési konfigurációk oldalon. De miért nem látom azokat az elektronikus jelentési célok oldalon?

Győződjön meg arról, hogy véletlenül **új**, és válassza ki azt a **referencia** mezőben. Az **Elektronikus jelentési célok** oldalon csak azokat a konfigurációkat láthatja, melyekhez a célok konfigurálva vannak.

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>Van-e bármilyen módon meghatározásához használt Azure Blob-tároló és kiválasztását Azure tároló fiók?

Szám Az alapértelmezett Azure Blob-tároló definiált és használt a dokumentumkezelő rendszer esetében használatos.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Mi az a célja a fájl rendeltetési cél beállításai? Mire jó ez a beállítás?

A **Fájl** cél a párbeszédpanel irányítására szolgál. Ha engedélyezi a cél, vagy ha nincs cél konfiguráció van meghatározva, lásd: nyílt, vagy Mentés párbeszédpanel kimeneti fájl létrehozása után.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Létezik példa egy olyan receptúrára, ami egy szállítói fiókra utaló receptúrát tartalmaz, ahová emaileket küldhetek?

A formula ER-konfigurációspecifikus. Például, ha az ISO 20022 Jóváírás Átutalása konfigurációt használja, használhatja az **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** vagy **model.Payments.Creditor.Identification.SourceID** karakterláncokat egy társított szállítói fiók eléréséhez.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Valamelyik formátumkonfigurációmban több fájl is van, melyek egy mappába lettek csoportosítva (Például Mappa1 tartalma Fájl1, Fájl2, és Fájl3). Hogyan állíthatom be úgy a célokat, hogy a Mappa1.zip ne legyen létrehozva, Fájl1 legyen emailben elküldve, Fájl2 legyen a SharePoint-ra küldve, és Fájl3-mat egyből a konfiguráció lefutása után megnyithassam?

Az előfeltétel, hogy a formátum az ER-konfigurációk rendelkezésre kell állnia. Ha megvan a formátum, nyissa meg az **Elektronikus jelentés célja** oldalt, majd hozzon létre új hivatkozást erre a konfigurációra. Ekkor négy fájlcélra lesz szüksége, egyre mindegyik eredménykomponenshez. Hozza létre az első fájlcélt, nevezze el pl. úgy, hogy **Mappa**, majd válassza ki a fájlnevet, ami a konfigurációban a mappát reprezentálja. Kattintson a **Beállítások** gombra, és győződjön meg róla, hogy minden cél ki van kapcsolva. Ehhez a fájlcélhoz nem lesz mappa létrehozva. A fájlok és szülőmappák közötti hierarchikus viszonyok miatt alapértelmezés szerint a fájlok ugyanúgy fognak viselkedni. Más szóval nem lesznek sehová elküldve. Ezen alapértelmezett viselkedés felülbírálásához három másik fájlcélt kell létrehoznia, egyet mindegyik fájlhoz. Az egyes célbeállításoknál be kell kapcsolnia azt a célt, ahová a fájlt küldeni kívánja.

# <a name="see-also"></a>Lásd még

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)


