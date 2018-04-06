---
title: "Szállítói számla automatizálása"
description: "Ez a témakör azokat a funkciókat mutatja be, amelyek a szállítói számlák végponttól végpontig történő automatizálására érhetők el, még a mellékleteket tartalmazó számlák esetében is."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendEditInvoiceHeaderStagingListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 551f3d5fc52fac725fcc9fedc37dc1c85fac5a26
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---
# <a name="vendor-invoice-automation"></a>Szállítói számla automatizálása

[!include[banner](../includes/banner.md)]

Ez a témakör azokat a funkciókat mutatja be, amelyek a szállítói számlák végponttól végpontig történő automatizálására érhetők el, még a mellékleteket tartalmazó számlák esetében is.

Azok a szervezetek amelyek egyszerűsítik a Kötelezettségek folyamatot, gyakran a számlafeldolgozás folyamatát tartják az egyik olyan kiemelt területnek, amelynek hatékonyabbnak kellene lennie. Sok esetben ezek a szervezetek a papíralapú számlák feldolgozását külső optikai karakterfelismerési (OCR) szolgáltatónak adják át. Ezután géppel olvasható számlázi metaadatokat kapnak az egyes számlák beolvasott képével. Az automatizálás elősegítése érdekében egy ún. „utolsó mérföld”megoldást építenek ki, amely lehetővé teszi az ilyen műtermékek felhasználását a számlázási rendszerben. A Microsoft Dynamics 365 for Finance and Operations most lehetővé teszi az „utolsó mérföld” azonnali automatizálását egy számlaautomatizálási megoldás révén.

## <a name="solution-context"></a>Megoldási környezet

A számlaautomatizálás lehetővé tesz egy szabványos felületet, amely elfogadja a számlafejléc és a számlasorok, illetve a számlára vonatkozó mellékletek számlametaadatait. Bármilyen olyan külső rendszer, amely képes létrehozni az ezzel a felülettel kompatibilis műtermékeket, képes les arra, hogy információkat küldjön a Finance and Operations rendszerbe a számlák és mellékletek automatikus feldolgozásához.

Az alábbi illusztráció olyan mintaintegrációs forgatókönyvet mutat be, amelyben a Contoso egy OCR-szolgáltatóval társult a beszállítói számlák feldolgozása tekintetében. A Contoso szállítói a szolgáltatónak e-mailben küldik el a számlákat. Az OCR-feldolgozással a szolgáltató számlametaadatokat (fejlécek és/vagy sorok) és a számla egy beolvasott képét hozza létre. Egy integrációs réteg átalakítja ezeket a műtermékeket úgy, hogy a Finance and Operations rendszer felhasználhassa őket.

![Mintaintegrációs forgatókönyv](media/vendor_invoice_automation_01.png)

Az előző forgatókönyv számos változata lehetséges, ha számlaintegrációra van szükség. Az adatok áttelepítése egy másik olyan eset, ahol ez a felület használható számlák és melléklet létrehozásához a Finance and Operations rendszerben.

### <a name="solution-components"></a>Megoldások összetevői

A megoldás helyigénye a következő összetevőkből áll:

+ A számlafejléc, a számlasorok és a számlamellékletek adatentitásai
+ A számlák kivételes feldolgozása
+ Mellékletek párhuzamos megjelenítése a számlákon

A témakör többi része ezen megoldási összetevők részletes leírását tartalmazza.

## <a name="data-entities"></a>Adatentitások

Az adatcsomag a Finance and Operations rendszerbe kötelezően elküldendő munkaegység, hogy a számlafejlécek, a számlasorok és a számmellékletek létrehozása lehetségessé váljon. A következő adatentitások használatosak az adatcsomagot alkotó műtermékekhez:

+ Szállítói számla fejléce
+ Szállítói számlasor
+ Szállítói számla dokumentumokmelléklete

A szállítói számla dokumentummelléklet a funkció részeként bevezetett új adatentitás. A Szállítói számla fejlécének entitását úgy módosította a rendszer, hogy az támogassa a mellékleteket. A Szállítói számla sorentitást nem módosították ehhez a funkcióhoz.

Ez a témakör nem nyújt részletes meghatározást az adatcsomagról. Nem mutatja be az adatcsomagok létrehozását sem. Ezt az információt itt találja: [Adatentitások és -csomagok keretrendszere](../../dev-itpro/data-entities/data-entities-data-packages.md).

A számlákat és mellékleteket tartalmazó tesztadatok gyors létrehozásához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Finance and Operations példányába.
1. Ugorjon a következőre: **Kötelezettségek** > **Számlák** > **Nyitott szállítói számlák**.
1. Hozzon létre sorokat és mellékleteket tartalmazó számlákat.

    > [!NOTE]
    > A mellékleteknek fejlécmellékleteknek kell lenniük. A Szállítói számla dokumentummelléklet-entitás jelenleg nem támogatja a sormellékleteket.

