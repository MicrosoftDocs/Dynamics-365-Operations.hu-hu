---
title: Perifériák csatlakozás a pénztárhoz (POS)
description: Ez a témakör ismerteti, hogyan csatlakoztasson perifériákat a kiskereskedelmi pénztárához.
author: BrianShook
ms.date: 03/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTerminalTable, RetailDevice
audience: Application User
ms.reviewer: josaw
ms.custom: 92383
ms.assetid: 83f31ea6-f0a2-4501-9d4d-a37b6eec2599
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: f1c53c7215d3a5a182f345d5e040274ae06f9b12
ms.sourcegitcommit: 116898def829c0f78bda8a117242aa308793465d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/01/2022
ms.locfileid: "8370951"
---
# <a name="connect-peripherals-to-the-point-of-sale-pos"></a>Perifériák csatlakozás a pénztárhoz (POS)

[!include [banner](includes/banner.md)]

Ez a témakör ismerteti, hogyan csatlakoztasson perifériákat a kiskereskedelmi pénztárához.

> [!NOTE]
> Specifikus telepítési utasítások: [A Retail Hardware Station konfigurálása és telepítése](retail-hardware-station-configuration-installation.md) és [A Modern (MPOS) konfigurálása, telepítése és aktiválása](retail-modern-pos-device-activation.md).

## <a name="key-components"></a>Kulcsösszetevők

Számos összetevő használatos az üzlet és az üzleten belüli pénztárak (POS) vagy csatornák, valamint azon perifériák közötti kapcsolat meghatározására, amelyek ezen pénztárakat vagy csatornákat használják a tranzakciók feldolgozásához. Ez a szakasz ismerteti az egyes összetevőket, és használatukat az üzlet telepítésében.

### <a name="pos-registers"></a>POS-pénztárgépek

Navigáció: Kattintson a **Kiskereskedelem és kereskedelem** &gt; **Csatorna beállítás** &gt; **Pénztár beállítás** &gt; **Pénztárak** gombra.

A pénztár (POS) pénztárgép egy entitás, amely egy adott pénztárpéldány jellemzőinek meghatározására szolgál. E jellemzők közé tartozik a pénztárgépen használt kiskereskedelmi perifériák hardverprofilja vagy beállítása, az üzlet, amelyhez a pénztárgép hozzá van rendelve, és a vizuális élménye annak a felhasználónak, aki bejelentkezik a pénztárgépre.

### <a name="devices"></a>Eszközök

Navigáció: Kattintson a **Kiskereskedelem és kereskedelem** &gt; **Csatorna beállítás** &gt; **Pénztár beállítás** &gt; **Eszközök** gombra.

Egy eszköz egy olyan entitás, amely egy pénztárhoz rendelt eszköz fizikai reprezentációja. Egy eszköz létrehozásakor a rendszer hozzárendeli azt egy pénztárhoz. Az eszköz-entitás nyomon követi a pénztárgép aktiválásáról, a használt klienstípusról, és az eszközre telepített alkalmazáscsomagról szóló információt. Az eszközök típusa lehet: **Retail modern POS** (MPOS) vagy **Retail Felhő-POS** (Felhő POS).

#### <a name="mpos"></a>MPOS

Az MPOS egy pénztárkliens-applikáció, amely Windows 8.1-re, vagy későbbi, PC alapú operációs rendszerekre telepíthető. Ha egy eszközhöz a **Retail modern POS** alkalmazástípust rendelték, akkor meghatározhatja a letöltési csomagot az adott eszközhöz. A letöltési csomagot testre szabhatja, hogy a telepítési csomag különböző verzióit tartalmazza. A különböző csomagok telepítésének lehetősége rugalmasságot biztosít olyan esetekben, amikor a különböző pénztárak különböző integrációkat igényelnek. Az MPOS telepítése a beépített hardverállomás telepítésével együtt történik.

#### <a name="cloud-pos"></a>Felhő POS

