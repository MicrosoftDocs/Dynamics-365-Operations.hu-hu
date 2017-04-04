---
title: "Meghatározza és fenntartsa a csatorna ügyfelek, nyilvántartások és hardver állomások"
description: "Ez a wiki ismerteti, hogyan csatlakoztasson perifériákat a kiskereskedelmi pénztárához."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92383
ms.assetid: 83f31ea6-f0a2-4501-9d4d-a37b6eec2599
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: dee5745670ad86000795f2913f99f49c0f123a00
ms.lasthandoff: 03/31/2017


---

# <a name="define-and-maintain-channel-clients-registers-and-hardware-stations"></a>Meghatározza és fenntartsa a csatorna ügyfelek, nyilvántartások és hardver állomások

Ez a wiki ismerteti, hogyan csatlakoztasson perifériákat a kiskereskedelmi pénztárához.

**Megjegyzés:** Adott telepítési útmutatásért lásd: [Kiskereskedelmi hardverállomás konfigurációja és telepítése](retail-hardware-station-configuration-installation.md) és [Modern Retail POS önkiszolgáló letöltés/telepítés, és Modern POS és felhő POS eszköz aktiválása](retail-modern-pos-device-activation.md).

## <a name="key-components"></a>Kulcsösszetevők
Számos összetevő használatos az üzlet és az üzleten belüli pénztárak (POS) vagy csatornák, valamint azon kiskereskedelmi perifériák közötti kapcsolat meghatározására, amelyek ezen pénztárakat vagy csatornákat használják a tranzakciók feldolgozásához. Ez a szakasz ismerteti az egyes összetevőket, és használatukat a kiskereskedelmi üzlet telepítésében.

### <a name="pos-registers"></a>POS-pénztárgépek

Navigációs: Kattintson a **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**regisztrálja**. A POS-pénztárgép egy entitás, amely egy adott példánya a POS jellemzőinek meghatározására szolgál. E jellemzők közé a hardverprofil vagy kiskereskedelmi felhasználó jelentkezik be, amely regisztrálja a nyilvántartásban, valamint az üzlet, az oltalom alatt álló hozzárendelt és a vizuális élmény használt perifériák beállításait.

### <a name="devices"></a>Eszközök

Navigációs: Kattintson a **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**eszközök**. Egy eszköz egy olyan entitás, amely egy pénztárhoz rendelt eszköz fizikai reprezentációja. Egy eszköz létrehozásakor a rendszer hozzárendeli azt egy pénztárhoz. Az eszköz-entitás nyomon követi a pénztárgép aktiválásáról, a használt klienstípusról, és az eszközre telepített alkalmazáscsomagról szóló információt. Az eszközök típusa lehet: **Retail modern POS** (MPOS) vagy **Retail Felhő-POS** (Felhő POS).

#### <a name="mpos"></a>MPOS

Az MPOS egy pénztárkliens-applikáció, amely Windows 8.1-re, vagy későbbi, PC alapú operációs rendszerekre telepíthető. Ha egy eszközhöz a **Retail modern POS** alkalmazástípust rendelték, akkor meghatározhatja a letöltési csomagot az adott eszközhöz. A letöltési csomagot testre szabhatja, hogy a telepítési csomag különböző verzióit tartalmazza. A különböző csomagok telepítésének lehetősége rugalmasságot biztosít olyan esetekben, amikor a különböző pénztárak különböző integrációkat igényelnek. Az MPOS telepítése a beépített hardverállomás telepítésével együtt történik.

#### <a name="cloud-pos"></a>Felhő POS

POS felhő egy böngésző alapú POS. Mivel azt fut a böngészőben, felhő POS Windows 8.1 vagy újabb PC-alapú operációs rendszer nem igényel. Ha a **Retail Felhő-POS** alkalmazástípust rendelte hozzá egy adott eszközhöz az irodában, akkor az eszközt használhatja a böngészőn keresztül, csomagok letöltése és telepítése nélkül. A Felhő POS egy hardverállomást igényel, hogy a billentyűzethez-ékelt vonalkód-olvasáson túl is képes legyen hardvert használni.

