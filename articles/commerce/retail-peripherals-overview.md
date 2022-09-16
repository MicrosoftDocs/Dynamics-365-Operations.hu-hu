---
title: Perifériák
description: Ez a cikk bemutatja a Commerce perifériákkal kapcsolatos fogalmakat.
author: BrianShook
ms.date: 09/08/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: josaw
ms.custom:
- "268444"
- intro-internal
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: b3113626b18ad7f074c808d7631d13b09071bef2
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2022
ms.locfileid: "9459994"
---
# <a name="peripherals"></a>Perifériák

[!include[banner](includes/banner.md)]

Ez a cikk bemutatja az üzlet perifériáihoz kapcsolódó fogalmakat. A perifériák pénztárhoz (POS) való csatlakoztatásának különböző módszereit írja le, valamint az összetevőket, amelyek a POS-kapcsolat kezeléséért felelősek

## <a name="concepts"></a>Koncepciók

### <a name="pos-registers"></a>POS-pénztárgépek

Navigáció: Ugrás a **Retail- és Commerce \> csatornabeállítási \> POS-beállítási pénztárgépre \>**. A pénztár (POS) pénztárgép egy entitás, amely egy adott pénztárpéldány jellemzőinek meghatározására szolgál. E jellemzők közé tartozik a pénztárgépen használt kiskereskedelmi perifériák hardverprofilja vagy beállítása, az üzlet, amelyhez a pénztárgép hozzá van rendelve, és a vizuális élménye annak a felhasználónak, aki bejelentkezik a pénztárgépre.

### <a name="devices"></a>Eszközök

Navigáció: Ugrás a **Retail- és Commerce \> csatornabeállítási \> POS-beállítási eszközökre \>** Egy eszköz egy olyan entitás, amely egy pénztárhoz rendelt eszköz fizikai reprezentációja. Egy eszköz létrehozásakor a rendszer hozzárendeli azt egy pénztárhoz. Az eszköz-entitás nyomon követi a pénztárgép aktiválásáról, a használt klienstípusról, és az eszközre telepített alkalmazáscsomagról szóló információt. 

Az eszközök a következő alkalmazástípusokra leképezve használhatók: Retail Modern POS Retail Cloud POS, Retail Modern POS – Android és Retail Modern POS – iOS.

### <a name="modern-pos"></a>Modern POS

A Modern POS a Microsoft Windows rendszeren futó pénztárprogram. Telepíthető Windows 10 és Windows 11 operációs rendszerekre.

### <a name="cloud-pos"></a>Felhő pénztár

A Cloud POS a Modern POS program böngészőalapú verziója, amely webböngészőben érhető el.

### <a name="modern-pos-for-ios"></a>Modern POS for iOS

A Modern POS for iOS a Modern POS program iOS-alapú változata, amely iOS-eszközökre telepíthető.

### <a name="modern-pos-for-android"></a>Modern POS for Android

A Modern POS for Android a Modern POS program Android-alapú változata, amely Android-eszközökre telepíthető.

### <a name="pos-peripherals"></a>Pénztárperifériák

A pénztárperifériák olyan eszközök, amely kifejezetten a pénztárfunkciókhoz támogatottak. A perifériák általában adott osztályokra vannak felosztva. Ezekről az osztályokról a cikk "Eszközosztályok" szakaszában olvashat bővebben.

### <a name="hardware-station"></a>Hardverállomás

Navigáció: Az összes üzletet tároló **Kiskereskedelmi és Commerce \> Channels \> áruházakhoz \> ugrás**. Válasszon ki egy üzletet, majd válassza ki a Hardver **hardveres gyorstárat**. A **Hardverállomás** beállítás csatornaszintű beállítás, amely definiálja azokat a példányokat, ahol telepítve lesz a perifériás logika. Ez a beállítás a csatorna szintjén a hardverállomás jellemzőinek meghatározására szolgál. Emellett azoknak a hardverállomásoknak a listázására is szolgál, amelyek a Modern POS példány rendelkezésére állnak egy adott üzletben. A hardverállomás be van építve a Windows és Android rendszeren futó Modern POS-programokba. A hardverállomás függetlenül is telepíthető önálló Microsoft Internet Information Services (IIS) programként. Ebben az esetben a hálózaton keresztül érhető el.

### <a name="hardware-profile"></a>Hardverprofil

Navigáció: Ugrás a Kiskereskedelmi és **Commerce \> csatorna beállítása \> POS-profilok \> hardverprofiljaihoz \>**. A hardverprofil a pénztárgéphez vagy a hardverállomáshoz konfigurált eszközök listája. A hardverprofil közvetlenül a pénztárgéphez vagy a hardverállomás-profilhoz lehet hozzárendelve.

## <a name="devices-classes"></a>Eszközökosztályok
A pénztárperifériák általában adott osztályokra vannak felosztva. Ez a szakasz a Modern POS által támogatott eszközöket ismerteti, áttekintést nyújtva róluk.

### <a name="printer"></a>Nyomtató

A nyomtatók közé a hagyományos pénztár nyugtanyomtatók és az egész oldalas nyomtatók tartoznak. A nyomtatókat az Object Linking and Beágyazott illesztőfelületek támogatják a Retail POS (OPOS) számára, Microsoft Windows illetve az illesztőfelületek segítségével. Legfeljebb két nyomtató használható egyszerre. Ezt a funkcionalitás támogatja azt a forgatókönyvet, amikor az önkiszolgáló diszkontáruházakban a nyugtákat a nyugtanyomtató nyomtatja ki, miközben a több információt tartalmazó vevői rendeléseket egy teljes oldalas nyomtató nyomtatja. A nyugtanyomtatók közvetlenül csatlakoztathatók a számítógéphez USB-n keresztül, hálózatra Ethernet-kábellel, és csatlakoztathatók Bluetooth használatával is.

### <a name="scanner"></a>Leolvasó

Legfeljebb két vonalkódolvasó használható egyszerre. Ezt a funkcionalitás azokat a forgatókönyveket támogatja, ahol a fizetés felgyorsítása érdekében a nagy vagy nehéz cikkek beolvasásához könnyebben mozgatható olvasóra van szükség, miközben a legtöbb szabványos méretű cikk beolvasására rögzített beágyazott vonalkódolvasó szolgál. A beolvasók OPOS, univerzális Windows Platform (UWP) vagy billentyűzethez-ékelt felületekkel támogathatók. A beolvasó és a számítógép csatlakoztatásához USB vagy Bluetooth használható.

### <a name="msr"></a>MSR

Egy USB mágnescsíkolvasó (MSR) állíthat be OPOS-illesztőprogramok segítségével. Ha egy önálló MSR-t szeretne használni az elektronikus átutalási (EFT) fizetési tranzakciókhoz, az MSR-t fizetési csatlakoztatóval kell kezelni. Az önálló MSR vásárlói hűségadatok beviteléhez, alkalmazott-bejelentkezéshez és ajándékkártya-bevitelhez a fizetési csatlakoztatótól függetlenül is használható.

### <a name="cash-drawer"></a>Pénzfiók

Hardverprofilonként két pénzfiók támogatható. Ez a lehetőség lehetővé teszi, hogy pénztárgépenként egyszerre két aktív műszak álljon rendelkezésre. Megosztott műszak, vagy egyszerre több hordozható pénztáreszközök által használt pénzfiók esetén hardverprofilonként csak egy pénzfiók engedélyezett. A pénzfiókok közvetlenül csatlakoztathatók a számítógéphez USB-n keresztül, hálózatra csatlakoztathatók, vagy nyugtanyomtatóra csatlakoztathatók RJ12-felület használatával. Néhány esetben a pénzfiókok Bluetooth használatával is is csatlakozhatnak.

### <a name="line-display"></a>Sor megjelenítése

Sorkijelző jeleníti meg a termékeket, tranzakcióegyenlegeket és más hasznos információkat a vevőnek a tranzakciók során. Egy sorkijelző csatlakoztatható a számítógéphez USB-n keresztül az OPOS-illesztőprogramok segítségével.

### <a name="signature-capture"></a>Aláírás rögzítése

Az aláírás-rögzítő eszközök közvetlenül a számítógéphez csatlakoztathatók USB vagy OPOS-illesztőprogramok segítségével. Ha az aláírás-rögzítés be van állítva, a vevőnek az eszközön kell elvégeznie az aláírást. Az aláírást a beadása után a pénztáros megtekinti elfogadásra.