A Felhő POS egy böngésző alapú POS. Mivel a böngészőben fut, a Felhő POS nem igényel Windows 8.1-et vagy későbbi, PC alapú operációs rendszert. Ha a **Retail Felhő-POS** alkalmazástípust rendelte hozzá egy adott eszközhöz a központban, akkor az eszközt használhatja a böngészőn keresztül, csomagok letöltése és telepítése nélkül. A Felhő POS egy hardverállomást igényel, hogy a billentyűzethez-ékelt vonalkód-olvasáson túl is képes legyen hardvert használni.

### <a name="hardware-profile"></a>Hardverprofil

Navigáció: Ugrás a Kiskereskedelmi és **Commerce \> csatorna beállítása \> POS-profilok \> hardverprofiljaihoz \>**.

A hardverprofil egy integrált vagy megosztott hardverállomáson keresztül azonosítja a POS-pénztárgéphez kapcsolódó hardvereket. A hardverprofil használatos még a fizetésfeldolgozó-paraméterek megadására, amelyek a fizetési szoftverfejlesztő készlettel (SDK) történő kommunikációra szolgálnak. A fizetési SDK a hardverállomás részeként van telepítve.

### <a name="hardware-station"></a>Hardverállomás

Navigáció: Menjen a **Retail and Commerce \> Channels \> Stores minden \>** üzletbe, válasszon ki egy üzletet, majd **válassza ki a Hardverekkel kapcsolatos gyorscímet**.

A hardverállomás az üzleti logika azon eleme, amely a POS perifériákat hajtja meg. A hardverállomás telepítése automatikusan megtörténik az MPOS-sal együtt. Másik lehetőségként a hardverállomást telepítheti egyedülálló elemként, amely később hozzáférhető MPOS-sal, vagy Felhő POS-sal, webszolgáltatáson keresztül. A hardverállomást a csatorna szintjén kell meghatározni.

## <a name="scenarios"></a>Forgatókönyvek

### <a name="mpos-with-connected-peripheral-devices"></a>MOPS kapcsolt perifériás eszközökkel

[![Hagyományos, rögzített pénztár.](./media/traditional-300x279.png)](./media/traditional.png)

Ha csatlakoztatni szeretne egy MPOS-t egy pénztárhoz egy hagyományos, rögzített pénztáras esetben, először navigáljon magához a pénztárhoz, majd rendeljen hozzá egy hardverprofilt. A pénztárakat megtalálja a **Kiskereskedelem és kereskedelem** &gt; **Csatorna beállítás** &gt; **POS beállítás** &gt; **Pénztárak** menüpont alatt. 

Miután hozzárendelte az új hardverprofilt, szinkronizálja a csatorna adatbázisában véghezvitt módosításokat a **Pénztárak** elosztási ütemezés használatával. Az elosztási ütemezéseket a **Kiskereskedelem és kereskedelem** &gt; **Kiskereskedelmi és kereskedelmi IT** &gt; **Elosztási ütemezés** menüpont alatt találja. 

Ezután állítson be egy külön hardverállomást a csatornához. Menjen a **Retail and Commerce \> Channels Minden \> üzletbe \>**, és válasszon ki egy üzletet. 

Ezután a Hardvereszköz **- és hardvergyorsítás** gyors oldalon **válassza** a Hozzáadás gombra egy hardverállomás hozzáadásához. Válassza **ki a** hardverállomás típusaként a Dedicated típust, majd adjon meg egy leírást. A **Hardverprofil mező** üresen hagyható, mert az ebben az esetben használt hardverprofil magát a POS-pénztárgépet használja. Ezután szinkronizálja a módosításokat a csatornával a csatorna konfigurációs **elosztási ütemezésének** használatával. Az elosztási ütemezéseket **a Retail and Commerce \> Retail and Commerce IT \> Distribution ütemezésében találja meg**. 

Végül az MPOS-ban **a** Hardverállomás kiválasztása művelettel válassza ki a leíráshoz korábban megadott értéknek megfelelő hardverállomást, **és állítsa a hardverállomást Aktív értékre**. 