### <a name="hardware-profile"></a>Hardverprofil

Navigációs: Kattintson a **kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**POS profilok**&gt;**hardverprofilok**. A hardverprofil azonosítja a pénztárgéphez vagy a hardverállomáshoz csatlakoztatott hardvert. A hardverprofil használatos még a fizetésfeldolgozó-paraméterek megadására, amelyek a fizetési szoftverfejlesztő készlettel (SDK) történő kommunikációra szolgálnak. (A fizetési SDK a hardverállomás részeként van telepítve.)

### <a name="hardware-station"></a>Hardverállomás

Navigálás: Kattintson a **kereskedelmi és kereskedelmi**&gt;**csatornák**&gt;**a kiskereskedelmi üzletek**&gt;**összes kiskereskedelmi üzletek**. Válasszon egy üzletet, majd kattintson a **Hardverállomások** gyorslapra. A hardverállomás az üzleti logika azon eleme, amely a POS perifériákat hajtja meg. A hardverállomás telepítése automatikusan megtörténik az MPOS-sal együtt. Másik lehetőségként a hardverállomást telepítheti egyedülálló elemként, amely később hozzáférhető MPOS-sal, vagy Felhő POS-sal, webszolgáltatáson keresztül. A hardverállomást a csatorna szintjén kell meghatározni.

### <a name="hardware-station-profile"></a>Hardverállomás profilja

Navigálás: Kattintson a **kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**POS profilok**&gt;**állomás hardverprofilok**. Mivel maga a hardverállomás a csatorna szintjén van meghatározva, tartalmaz példány-specifikus információkat, úgy mint a hardverállomás URL címe. A hardverállomás-profil olyan információkat tartalmaz, amelyek lehetnek statikusak, vagy megoszthatja őket több hardverállomás között. A statikus információk közé tartozik a használandó port, a hardverállomás csomagja és a hardverprofil. A statikus információk tartalmazzák még a telepített hardverállomás típusának leírását, úgy mint **Pénztár **vagy **Visszáru**, attól függően, hogy az adott hardverállomás milyen hardvereket igényel.

## <a name="scenarios"></a>Esetek
### <a name="mpos-with-connected-peripheral-devices"></a>MOPS kapcsolt perifériás eszközökkel

[![Rögzített értékesítési pont, hagyományos](./media/traditional-300x279.png)](./media/traditional.png) MPOS csatlakozni egy hagyományos, rögzített POS forgatókönyv POS-perifériák, először keresse meg magát a nyilvántartásban, és hardverprofil hozzárendelése. A POS-pénztárgépek címen található **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**regisztrálja**. Miután hozzárendelte az új hardverprofilt, szinkronizálja a csatorna adatbázisában véghezvitt módosításokat a „Pénztárak” elosztási ütemezés használatával. Megtalálhatja az elosztási ütemezések, **kereskedelmi és kereskedelmi**&gt;**a Retail IT**&gt;**elosztási ütemezés**. Ezután állítson be egy „helyi” hardverállomást a csatornán. Kattintson a **kereskedelmi és kereskedelmi**&gt;**csatornák**&gt;**a kiskereskedelmi üzletek**&gt;**minden kiskereskedelmi üzletek**, és válasszon egy üzletet. Ezután a **Hardverállomások** gyorslapon kattintson a **Hozzáadás** gombra egy hardverállomás hozzáadásához. Adjon meg egy leírást, adja meg a **localhost** mezőt az állomás nevének, majd szinkronizálja a csatornában véghezvitt módosításokat a „Csatornakonfiguráció” elosztási ütemezés használatával. Megtalálhatja az elosztási ütemezések, **kereskedelmi és kereskedelmi**&gt;**a Retail IT**&gt;**elosztási ütemezés**. Végül az MPOS-ban használja a **Hardverállomás kiválasztása** műveletet, hogy kijelölje a **localhost** hardverállomást. Állítsa a hardverállomást **Aktív** állapotúra. A használt hardverprofilnak magából a pénztárból kell származnia. Ebben az esetben nincs szükség a hardverállomás-profilra. **Megjegyzés:** Bizonyos hardverprofil módosítások, például a pénztárfiókban véghezvitt módosítások egy új műszak megnyitását igénylik, a módosítások csatornához történő szinkronizálása után. **Megjegyzés:** A Felhő POS csak az egyedülálló hardverállomás használatával kommunikálhat a kiskereskedelmi perifériákkal.