### <a name="scale"></a>Arány

Mérleg csatlakoztatható a számítógéphez USB-n keresztül az OPOS-illesztőprogramok segítségével. Olyan termék tranzakció való hozzáadásakor, amelynek a megjelölése „Lemért” cikk, a pénztár beolvassa a tömeget a mérlegről, a terméket hozzáadja a tranzakcióhoz, és a mérleg által megadott mennyiséget használja.

### <a name="pin-pad"></a>PIN-billentyűzet

A személyes azonosítószámot (PIN) megadó számbillentyűzetek OPOS-on keresztül támogatottak, de fizetési csatlakozón keresztül lehet kezelni őket.

### <a name="secondary-display"></a>Másodlagos kijelző

Ha a másodlagos kijelző be van állítva, a 2-es számú Windows megjelenítő használatos az alapvető információk megjelenítése. Alapértelmezés szerint a másodlagos kijelző nem konfigurálható, és korlátozott tartalmat jelenít meg. A másodlagos megjelenítés célja egy független szoftverszállítói bővítmény támogatása. 

### <a name="payment-device"></a>Fizetésre szolgáló eszköz

A fizetési eszközök támogatása a fizetési csatlakozón keresztül valósul meg. A fizetési eszközök egy vagy sok, más eszközosztályok által biztosított funkció végrehajtására képesek. Egy fizetési eszköz működhet például MSR/kártyaolvasóként, sorkijelzőként, aláírás-rögzítő eszközként vagy PIN-billentyűzetként. A fizetési eszközök támogatása függetlenül történik az önálló eszközök támogatásától, amely a hardverprofilban szereplő más eszközökhöz biztosított.

## <a name="supported-interfaces"></a>Támogatott interfészek
### <a name="opos"></a>OPOS

Annak a biztosítása, hogy az eszközök lehető legnagyobb választéka legyen használható a Commerce programmal, elsődleges perifériaplatformként az OLE for POS ipari szabványt támogatja. Az OLE for POS szabvány kidolgozója a National Retail Federation (NRF), amely iparági szabvány kommunikációs protokollokat határoz meg a perifériaeszközök számára. Az OPOS az OLE for POS szabvány széles körben elfogadott implementációja. Az 1990-es évek közepén fejlesztették ki, és azóta többször módosult. Az OPOS eszközillesztőprogram-architektúrát biztosít, amely lehetővé teszi a pénztárhardverek és a Windows-alapú pénztárrendszerek egyszerű integrációját. Az OPOS-vezérlők kezelik a kommunikációt a pénztárszoftver és a kompatibilis hardver között. Az OPOS-vezérlők két részből állnak:

-   **Vezérlőobjektum** – Egy eszközosztály (például sorkijelző) vezérlőobjektuma biztosítja a felületet a program számára. A Monroe Consulting Services ([www.monroecs.com](http://www.monroecs.com/)) standardizált OPOS vezérlőobjektum-készletet kínál: ezek közönséges vezérlőobjektumok (CCOs) néven ismertek. A CCO-k a Commerce POS-komponensének tesztelésére szolgálnak. Ezért a tesztek segítenek garantálni azt, hogy ha a Commerce támogat egy eszközosztályt az OPOS-on keresztül, sokféle eszköztípus támogatható, amennyiben a gyártó biztosít OPOS-hoz készített szolgáltatásobjektumot. Nem kell külön tesztelni minden egyes eszköztípust.
-   **Szolgáltatásobjektum** – A szolgáltatásobjektum biztosítja a kommunikációt a vezérlőobjektum (CCO) és az eszköz között. Általában az eszköz szolgáltatásobjektumát az eszköz gyártója biztosítja. Azonban egyes esetekben előfordulhat, hogy a szolgáltatásobjektumot le kell töltenie a gyártó webhelyéről. Rendelkezésre állhat például egy újabb szolgáltatásobjektum. A gyártó webhelyének címét lásd a hardverdokumentációban.

[![Vezérlőobjektum és szolgáltatásobjektum.](./media/retail_peripherals_overview01.png)](./media/retail_peripherals_overview01.png) Vezérlőobjektum és szolgáltatásobjektum Az OLE for POS pénztárimplementáció támogatása segít garantálni azt, hogy ha az eszközgyártók és a pénztár-közzétevők helyesen implementálták a szabványt, a pénztárrendszerek és a támogatott eszközök képesek együtt dolgozni, még akkor is, ha korábban nem tesztelték őket együtt. 

> [!NOTE]
> Az OPOS-támogatás nem garantálja az összes, OPOS-illesztőprogrammal rendelkező eszköz támogatását. A Commerce rendszernek először támogatnia kell az első adott eszköztípust, vagy osztályt az OPOS-on keresztül. Ezenkívül a szolgáltatásobjektumok nem mindig naprakészek a CCO-k a legújabb verziójával. Tudatában kell lennie annak, hogy általánosságban a szolgáltatásobjektumok minősége vegyes.

### <a name="windows"></a>Windows

A nyugtanyomtatás a pénztárban az OPOS-ra van optimalizálva. Az OPOS általában sokkal gyorsabb, mint a Windows-nyomtatás. Ezért célszerű az OPOS használata, különösen a környezetekben, ahol 40 oszlopos nyugták nyomtatása történik, és a tranzakciós időnek rövidnek kell lennie. A legtöbb eszköz esetében OPOS-vezérlők használhatók. Azonban egyes OPOS-nyugtanyomtatók a Windows-illesztőprogramokat is támogatják. A Windows-illesztőprogram használatakor elérheti a legújabb betűtípusokat és az egyes hálózati nyomtatót több pénztárgéphez. Azonban vannak hátrányai is a Windows-illesztőprogramok használatának. Az alábbiakban példa látható a hátrányokra:

-   A Windows-illesztőprogramok használatakor megtörténik a képek renderelés a nyomtatás előtt. Ezért a nyomtatás általában lassabb, mint az OPOS-vezérlőket használó nyomtatók esetében.
-   A nyomtatón keresztül csatlakoztatott („láncba kötött”) eszközök nem feltétlenül működnek megfelelően a Windows-illesztőprogramok használatakor. Előfordulhat például, hogy a pénztárgépfiók nem nyílik ki, vagy a nyugtanyomtató nem úgy működik, mint ahogy várt.
-   Az OPOS emellett változók szélesebb körét támogatja, amelyeket kifejezetten a nyugtanyomtatókhoz terveztek: ilyen például a papírvágás vagy az elismervénynyomtatás.
-   A Windows-nyomtatók nem támogatottak az IIS hardverállomáson keresztül. 

Ha OPOS-vezérlők érhetők el a Windows-nyomtatóhoz, amelyet használ, a nyomtatónak még mindig gond nélkül működnie kell a Commerce programmal.

### <a name="plug-and-play-devices"></a>Beépülő és lejátss eszközök

Ha egy olyan Windows operációs rendszer olyan verziójához csatlakozik, amely támogatja ezt az eszköztípust, nem szükséges illesztőprogram ahhoz, hogy az eszköz használható legyen a használatban. Ha például a Windows észlel egyKezelőeszközt, az operációs rendszer tudja, hogy az eszköz "Bekezelő" osztálytípusú, és az eszközt szövegkezelő eszközként kezeli. Nincs szükség további beállításra. 

POS-perifériák esetében számos POS-eszközt lehet aláásni, és ezt a Windows OPERÁCIÓS rendszer is felismerheti emberi felületi eszközként (HID). Előfordulhat azonban, hogy a Windows nem tudja megállapítani az eszköz által adott lehetőségeket, mivel az eszköz nem határozza meg az eszköz osztályát vagy típusát. A Windows 10 rendszerben a vonalkódolvasók és az MSR-ek eszközosztályainak hozzáadása történt meg. Ezért ha egy eszköz azt kommunikálja a Windows 10 rendszernek, hogy a fenti osztályok egyikébe tartozik, a Windows figyeli az eseményeket az eszközről a megfelelő időpontokban.

A Modern POS támogatja az UWP MSR-eket és beolvasókat. Amikor tehát a Modern POS készen áll az eszközök egyikének bevitelére, és ehhez az eszközosztályhoz tartozó eszköz csatlakoztatva van, akkor használható az eszköz. Ha például egy Windows 10-es számítógépen egy leolvasóról van leolvasó a windows 10-es verzióban, és a vonalkód-beolvasó a Modern POS rendszerhez van beállítva, akkor a vonalkód-leolvasó aktívvá válik a bejelentkezési lapon. Nincs szükség további beállításra.

A POS-perifériák további osztályai kerülnek a Windows alkalmazásba, például a pénztárfiókok és a nyugtanyomtatók osztályai. Az új eszközosztályok támogatása a Modern POS programban függőben van.

> [!NOTE] 
> Ha a Windows 10 [áramkezelési funkcióval kezelt ÉS AOS szelektív felfüggesztése van a rendszerben, bizonyos FUNKCIÓK elérhetetlenné vagy megbízhatatlanná válhatnak](/windows-hardware/drivers/usbcon/usb-selective-suspend). Ha egy PERIFÉRIÁS periféria elérhetetlenné válik, lehet, hogy le kell tiltani az adott eszközre vonatkozó szelektív felfüggesztési funkciót. A további tudnivalókat lásd [a Szelektív felfüggesztés engedélyezése.](/windows-hardware/drivers/usbcon/usb-selective-suspend#enabling-selective-suspend) 

### <a name="keyboard-wedge"></a>Billentyűzet ék

A billentyűzet ék eszközök adatokat küldenek a számítógépnek úgy, mintha az adatok a billentyűzeten lettek volna beírva. Ezért alapértelmezés szerint a pénztár aktív mezője megkapja a beolvasott vagy lehúzott adatokat. Bizonyos esetekben ez a viselkedés azt okozhatja, hogy hibás típusú adatok olvasódnak be a nem megfelelő mezőbe. Egy vonalkód például a hitelkártyaadatoknak szánt mezőbe olvasódhat be. A POS számos esetben azt határozza meg, hogy a beolvasott vagy leolvasott adatok vonalkód vagy kártya lehúzása-e. Ezért az adatok megfelelően kezeli a rendszer. Ha azonban az eszközök BILLENTYŰZET-billentyűparancsok helyett OPOS-eszközként vannak beállítva, akkor még inkább szabályozható, hogy az ilyen eszközök adatai hogyan használhatók fel, mivel több "ismert" információ arról az eszközről, amelyről az adatok származnak. A vonalkód-leolvasók adatait például automatikusan vonalkódként ismeri fel a rendszer, és a kapcsolódó bejegyzés megkeresése az adatbázisban könnyebb és gyorsabb, mint ha általános karakterlánc-keresés futna le, úgy, mint a billentyűzet ék eszközök esetében.

> [!NOTE]
> Ha billentyűzetolvasókat használ a POS-ban, akkor úgy kell őket programozni, hogy küldjenek vissza egy soremelést, vagy egy **Enter** eseményt az utolsó beolvasott karakter után. Ha ez a konfigurálás nem történik meg, akkor a billentyűzetolvasók nem fognak megfelelően működni. Az eszközgyártó által benyújtott dokumentációból tájékozódhat a soremelés esemény hozzáfűzéséről.  

### <a name="device-printers"></a>Eszköznyomtatók

Az "Eszköz" típusú nyomtatók beállíthatók úgy, hogy a felhasználó rákérdezhet a számítógéphez beállított nyomtató kiválasztására. Ha az "Eszköz" típusú nyomtatót beállítja, és a Modern POS használ nyomtatási parancsot, a rendszer megkérdezi a felhasználótól, hogy válasszon egy nyomtatót a listáról. Ez a viselkedés eltér a Windows-illesztőprogramok viselkedésától, mivel a hardverprofil "Windows" nyomtatótípusa nem mutatja a felhasználónak a nyomtatók listáját. Ehelyett arra van szükség, hogy egy elnevezett nyomtatót legyen megadva az **Eszköznév** mezőben.

### <a name="network"></a>Hálózat

Hálózati címmel rendelkező pénzfiókok, nyugtanyomtatók és fizetési terminálok hálózaton keresztül is használhatók vagy a Modern POS for Windows alkalmazásba beépített folyamatközi kommunikációs (IPC) hardverállomáson keresztül, vagy az IIS-hardverállomáson át más Modern POS-ügyfelek esetében.

## <a name="hardware-station-deployment-options"></a>Hardverállomás-telepítési lehetőségek

### <a name="dedicated"></a>Kijelölt

A korszerű POS-ügyfelek esetében a Windows és az Android **Dedikált** vagy beépített hardverállomásokat tartalmaz. Ezek az ügyfelek közvetlenül tudnak kommunikálni a perifériákkal az alkalmazásokba épített üzleti logikát használva. Az Android alkalmazás csak hálózati eszközöket támogat. Ha további tájékoztatást szeretne a perifériás támogatással kapcsolatban az Android esetében, látogassa meg a [POS Hybrid alkalmazás beállítása Android vagy iOS rendszerre](./dev-itpro/hybridapp.md) cikket.

A következő lépések szerint használja a kijelölt hardverállomást.

1. Rendeljen hardverprofilt egy pénztárgéphez, amely a Modern POS for Windows vagy application rendszert Android fogja használni.
1. Hozzon létre egy "Dedicated" típusú hardverállomást az üzlethez, ahol a pénztárgépet használni fogják. 
1. A Modern POS nem fiókos módban való megnyitása, **és** a hardverállomás funkcióinak bekapcsolása a Hardverműveletek kezelése művelettel. A kijelölt hardverállomás alapértelmezés szerint aktív lesz. 
1. Kijelentkezés a Modern POS rendszerből Ezután jelentkezzen be, és nyisson meg egy műszakot. Ezzel használhatók a hardverprofilban konfigurált perifériák. 

### <a name="shared"></a>Megosztott

Más néven "IIS" hardverállomásként is hivatkoznak, ami arról ad tájékoztatást, hogy a POS-alkalmazás a Microsoft Internet Information Services szolgáltatáson keresztül kapcsolódik a hardverállomáshoz. A pénztáralkalmazás az IIS-hardverállomáshoz webes szolgáltatásokon át csatlakozik, amelyek azon a számítógépen futnak, amelyhez az eszközök kapcsolódnak. Megosztott hardverállomás használatakor a hardverállomáshoz csatlakozó perifériákat bármely pénztárgép használhatja, amely ugyanazon a hálózaton van, mint az IIS-hardverállomás. Mivel csak a Modern POS for Windows és az Android tartalmazza a perifériák beépített támogatását, minden más Modern POS alkalmazásnak az IIS-hardverállomást kell használnia a kommunikációhoz a hardverprofilban konfigurált pénztárperifériákkal. Emiatt az IIS-hardverállomás minden egyes példányához szükség van egy számítógépre, amely az eszközökkel kommunikáló webes szolgáltatást és alkalmazást futtatja. 

A megosztott hardverállomás lehetővé teszi, hogy több értékesítési ügyfél közösen használja a perifériákat, vagy egy-egy értékesítési pont vállalt perifériás készletének kezelésére használható. 

Amikor egy hardvereszköz használható a perifériák több POS-ügyfél közötti megosztásának támogatására, csak a pénzfiókok, a nyugta- és a kifizetési terminálok használhatók. Önálló vonalkódolvasók, MSR-ek, sorkijelzők, mérlegek vagy más eszközök közvetlenül nem csatlakoztathatók. Ellenkező esetben ütközés történik, amikor több pénztáreszköz próbálja egyszerre igényelni ugyanazokat a perifériákat. A támogatott eszközök ütközésének kezelése a következő:

-   **Pénzfiók** – A pénztárfiók nyitását az eszköznek küldött esemény váltja ki. Problémák léphetnek fel, ha egy pénztárgépfiókot akkor hívnak ki, amikor a fiók már ki van nyitva. A megosztott hardverállomás konfigurációjában használt **pénztárfiókot** a Hardverprofilban megosztottra kell állítani. Ez a beállítás megakadályozza, hogy a pénztár ellenőrizze azt, hogy a pénztárfiók már nyitva van-e, amikor a megnyitás parancsot küldi.
-   **Nyugtanyomtató** – Ha a hardverállomásra egy időben két nyugtanyomtatási parancsot küldenek, a parancsok egyike elveszhet az eszköztől függően. Egyes eszközöknek belső memóriája vagy készletezési funkciója van, amely megakadályozhatja a probléma előfordulását. Ha egy nyomtatási parancs nem sikeres, a pénztáros hibaüzenetet kap, és újra megpróbálhatja kiadni a nyomtatási parancsot a pénztárról.
-   **Fizetési terminál** – Ha a pénztáros megpróbál végrehajtani egy tranzakciót egy fizetési terminálról, amely már használatban van, egy üzenet értesíti a pénztárost, hogy a terminál használatban van, és megkér, hogy próbálkozzon újra később. A pénztárosok általában látják, hogy a terminál már használatban van, és várnak, amíg a másik tranzakció befejeződik, mielőtt újra próbálkoznának.

A jövőbeli programverziók egyik tervezett funkciója annak az ellenőrzése, hogy nem támogatott eszközök vannak-e beállítva egy megosztott hardverállomáshoz hozzárendelt hardverprofilhoz. Ha az ellenőrzés nem támogatott eszközöket érzékel, a felhasználó kap egy üzenetet, amely arról tájékoztatja, hogy az eszközök nem támogatottak a megosztott hardverállomásokhoz. Megosztott hardverállomások esetében a **Kiválasztás fizetéskor** beállítás beállítása **Igen** a pénztárgép szintjén. A pénztárfelhasználó kérést kap a hardverállomás kiválasztására, amikor fizetést választanak egy tranzakciókhoz a pénztárgépen. Ha a hardverállomás kijelölése csak a fizetés idején történik, a hardverállomás kiválasztása közvetlenül a mobil forgatókönyvek pénztár-munkafolyamatához adódik hozzá. További előny, hogy a fizetési terminál sorkijelzője nem használt a megosztott forgatókönyvek esetében. Ha a fizetési terminált használják sorkijelzőként, más felhasználók számára a terminál zárolva lehet a tranzakció befejezéséig. Mobil forgatókönyvek esetében sorok adódhatnak hozzá a tranzakcióhoz hosszabb időszakra vonatkozóan. Ezért a **Kiválasztás fizetéskor** kapcsoló szükséges az eszköz optimális rendelkezésre állásának biztosítása érdekében.

### <a name="network-peripherals"></a>Hálózati perifériák

A hardverprofilban levő eszközök hálózati megjelölése lehetővé teszi a pénzfiókok, nyugtanyomtatók és fizetési terminálok hálózati kapcsolaton keresztül való csatlakoztatását.

#### <a name="modern-pos-for-windows"></a>Modern POS for Windows

Két helyen lehet megadni a hálózati perifériákhoz tartozó IP-címeket. Ha a Modern POS Windows-ügyfél hálózati perifériák egyetlen készletet használja, az IP-címeket az eszközökhöz a Művelet panel **IP-konfiguráció** beállításának segítségével adja a pénztárgéphez. Az olyan hálózati eszközök esetében, amelyeken több pénztárgép osztozik, a hozzárendelt hálózati eszközökkel rendelkező hardverprofil közvetlenül rendelhető egy megosztott hardverállomáshoz. Az IP-címek hozzárendeléséhez jelölje ki a hardverállomást az **Üzletek** oldalon, és alkalmazza az **IP-konfiguráció** lehetőséget a **Hardverállomások** szakaszban a hardverállomáshoz hozzárendelt hálózati eszközök megadásához. Az olyan hardverállomásoknál, amelyek csak hálózati eszközökkel rendelkeznek, nem kell telepíteni magát a hardverállomást. Ebben az esetben a hardverállomásra csak ahhoz van szükség, hogy fogalmi szinten csoportosítsuk a hálózati címmel rendelkező eszközöket a helyük szerint az üzletben.

#### <a name="cloud-pos-and-modern-pos-for-ios"></a>Cloud POS és Modern POS iOS rendszerhez

A fizikailag csatlakoztatott és hálózati címmel rendelkező perifériákat működtető logika a hardverállomásban található. Ezért a Modern POS for Windows és Android kivételével az összes ügyfél esetében egy IIS-hardverállomást kell telepíteni és aktiválni ahhoz, hogy a pénztár kommunikálhasson a perifériákkal, függetlenül attól, hogy a perifériák fizikailag csatlakoztatottak egy hardverállomáshoz, vagy a hálózaton keresztül vannak megcímezve.

## <a name="setup-and-configuration"></a>Beállítás és konfigurálás
### <a name="hardware-station-installation"></a>Hardverállomás-telepítés

Az IIS hardverállomások telepítésével kapcsolatos útmutatás [: Hardverállomás konfigurálása és telepítése](retail-hardware-station-configuration-installation.md).

### <a name="modern-pos-for-windows-setup-and-configuration"></a>Modern POS for Windows telepítés és beállítás

További információ: [A (MPOS) konfigurálása, telepítése és aktiválása](retail-modern-pos-device-activation.md).

### <a name="modern-pos-for-android-and-ios-setup-and-configuration"></a>Modern POS for Android és iOS telepítése és beállítása

További információk: [A POS Hybrid alkalmazás beállítása Android és iOS rendszerre](./dev-itpro/hybridapp.md).

### <a name="opos-device-setup-and-configuration"></a>OPOS-eszköz telepítése és beállítása

További információért a OPOS-összetevőkről lásd a dokumentum „Támogatott interfészek” részét. Az OPOS-illesztőprogramokat általában az eszköz gyártója biztosítja. Az OPOS-eszközillesztő a telepítésekor egy kulcsot ad a Windows beállításjegyzékéhez a következő helyek egyikén:

-   **32 bites rendszer:** HKEY\_ LOCAL\_ MACHINE\SOFTWARE\OLEforRetail\ServiceOPOS
-   **64 bites rendszer:** HKEY\_ LOCAL\_ MACHINE\SOFTWARE\SZORÍTÁS6432Node\OLEforRetail\ServiceOPOS

A ServiceOPOS beállításjegyzék-helyen belül a konfigurált eszközök az OPOS-eszközosztály szerint vannak rendezve. A rendszer több eszköz-illesztőprogramot ment.

## <a name="supported-scenarios-by-hardware-station-type"></a>Támogatott forgatókönyvek hardverállomás-típus szerint
### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Ügyfelek támogatása – IPC-hardverállomás kontra IIS-hardverállomás

A következő táblázat a támogatott topológiákat és telepítési forgatókönyveket mutatja.

| Ügyfél      | IPC-hardverállomás | IIS-hardverállomás |
|-------------|----------------------|----------------------|
| Windows alkalmazás | Igen                  | Igen                  |
| Felhő pénztár   | Nem                   | Igen                  |
| Android     | Igen                  | Igen                  |
| iOS         | Nem                   | Igen                  |

### <a name="network-peripherals"></a>Hálózati perifériák

A Modern POS for Windows és Android alkalmazásba beépített hardverállomás segítségével közvetlenül támogathatók a hálózati perifériák. Az összes többi ügyfél esetében telepíteni kell az IIS-hardverállomást.

| Ügyfél      | IPC-hardverállomás | IIS-hardverállomás |
|-------------|----------------------|----------------------|
| Windows alkalmazás | Igen                  | Igen                  |
| Felhő pénztár   | Nem                   | Igen                  |
| Android     | Igen                  | Igen                  |
| iOS         | Nem                   | Igen                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Támogatott eszköztípusok hardverállomás-típus szerint
### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS for Windows IPC (beépített) hardverállomással

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Támogatott eszközosztály</th>
<th>Támogatott interfészek</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nyomtató</td>
<td><ul>
<li>OPOS</li>
<li>Windows-illesztőprogram</li>
<li>Eszköz</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="even">
<td>2. nyomtató</td>
<td><ul>
<li>OPOS</li>
<li>Windows-illesztőprogram</li>
<li>Eszköz</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="odd">
<td>Sor megjelenítése</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Két kijelző</td>
<td>Windows-illesztőprogram</td>
</tr>
<tr class="odd">
<td>MSR</td>
<td><ul>
<li>OPOS</li>
<li>UWP (Nem szükséges beállítás.)</li>
<li>Billentyűzet ék (Nem kell beállítani.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Kiállító</td>
<td><ul>
<li>OPOS</li>
<li>Hálózat </br><strong>Megjegyzés:</strong> Csak egy fiókot lehet beállítani, ha a <strong>Megosztott műszak használata</strong> be van állítva a fiókon.</li>
</ul></td>
</tr>
<tr class="odd">
<td>2. fiók</td>
<td><ul>
<li>OPOS</li>
<li>Hálózat </br><strong>Megjegyzés:</strong> Csak egy fiókot lehet beállítani, ha a <strong>Megosztott műszak használata</strong> be van állítva a fiókon.</li>
</ul></td>
</tr>
<tr class="even">
<td>Leolvasó</td>
<td><ul>
<li>OPOS</li>
<li>UWP (Nem szükséges beállítás.)</li>
<li>Billentyűzet ék (Nem kell beállítani.)</li>
</ul></td>
</tr>
<tr class="odd">
<td>2. leolvasó</td>
<td><ul>
<li>OPOS</li>
<li>UWP (Nem szükséges beállítás.)</li>
<li>Billentyűzet ék (Nem kell beállítani.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Lépték</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>PIN-billentyűzet</td>
<td>OPOS (A támogatás nyújtása a fizetési csatlakoztató testreszabásával történik.)</td>
</tr>
<tr class="even">
<td>Aláírás rögzítése</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Fizető terminál</td>
<td><ul>
<li>Egyéni eszközök támogatása</li>
<li>Hálózat (További tudnivalókért lásd a fizetési csatlakoztató dokumentációját.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-committed-shared-iis-hardware-station"></a>Minden Modern POS-ügyfél, amely vállalt „megosztott” IIS hardverállomással rendelkezik

> [!NOTE]
> Ha az IIS hardverállomás "vállalt", akkor egy az egyhez kapcsolat van a POS-ügyfél és a hardverállomás között.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Támogatott eszközosztály</th>
<th>Támogatott interfészek</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nyomtató</td>
<td><ul>
<li>OPOS</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="even">
<td>2. nyomtató</td>
<td><ul>
<li>OPOS</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="odd">
<td>Sor megjelenítése</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>MSR</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Kiállító</td>
<td><ul>
<li>OPOS</li>
<li>Hálózat </br><strong>Megjegyzés:</strong>: Hardverprofilonként csak egy fiókot lehet beállítani, ha a <strong>Megosztott műszak használata</strong> be van állítva a fiókon.</li>
</ul></td>
</tr>
<tr class="even">
<td>2. fiók</td>
<td><ul>
<li>OPOS</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="odd">
<td>Leolvasó</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>2. leolvasó</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Lépték</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>PIN-billentyűzet</td>
<td>OPOS (A támogatás nyújtása a fizetési csatlakoztató testreszabásával történik.)</td>
</tr>
<tr class="odd">
<td>SIG rögzítés</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Fizető terminál</td>
<td><ul>
<li>Egyéni eszközök támogatása</li>
<li>Hálózat (További tudnivalókért lásd a fizetési csatlakoztató dokumentációját.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-share-an-iis-hardware-station"></a>Minden Modern POS-ügyfél, amely IIS hardverállomást megoszt.

> [!NOTE]
> Ha az IIS-hardverállomás „megosztott”, több eszköz egyszerre használhatja a hardverállomást. Ebben az esetben csak az alábbi táblázatban felsorolt eszközöket kell használnia. Ha megpróbál megosztani a listában nem szereplő eszközöket, például vonalkódolvasókat és MSR-eket, hiba fordul elő, ha több eszköz próbálja magának igényelni ugyanazt a perifériát. A jövőben az ilyen konfigurációkat kifejezetten tiltani fogjuk.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Támogatott eszközosztály</th>
<th>Támogatott interfészek</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nyomtató</td>
<td><ul>
<li>OPOS</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="even">
<td>2. nyomtató</td>
<td><ul>
<li>OPOS</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="odd">
<td>Kiállító</td>
<td><ul>
<li>OPOS</li>
<li>Hálózat </br><strong>Megjegyzés:</strong>: Hardverprofilonként csak egy fiókot lehet beállítani, ha a <strong>Megosztott műszak használata</strong> be van állítva a fiókon.</li>
</ul></td>
</tr>
<tr class="even">
<td>2. fiók</td>
<td><ul>
<li>OPOS</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="odd">
<td>Fizető terminál</td>
<td><ul>
<li>Egyéni eszközök támogatása</li>
<li>Hálózat (További tudnivalókért lásd a fizetési csatlakoztató dokumentációját.)</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Konfiguráció a támogatott forgatókönyvekhez
A hardverprofilok létrehozásával kapcsolatos további tudnivalókat lásd: [Perifériák csatlakoztatása a pénztárhoz (POS)](define-maintain-channel-clients-registers-hw-stations.md). 

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS for Windows IPC (beépített) hardverállomással

Ez a konfigurációban a leggyakoribb konfiguráció a hagyományos, rögzített pénztárgépek esetében. Ennek a forgatókönynek az esetében a hardverprofil-adatok közvetlenül a pénztárgéphez vannak rendelve. Az EFT-terminálszám szintén a pénztárgépen kell beállítani. A konfiguráció beállításához kövesse az alábbi lépéseket:

1.  Hozzon létre egy hardverprofilt, amelyben minden szükséges periféria konfigurálva van.
2.  Képezze le a hardverprofilt a pénztárgépre.
3.  Hozzon létre egy **Dedikált** típusú hardverállomást az üzlethez, ahol a pénztárgépet használni fogja. A leírás opcionális. 

    > [!NOTE]
    > A hardverállomás többi tulajdonságát nem kell beállítani. Minden más szükséges információ, például a hardverprofil, a pénztárgépből származik.

4.  Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.
5.  Válassza ki az **1090** elosztási ütemezést az új hardverprofil és az üzlet szinkronizálásához. A POS-hoz **való** módosítások szinkronizálása esetén válassza a Futtatás most lehetőséget.
6.  Válassza ki az **1040** elosztási ütemezést az új hardverállomás és az üzlet szinkronizálásához. A POS-hoz **való** módosítások szinkronizálása esetén válassza a Futtatás most lehetőséget.
7.  Telepítse és aktiválja a Modern POS for Windows alkalmazást.
8.  Indítsa el a Modern POS for Window alkalmazást, és kezdje el használni a kapcsolódó perifériaeszközöket.

### <a name="modern-pos-for-android-with-an-ipc-built-in-hardware-station"></a>Modern POS for Android IPC (beépített) hardverállomással

**Új a 10.0.8** – az Epson hálózati nyomtatók és a DK-porton keresztül az ilyen nyomtatókhoz csatlakoztatott pénztárfiókok mostantól támogatottak a Modern POS for Android app alkalmazásban. A részleteket lásd a [A POS Hybrid alkalmazás telepítése Android és iOS rendszerre](./dev-itpro/hybridapp.md) cikkben.

### <a name="all-modern-pos-clients-that-have-a-committed-shared-iis-hardware-station"></a>Minden Modern POS-ügyfél, amely vállalt, megosztott IIS hardverállomással rendelkezik

Ez a konfiguráció minden Modern POS ügyféllel használható, amelynek olyan hardverállomása van, amelyet kizárólag egy pénztárgép használ. A konfiguráció beállításához kövesse az alábbi lépéseket:

1.  Hozzon létre egy hardverprofilt, amelyben minden szükséges periféria konfigurálva van.
2.  Hozzon létre egy **Dedikált** típusú hardverállomást az üzlethez, ahol a pénztárgépet használni fogja.
3.  A dedikált hardverállomáson állítsa be a következő tulajdonságokat:
    -   **Állomásnév** – Annak a gazdaszámítógépnek a neve, ahol a hardverállomás futni fog. 
    
        > [!NOTE]
        > A Cloud POS felhő képes a **localhost** feloldására, hogy meghatározza a helyi számítógépet, amelyen a Cloud POS fut. Azonban a tanúsítványnak, amely ahhoz szükséges, hogy a hardverállomás és a Cloud POS párosítható legyen, szintén a „Localhost” számítógépnevet kell tartalmaznia. A problémák elkerülése érdekében azt javasoljuk, hogy szükség szerint listázza az üzlet minden dedikált hardverállomásának egy-egy példányát. Minden hardverállomás esetében az állomásnévnek annak a számítógépnek a nevének kell lennie, ahol a hardverállomás telepítve lesz.
    
    -   **Port** – A hardverállomás portja, amellyel a Modern POS-ügyféllel kommunikál.
    -   **Hardverprofil** – Ha a hardverprofil nincs megadva a hardverállomáson, a rendszer a pénztárgéphez rendelt hardverprofilt használja.
    -   **EFT pénztárszám** – Az EFT-terminálazonosító, amelyet az EFT-engedélyek küldésekor kell használni. Ezt az azonosítót a hitelkártya-feldolgozó biztosítja.
    -   **Csomag neve** – A hardverállomás telepítésekor használandó hardverállomás-csomag.

4.  Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.
5.  Válassza ki az **1090** elosztási ütemezést az új hardverprofil és az üzlet szinkronizálásához. A POS-hoz **való** módosítások szinkronizálása esetén válassza a Futtatás most lehetőséget.
6.  Válassza ki az **1040** elosztási ütemezést az új hardverállomás és az üzlet szinkronizálásához. A POS-hoz **való** módosítások szinkronizálása esetén válassza a Futtatás most lehetőséget.
7.  Telepítse a hardverállomást. A hardverállomás telepítésével kapcsolatos további tudnivalókért lásd: [A Retail Hardware Station konfigurálása és telepítése](retail-hardware-station-configuration-installation.md).
8.  Telepítse és aktiválja a Modern POS alkalmazást. A Modern POS telepítésével kapcsolatos további tudnivalókért lásd: [A Modern pénztár (MPOS) konfigurálása, telepítése és aktiválása](retail-modern-pos-device-activation.md).
9.  Jelentkezzen be a Modern POS alkalmazásba, és válassza a **Nem pénztárgépfiókkal kapcsolatos művelet végrehajtása** lehetőséget+.
10. Indítsa el a **Hardverállomások kezelése** művelet.
11. Válassza a **Kezelés lehetőséget**.
12. A hardverállomás kezelése lapon kapcsolja be a hardverállomást.
13. Válassza ki a használni kívánt hardverállomást, majd válassza a Pár **lehetőséget**.
14. A hardverállomás párosítása után válassza a Bezárás **lehetőséget**.
15. A hardverállomás kiválasztási lapján válassza ki a legutóbb kiválasztott hardverállomást aktívvá tenni.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Minden Modern POS-ügyfél, amely megosztott IIS-hardverállomással rendelkezik

Ez a konfiguráció minden olyan Modern POS-ügyfél esetében használható, amely hardverállomásokat oszt meg más eszközökkel. A konfiguráció beállításához kövesse az alábbi lépéseket:

1.  Hozzon létre egy hardverprofilt, amelyben a szükséges perifériák konfigurálva vannak.
2.  Hozzon létre egy **Megosztott** típusú hardverállomást az üzlethez, ahol a pénztárgépet használni fogja.
3.  A megosztott hardverállomáson állítsa be a következő tulajdonságokat:
    -   **Állomásnév** – Annak a gazdaszámítógépnek a neve, ahol a hardverállomás futni fog.
    -   **Leírás** – Szöveg, amely segít azonosítani a hardverállomást, például **Visszáruk** vagy **Üzlet front**.
    -   **Port** – A hardverállomás portja, amellyel a Modern POS-ügyféllel kommunikál.
    -   **Hardverprofil** – A megosztott hardverállomások esetében minden hardverállomásnak rendelkeznie kell egy hardverprofillal. A hardverprofilok megoszthatók a hardverállomások között, de hozzá kell rendelni őket minden egyes hardverállomáshoz. Ezen kívül megosztott műszakok használatát javasoljuk, ha ugyanazt a megosztott hardverállomást több eszköz használja. Megosztott műszak beállításához váltsa át a **Retail and Commerce \> Csatorna beállítása \> POS- és hardverprofilok \> beállítását \>**. Minden megosztott hardverprofil esetében válassza ki a pénztárfiókot, és állítsa a **Megosztott műszakfiók** beállítást **Igen** értékre.
    -   **EFT pénztárszám** – Az EFT-terminálazonosító, amelyet az EFT-engedélyek küldésekor kell használni. Ezt az azonosítót a hitelkártya-feldolgozó biztosítja.
    -   **Csomag neve** – A hardverállomás telepítésekor használandó hardverállomás-csomag.

4.  Az üzletben szükséges minden további hardverállomás esetében ismételje meg a 2. és 3. lépést.
5.  Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.
6.  Válassza ki az **1090** elosztási ütemezést az új hardverprofil és az üzlet szinkronizálásához. A POS-hoz **való** módosítások szinkronizálása esetén válassza a Futtatás most lehetőséget.
7.  Válassza ki az **1040** elosztási ütemezést az új hardverállomás és az üzlet szinkronizálásához. A POS-hoz **való** módosítások szinkronizálása esetén válassza a Futtatás most lehetőséget.
8.  Telepítse a hardverállomás minden, a 2. és 3. lépésben beállított gazdagépen. A hardverállomás telepítésével kapcsolatos további tudnivalókért lásd: [A Retail Hardware Station konfigurálása és telepítése](retail-hardware-station-configuration-installation.md).
9.  Telepítse és aktiválja a Modern POS alkalmazást. A Modern POS telepítésével kapcsolatos további tudnivalókért lásd: [A Modern pénztár (MPOS) konfigurálása, telepítése és aktiválása](retail-modern-pos-device-activation.md).
10. Jelentkezzen be a Modern POS alkalmazásba, és válassza a **Nem pénztárgépfiókkal kapcsolatos művelet végrehajtása** lehetőséget+.
11. Indítsa el a **Hardverállomások kezelése** művelet.

12. Válassza a **Kezelés lehetőséget**.
13. A hardverállomás kezelése lapon kapcsolja be a hardverállomást.
14. Válassza ki a használni kívánt hardverállomást, majd válassza a Pár **lehetőséget**.
15. Minden, a Modern POS által használt hardverállomás esetében ismételje meg a 14. lépést.
16. Miután az összes szükséges hardverhibát párosításra kiválasztotta, válassza a Bezárás **lehetőséget**.
17. A hardverállomás kiválasztási lapján válassza ki a legutóbb kiválasztott hardverállomást aktívvá tenni. 

> [!NOTE]
> Ha az eszközök gyakran használnak különböző hardverállomásokat, a Modern POS alkalmazást ajánlott úgy beállítani, hogy a hardverállomás kiválasztását kérje a pénztárosoktól a fizetési folyamat kezdetén. Ugorjon a **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Pénztár beállítása \> Pénztárgépek** pontra. Jelölje ki a pénztárgépet, és állítsa be a **Kiválasztás fizetéskor** opciót az **Igen** értékre. Használja a **1090** elosztási ütemezést a módosítások szinkronizálására a csatornaadatbázisba.

## <a name="extensibility"></a>Bővíthetőség
A hardverállomás bővítési forgatókönyveivel kapcsolatos tudnivalókat lásd a [POS integrálása új hardvereszközrel, és bővítménytelepítő generálása](dev-itpro/hardware-device-extension.md).

## <a name="security"></a>Biztonság
Az aktuális biztonsági előírások szerint a következő beállításokat lehet éles környezetben lehet használni: 

### <a name="hardware-station-installer"></a>Hardverállomás telepítője
A hardverállomás-telepítő automatikusan végrehajtja ezeket a jegyzékmódosításokat az önkiszolgáló telepítés részeként.

-   A Secure Sockets Layer (SSL) használatát le kell tiltani.
-   Csak a Transport Layer Security (TLS) 1.2-es verzióját (vagy a jelenlegi legmagasabb verziót) kell engedélyezni és használni. 

### <a name="ssl-and-tls"></a>SSL és TLS
Alapértelmezés szerint az SSL és a TLS összes verziója le van tiltva, a TLS 1.2 kivételével. Az értékek engedélyezéséhez vagy szerkesztéséhez kövesse az alábbi lépéseket:
    1.  Nyomja le a Windows billentyű + R kombinációt **Futtatás** ablak megnyitásához.
    2.  A Megnyitás **mezőben** írja be a **Regedit parancsot**, majd válassza az **OK gombra.**
    3.  Ha megjelenik a **Felhasználói fiókok** ellenőrzése jelölőnégyzet, válassza az Igen **lehetőséget**.
    4.  A **Beállításjegyzék-szerkesztő** ablakban keresse meg **HKEY\_LOCAL\_MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols** kulcsot. A következő kulcsok bevitele automatikusan megtörtént csak a TLS 1.2 engedélyezéséhez:
        -   TLS 1.2Server:Enabled=1
        -   TLS 1.2Server:DisabledByDefault=0
        -   TLS 1.2Client:Enabled=1
        -   TLS 1.2Client:DisabledByDefault=0
        -   TLS 1.1Server:Enabled=0
        -   TLS 1.1Client:Enabled=0
        -   TLS 1.0Server:Enabled=0
        -   TLS 1.0Client:Enabled=0
        -   SSL 3.0Server:Enabled=0
        -   SSL 3.0Client:Enabled=0
        -   SSL 2.0Server:Enabled=0
        -   SSL 2.0Client:Enabled=0
-   Nincs nyitva további hálózati port, hacsak nincs szükség rá ismert, megadott okból.
-   A forrásokat átfogó erőforrás-megosztást le kell tiltani, és meg kell határozni az engedélyezett, elfogadott forrásokat.
-   Csak megbízható tanúsítványszolgáltatók használhatók a hardverállomást futtató számítógépeken használt tanúsítványok beszerezéséhez.

> [!NOTE]
> Nagyon fontos az IIS biztonsági irányelvek és a Payment Card Industry (PCI) követelmények áttekintése.

## <a name="peripheral-simulator"></a>Perifériaszimulátor
Információért lásd: [Commerce rendszer Periféria-szimulátora](dev-itpro/retail-peripheral-simulator.md).

## <a name="microsoft-tested-peripheral-devices"></a>Microsoft által tesztelt perifériaeszközök
### <a name="ipc-built-in-hardware-station"></a>IPC (beépített) hardverállomás

A következő perifériákat a Modern POS for Windows beépített IPC-hardverállomásnak használatával tesztelték.

#### <a name="printer"></a>Nyomtató

| Gyártó | Modell    | Interfész | Megjegyzések                |
| ------------ | -------- | --------- | ----------------------- |
| Epson        | TM-T88V  | OPOS      |                         |
| Epson        | TM-T88IV | OPOS      |                         |
| HP           | H300     | OPOS      | Tápellátású USB             |
| Star         | TSP650II | Egyéni    | Hálózaton keresztül csatlakozó   |
| Star         | mPOP     | OPOS      | Bluetooth-kapcsolattal csatlakozó |
| Toshiba      | HSP100   | OPOS      |                         |
| Toshiba      | HSP150   | OPOS      |                         |

> [!NOTE]
> A beépített hardverállomás esetén a TSP 100 nyomtató nem támogatott. A beépített hardverállomás 64 bites folyamatot használ, amely nem kompatibilis a meglévő Star TP 100-illesztőprogramokkal. 

#### <a name="bar-code-scanner"></a>Vonalkódolvasó

| Gyártó  | Modell         | Interfész | Megjegyzések |
| ------------- | ------------- | --------- | -------- |
| Datalogic     | Magellan 8400 | OPOS      |          |
| Honeywell     | 1900          | UWP       |          |
| HP-integrált | E1L07AA       | OPOS      |          |
| Szimbólum        | LS2208        | OPOS      |          |

#### <a name="payment-terminals-and-pin-pads"></a>Fizetési terminálok és PIN-billentyűzetek

Dynamics 365 Commerce A <a0/-1><a2/<a2/5><a2/<a3/"<a2/5><a3/ a fizetési szolgáltatások Adyen szolgáltatás [A Dynamics 365 Payment Connector for Adyen az eszköz-adyen](dev-itpro/adyen-connector.md)[payment terminal alkalmazásprogramozási felületet (API)](https://www.adyen.com/blog/introducing-the-terminal-api) használja, és az API által támogatott összes fizetési terminállal kommunikál. A támogatott fizetési terminálok teljes listáját [lásd az Adyen POS terminálok esetében](https://www.adyen.com/pos-payments/terminals).

Egyéni csatlakoztató létrehozásával más fizetési szolgáltatókat Dynamics 365 Commerce is használhat. Bármely fizetési szolgáltató által támogatott fizetési terminál használható a következővel:Dynamics 365 Commerce Ehhez hasonlóan lehetővé teszi bármely, Dynamics 365 Commerce a fizetési szolgáltató által támogatott fizetésieszköz-integrációs modellt, például a helyi IP-t, a felhő API-t vagy a POS-hoz történő közvetlen (például AI-n keresztüli) kapcsolatot. A további tudnivalókat [lásd: Végpontok közötti fizetési integráció létrehozása a fizetési terminálok számára](dev-itpro/end-to-end-payment-extension.md).

#### <a name="cash-drawer"></a>Pénztárfiók

| Gyártó | Modell     | Interfész | Megjegyzések                |
|--------------|-----------|-----------|-------------------------|
| Star         | mPOP      | OPOS      | Bluetooth-kapcsolattal csatlakozó |
| APG          | Atwood    | Egyéni    | Hálózaton keresztül csatlakozó   |
| Star         | SMD2-1317 | OPOS      |                         |
| HP           | QT457AA   | OPOS      |                         |
| Epson        |           | Egyéni    | Összekapcsolva az Epson nyomtatóval DK porton keresztül |

#### <a name="line-display"></a>Sor megjelenítése

| Gyártó | Modell    | Interfész | Megjegyzések |
| ------------ | -------- | --------- | -------- |
| Epson        | DM-D110  | OPOS      |          |
| HP           | T-sorozat | OPOS      |          |

#### <a name="signature-capture"></a>Aláírás rögzítése

| Gyártó | Modell  | Interfész | Megjegyzések |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Lépték

| Gyártó | Típus         | Interfész | Megjegyzések |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>MSR

| Gyártó | Típus       | Interfész | Megjegyzések |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="dedicated-iis-hardware-station"></a>Dedikált IIS-hardverállomás

A következő perifériákat dedikált (nem megosztott) IIS-hardverállomás használatával tesztelték, a Modern POS for Windows és a Cloud POS alkalmazással.

#### <a name="printer"></a>Nyomtató

| Gyártó | Modell    | Interfész | Megjegyzések                |
| ------------ | -------- | --------- | ----------------------- |
| Epson        | TM-T88V  | OPOS      |                         |
| Epson        | TM-T88IV | OPOS      |                         |
| HP           | H300     | OPOS      | Tápellátású USB             |
| Star         | TSP650II | Egyéni    | Hálózaton keresztül csatlakozó   |
| Star         | mPOP     | OPOS      | Bluetooth-kapcsolattal csatlakozó |
| Toshiba      | HSP100   | OPOS      |                         |
| Toshiba      | HSP150   | OPOS      |                         |

#### <a name="bar-code-scanner"></a>Vonalkódolvasó

| Gyártó  | Modell         | Interfész | Megjegyzések |
| ------------- | ------------- | --------- | -------- |
| Datalogic     | Magellan 8400 | OPOS      |          |
| HP-integrált | E1L07AA       | OPOS      |          |
| Szimbólum        | LS2208        | OPOS      |          |

#### <a name="payment-terminals-and-pin-pads"></a>Fizetési terminálok és PIN-billentyűzetek

Dynamics 365 Commerce A <a0/-1><a2/<a2/5><a2/<a3/"<a2/5><a3/ a fizetési szolgáltatások Adyen szolgáltatás A [Dynamics 365 Payment Connector for Adyen az eszköz-adyen](dev-itpro/adyen-connector.md)[fizetési terminál API-t](https://www.adyen.com/blog/introducing-the-terminal-api) használja, és minden olyan fizetési terminállal kommunikálhat, amit ez az API támogat. A támogatott fizetési terminálok teljes listáját [lásd az Adyen POS terminálok esetében](https://www.adyen.com/pos-payments/terminals).

Egyéni csatlakoztató létrehozásával más fizetési szolgáltatókat Dynamics 365 Commerce is használhat. Bármely fizetési szolgáltató által támogatott fizetési terminál használható a következővel:Dynamics 365 Commerce Ehhez hasonlóan lehetővé teszi bármely, Dynamics 365 Commerce a fizetési szolgáltató által támogatott fizetésieszköz-integrációs modellt, például a helyi IP-t, a felhő API-t vagy a POS-hoz történő közvetlen (például AI-n keresztüli) kapcsolatot. A további tudnivalókat [lásd: Végpontok közötti fizetési integráció létrehozása a fizetési terminálok számára](dev-itpro/end-to-end-payment-extension.md).

#### <a name="cash-drawer"></a>Pénztárfiók

| Gyártó | Modell     | Interfész | Megjegyzések              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Egyéni    | Hálózaton keresztül csatlakozó |
| Star         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |
| Epson        |           | Egyéni    | Összekapcsolva az Epson nyomtatóval DK porton keresztül |

#### <a name="line-display"></a>Sor megjelenítése

| Gyártó  | Típus   | Interfész | Megjegyzések |
|---------------|---------|-----------|----------|
| HP-integrált | G6U79AA | OPOS      |          |
| Epson         | M58DC   | OPOS      |          |

#### <a name="signature-capture"></a>Aláírás rögzítése

| Gyártó | Típus  | Interfész | Megjegyzések |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Lépték

| Gyártó | Típus         | Interfész | Megjegyzések |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>MSR

| Gyártó | Típus       | Interfész | Megjegyzések |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="shared-iis-hardware-station"></a>Megosztott IIS-hardverállomás

A következő perifériákat megosztott IIS-hardverállomás használatával tesztelték, a Modern POS for Windows és a Cloud POS alkalmazással. 

> [!NOTE]
> Csak egy nyomtató, fizetési terminál és pénzfiók támogatott.

#### <a name="printer"></a>Nyomtató

| Gyártó | Modell    | Interfész | Megjegyzések                |
| ------------ | -------- | --------- | ----------------------- |
| Epson        | TM-T88V  | OPOS      |                         |
| Epson        | TM-T88IV | OPOS      |                         |
| HP           | H300     | OPOS      | Tápellátású USB             |
| Star         | mPOP     | OPOS      | Bluetooth-kapcsolattal csatlakozó |
| Toshiba      | HSP100   | OPOS      |                         |
| Toshiba      | HSP150   | OPOS      |                         |

#### <a name="payment-terminal"></a>Fizetési terminál

Dynamics 365 Commerce A <a0/-1><a2/<a2/5><a2/<a3/"<a2/5><a3/ a fizetési szolgáltatások Adyen szolgáltatás A [Dynamics 365 Payment Connector for Adyen az eszköz-adyen](dev-itpro/adyen-connector.md)[fizetési terminál API-t](https://www.adyen.com/blog/introducing-the-terminal-api) használja, és minden olyan fizetési terminállal kommunikálhat, amit ez az API támogat. A támogatott fizetési terminálok teljes listáját [lásd az Adyen POS terminálok esetében](https://www.adyen.com/pos-payments/terminals).

Egyéni csatlakoztató létrehozásával más fizetési szolgáltatókat Dynamics 365 Commerce is használhat. Bármely fizetési szolgáltató által támogatott fizetési terminál használható a következővel:Dynamics 365 Commerce Ehhez hasonlóan lehetővé teszi bármely, Dynamics 365 Commerce a fizetési szolgáltató által támogatott fizetésieszköz-integrációs modellt, például a helyi IP-t, a felhő API-t vagy a POS-hoz történő közvetlen (például AI-n keresztüli) kapcsolatot. A további tudnivalókat [lásd: Végpontok közötti fizetési integráció létrehozása a fizetési terminálok számára](dev-itpro/end-to-end-payment-extension.md).

#### <a name="cash-drawer"></a>Pénztárfiók

| Gyártó | Modell     | Interfész | Megjegyzések              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Egyéni    | Hálózaton keresztül csatlakozó |
| Star         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |
| Epson        |           | Egyéni    | Összekapcsolva az Epson nyomtatóval DK porton keresztül |


## <a name="troubleshooting"></a>Hibaelhárítás
### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>A Modern POS észleli a hardverállomást a kiválasztási listájában, de nem tudja befejezni a párosítást

**Megoldás:** Az alábbi listában szereplő lehetséges meghibásodási pontok ellenőrzése:

-   A Modern POS rendszert futtató számítógép megbízik a tanúsítványban, amely a hardverállomást futtató számítógépen fut.
    -   A telepítő ellenőrzéséhez egy webböngészőben nyissa meg a következő URL-címet:  https://&lt;Számítógép neve&gt;:&lt;Port száma&gt;/HardwareStation/ping.
    -   Ez az URL-cím egy ping segítségével ellenőrzi, hogy a számítógép elérhető, és a böngésző jelzi, hogy a tanúsítvány megbízható-e. (Például a címsorban Internet Explorer megjelenik egy zárolási szimbólum. Ennek a szimbólumnak a kiválasztásakor ellenőrzi, Internet Explorer hogy a tanúsítvány jelenleg megbízható-e. Telepítheti a tanúsítványt a helyi számítógépen a megjelenített tanúsítvány adatainak megtekintésével.)
-   A hardverállomást futtató számítógépen a hardverállomás által használt port megnyílik a tűzfalon.
-   A hardverállomás megfelelően telepítette a kereskedői számla adatait a Kereskedői adatok telepítése eszköz segítségével, amely a hardverállomás telepítőjének a végén fut.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>A Modern POS nem tudja észlelni a hardverállomást a kiválasztási listájában

**Megoldás:** A következő tényezők valamelyike okozhatja a hibát:

-   Nincs megfelelően beállítva a hardverállomás a Headquartersban. A további tudnivalókat lásd [a Retail hardverállomás konfigurálása és telepítése.](retail-hardware-station-configuration-installation.md#troubleshooting) 
-   A feladatok még nem futottak a csatornakonfiguráció frissítéséhez. Ebben az esetben futtassa az 1070-es munkát a csatorna konfigurálására.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>A Modern POS nem tükrözi az új pénzfiók-beállításokat

**Megoldás:** Az aktuális köteg lezárása. A pénzfiókon végrehajtott módosítások nem frissülnek a Modern POS alkalmazásban az aktuális köteg lezárásáig.

### <a name="modern-pos-is-reporting-an-issue-with-a-peripheral"></a>A Modern POS a perifériákkal kapcsolatos hibát jelez

**Megoldás:** Az alábbiakban a probléma néhány jellemző oka látható:

-   Győződjön meg arról, hogy bezárta a többi eszköz-illesztőprogram konfigurációs segédprogramot. Ha ezek a segédprogramok nyitva vannak, megakadályozhatják, hogy a Modern POS vagy a hardverállomás átvegye az eszköz vezérlését.
-   Ha a periférián több pénztáreszköz osztozik, győződjön meg arról, hogy a következő kategóriák valamelyikébe tartozik:
    -   Pénzfiók
    -   Nyugtanyomtató
    -   Fizető terminál

    Ha a periféria nem tartozik egyik fenti kategóriába sem, a hardverállomás nem teszi lehetővé a periféria megosztását több pénztáreszköz között.
-   Néha az eszköz-illesztőprogramok okozzák azt, hogy a Common Control Object (CCO) összetevők nem működnek megfelelően. Ha az eszközt nemrégiben telepítették, de nem működik megfelelően, vagy más problémák merülnek fel, gyakran megoldhatja a problémát a CCO-k újratelepítésével. A CCO-k letöltéséhez látogasson el ide: <http://monroecs.com/oposccos_current.htm>.
-   Ha gyakran módosítja a perifériákat tesztelés és hibaelhárítás közben, előfordulhat, hogy alaphelyzetbe kell állítania az IIS-t ahelyett, hogy megvárná a gyorsítótár frissítését. Az ISS alaphelyzetbe állításához kövesse az alábbi lépéseket:
    1.  A **Start** menübe írja be a következőt: **CMD**.
    2.  A keresési eredmények között kattintson a jobb gombbal **a** parancssorra, **majd válassza a Futtatás rendszergazdaként parancsot**.
    3.  A **parancssor** ablakában írja be az **iisreset /Restart** parancsot, majd nyomja le az Enter billentyűt.
    4.  Az IIS újraindítása után indítsa újra a Modern POS alkalmazást.
-   Miközben gyakori változtatásokat hajt végre a perifériákon, ha emellet gyakran indítja el a pénztárügyfelet és lép ki belőle, az előző pénztármunkamenetből származó dllhost folyamat zavarhatja az aktuális munkamenetet. Ebben az esetben az eszköz néha nem használható, amíg be nem zárja az előző munkamenetet kezelő dinamikus csatolású függvénytár (DLL) gazdagépet. A DLL-gazdagép bezárásához kövesse az alábbi lépéseket:
    1.  A **Start** menübe írja be a következőt: **Feladatkezelő**.
    2.  A keresési eredmények között válassza ki a **Feladatkezelőt**.
    3.  A Feladatkezelő Lap **Részletek** lapján válassza ki azt az oszlopfejlécet, **amely** A név feliratú, és betűrendbe rendezi a táblázatot.
    4.  Görgesse lefelé, amíg meg nem találja a dllhost.exe alkalmazást.
    5.  Válasszon ki minden DLL-állomást, majd a Záró **feladatot**.
    6.  A DLL-gazdagépek bezárása után indítsa újra a Modern POS alkalmazást.


## <a name="additional-resources"></a>További erőforrások

[Perifériaszimulátor a Commerce-hez](dev-itpro/retail-peripheral-simulator.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]