> [!NOTE]
> - Bizonyos hardverprofil módosítások, például a pénztárfiókban véghezvitt módosítások egy új műszak megnyitását igénylik, a módosítások csatornához történő szinkronizálása után.
> - A Felhő POS csak az egyedülálló hardverállomás használatával kommunikálhat a perifériákkal.

### <a name="mpos-or-cloud-pos-with-a-stand-alone-hardware-station"></a>MPOS vagy Felhő POS egyedülálló hardverállomással

[![Megosztott hardverperifériák.](./media/shared-300x254.png)](./media/shared.png)

Ebben az esetben egy önálló hardverállomás van megosztva az MPOS és a Felhő POS ügyfelek között. Ehhez az esethez létre kell hozni egy megosztott hardverállomást, és meg kell adni a hardverállomás által használt letöltési csomagot, portot és hardverprofilt. Új hardverállomást **úgy** határozhat meg, hogy az adott csatornában (**a Retail és Commerce \> Channels \> Stores Összes \>** üzletében) kiválasztja a **Hardveres gyorstárat, és hozzáad egy új, Megosztott típusú** hardverállomást. 

Ezután adjon meg egy leírást, ami segít a pénztárosnak a hardverállomás azonosításában. Az **Állomás neve** mezőbe írja be az állomás-számítógép URL címét a következő formátumban: `https://<MachineName:Port>/HardwareStation`. (Csere **&lt; Gépnév:Port&gt;** a hardverállomás aktuális gépnevével.) Önálló hardverállomás esetén meg kell adnia az elektronikus átutalási (EFT) terminál azonosítóját is. Ez az érték azonosítja a hardverállomáshoz csatlakoztatott EFT terminált, amikor a fizetési csatlakoztató kommunikál a fizetési szolgáltatóval. 

Ezután a hardverállomást fogadó gépről menjen a Központ csatornájára, és válassza ki a hardverállomást. Ezután válassza a **Letöltés** lehetőséget a hardverállomás telepítője letöltéséhez, majd telepítse a hardverállomást. A hardverállomás telepítésével kapcsolatos további tudnivalókat [lásd A Retail hardverállomás konfigurálása és telepítése.](retail-hardware-station-configuration-installation.md) 

Ezután az MPOS-ban vagy Felhő POS-ban használja a **Hardverállomás kiválasztása** műveletet, hogy kiválassza az előbb telepített hardverállomást. Válassza ki a **Párosítás** műveletet, hogy létrehozzon egy biztonságos kapcsolatot a pénztár és a hardverállomás között. Ezt a lépést mindig el kell végezni, amikor egy pénztárat csatlakoztat egy hardverállomáshoz. 

Miután párosította a hardverállomást, ugyanezen művelet használatos a hardverállomás aktiválásra, a használatakor. Erre az esetre a hardverprofilt a pénztárgép helyett a megosztott hardverállomáshoz kell hozzárendelni. Ha valamilyen okból nincs hardverprofil hozzárendelve egy hardverállomáshoz, akkor a rendszer a pénztárgéphez rendelt hardverprofilt használja.

## <a name="client-maintenance"></a>Kliens karbantartás

### <a name="registers"></a>Pénztárgépek

A POS-pénztárgépeket elsősorban maguknál a pénztárgépeknél, valamint a pénztárgépekhez hozzárendelt profilok által kezelik. Az adott pénztárgépre jellemző tulajdonságokat a pénztár szintjén kezeli a rendszer. Ezek közé a tulajdonságok közé tartozik az üzlet, ahol a pénztárat használják, a pénztár száma, a leírás, és a pénztárra vonatkozó EFT terminálazonosító.

### <a name="pos-profiles"></a>POS-profilok