### <a name="mpos-or-cloud-pos-with-a-stand-alone-hardware-station"></a>MPOS vagy Felhő POS egyedülálló hardverállomással

\[felirat azonosítója = "melléklet\_340041" igazítása = "alignleft" szélesség "300" =\][![megosztott perifériák](./media/shared-300x254.png)](./media/shared.png) perifériák megosztott\[/felirat\] ebben a forgatókönyvben egy önálló hardver állomás MPOS és felhő POS ügyfelek által közösen. Ebben az esetben létre kell hoznia egy hardverállomás-profilt, hogy megadja a letöltési csomagot, a portot és a hardverállomás által használt hardverprofilt. A hardverprofil állomás található **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**POS profilok**&gt;**station hardverprofilok**. Az állomás Hardverprofil létrehozását követően keresse meg az adott kiskereskedelmi csatorna (**kereskedelmi és kereskedelmi**&gt;**csatornák**&gt;**kiskereskedelmi üzletek**&gt;**összes kiskereskedelmi üzletek**), és adjunk hozzá egy új hardver állomás. Rendelje hozzá ezt az új hardverállomást a korábban létrehozott hardverállomás-profilhoz. Ezután adjon meg egy leírást, ami segít a pénztárosnak a hardverállomás azonosításában. A a **állomás neve** mezőjébe írja be a fogadó számítógép URL-CÍMÉT a következő formátumban: **https://&lt;MachineName:Port&gt;/HardwareStation**. (Csere **&lt;MachineName:Port&gt;** a hardver állomás és a port, a hardverprofil állomás megadott tényleges gép neve.) Egy önálló hardver állomás is adjon meg az elektronikus átutalás (EFT) terminálazonosítót. Ez az érték azonosítja a hardverállomáshoz csatlakoztatott EFT terminált, amikor a fizetési csatlakoztató kommunikál a fizetési szolgáltatóval. Ezután a tényleges hardverállomás-számítógépből navigáljon a csatornára és válassza ki a hardverállomást. Majd kattintson a **Letöltés** gombra és telepítse a hardverállomást. Ezután az MPOS-ban vagy Felhő POS-ban használja a **Hardverállomás kiválasztása** műveletet, hogy kiválassza az előbb telepített hardverállomást. Válassza ki a **Párosítás** műveletet, hogy létrehozzon egy biztonságos kapcsolatot a pénztár és a hardverállomás között. Ezt a lépést mindig el kell végezni, amikor egy pénztárat csatlakoztat egy hardverállomáshoz. Miután párosította a hardverállomást, ugyanezen művelet használatos a hardverállomás aktiválásra, a használatakor. Ebben az esetben a hardverprofil magát a nyilvántartás helyett az állomás hardverprofil kell rendelhető. Ha valamilyen okból a hardver állomás nincs közvetlenül a kijelölt hardverprofil, majd a hardverprofil az oltalom alatt álló rendelt használatos

## <a name="client-maintenance"></a>Kliens karbantartás
### <a name="registers"></a>Pénztárgépek

A POS-pénztárgépeket elsősorban maguknál a pénztárgépeknél, valamint a pénztárgépekhez hozzárendelt profilok által kezelik. Az adott pénztárgépre jellemző tulajdonságokat a pénztár szintjén kezeli a rendszer. Ezek közé a tulajdonságok közé tartozik az üzlet, ahol a pénztárat használják, a pénztár száma, a leírás, és a pénztárra vonatkozó EFT terminálazonosító.