1. Nyissa meg az **Adatkezelés** munkaterületet.
1. Hozzon létre egy exportálási feladatot, amely tartalmazza a Szállítói számla fejlécet, a Szállítói számlasort és a Szállítói számla dokumentummelléklet-entitásokat.
1. Exportálja az adatokat.
1. Töltse le az exportált adatokat csomagként. A csomag segítségével most célpéldányokba importálhatja az adatokat tesztelési célból.

### <a name="determining-the-legal-entity-for-an-invoice"></a>A jogi személy meghatározása egy számlához

Az adatcsomagok segítségével importált számlák kétféle módon társíthatók ahhoz a jogi személyhez, amelyhez tartoznak:

+ A számlát feldolgozó importálási feladat ugyanabba a vállalatba importálja a számlát, amelyben a feladat ütemezése történt az **Adatkezelés** munkaterületen. Más szóval a feladathoz tartozó vállalat határozza meg, hogy a számla melyik vállalathoz tartozik.
+ Amikor a számlákat tartalmazó adatcsomagot a hívó fél a Finance and Operations rendszerbe küldi (vagyis a Finance and Operations rendszeren kívül futó integrációs alkalmazásba), explicit módon lehet feltüntetni a Vállalatazonosítót a HTTP-kérelmen. Ebben az esetben a rendszer felülírja azt a vállalati környezetet, amelyben a Finance and Operations feldolgozási feladata fut, és a számlákat a rendszer a vállalatba a HTTP-kérelmen keresztül importálja.

> [!NOTE]
> Ez a viselkedés szabványos adatkezelési viselkedés. Ezt a számlák összefüggésében csak a teljesség kedvéért ismertetjük itt.

## <a name="exception-processing"></a>Kivétel feldolgozása

Olyan esetekben, amikor szállítói számlák integráción keresztül kerülnek a Finance and Operations rendszerbe, kell lennie egy egyszerű módnak arra, hogy a Kötelezettségek csapat egyik tagja feldolgozhassa a kivételeket és a hibás számlákat, valamint hogy függőben lévő számlákat hozzon létre a hibás számlákból. A szállítói számlák kivétellel történő feldolgozása kivétel most már a Finance and Operations része.

### <a name="exceptions-list-page"></a>Kivételek listájának oldala

A számlázási kivételeket tartalmazó új listaoldal itt érhető el: **Kötelezettségek** > **Számlák** > **Importálási hibák** > **Szállítói számlák, amelyeknek sikertelen volt az importálása**. Ez a lap a Szállítói számla fejlécének adatentitásában szereplő előkészítési tábla szállítói számla fejlécrekordjait jeleníti meg. Vegye figyelembe, hogy ugyanezeket a rekordokat tekintheti meg az **Adatkezelés** munkaterületen is, ahol elvégezheti ugyanazokat a műveleteket, amelyek a kivételkezelési funkcióban szerepelnek. Azonban a kivételkezelési funkció által nyújtott felhasználói felület a funkcionális felhasználókra van optimalizálva.

![Kivételek listájának oldala](media/vendor_invoice_automation_02.png)

Ez a listaoldal a következő mezőket tartalmazza, amelyek a csatornán keresztül érkeznek:

+ **Vállalat** – Az a vállalat, amelyhez a számla tartozik
+ **Hibaüzenet** – Az adatkezelési keretrendszer hibaüzenetének magyarázata arra, hogy miért nem lehet létrehozni a számlát.
+ **Szám** – A számlaszám
+ **Számlafogadó**
+ **Név** – A szállító neve
+ **Szállítói számla**
+ **Beszerzési rendelés** – A számlához tartozó beszerzési rendelés száma
+ **Feladási dátum**
+ **Számla dátuma**
+ **Számla leírása**
+ **Pénznem**
+ **Eseménynapló**
+ **Hivatkozási sor** – A külső rendszerből származó azonosító

    > [!NOTE]
    > A sorhivatkozás nem a számla azonosítója.

Ezen listaoldalon van még egy betekintő ablaktábla is, amely az alábbi módon használható:

+ Teljes hibaüzenet megtekintése, hogy ne kelljen kibontania a **Hibaüzenet** oszlopot a rácson.
+ A számla mellékletlistájának megtekintése, amennyiben a számla mellékletekkel érkezett.

A listaolda a következő műveleteket támogatja:

+ **Szerkesztés** – A kivételrekord megnyitása szerkesztési módban a problémák elhárítása érdekében.
+ **Lehetőségek** – A listaoldalakon elérhető szokásos lehetőségek. Használhatja a **Hozzáadás a munkaterülethez** lehetőséget a kivételek listaoldal munkaterülethez listaként vagy csempeként történő rögzítéséhez.