A pénztárprofilokat megtalálja a **Kiskereskedelem és kereskedelem** &gt; **Csatorna beállítás** &gt; **POS beállítás** &gt; **Pénztárprofilok** menüpont alatt. Célszerű profilokkal kezelni a pénztár különböző funkcióit, mivel a profilokat több pénztár között megoszthatja. A profilok társíthatóak egy egyedi pénztárhoz, vagy ha a profil az egész üzletben hatékony, akkor az üzlethez. Az következő bekezdések ismertetik a pénztár-profilokat és használatukat.

#### <a name="offline-profile"></a>Offline profil

Az offline profil az üzlet szintjén van beállítva. Ez arra használatos, hogy megadja a pénztáron végrehajtott tranzakciók feltöltési beállításait akkor, amikor a pénztár nincs csatlakoztatva a csatorna adatbázisához.

#### <a name="functionality-profile"></a>Funkcióprofil

Az funkcionalitás profil az üzlet szintjén van beállítva. Ez használatos a pénztárral végrehajtható, teljes üzletre kiterjedő funkciók megadásához. A következő funkciók kezelhetőek a funkcionalitás profilon keresztül. Ezek a funkciók egy gyorslapon vannak elrendezve.

- **Általános** Gyorslap:

    - Nemzetközi Szabványügyi Szervezet (ISO).
    - Vevő létrehozása offline módban.
    - Nyugtaprofil Email.
    - Központi munkatársak bejelentkezésének hitelesítése.

- **Funkciók** Gyorslap:

    - A bejelentkezés és a kiegészített bejelentkezés kezelése.
    - A pénztár pénzügyekkel és pénznemekkel kapcsolatos vonatkozásai, úgy mint az árak beírása és hogy van-e szükség tizedesjegyekre a váltópénzeknél.
    - Időregisztráció engedélyezése a pénztárban.
    - Termékek és kifizetések megjelenítése a pénztárban és a nyugtákon.
    - Napvégi zárás kezelése.
    - Csatorna adatbázis tranzakciók visszatartási paraméterei.
    - Vevők keresése és létrehozása a pénztárban.
    - Engedmények számítása.

- **Összeg** Gyorslap:

    - Engedélyezett maximális és minimális árak.
    - Engedmények használata és kiszámítása.

- **Infókódok** Gyorslap:

    - Az infókódok pénztári kezelésének minden vonatkozása. Részletek: [Információs kódok és információs kódcsoportok](info-codes-retail.md).

- **Nyugta számozása** Gyorslap:

    - Nyugtaszámozási maszkok megadása, amelyek az üzletszám, terminálszám, konstansok szegmenseit tartalmazhatják, valamint azt, hogy az értékesítés, a visszatérítés, az értékesítési rendelések és az árajánlatok nyomtatása külön sorozatban vagy ugyanazon a sorozaton belül van-e.

#### <a name="receipt-profiles"></a>Nyugtaprofilok