### <a name="pos-profiles"></a>POS-profilok

Megtalálhatja a POS-profilok: **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**POS profilok**. Célszerű profilokkal kezelni a pénztár különböző funkcióit, mivel a profilokat több pénztár között megoszthatja. A profilok társíthatóak egy egyedi pénztárhoz, vagy ha a profil az egész üzletben hatékony, akkor a kiskereskedelmi üzlethez. Az következő bekezdések ismertetik a pénztár-profilokat és használatukat.

#### <a name="offline-profile"></a>Offline profil

Az offline profil az üzlet szintjén van beállítva. Ez arra használatos, hogy megadja a pénztáron végrehajtott tranzakciók feltöltési beállításait akkor, amikor a pénztár nincs csatlakoztatva a csatorna adatbázisához.

#### <a name="functionality-profile"></a>Funkcióprofil

Az funkcionalitás profil az üzlet szintjén van beállítva. Adja meg az üzlet egészére érvényes beállításokat a függvények a POS végrehajtható szolgál. A következő lehetőségeket a funkcióprofil keresztül kezeli. Ezek a funkciók egy gyorslapon vannak elrendezve.

-   **Általános** Gyorslap:
    -   Nemzetközi Szabványügyi Szervezet (ISO).
    -   Vevő létrehozása offline módban.
    -   Nyugtaprofil Email.
    -   Központi munkatársak bejelentkezésének hitelesítése.
-   **Funkciók** Gyorslap:
    -   A bejelentkezés és a kiegészített bejelentkezés kezelése.
    -   A pénztár pénzügyekkel és pénznemekkel kapcsolatos vonatkozásai, úgy mint az árak beírása és hogy van-e szükség tizedesjegyekre a váltópénzeknél.
    -   Időregisztráció engedélyezése a pénztárban.
    -   Termékek és kifizetések megjelenítése a pénztárban és a nyugtákon.
    -   Napvégi zárás kezelése.
    -   Csatorna adatbázis tranzakciók visszatartási paraméterei.
    -   Vevők keresése és létrehozása a pénztárban.
    -   Engedmények számítása.
-   **Összeg** Gyorslap:
    -   Engedélyezett maximális és minimális árak.
    -   Engedmények használata és kiszámítása.
-   **Infókódok** Gyorslap:
    -   Hogyan kezeli az információ kódok a POS minden aspektusát. A részleteket lásd: [Info kódok](info-codes-retail.md).
-   **Nyugta számozása** Gyorslap:
    -   A nyugtaszámozási maszkok megadása, amelyek tartalmazhatnak számsorokat az üzletszámból, a terminálszámból, konstansokból, és annak megadása, hogy az értékesítések, visszáruk, vevői rendelések és árajánlatok külön számsorokba, vagy egy folyamatos számsorba legyenek nyomtatva.

#### <a name="receipt-profiles"></a>Nyugtaprofilok

A nyugtaprofilok közvetlenül a nyomtatókhoz vannak rendelve, a hardverprofilon belül. Arra használatosak, hogy egy adott nyomtatónál nyomtatott nyugtatípusokat adjunk meg. A profilok beállításokat tartalmaznak, amelyek meghatározzák a nyugta formátumát, valamint hogy a nyugta mindig ki legyen-e nyomtatva, vagy a pénztáros döntsön a nyomtatás szükségességéről. A különböző nyomtatók különböző nyugtaprofilokat használhatnak. Például, az 1-es nyomtató egy szabványos hőmérsékleti nyugtanyomtató, így kisebb nyugtaformátumai vannak. Azonban a 2-es nyomtató egy teljes méretű nyomtató, amelyet a több helyet igénylő vásárlói rendelés nyugták nyomtatására használják.

#### <a name="hardware-profiles"></a>Hardverprofilok