### <a name="exception-details-page"></a>Kivételadatok lap

Amikor elindítja a szerkesztési módot, megjelenik a problémás számla kivételadatokat tartalmazó lapja. Amennyiben mellékletek vannak, a számla és az alapértelmezett melléklet párhuzamosan jelennek meg a kivételadatokat tartalmazó lapon.

![Kivételadatok lap](media/vendor_invoice_automation_03.png)

Az előző példában nem voltak sorok a beérkezett szállítói számla fejlécében. Ebből következően a sorokra vonatkozó szakasz üres.

A kivételadatokat tartalmazó lap a következő műveletet támogatja:

+ **Függőben lévő számla létrehozása** – Miután a kivételfeldolgozás során kijavította a számlán a problémákat, erre a gombra kattintva függőben lévő számlát hozhat létre. A függőben lévő számlák létrehozása a háttérben (aszinkron műveletként) megy végbe.

### <a name="shared-service-vs-organization-based-exception-processing"></a>Megosztott szolgáltatások és szervezetalapú kivételfeldolgozás

A kivételek listaoldal támogatja azokat a szabványos biztonsági beállításokat, amelyeket az **Adatkezelés** munkaterület támogat az előkészítési rekordok feldolgozására. A számlaimportálás feladat biztosítása a következő módokon történik:

+ Felhasználói szerepkör szerint
+ Felhasználónként
+ Jogi személy szerint

![Felhasználói szerepkör és jogi személy által biztosított importálási feladat](media/vendor_invoice_automation_04.png)

Ha a számlaimportálási feladathoz a biztonság van beállítva, a kivételek listaoldal tiszteletben tartja ezeket a beállításokat. A felhasználók csak azokat a kivételrekordokat látják, amelyeket ez a beállítás lehetővé tesz a számukra.

Például a Contoso úgy döntött, hogy jogi személy szerint dolgozza fel a számlázási kivételeket. Ezért a biztonság a számlaimportálásai feladatban úgy van beállítva, hogy az A jogi személy felhasználója csak a számlázási kivételeket láthatja az A jogi személyben, míg a B jogi személyben lévő felhasználó csak a számlázási kivételeket látja a B jogi személyben. Ez a beállítás lehetővé teszi a feladatkörök szétválasztását a számlázási kivételek kezelése során.

A Contoso dönthetett úgy is, hogy nem hoz létre biztonsági beállításokat, így ugyanazon felhasználók minden jogi személyhez tartozó számlázási kivételt feldolgozhatnak. Ez a beállítás egy megosztott szolgáltatási forgatókönyvet tesz lehetővé a számlázási kivételek kezelésére.

## <a name="side-by-side-attachment-viewer"></a>Mellékletek párhuzamos megjelenítése

A szállítói számlákhoz tartozó mellékletek könnyű megtekintéséhez a számlázási folyamatban használt lapok mostantól tartalmaznak mellékletmegjelenítőt:

+ **Kivételkezelés**
+ **Függőben lévő szállítói számlák** lap (megtalálható a számlaellenőrzési folyamatban is)
+ **Számlanapló** lekérdezési lap (a feladott számlákhoz)

Itt látható a mellékletmegjelenítő által kínált fő funkció:

+ A Dokumentumkezelés által támogatott össze melléklettípus megtekintése (fájlok, képek, URL-címek és megjegyzések).
+ Többoldalas TIFF-fájlok megtekintése.
+ Végezze el a következő műveleteket a képfájlokon:
  + Jelölje ki a kép részeit.
  + Blokkolja a kép részeit.
  + Adjon hozzá jegyzetet a képhez.
  + Nagyítás és kicsinyítés a képen.
  + Pásztázzon a képen.
  + Vonja vissza vagy reprodukálja a műveleteket.
  + Igazítsa méretre a képet.

> [!NOTE]
> Ezek a műveletek csak képfájlok (JPEG, TIFF, PNG stb.) esetében érhetők el. Az ilyen műveletekkel végzett képek módosításait a rendszer a képfájlba menti. A mellékletmegjelenítő jelenleg nem tartalmaz verziókövetési vagy auditáló lehetőségeket.

### <a name="default-attachment"></a>Alapértelmezett melléklet

Ha egy szállítói számla egynél több melléklettel rendelkezik, az egyik dokumentumot beállíthatja alapértelmezett mellékletként a **Mellékletek** lapon. Az **Alapértelmezett melléklet** lehetőség új beállítás, amelyet a funkció részeként adtunk hozzá a rendszerhez. Ez a beállítás is ki van téve a Szállítói számla dokumentummelléklet-entitásnak. Emiatt az alapértelmezett melléklet integrációkon keresztül állítható be.