A nyugtaprofilok a hardverprofil nyomtatóihoz vannak hozzárendelve. Arra használatosak, hogy egy adott nyomtatónál nyomtatott nyugtatípusokat adjunk meg. A profilok beállításokat tartalmaznak, amelyek meghatározzák a nyugta formátumát, valamint hogy a nyugta mindig ki legyen-e nyomtatva, vagy a pénztáros döntsön a nyomtatás szükségességéről. A különböző nyomtatók különböző nyugtaprofilokat használhatnak. Például, az 1-es nyomtató egy szabványos hőmérsékleti nyugtanyomtató, így kisebb nyugtaformátumai vannak. Azonban a 2-es nyomtató egy teljes méretű nyomtató, amelyet a több helyet igénylő vásárlói rendelés nyugták nyomtatására használják. A további tudnivalókat lásd: Nyugtaprofil [konfigurálása](configure-emailed-receipt-formats.md#configure-a-receipt-profile).

#### <a name="hardware-profiles"></a>Hardverprofilok

A hardverprofilok magyarázata a témakör korábbi részében, az ügyfélbeállítás egyik összetevőjeként ismertető. A hardverprofilok közvetlenül a POS-pénztárgéphez vagy egy megosztott hardverállomáshoz vannak hozzárendelve, és az adott POS-pénztárgép vagy hardverállomás által használt eszközök típusának megadására használhatók. A hardverprofilokkal adhatóak meg továbbá az EFT beállítások, amelyek a fizetési SDK-val való kommunikációt végzik.

#### <a name="visual-profiles"></a>Vizuális profilok

A vizuális profilok egy adott pénztárgép témacsoportjainak megadására használhatók, és a pénztárgép szintjén vannak hozzárendelve. A profilok tartalmazzák az alkalmazott alkalmazástípus beállításait (MPOS vagy Cloud POS), a kiemelőszínt és a téma, a betűsémát, a bejelentkezési oldal hátterét és a POS hátterét. A további tudnivalókat lásd [a Pénztár vizuális profilok létrehozása.](tasks/create-pos-visual-profile-2016-02.md) 

### <a name="custom-fields"></a>Egyéni mezők

Létrehozhat egyéni mezőket, hogy olyan mezőket adjon hozzá a pénztárhoz, amelyek gyárilag nem szerepelnek benne. További információkért az egyéni mezők használatáról lásd: [Munka az egyéni mezőkkel blogbejegyzés](https://blogs.msdn.microsoft.com/axsupport/2012/08/06/ax-for-retail-2012-working-with-custom-fields/).

### <a name="language-text"></a>Nyelvfüggő szöveg

Felülírhatja a pénztárgép alapértelmezett karakterláncait a nyelvi szövegbejegyzés használatával. A pénztárgép karakterláncának felülírásához adjon hozzá egy új nyelvi szövegsort. Ezután adjon meg egy azonosítót. Az alapértelmezett karakterlánc felülírása megtörténik, és a pénztáron az alapértelmezett karakterlánc helyett a megadott szöveg fog megjelenni.

### <a name="channel-reports-configuration"></a>Csatornajelentések konfigurálása

Beállíthatja a kiskereskedelmi csatornán elérhető jelentéseket a **Csatorna jelentéseinek konfigurációja** oldalon. Új jelentéseket hozhat létre, ha megadja a jelentés XML-definícióját, és hozzárendeli a jelentést a pénztár egy adott engedélycsoportjához.

### <a name="devices"></a>Eszközök

Ez a cikk korábban már bemutatta az eszközöket. Egy adott pénztár aktivációját kezelheti velük. Továbbá az eszközök használatával adhatja meg a pénztárnál használt alkalmazást, és az MPOS kliens telepítését végző telepítési csomagot. Itt szerepelnek az eszközök aktivációs szakaszai:

- **Függőben lévő** – az eszköz aktiválásra készen áll.
- **Aktív** – az eszközt aktiválták.
- **Inaktív** – az eszköz ki lett kapcsolva, a központban vagy a pénztáron keresztül.
- **Tiltott** – Az eszköz le van tiltva.

Az aktiválással kapcsolatos további információk tartalmazzák a dolgozót, aki megváltoztatta az eszköz aktivációs állapotát, egy időbélyeget az aktivációról, és hogy érvényesítve lett-e az eszköz konfigurációja.

### <a name="client-data-synchronization"></a>Kliensadatok szinkronizálása

A pénztárkliensben az aktivációs állapotban bekövetkezett változásokon kívül minden változást szinkronizálni kell a csatorna adatbázisában, hogy érvénybe lépjenek. A módosítások szinkronizálásához a csatorna adatbázisában, navigáljon a **Kiskereskedelem és kereskedelem** &gt; **Kiskereskedelemi és kereskedelmi IT** &gt; **Elosztási ütemezés** menüpontra és futtassa a szükséges elosztási ütemezést. A kliensváltoztatásokhoz futtassa a **Pénztárak** és **Csatornakonfiguráció** elosztási ütemezéseket.

## <a name="additional-resources"></a>További erőforrások

[A Retail Hardware Station konfigurálása és telepítése](retail-hardware-station-configuration-installation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