Ez a cikk már korábban bemutatta a hardverprofilokat, a kliensbeállítás egyik összetevőjeként. A hardverprofilok közvetlenül a pénztárhoz vagy a hardverállomás-profilhoz vannak hozzárendelve. Arra használatosak, hogy meghatározza velük egy adott pénztár vagy hardverállomás által használt eszközök típusait. A hardverprofilokkal adhatóak meg továbbá az EFT beállítások, amelyek a fizetési SDK-val való kommunikációt végzik.

#### <a name="visual-profiles"></a>Vizuális profilok

A vizuális profilok hozzárendelése a pénztár szintjén történik. Megadhatja velük az adott regiszter témáját. A profilok tartalmaznak beállításokat a használt alkalmazástípusra (MPOS vagy Felhő POS), a kiemelési színre és témára, a betűsémára, a bejelentkezési háttérre és a pénztár háttérre vonatkozólag.

### <a name="custom-fields"></a>Egyéni mezők

Létrehozhat egyéni mezőket vehetünk fel mezőket, amelyek nem a POS nem biztosított. Egyéni mezők használatával kapcsolatos további tudnivalókért tanulmányozza a [használata egyéni mezőket blogbejegyzés](https://blogs.msdn.microsoft.com/axsupport/2012/08/06/ax-for-retail-2012-working-with-custom-fields/).

### <a name="language-text"></a>Nyelvfüggő szöveg

Felülírhatja a pénztárgép alapértelmezett karakterláncait a nyelvi szövegbejegyzés használatával. A pénztárgép karakterláncának felülírásához adjon hozzá egy új nyelvi szövegsort. Ezután adjon meg egy azonosítót. Az alapértelmezett karakterlánc felülírása megtörténik, és a pénztáron az alapértelmezett karakterlánc helyett a megadott szöveg fog megjelenni.

### <a name="hardware-station-profiles"></a>Hardverállomás profiljai

Ez a cikk korábban már bemutatta a hardverállomás-profilokat. Ezekkel nem-példányspecifikus információkat rendelhet a hardverállomásokhoz.

### <a name="channel-reports-configuration"></a>Csatornajelentések konfigurálása

Beállíthatja a kiskereskedelmi csatornán elérhető jelentéseket a **Kiskereskedelmi csatorna jelentéseinek konfigurációja** oldalon. Új jelentéseket hozhat létre, ha megadja a jelentés XML-definícióját, és hozzárendeli a jelentést a pénztár egy adott engedélycsoportjához.

### <a name="devices"></a>Eszközök

Ez a cikk korábban már bemutatta az eszközöket. Egy adott pénztár aktivációját kezelheti velük. Továbbá az eszközök használatával adhatja meg a pénztárnál használt alkalmazást, és az MPOS kliens telepítését végző telepítési csomagot. Itt szerepelnek az eszközök aktivációs szakaszai:

-   **Függőben lévő** – az eszköz aktiválásra készen áll.
-   **Aktív** – az eszközt aktiválták.
-   **Inaktív** – az eszköz ki lett kapcsolva, az irodában vagy a pénztáron keresztül.
-   **Tiltott** – Az eszköz le van tiltva.

Az aktiválással kapcsolatos további információk tartalmazzák a dolgozót, aki megváltoztatta az eszköz aktivációs állapotát, egy időbélyeget az aktivációról, és hogy érvényesítve lett-e az eszköz konfigurációja.

### <a name="client-data-synchronization"></a>Kliensadatok szinkronizálása

A pénztárkliensben az aktivációs állapotban bekövetkezett változásokon kívül minden változást szinkronizálni kell a csatorna adatbázisában, hogy érvénybe lépjenek. A csatorna adatbázis módosításainak szinkronizálását, keresse meg **kereskedelmi és kereskedelmi**&gt;**kiskereskedelmi IT**&gt;**elosztási ütemezés**, és futtassa a szükséges elosztási ütemezés. A kliensváltoztatásokhoz futtassa a „Pénztárak” és „Csatornakonfiguráció” elosztási ütemezéseket.