Csak egy dokumentum állítható be alapértelmezett mellékletként. Ha egy dokumentumot alapértelmezett mellékletként állított be, ez automatikusan megjelenik a mellékletmegjelenítőben a számla megnyitásakor. Ha nem állít be egyetlen dokumentumot sem alapértelmezett mellékletként, a mellékletmegjelenítő nem jelenít meg automatikusan mellékleteket a számla megnyitásakor.

### <a name="showhide-invoice-attachments"></a>Számlamellékletek megjelenítése/elrejtése

A **Kivétel feldolgozása**, **Függőben lévő számla** és **Számlanapló** lekérdezési lapok lehetővé teszik a mellékletmegjelenítő megjelenítését vagy elrejtését.

### <a name="security"></a>Biztonság

A mellékletmegjelenítő következő műveletei szerepkör-alapú biztonságon keresztül vannak szabályozva:

+ Kiemelés
+ Zárolás
+ Jegyzet

### <a name="pending-vendor-invoices-page"></a>Függőben levő szállítói számlák lap

A következő jogosultságok írásvédett vagy olvasási/írási hozzáférést biztosítanak a mellékletmegjelenítőnek a kiemelési, zárolási és jegyzet műveletekhez:

+ **Szállítói számla képének karbantartása** – Ez a jogosultság olvasási/írási hozzáférést biztosít.
+ **Szállítói számla képének megtekintése** – Ez a jogosultság írásvédett hozzáférést biztosít.

A következő feladatok csak írásvédett hozzáférést vagy olvasási/írási hozzáférést biztosítanak a mellékletek megtekintéséhez a következő műveletekhez:

+ **Szállítói számlák karbantartása** – A Szállítói számla képének karbantartása jogosultság hozzá van rendelve ehhez a feladathoz.
+ **A szállítói számlák állapotának lekérdezése** – A szállítói számlák állapotának lekérdezése jogosultság hozzá van rendelve ehhez a feladathoz.

A következő szerepkörök írásvédett hozzáférést vagy olvasási/írási hozzáférést biztosítanak a mellékletek megtekintéséhez a következő műveletekhez:

+ **Kötelezettségkezelő adminisztrátor** és **Kötelezettségkezelő vezető** – A Szállítói számlák karbantartása feladat hozzá van rendelve ezen szerepkörökhöz.
+ **Kötelezettségkezelő adminisztrátor**, **Kötelezettségkezelő vezető**, **Kötelezettségek központosított fizetési adminisztrátora** és **Kötelezettségkifizetési adminisztrátor** – A szállítói számlák állapotának lekérdezése feladat hozzá van rendelve ezen szerepkörökhöz.

### <a name="invoice-exception-details-page"></a>Kivételszámla-adatok lap

A következő jogosultságok írásvédett vagy olvasási/írási hozzáférést biztosítanak a mellékletmegjelenítőnek a kiemelési, zárolási és jegyzet műveletekhez.

> [!NOTE]
> Az ebben a szakaszban ismertetett szerepkörök írásvédett jogosultságokat biztosítanak a mellékletmegjelenítőben levő számlaképekhez. Ha egy szerepkörnek írási hozzáféréssel is kell rendelkeznie a képek tekintetében, írási jogosultságot adhat annak a szerepkörnek az itt bemutatott jogosultsági és feladat műveletek segítségével.

+ **Szállítói számla fejléce – entitáskép karbantartása** – Ez a jogosultság olvasási/írási hozzáférést biztosít a mellékletmegjelenítőben levő számlaképekhez.
+ **Szállítói számla fejléce – entitáskép megtekintése** – Ez a jogosultság írásvédett hozzáférést biztosít a mellékletmegjelenítőben levő számlaképhez.

A következő feladatok írásvédett hozzáférést biztosítanak a mellékletek megtekintéséhez a következő műveletekhez:

+ **Szállítói számlák karbantartása** – A Szállítói számla fejléce – entitáskép karbantartása jogosultság hozzá van rendelve ehhez a feladathoz.

A következő szerepkörök írásvédett hozzáférést biztosítanak a mellékletek megtekintéséhez a következő műveletekhez:

+ **Kötelezettségkezelő adminisztrátor** és **Kötelezettségkezelő vezető** – A Szállítói számlák karbantartása feladat hozzá van rendelve ezen szerepkörökhöz.

Alapértelmezés szerint ha felhasználói szerepkör szerkesztési jogokat biztosít minden lapon, a felhasználónak is szerkesztési jogai lesznek a mellékletmegjelenítőn a kiemelési, zárolási és jegyzet műveletek tekintetében. Azonban ha vannak olyan forgatókönyvek, ahol egy adott szerepkörnek szerkesztési jogosultsággal kell rendelkeznie a lapon de a mellékletmegjelenítőn nem, az előző listából származó megfelelő jogosultságok használhatók a felhasználási eset kielégítésére.

