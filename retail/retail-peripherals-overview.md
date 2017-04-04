---
title: "Kiskereskedelmi perifériák – áttekintés"
description: "Ez a témakör ismerteti a kiskereskedelmi perifériák kapcsolatos fogalmakat. A periféria csatlakoztatható a pont (POS) értékesítés, és az összetevők, amelyek a kapcsolatot a POS kezeléséért felelős különböző módszereket írja le."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 268444
ms.assetid: 2ea93e43-8019-49a0-a7f8-325565ebc52d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 79a43c35691f16d773b88faad63c4ab79cb93f1f
ms.openlocfilehash: c6fb3922ba2c4b15f1043d0bcbac40ff2da9a469
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripherals-overview"></a>Kiskereskedelmi perifériák – áttekintés

Ez a témakör ismerteti a kiskereskedelmi perifériák kapcsolatos fogalmakat. A periféria csatlakoztatható a pont (POS) értékesítés, és az összetevők, amelyek a kapcsolatot a POS kezeléséért felelős különböző módszereket írja le.

<a name="concepts"></a>Koncepció
--------

### <a name="pos-registers"></a>POS-pénztárgépek

Navigációs: Kattintson a **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**regisztrálja**. A pont (POS) értékesítés nyilvántartás egy entitás, amely egy adott példánya a POS jellemzőinek meghatározására szolgál. E jellemzők közé a hardverprofil vagy a felhasználó bejelentkezik az említett nyilvántartásban a nyilvántartásban, valamint az üzlet, az oltalom alatt álló hozzárendelt és a vizuális élmény használt kiskereskedelmi perifériák beállításait.

### <a name="devices"></a>Eszközök

Navigációs: Kattintson a **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**eszközök**. Egy eszköz egy olyan entitás, amely egy pénztárhoz rendelt eszköz fizikai reprezentációja. Egy eszköz létrehozásakor van rendelve egy POS nyilvántartásba. Az eszköz-entitás nyomon követi a pénztárgép aktiválásáról, a használt klienstípusról, és az eszközre telepített alkalmazáscsomagról szóló információt. Eszközök rendelhetők a következő alkalmazás típusok: Modern Retail POS, a Retail POS-felhő, kiskereskedelmi Modern POS – Windows Phone, Modern Retail POS – Android és kiskereskedelmi Modern POS – iOS.

### <a name="retail-modern-pos"></a>Retail Modern POS

Modern POS a POS-program, a Microsoft Windows rendszer. A Windows 10 operációs rendszer (OSs) is telepíthető.

### <a name="cloud-pos"></a>Felhő POS

POS felhő a Modern POS program elérhető a webböngészőben böngésző alapú verziója is.

### <a name="modern-pos-for-ios"></a>Az iOS modern POS

Az iOS modern POS iOS eszközök telepíthetők a Modern POS program iOS-alapú változata.

### <a name="modern-pos-for-android"></a>Modern POS for Android

Modern POS for Android Android eszközök telepíthetők a Modern POS program Android-alapú változata.

### <a name="pos-peripherals"></a>POS-perifériák

POS-perifériák olyan eszköz, amely kifejezetten a POS-funkciók támogatottak. A perifériák általában adott osztályokba vannak felosztva. További információt a következő osztályok című "Eszközosztályok" témakör.

### <a name="hardware-station"></a>Hardverállomás

Navigálás: Kattintson a **kereskedelmi és kereskedelmi**&gt;**csatornák**&gt;**a kiskereskedelmi üzletek**&gt;**összes kiskereskedelmi üzletek**. Válasszon egy üzletet, majd kattintson a **Hardverállomások** gyorslapra. A **állomás hardveres** értéke a csatorna szintű beállítás, amely definiálja a példányok, ahol a kiskereskedelmi perifériás logikát alkalmazva lesz. Ezt a beállítást a csatorna szintjén hardver pályaudvar jellemzőinek meghatározására szolgál. A Modern POS példány egy adott raktárban rendelkezésre álló lista hardver állomások is szolgál. A hardver állomás a Modern POS program beépített Windows. A hardver állomás egymástól függetlenül is telepíthető a Microsoft Internet Information Services (IIS) önálló programként. Ebben az esetben is elérhető a hálózaton keresztül.

### <a name="hardware-profile"></a>Hardverprofil

Navigációs: Kattintson a **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**POS profilok**&gt;**hardverprofilok**. A hardverprofil olyan POS-pénztárgép vagy a hardver állomás konfigurált eszközök listáját. A hardverprofil rendelhetők közvetlenül a POS-pénztárgép vagy a hardver állomás.

## <a name="devices-classes"></a>Eszközök osztályok
POS-perifériák általában osztályokba vannak felosztva. Ez a szakasz ismerteti, és áttekintést nyújt a Modern POS támogató eszközök.

### <a name="printer"></a>Nyomtató

Nyomtatók például hagyományos POS bevételezési nyomtatók és egész oldalas nyomtatók. Nyomtató objektumcsatolás és beágyazás a Retail POS (OPOS) és Microsoft Windows illesztőprogram-összeköttetések keresztül támogatja. Legfeljebb két nyomtató használható egyszerre. Ezt a lehetőséget, ahol cash-and-carry vevői nyugták beérkezési nyomtatókon nyomtatott lehetőséget támogat, egy teljes oldalas nyomtató nyomtatott vevői rendelések, amelyek további információkat, mivel. Bevételezési nyomtatók közvetlenül csatlakozó számítógép keresztül USB, via Ethernet hálózathoz csatlakozik vagy csatlakoztatott Bluetooth.

### <a name="scanner"></a>Leolvasó

Legfeljebb két vonalkód képolvasók egyszerre is használható. Ezt a lehetőséget, ha a lapolvasó több mobil szükség annak érdekében, hogy a nagy vagy nehéz elemek beolvasása rögzített beágyazott képolvasó kivételt alkalommal gyorsabb szolgál a legtöbb szabványos méretű elemeket, mivel lehetőséget támogat. Képolvasók OPOS, univerzális Windows Platform (UWP) vagy billentyűzet ék felületek nem használható. Csatlakoztasson képolvasót a számítógéphez az USB- vagy Bluetooth használható.

### <a name="msr"></a>MSR

Egy USB mágnescsík-olvasó (MSR) OPOS-illesztőprogramok segítségével állíthat be. Ha egy önálló MSR elektronikus adatátviteli (EFT) fizetési tranzakciók, az MSR fizetési csatlakoztató kell kezelni. Önálló MSRs vevő hűséges, alkalmazott-bejelentkezés, és ajándék kártya tételt, függetlenül a fizetési csatlakoztató használható.

### <a name="cash-drawer"></a>Pénzfiók

Két cash szekrények / hardverprofil nem használható. Ez a lehetőség lehetővé teszi, hogy pénztárgépenként használhatók egyszerre két aktív műszakban. Megosztott shift, vagy a pénzfiók egyszerre több hordozható POS eszközök által használt hardver profilonként csak egy pénzfiók engedélyezett. Készpénz szekrények közvetlenül kapcsolódik egy számítógéphez USB, hálózati kapcsolat vagy egy nyugtanyomtatója RJ12 összeköttetés keresztül csatlakozik. Néhány esetben készpénz szekrények is csatlakozhatnak Bluetooth.

### <a name="line-display"></a>Sor megjelenítése

Sor megjelenítése termékek, tranzakció egyenlegének és más hasznos információk megjelenítése a vevő a tranzakció során használják. Egy sor megjelenítése OPOS-illesztőprogramok segítségével csatlakozhatnak a számítógéphez USB keresztül.

### <a name="signature-capture"></a>Aláírás rögzítése

Aláírás-rögzítő eszközök OPOS-illesztőprogramok segítségével közvetlenül a számítógép USB keresztül csatlakozhatnak. Aláírás rögzítése úgy van beállítva, ha a vevő kéri bejelentkezni az eszközön. Az aláírás biztosítja, miután a pénztáros elfogadásra látható.

### <a name="scale"></a>Lépték

Mérlegek OPOS-illesztőprogramok segítségével csatlakoztatható a számítógép USP keresztül. Olyan termék, amely egy "Weighed" termék van megjelölve egy tranzakció való hozzáadásakor a POS beolvassa a skála a tömeg, a termék hozzáadása a tranzakcióhoz, és a skálán megadott mennyiséget használja.

### <a name="pin-pad"></a>PIN-billentyűzet

Személyes azonosítószámát (PIN) számgombok OPOS keresztül támogatja, de a kifizetés csatlakozón keresztül lehet kezelni.

### <a name="secondary-display"></a>Másodlagos videokártyaként

Másodlagos kijelző be van állítva, ha a 2-es számú Windows megjelenítési használatos alapvető információk megjelenítése. A másodlagos videokártyaként célja a független szoftvergyártóknak bővítmény támogatja, mert a beépített a másodlagos videokártyaként nem konfigurálható, és korlátozott tartalom megjelenítése.

### <a name="payment-device"></a>Fizetésre szolgáló eszköz

Fizetési eszközök támogatása a fizetési csatlakozón keresztül valósul meg. Fizetési eszközök egy vagy sok más eszközosztályok biztosító funkciók hajtható végre. Például a fizetési eszköz egy MSR: kártyaolvasó, a sor megjelenítése, az Aláírás-rögzítő eszköz vagy a PIN-billentyűzet útválasztójaként működjön. Fizetési eszközök történik, függetlenül az önálló eszköz támogatása, amely más eszközökkel, amelyek szerepelnek a hardverprofil előírt támogatást.

## <a name="supported-interfaces"></a>Támogatott felületek
### <a name="opos"></a>AZ OPOS

Annak biztosítása, hogy az eszközök a legnagyobb tartomány használható Microsoft Dynamics 365 - műveletekhez kiskereskedelmi, a POS ipari szabvány a az OLE a Microsoft Dynamics 365 műveletek - kiskereskedelmi támogatott elsődleges kiskereskedelmi periféria platform. Az OLE POS standard által a nemzeti kiskereskedelmi összevonási (NRF), amely megállapítja a kiskereskedelmi perifériák Számítástechnikai szabványos kommunikációs protokoll állította elő. Az OPOS a POS szabványos OLE széles körben elfogadott végrehajtását. Azt fejlesztették ki, az a mid-1990-es évek, és azóta többször módosult. Az OPOS itt egy eszköz illesztőprogram-architektúra, amely lehetővé teszi a POS – hardverprofil POS Windows-alapú rendszerekkel való integrációját. Az OPOS leíró kommunikációját a POS szoftver- és hardverkompatibilitási szabályozza. Az OPOS-vezérlők két részből áll:

-   **Vezérlőelem-objektum** – az ellenőrzési objektum egy eszköztelepítő-osztály (például sor megjelenítése) a felületet biztosít a program. Monroe konzultációt szolgáltatások ([www.monroecs.com](http://www.monroecs.com/)) kínál standardizált OPOS vezérlő objektumok, amelyek a közös ellenőrző objektumok (CCOs) nevezik. A CCOs segítségével Microsoft Dynamics 365 műveletek – a Retail POS rendszer tesztelése. Ezért a tesztek segítségével garantálja, ha a Microsoft Dynamics 365 műveletek - kiskereskedelmi támogatja eszközosztály keresztül OPOS, többféle eszköz használható, feltéve, hogy a gyártó biztosítja a szolgáltatásobjektum az OPOS épített. Nem kell külön vizsgálat minden egyes eszköz típusa.
-   **A szolgáltatás tárgya** – a szolgáltatás tárgya a vezérlő objektum (szénmonoxid CCO) és az eszköz közötti kommunikációt teszi lehetővé. Általában a szolgáltatásobjektum az eszköz biztosítja az eszköz gyártójával. Azonban egyes esetekben előfordulhat a szolgáltatásobjektum letölthető a gyártó webhelyét. Ha például egy újabb szolgáltatási objektum állhatnak rendelkezésre. A címe a gyártó webhelyén található, a hardver dokumentációjában talál.

[![Objektum és az objektum](./media/retail_peripherals_overview01.png)](./media/retail_peripherals_overview01.png) POS segítségével garantálja, hogy az eszközök gyártói és a POS-gyártók helyesen alkalmazza a standard, ha POS rendszereket és támogatott eszközök együtt dolgozzanak, akkor is, ha azok nem korábban vizsgált együtt OLE OPOS végrehajtásának támogatása. **Megjegyzés:** OPOS-támogatás nem támogatja az összes eszközt, amelyek az OPOS-illesztőprogramok garantálja. A Microsoft Dynamics 365 - műveletekhez kiskereskedelmi először támogatnia kell adott eszköztípust vagy osztály OPOS keresztül. Ezenkívül a szolgáltatás tárgyai nem mindig lehet naprakészen a legújabb verzióját a CCOs. Is kell tudatában annak, hogy általánosságban Szolgáltatásobjektumok minősége függ.

### <a name="windows"></a>Windows

Nyugta nyomtatása a POS az OPOS van optimalizálva. Az OPOS általában sokkal gyorsabb, mint a Windows nyomtatás. Ezért célszerű OPOS, különösen a kiskereskedelmi környezetben, ha 40 oszlop elismervények nyomtatásakor és tranzakciós idők gyors kell használni. A legtöbb eszköz OPOS vezérlők fogja használni. Egyes OPOS beérkezési nyomtatók is Windows illesztőprogramok támogatják. Windows illesztőprogramot használ, elérheti a legújabb betűtípusok és egy hálózati nyomtató több jegyzékbe. Azonban vannak hátrányai Windows illesztőprogramok használata. Íme néhány példa az ilyen hátrányai:

-   A Windows illesztőprogramok használatakor képek jelennek meg, a nyomtatás előtt. Ezért a nyomtatás általában lassabb, mint az OPOS-vezérlőket használó nyomtatók.
-   A nyomtató ("lánckapcsolt") keresztül csatlakoztatott eszközök nem működnek megfelelően Windows illesztőprogramok használatakor. Például a pénztárfiók nem lehet megnyitni, vagy a slip nyomtató várt nem lehet szó.
-   OPOS is támogat egy szélesebb körű jellemző kiskereskedelmi beérkezési nyomtatók, mint például a papír vágás, vagy a slip nyomtatás változók.

OPOS-vezérlők Windows nyomtató használata esetén érhetők el, ha a nyomtató még mindig gond nélkül működniük kell a Microsoft Dynamics 365 műveletek - kiskereskedelmi.

### <a name="universal-windows-platform"></a>Univerzális Windows Platform

UWP, kiskereskedelmi perifériák esetében kapcsolódik a Windows Plug and Play eszközök támogatása. A Plug and Play eszköz a Windows operációs rendszer verziója, amely támogatja az ilyen típusú eszköz csatlakozik, nincs illesztőprogram esetén az eszköz rendeltetésszerű használata szükséges. Például, ha a Windows észleli a hangszóró Bluetooth-eszköz, az operációs rendszer tudja, hogy rendelkezik-e az eszköz a **előadói** osztálytípus. Ezért és azt, hogy az eszköz előadó kezeli. Nincs további beállítási szükség. POS eszközök sok USB-eszköz is csatlakoztatható, és Windows mint emberi összeköttetési eszközök (HIDs) felismeri őket. Azonban nem lehet képes meghatározni a szolgáltatásokat is biztosít az eszköz, mert az eszköz nem adja meg az osztály vagy eszköz típusa. A Windows 10 vonalkód képolvasók és MSRs eszközosztályok kerültek. Ezért ha egy eszköz kijelenti magát Windows 10 ezek az osztályok egyikének eszközként, Windows figyeli a események az eszközről a megfelelő időpontokban. Modern POS UWP MSRs és képolvasókat magába foglaló támogatja. Ezért amikor készen áll az egyik ilyen eszközök, és ezek az osztályok valamelyikébe tartozik eszköz csatlakoztatva van, az eszköz használható. Például ha egy UWP kód képolvasó sáv Windows 10 számítógép csatlakoztatva van, és a vonalkód-bejelentkezés Modern POS van beállítva, a vonalkód-leolvasót aktívvá válik a bejelentkezési képernyőn. Nincs további beállítási szükség. Windows kiegészítő osztályok pont szolgáltatás UWP eszközök hozzáadott. Ezek az osztályok készpénz szekrények és beérkezés nyomtatók osztályok tartalmazzák. A Modern POS új eszközosztályok támogatását függőben.

### <a name="keyboard-wedge"></a>Billentyűzet ék

Billentyűzet ék eszközök adatokat küldjenek a számítógép, mint ha adatok lettek beírva a billentyűzeten. Ezért alapértelmezés szerint aktív a POS mező az adatokat kapni fogja, amely a beolvasott vagy Lehúzott. Bizonyos esetekben a jelenség miatt a megfelelő mezőbe a beolvasandó adatok nem megfelelő típusú. A vonalkód például hitelkártya adatok szánva mezőkbe lesznek megvizsgálhatók. Sok esetben nincs logika, amely meghatározza, hogy az adatok beolvasása vagy Lehúzott vonalkód vagy a kártya lehúzásával a POS-nál. Ezért az adatok megfelelően kezeli. Beállításakor eszközök OPOS, billentyűzet ék eszközök helyett, van azonban pontosabban hogyan ezek az eszközök adatait is fel lehet használni, mert több "ismert" az eszközről, amely az adatok származnak. Vonalkód-leolvasót adatait automatikusan elismerni a vonalkód használatát, és a könnyebb és gyorsabb, mint ha egy általános karakterlánc keresése használták, mint a billentyűzet ék eszközök esetében a kapcsolódó bejegyzés az adatbázisban található.

### <a name="native-printer"></a>Natív nyomtató

Natív (vagy "Eszköz" a típus neve a hardverprofilban) nyomtatók beállítható úgy, hogy a felhasználót a számítógépen konfigurált nyomtató kiválasztása. Ha a nyomtató a **eszköz** típus van beállítva, Modern POS print parancs ütközik, ha a felhasználótól a listában jelöljön ki egy nyomtatót. Ez a viselkedés eltér a viselkedés a Windows-illesztőprogramok, mert a **a Windows** nyomtató típusa a hardverprofil nem jeleníti meg a nyomtatók listáját. Ehelyett van szükség, hogy egy elnevezett nyomtatót kell megadni a **eszköz neve** mezőben.

### <a name="windows"></a>Windows

A **a Windows** nyomtatók csak használt eszköz típusát. Ha Windows-nyomtatót a hardverprofilban van konfigurálva, az adott nyomtató nevét meg kell adni. Modern POS ütközik a nyomtatási eseményeket, ha a Windows-nyomtató úgy van beállítva, ha az esemény továbbítja a megadott Windows-nyomtató. A felhasználó nem kéri a nyomtatót.

### <a name="network"></a>Hálózat

Hálózati címmel rendelkező készpénz szekrények, beérkezés nyomtatók és fizetési terminálok hálózaton közvetlenül a folyamatközi kommunikáció (IPC) hardver állomás a Modern POS for Windows alkalmazásba épített vagy keresztül az IIS hardver állomás más Modern POS ügyfelek esetében használható.

## <a name="hardware-station-deployment-options"></a>Hardver állomás központi telepítési lehetőségek
### <a name="ipc-built-in"></a>Az IPC (beépített)

A folyamatközi kommunikáció (IPC) hardver állomás van beépítve a Modern POS for Windows alkalmazást. A Modern POS for Windows alkalmazás által használt regiszter hardverprofil hozzárendelése az IPC hardver állomás használatához. Hozzon létre egy hardver pályaudvar a **Dedicated** az üzlet, az oltalom alatt álló helyének típusát. Amikor elindítja a Modern POS, az IPC hardver állomás lesz aktív, és a POS-perifériák beállított használatra kész lesz. Ha átmenetileg nincs szüksége a helyi hardver valamilyen okból, a **kezelése a hardver állomások** művelet a állomás hardveres lehetőségek kikapcsolása. Modern POS is használhatja az IPC hardver állomás közvetlenül kommunikálni a network Peripherals céghez.

### <a name="iis"></a>IIS

Az IIS vagy a hardver állomás kétféleképpen önálló verzióját használhatja. A leíró "IIS" azt jelenti, hogy a POS alkalmazás csatlakozik-e a hardver állomáson keresztül a Microsoft Internet Information Services. A POS alkalmazás csatlakozik az IIS hardver állomás webes szolgáltatásokat futtató számítógépen keresztül az eszközök kapcsolódási helyétől. Az IIS használatakor a hardver állomás csatlakozik kiskereskedelmi perifériák is használható, amely ugyanazon a hálózaton, az IIS hardver állomásként POS nyilvántartások által. Csak a Modern POS for Windows tartalmazza a kiskereskedelmi perifériák beépített támogatását, mert minden más Modern POS alkalmazást kell használnia az IIS hardver állomás kommunikálni a hardverprofilban konfigurált POS-perifériák. Emiatt az IIS hardver állomás minden egyes példánya a webes szolgáltatást futtató számítógép és az eszközök kommunikáló alkalmazás szükséges. Az IIS hardver állomás szükség minden nem - Windows Modern POS alkalmazás.

#### <a name="dedicated"></a>Dedikált

Modern POS hardver állomásain használja a **Dedicated** észleli, hogy a perifériák közvetlenül csatlakoztatva a számítógéphez, az alkalmazás helyének típusát. Azonban a **Dedicated** típusú IIS hardver állomásokra vonatkozó is használható. A POS alkalmazás felhő POS használó hagyományos, rögzített POS esetén a **Dedicated** station hardvertípus felhő POS rendszert futtató számítógépen telepített IIS hardver állomások szolgál. Kiskereskedelmi perifériák szempontból az IIS dedikált hardveres állomás jobban kiskereskedelmi perifériás hagyományos, rögzített POS forgatókönyvek támogatása. Dedikált hardveres állomások támogatja az összes perifériás eszközt támogat a hardverprofilban.

#### <a name="shared"></a>Megosztott

Megosztott hardver állomások célja, hogy a nap során több POS eszköz segítségével. Megosztott állomások támogatása csak készpénz szekrények, beérkezés nyomtatók és fizetési terminálok optimalizált hardver. Önálló vonalkód képolvasók, MSRs, sorban megjeleníti, mérleg vagy más eszközök közvetlenül csatlakozni. Ellenkező esetben ütközés igényelni a perifériák egyszerre több POS eszköz közben történik. Itt látható, hogyan kezeli az ütközéseket a támogatott eszközök:

-   **Pénzfiók** – a pénztárfiók keresztül küld az eszköz esemény nyitja meg. Csak akkor történik, amikor a pénzfiók nevezik probléma akkor jelentkezik, ha a pénztárfiók már meg nyitva. Megosztott hardver állomások, esetében a pénztárfiók értékre kell állítani **megosztott** a hardverprofilban. Ez a beállítás megakadályozza, hogy a POS ellenőrzése a pénztárfiók már nyitott Megnyitás parancsokat küld.
-   **Nyugtanyomtatója** – két beérkezési nyomtatási parancsok kerülnek a hardver állomás egy időben, a parancsok egyikét is elveszhet, az eszköztől függően. Egyes eszközök belső memória van, vagy a készletezés, amely megakadályozhatja, hogy a probléma. Print parancs nem sikeres, ha a pénztáros hibaüzenetet kap, és a print parancs a POS-ból próbálkozás.
-   **Fizetési terminál** – Ha a pénztáros megpróbálja pályázati egy fizetési terminál egy tranzakciót, amely már használatban van, egy üzenet értesíti a pénztáros, hogy a terminál használatban van, és megkérdezi, hogy a pénztáros próbálkozzon újra később. A pénztárosok általában látható, hogy a terminál már használatban van, és várakozik, amíg a másik tranzakció befejezése előtt újra pályázati próbálnak.

Valamely jövőbeli programverzióban felismeri, hogy nem támogatott eszközök be vannak állítva egy megosztott hardver állomás hozzárendelt hardverprofil tervezett ellenőrzési. Nem támogatott eszközöket fedez fel, ha a felhasználó kap egy üzenetet, amely arról tájékoztatja, hogy az eszközök megosztott hardver állomások nem használható. Megosztott hardver állomások, esetében a **kijelölése esetén a pályázati** beállítás **Igen** a tételjegyzék szintjén. A POS-felhasználó majd válasz kiválasztására kéri a hardver állomás ajánlatot kijelölésekor a POS-tranzakciókhoz. Csak a pályázat idején a hardver állomás kijelölésekor a hardver állomás kiválasztása közvetlenül a POS munkafolyamat mobil környezetben kerül. További előnye, mint a terminál kifizetési sor megjelenítése megosztott környezetben használják. Ha a fizetési terminál egy sor megjelenítése használják, más felhasználók a Terminálszolgáltatások segítségével a tranzakció befejezéséig blokkolhatja. Mobil esetekben sorok tranzakció hosszabb időszakra is hozzáadódik. Ezért a **kijelölése esetén a pályázati** kapcsoló szükséges optimális eszköz rendelkezésre állásának biztosítása érdekében.

### <a name="network-peripherals"></a>Network Peripherals céghez

Hálózati eszközök a hardverprofilban kijelölése lehetővé teszi a készpénz szekrények, beérkezés nyomtatók és fizetési terminálok hálózati kapcsolaton keresztül kell csatlakoztatni.

#### <a name="modern-pos-for-windows"></a>Modern POS for Windows

Két helyen network Peripherals céghez tartozó IP-címeket is megadhat. Ha a Modern POS Windows ügyfél egy adott csoportját network Peripherals céghez használ, az IP-címeket az eszközökhöz tartozó meg segítségével a **IP-konfiguráció** meg magát a jegyzékhez a műveletpanelen lehetőség. Hálózati eszközök közös POS-pénztárgépek között, amely rendelkezik hozzárendelt hálózati eszközök hardverprofil rendelhetők közvetlenül egy megosztott hardver állomás. IP-címek hozzárendelése, jelölje ki a hardver állomás a **kiskereskedelmi üzletek** oldal, és alkalmazza a **IP-konfiguráció** lehetőségével a **hardver állomások** szakaszban adja meg a hálózati eszközök hardver pályaudvarért rendelt. Hardver állomások, amelyek csak a hálózati eszközöket nem kell telepíteni a hardver állomás magát. Ebben az esetben a hardver állomás van szükség csak elméletben a helyük a kiskereskedelmi üzlet a megfelelő hálózati címmel rendelkező eszközök csoportosítása.

#### <a name="cloud-pos-modern-pos-for-ios-and-modern-pos-for-android"></a>Felhő POS, Modern POS az iOS és Android a Modern POS

A meghajtók fizikailag csatlakoztatott és hálózati címmel rendelkező perifériák logikájának a hardver állomás található. POS ügyfelek kivételével a Modern POS for Windows, ezért egy IIS hardver állomáson kell telepített és aktív ahhoz, hogy a POS perifériákat, függetlenül attól, hogy azok perifériák fizikailag csatlakoztatott hardver állomáson vagy foglalkozik a hálózaton keresztül kommunikáljon.

## <a name="setup-and-configuration"></a>Telepítés és beállítás
### <a name="hardware-station-installation"></a>Hardvertelepítés állomás

Információ: [kiskereskedelmi hardver állomás konfigurációs és telepítési](retail-hardware-station-configuration-installation.md).

### <a name="modern-pos-for-windows-setup-and-configuration"></a>Modern POS for Windows telepítés és beállítás

Információ: [a Modern Retail POS konfigurációs és telepítési](retail-modern-pos-device-activation.md).

### <a name="opos-device-setup-and-configuration"></a>Az OPOS-eszköz telepítése és beállítása

További információt a OPOS összetevők című "Támogatott felületek" dokumentum. Az OPOS-illesztőprogramok általában az eszköz gyártója által biztosított. Az OPOS eszközillesztő telepítve van, amikor egy kulcsot hozzáadja a Windows rendszerleíró adatbázis a következő helyek egyikén:

-   **32 bites rendszer:** HKEY\_helyi\_MACHINESOFTWAREOLEforRetailServiceOPOS
-   **64 bites rendszerben:** HKEY\_helyi\_MACHINESOFTWAREWOW6432NodeOLEforRetailServiceOPOS

A ServiceOPOS rendszerleíró helyre konfigurált eszközök az OPOS eszköztelepítő-osztály szerint vannak rendezve. Több eszköz-illesztőprogramokat a rendszer menti.

## <a name="supported-scenarios-by-hardware-station-type"></a>Forgatókönyvek hardvertípus állomás által támogatott
### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Ügyfelek támogatása – az IPC hardver állomás és az IIS hardver állomás

A következő táblázat a topológiákat és telepítési forgatókönyvek támogatottak.

| Ügyfél      | Az IPC hardver állomás | Az IIS hardver állomás |
|-------------|----------------------|----------------------|
| Windows-alkalmazás | Igen                  | Igen                  |
| Felhő POS   | Nincs                   | Igen                  |
| Android     | Nincs                   | Igen                  |
| iOS         | Nincs                   | Igen                  |

### <a name="network-peripherals"></a>Network Peripherals céghez

A Modern POS for Windows alkalmazás beépített hardver állomás segítségével közvetlenül nem használható Network Peripherals céghez. Más ügyfelek esetében telepíteni kell az IIS hardver állomás.

| Ügyfél      | Az IPC hardver állomás | Az IIS hardver állomás |
|-------------|----------------------|----------------------|
| Windows-alkalmazás | Igen                  | Igen                  |
| Felhő POS   | Nincs                   | Igen                  |
| Android     | Nincs                   | Igen                  |
| iOS         | Nincs                   | Igen                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Eszköztípusok hardvertípus állomás által támogatott
### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS for Windows egy IPC (beépített) hardver állomáson

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Támogatott eszköz osztály</th>
<th>Támogatott felületek</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nyomtató</td>
<td><ul>
<li>AZ OPOS</li>
<li>Windows-illesztőprogram</li>
<li>Eszköz</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="even">
<td>2. nyomtató</td>
<td><ul>
<li>AZ OPOS</li>
<li>Windows-illesztőprogram</li>
<li>Eszköz</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="odd">
<td>Sor megjelenítése</td>
<td>AZ OPOS</td>
</tr>
<tr class="even">
<td>Két kijelző</td>
<td>Windows-illesztőprogram</td>
</tr>
<tr class="odd">
<td>MSR</td>
<td><ul>
<li>AZ OPOS</li>
<li>UWP (nem kell beállítani.)</li>
<li>Billentyűzet ék (nem kell beállítani.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Kiállító</td>
<td><ul>
<li>AZ OPOS</li>
<li>Hálózati <strong>Megjegyzés:</strong> Ha csak egy fiók be lehet állítani <strong>használata megosztott shift</strong> a fiók van beállítva.</li>
</ul></td>
</tr>
<tr class="odd">
<td>2. fiók</td>
<td><ul>
<li>AZ OPOS</li>
<li>Hálózati <strong>Megjegyzés:</strong> Ha csak egy fiók be lehet állítani <strong>használata megosztott shift</strong> a fiók van beállítva.</li>
</ul></td>
</tr>
<tr class="even">
<td>Leolvasó</td>
<td><ul>
<li>AZ OPOS</li>
<li>UWP (nem kell beállítani.)</li>
<li>Billentyűzet ék (nem kell beállítani.)</li>
</ul></td>
</tr>
<tr class="odd">
<td>2. leolvasó</td>
<td><ul>
<li>AZ OPOS</li>
<li>UWP (nem kell beállítani.)</li>
<li>Billentyűzet ék (nem kell beállítani.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Lépték</td>
<td>AZ OPOS</td>
</tr>
<tr class="odd">
<td>PIN-billentyűzet</td>
<td>Az OPOS (nyújtott támogatás a fizetési csatlakoztató testreszabással.)</td>
</tr>
<tr class="even">
<td>Aláírás rögzítése</td>
<td>AZ OPOS</td>
</tr>
<tr class="odd">
<td>Fizető terminál </td>
<td><ul>
<li>Egyéni eszközök támogatása</li>
<li>Hálózati (További információ a fizetési összekötő dokumentációjában talál.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Modern POS ügyfelek csak egy IIS dedikált hardveres állomás

**Megjegyzés:** az IIS hardver állomás "fordítja," Amikor a POS-ügyfél és a hardver állomás között-az-egyhez kapcsolat áll fenn.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Támogatott eszköz osztály</th>
<th>Támogatott felületek</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nyomtató</td>
<td><ul>
<li>AZ OPOS</li>
<li>Windows-illesztőprogram <strong>Megjegyzés:</strong> a Windows-nyomtatókat a hálózaton, a felhasználó a hardver állomás a nyomtató eléréséhez engedéllyel kell rendelkeznie.</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="even">
<td>2. nyomtató</td>
<td><ul>
<li>AZ OPOS</li>
<li>Windows-illesztőprogram</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="odd">
<td>Sor megjelenítése</td>
<td>AZ OPOS</td>
</tr>
<tr class="even">
<td>MSR</td>
<td>AZ OPOS</td>
</tr>
<tr class="odd">
<td>Kiállító</td>
<td><ul>
<li>AZ OPOS</li>
<li>Hálózati <strong>Megjegyzés:</strong> ha hardver profilonként csak egy fiók be lehet állítani <strong>használata megosztott shift</strong> a fiók van beállítva.</li>
</ul></td>
</tr>
<tr class="even">
<td>2. fiók</td>
<td><ul>
<li>AZ OPOS</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="odd">
<td>Leolvasó</td>
<td>AZ OPOS</td>
</tr>
<tr class="even">
<td>2. leolvasó</td>
<td>AZ OPOS</td>
</tr>
<tr class="odd">
<td>Lépték</td>
<td>AZ OPOS</td>
</tr>
<tr class="even">
<td>PIN-billentyűzet</td>
<td>Az OPOS (nyújtott támogatás a fizetési csatlakoztató testreszabással.)</td>
</tr>
<tr class="odd">
<td>SIG rögzítés</td>
<td>AZ OPOS</td>
</tr>
<tr class="even">
<td>Fizető terminál </td>
<td><ul>
<li>Egyéni eszközök támogatása</li>
<li>Hálózati (További információ a fizetési összekötő dokumentációjában talál.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Modern POS ügyfelek csak egy megosztott IIS hardver állomás

**Megjegyzés:** megosztásakor az IIS hardver állomás"," több eszköz egyszerre használhatja a hardver állomás. Ebben az esetben csak az alábbi táblázatban felsorolt eszközöket kell használnia. Megpróbál megosztani az eszközök, amelyek nem jelennek meg itt, például vonalkód képolvasók és MSRs, ha hiba fordul elő, ha több eszközt próbál igényelni a azonos periféria. A jövőben ilyen konfiguráció kifejezetten meggátolja.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Támogatott eszköz osztály</th>
<th>Támogatott felületek</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nyomtató</td>
<td><ul>
<li>AZ OPOS</li>
<li>Windows-illesztőprogram <strong>Megjegyzés:</strong> a Windows-nyomtatókat a hálózaton, a felhasználó a hardver állomás a nyomtató eléréséhez engedéllyel kell rendelkeznie.</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="even">
<td>2. nyomtató</td>
<td><ul>
<li>AZ OPOS</li>
<li>Windows-illesztőprogram</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="odd">
<td>Kiállító</td>
<td><ul>
<li>AZ OPOS</li>
<li>Hálózati <strong>Megjegyzés:</strong> ha hardver profilonként csak egy fiók be lehet állítani <strong>használata megosztott shift</strong> a fiók van beállítva.</li>
</ul></td>
</tr>
<tr class="even">
<td>2. fiók</td>
<td><ul>
<li>AZ OPOS</li>
<li>Hálózat</li>
</ul></td>
</tr>
<tr class="odd">
<td>Fizető terminál </td>
<td><ul>
<li>Egyéni eszközök támogatása</li>
<li>Hálózati (További információ a fizetési összekötő dokumentációjában talál.)</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Konfiguráció támogatott forgatókönyvek
Hardverprofilok létrehozásával kapcsolatos további tudnivalókért lásd: [megadása és karbantartása a csatorna ügyfélprogramokat, köztük a nyilvántartások és hardver állomások](define-maintain-channel-clients-registers-hw-stations.md). **Megjegyzés:** Microsoft Dynamics 365 1611 műveletek verziójához, a hardverprofil állomás már nem használatos. Attribútumok, amelyek korábban úgy állítottuk be a hardverprofilban állomás most a hardver állomás maga részét képezik.

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS for Windows egy IPC (beépített) hardver állomáson

Ebben a konfigurációban a leggyakoribb beállítás a hagyományos, rögzített POS-pénztárgépek. Ebben a forgatókönyvben a hardverprofil-adatainak van rendelve közvetlenül maga a nyilvántartásban. EFT-terminálszám magát a nyilvántartásban kell meghatározni. Ez a konfiguráció beállításához kövesse az alábbi lépéseket.

1.  Hozzon létre egy hardverprofilt, ahol minden szükséges periféria vannak konfigurálva.
2.  A POS-pénztárgép képezze le a hardverprofilt.
3.  Hozzon létre egy hardver pályaudvar a **Dedicated** a kiskereskedelmi üzlet a POS-pénztárgép helyének típusát. Leírás megadása nem kötelező. **Megjegyzés:** ne kelljen a hardver állomáson bármely egyéb tulajdonságainak beállítása. Minden más szükséges információt, például a hardverprofil magát a regiszterből származnak.
4.  Kattintson a **kereskedelmi és kereskedelmi**&gt;**a Retail IT**&gt;**elosztási ütemezés**.
5.  Válassza ki a **1090** elosztási ütemezés szinkronizálni az új hardverprofil az üzlethez. Kattintson a **futtatása most** a POS változások szinkronizálása.
6.  Válassza ki a **1040** elosztási ütemezés szinkronizálni az új hardver-állomás az üzlethez. Kattintson a **futtatása most** a POS változások szinkronizálása.
7.  Telepítse és aktiválja a Modern POS for Windows.
8.  Indítsa el a Modern POS for Windows, és a kapcsolódó perifériák használatának megkezdéséhez.

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Modern POS ügyfelek csak egy IIS dedikált hardveres állomás

Ez a konfiguráció alkalmas Modern POS ügyfelek csak egy kizárólag egy POS által használt hardver-állomás regisztrálja. Ez a konfiguráció beállításához kövesse az alábbi lépéseket.

1.  Hozzon létre egy hardverprofilt, ahol minden szükséges periféria vannak konfigurálva.
2.  Hozzon létre egy hardver pályaudvar a **Dedicated** a kiskereskedelmi üzlet a POS-pénztárgép helyének típusát.
3.  A dedikált hardveres állomáson a következő tulajdonságok beállításával:
    -   **Állomásnév** – ahol a hardver állomás futni fog a gazdaszámítógép nevét. **Megjegyzés:** POS felhő megoldható **localhost** a helyi számítógépen, amelyen fut felhő POS meghatározásához. Azonban a tanúsítvány, amely szükséges ahhoz, hogy a hardver állomás felhő POS párosítani is rendelkeznie kell "a Localhost" a számítógép neve. Problémák elkerülése érdekében azt javasoljuk, hogy szükség szerint az üzlet minden dedikált hardveres állomás példánya listára. Minden hardver állomás az állomásnevet kell az adott számítógép nevét ahol a hardver van telepítve lesz.
    -   **Port** – a port a hardver állomás segítségével a Modern POS-ügyfél kommunikál.
    -   **Hardverprofil** – Ha a hardverprofil nem feltéve állomáson a hardver magát, a hardverprofil az oltalom alatt álló rendelt lesz.
    -   **EFT POS hány** – az EFT-Terminálazonosító EFT engedélyek küldésekor használni. Ez az azonosító a hitelkártya-feldolgozó által biztosított.
    -   **Csomag neve** – a hardver station csomagot használja, ha a hardver-állomás telepítve van.

4.  Kattintson a **kereskedelmi és kereskedelmi**&gt;**a Retail IT**&gt;**elosztási ütemezés**.
5.  Válassza ki a **1090** elosztási ütemezés szinkronizálni az új hardverprofil az üzlethez. Kattintson a **futtatása most** a POS változások szinkronizálása.
6.  Válassza ki a **1040** elosztási ütemezés szinkronizálni az új hardver-állomás az üzlethez. Kattintson a **futtatása most** a POS változások szinkronizálása.
7.  Telepítse a hardver állomás. A hardver állomás telepítésével kapcsolatos további tudnivalókért lásd: [kiskereskedelmi hardver állomás konfigurációs és telepítési](retail-hardware-station-configuration-installation.md).
8.  Telepítse és aktiválja a Modern POS. Modern POS telepítésével kapcsolatos további tudnivalókért lásd: [a Modern Retail POS konfigurációs és telepítési](retail-modern-pos-device-activation.md).
9.  Jelentkezzen be a Modern POS, és válassza a **nem fiók műveletek**.
10. Indítsa el a **kezelése, hardver állomások** művelet.
11. Kattintson a **kezelésére**.
12. A hardver állomás kezelése lapon állítsa be, hogy kapcsolja be a hardver állomás.
13. Jelölje ki, majd kattintson a hardver állomás **pár**.
14. Miután a hardver állomás van párosított, kattintson a **közeli**.
15. A hardver állomás kiválasztása lapon kattintson a legutóbb kijelölt hardver állomás tegye aktívvá.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Modern POS ügyfelek csak egy megosztott IIS hardver állomás

Ez a konfiguráció alkalmas Modern POS ügyfelek hardver állomások megosztani más eszközökkel. Ez a konfiguráció beállításához kövesse az alábbi lépéseket.

1.  Ha vannak beállítva a szükséges perifériák Hardverprofil létrehozása.
2.  Hozzon létre egy hardver pályaudvar a **megosztott** a kiskereskedelmi üzlet a POS-pénztárgép helyének típusát.
3.  A megosztott hardver állomáson a következő tulajdonságok beállításával:
    -   **Állomásnév** – ahol a hardver állomás futni fog a gazdaszámítógép nevét.
    -   **Leírás** – szöveg, amely segít a azonosítja a hardver állomás például a **vissza** vagy **tároló első**.
    -   **Port** – a port a hardver állomás segítségével a Modern POS-ügyfél kommunikál.
    -   **Hardverprofil** – megosztott hardver állomások, minden hardver állomás tartalmaznia kell egy hardverprofilt. A hardverprofilok hardver állomások között megosztható, de meg kell adni minden egyes hardver helytől. Ezen kívül javasoljuk megosztott műszakok használja az azonos megosztott hardver állomás több eszköz használatakor. Megosztott shift beállításához kattintson a **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**POS profilok**&gt;**a hardverprofilok**. Minden megosztott hardverprofil, válassza ki a pénztárfiók, és a **megosztott shift fiók** be **Igen**.
    -   **EFT POS hány** – az EFT-Terminálazonosító EFT engedélyek küldésekor használni. Ez az azonosító a hitelkártya-feldolgozó által biztosított.
    -   **Csomag neve** – a hardver station csomagot használja, ha a hardver-állomás telepítve van.

4.  Minden további hardver állomás, amely szükséges az üzlet ismételje meg a 2. és 3.
5.  Kattintson a **kereskedelmi és kereskedelmi**&gt;**a Retail IT**&gt;**elosztási ütemezés**.
6.  Válassza ki a **1090** elosztási ütemezés szinkronizálni az új hardverprofil az üzlethez. Kattintson a **futtatása most** a POS változások szinkronizálása.
7.  Válassza ki a **1040** elosztási ütemezés szinkronizálni az új hardver-állomás az üzlethez. Kattintson a **futtatása most** a POS változások szinkronizálása.
8.  Telepítse a hardver állomás minden állomáson, 2 és 3 lépést beállított. A hardver állomás telepítésével kapcsolatos további tudnivalókért lásd: [kiskereskedelmi hardver állomás konfigurációs és telepítési](retail-hardware-station-configuration-installation.md).
9.  Telepítse és aktiválja a Modern POS. Modern POS telepítésével kapcsolatos további tudnivalókért lásd: [a Modern Retail POS konfigurációs és telepítési](retail-modern-pos-device-activation.md).
10. Jelentkezzen be a Modern POS, és válassza a **nem fiók műveletek**.
11. Indítsa el a **kezelése, hardver állomások** művelet.

12. Kattintson a **kezelésére**.
13. A hardver állomás kezelése lapon állítsa be, hogy kapcsolja be a hardver állomás.
14. Jelölje ki, majd kattintson a hardver állomás **pár**.
15. Minden Modern POS által használt hardver állomás ismételje meg a 14.
16. Miután a szükséges hardver-állomások párosított vannak, kattintson a **közeli**.
17. A hardver állomás kiválasztása lapon kattintson a legutóbb kijelölt hardver állomás tegye aktívvá. **Megjegyzés:** eszközök gyakran használják a különböző hardver-állomásokon, ha ajánlott megadását kérje a hardver állomáson bejelölni, ha a pályázati eljárás megkezdése a pénztárosok Modern POS beállítani, hogy. Kattintson a **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**regisztrálja az**. Jelölje ki a nyilvántartásban, és állítsuk be a **kiválasztása után a pályázat** be **Igen**. Használja a **1090** elosztási ütemezés a csatorna adatbázis módosításainak szinkronizálását.

## <a name="extensibility"></a>Bővíthetőség
Információt a hardver pályaudvar bővítési forgatókönyvek, lásd: [állomás hardver bővítési](dev-itpro/hardware-station-extensibility.md).

## <a name="security"></a>Biztonság
Aktuális biztonsági normáknak megfelelően az alábbi beállításokat a termelési környezetben használható: **Megjegyzés:** a hardver állomás telepítő automatikusan végrehajtja ezeket a módosításokat az önkiszolgáló áruház-telepítés részeként.

-   Secure Sockets Layer (SSL) le kell tiltani.
-   Csak Transport Layer Security (TLS) 1.2-es verziója (vagy a jelenlegi legmagasabb verziójú) kell engedélyezni és használni. **Megjegyzés:** alapértelmezés szerint az SSL és a TLS TLS 1.2 kivételével az összes verzióját le vannak tiltva. Ezek az értékek engedélyezése vagy szerkeszteni, kövesse az alábbi lépéseket:
    1.  Nyomja le a Windows billentyű kulcs + S billentyűvel nyissuk meg a **futtatni** ablakot.
    2.  A a **nyitott** mezőjébe írja be a **Regedit**, majd **OK**.
    3.  Ha egy **felhasználói fiókok felügyelete** üzenetablak jelenik meg, kattintson a **Igen**.
    4.  A a **a Rendszerleíróadatbázis-szerkesztő** ablakban keresse meg **HKEY\_helyi\_MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols**. A következő billentyűk csak a TLS 1.2 engedélyezése automatikusan van megadva:
        -   TLS 1.2Server: engedélyezve = 1
        -   TLS-1.2Server:DisabledByDefault = 0
        -   TLS 1.2Client: engedélyezve = 1
        -   TLS-1.2Client:DisabledByDefault = 0
        -   TLS 1.1Server: engedélyezve = 0
        -   TLS 1.1Client: engedélyezve = 0
        -   TLS 1.0Server: engedélyezve = 0
        -   TLS 1.0Client: engedélyezve = 0
        -   SSL 3.0Server: engedélyezve = 0
        -   SSL 3.0Client: engedélyezve = 0
        -   SSL 2.0Server: engedélyezve = 0
        -   SSL 2.0Client: engedélyezve = 0
-   Nincs további hálózati portokat kell nyitva, kivéve, ha ismert, meghatározott okokból szükséges.
-   Cross-eredetű erőforrás-megosztás le kell tiltani, és meg kell határozniuk az engedélyezett származású elfogadott.
-   Csak a megbízható tanúsítványszolgáltatók használandó hardver pályaudvar futtató számítógépeken használt tanúsítványokat beszerezni.

**Megjegyzés:** nagyon fontos biztonsági irányelveket az IIS Szolgáltatáshoz és a fizetési üdvözlőlap ipar (PCI) követelmények áttekintése.

## <a name="peripheral-simulator"></a>Perifériaszimulátor
Információ: [kiskereskedelmi perifériás szimulátor](retail-peripheral-simulator.md).

## <a name="microsofttested-peripheral-devices"></a>Microsofttested perifériák
### <a name="ipc-built-in-hardware-station"></a>Az IPC (beépített) hardver állomás

A következő perifériákat vizsgálták a Modern POS for Windows rendszerbe épített IPC hardver állomás segítségével.

#### <a name="printer"></a>Nyomtató

| Gyártó | Típus    | Interfész | Megjegyzések                |
|--------------|----------|-----------|-------------------------|
| Epson        | TM-T88IV | AZ OPOS      |                         |
| Epson        | TM-T88V  | AZ OPOS      |                         |
| Csillag         | TSP650II | AZ OPOS      |                         |
| Csillag         | TSP650II | Egyéni    | Hálózaton keresztül csatlakozó   |
| Csillag         | mPOP     | AZ OPOS      | Bluetooth kapcsolat |
| HP           | F7M67AA  | AZ OPOS      | Táplálású USB             |

#### <a name="bar-code-scanner"></a>Vonalkódolvasó

| Gyártó  | Típus         | Interfész | Megjegyzések |
|---------------|---------------|-----------|----------|
| Motorola      | DS9208        | AZ OPOS      |          |
| Honeywell     | 1900          | UWP       |          |
| Szimbólum        | LS2208        | AZ OPOS      |          |
| Integrált HP | E1L07AA       | AZ OPOS      |          |
| Datalogic     | Magellan 8400 | AZ OPOS      |          |

#### <a name="pin-pad"></a>PIN-billentyűzet

| Gyártó | Típus  | Interfész | Megjegyzések                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | AZ OPOS      | A fizetési csatlakoztató testreszabás igényel |

#### <a name="payment-terminal"></a>Fizető terminál 

| Gyártó | Típus | Interfész | Megjegyzések                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Egyéni    | A fizetési csatlakoztató testreszabás igényel                                |
| VeriFone     | MX925 | Egyéni    | A fizetési csatlakoztató; testreszabás igényel a hálózati és USB keresztül |
| VeriFone     | MX915 | Egyéni    | A fizetési csatlakoztató; testreszabás igényel a hálózati és USB keresztül |

#### <a name="cash-drawer"></a>Pénzfiók

| Gyártó | Típus     | Interfész | Megjegyzések                |
|--------------|-----------|-----------|-------------------------|
| Csillag         | mPOP      | AZ OPOS      | Bluetooth kapcsolat |
| APG          | Atwood    | Egyéni    | Hálózaton keresztül csatlakozó   |
| Csillag         | SMD2-1317 | AZ OPOS      |                         |
| HP           | QT457AA   | AZ OPOS      |                         |

#### <a name="line-display"></a>Sor megjelenítése

| Gyártó  | Típus   | Interfész | Megjegyzések |
|---------------|---------|-----------|----------|
| Integrált HP | G6U79AA | AZ OPOS      |          |
| Epson         | M58DC   | AZ OPOS      |          |

#### <a name="signature-capture"></a>Aláírás rögzítése

| Gyártó | Típus  | Interfész | Megjegyzések |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | AZ OPOS      |          |

#### <a name="scale"></a>Lépték

| Gyártó | Típus         | Interfész | Megjegyzések |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | AZ OPOS      |          |

#### <a name="msr"></a>MSR

| Gyártó | Típus       | Interfész | Megjegyzések |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | AZ OPOS      |          |
| HP           | IDRA-334133 | AZ OPOS      |          |

### <a name="dedicated-iis-hardware-station"></a>Dedikált IIS hardver állomás

A következő perifériákat egy kijelölt (nem megosztott) IIS hardver állomás felhő POS és Modern POS for Windows segítségével vizsgálták.

#### <a name="printer"></a>Nyomtató

| Gyártó | Típus    | Interfész | Megjegyzések                  |
|--------------|----------|-----------|---------------------------|
| Epson        | TM-T88IV | AZ OPOS      |                           |
| Epson        | TM-T88V  | AZ OPOS      |                           |
| Csillag         | TSP650II | AZ OPOS      |                           |
| Csillag         | TSP650II | Egyéni    | Hálózaton keresztül csatlakozó     |
| Csillag         | TSP100   | AZ OPOS      | TSP650II illesztőprogramokra van szüksége |
| HP           | F7M67AA  | AZ OPOS      | Táplálású USB               |

#### <a name="bar-code-scanner"></a>Vonalkódolvasó

| Gyártó  | Típus   | Interfész | Megjegyzések |
|---------------|---------|-----------|----------|
| Motorola      | DS9208  | AZ OPOS      |          |
| Szimbólum        | LS2208  | AZ OPOS      |          |
| Integrált HP | E1L07AA | AZ OPOS      |          |

#### <a name="pin-pad"></a>PIN-billentyűzet

| Gyártó | Típus  | Interfész | Megjegyzések                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | AZ OPOS      | A fizetési csatlakoztató testreszabás igényel |

#### <a name="payment-terminal"></a>Fizető terminál 

| Gyártó | Típus | Interfész | Megjegyzések                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Egyéni    | A fizetési csatlakoztató testreszabás igényel                                |
| VeriFone     | MX925 | Egyéni    | A fizetési csatlakoztató; testreszabás igényel a hálózati és USB keresztül |
| VeriFone     | MX915 | Egyéni    | A fizetési csatlakoztató; testreszabás igényel a hálózati és USB keresztül |

#### <a name="cash-drawer"></a>Pénzfiók

| Gyártó | Típus     | Interfész | Megjegyzések              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Egyéni    | Hálózaton keresztül csatlakozó |
| Csillag         | SMD2-1317 | AZ OPOS      |                       |
| HP           | QT457AA   | AZ OPOS      |                       |

#### <a name="line-display"></a>Sor megjelenítése

| Gyártó  | Típus   | Interfész | Megjegyzések |
|---------------|---------|-----------|----------|
| Integrált HP | G6U79AA | AZ OPOS      |          |
| Epson         | M58DC   | AZ OPOS      |          |

#### <a name="signature-capture"></a>Aláírás rögzítése

| Gyártó | Típus  | Interfész | Megjegyzések |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | AZ OPOS      |          |

#### <a name="scale"></a>Lépték

| Gyártó | Típus         | Interfész | Megjegyzések |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | AZ OPOS      |          |

#### <a name="msr"></a>MSR

| Gyártó | Típus       | Interfész | Megjegyzések |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | AZ OPOS      |          |
| HP           | IDRA-334133 | AZ OPOS      |          |

### <a name="shared-iis-hardware-station"></a>Megosztott IIS hardver állomás

A következő perifériákat felhő POS és Modern POS for Windows megosztott IIS hardver állomás segítségével vizsgálták. **Megjegyzés:** csak egy nyomtató, a fizetési terminál és a pénzfiók támogatottak.

#### <a name="printer"></a>Nyomtató

| Gyártó | Típus    | Interfész | Megjegyzések                  |
|--------------|----------|-----------|---------------------------|
| Epson        | TM-T88IV | AZ OPOS      |                           |
| Epson        | TM-T88V  | AZ OPOS      |                           |
| Csillag         | TSP650II | AZ OPOS      |                           |
| Csillag         | TSP650II | Egyéni    | Hálózaton keresztül csatlakozó     |
| Csillag         | TSP100   | AZ OPOS      | TSP650II illesztőprogramokra van szüksége |
| HP           | F7M67AA  | AZ OPOS      | Táplálású USB               |

#### <a name="payment-terminal"></a>Fizető terminál 

| Gyártó | Típus | Interfész | Megjegyzések                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| VeriFone     | MX925 | Egyéni    | A fizetési csatlakoztató; testreszabás igényel a hálózati és USB keresztül |
| VeriFone     | MX915 | Egyéni    | A fizetési csatlakoztató; testreszabás igényel a hálózati és USB keresztül |

#### <a name="cash-drawer"></a>Pénzfiók

| Gyártó | Típus     | Interfész | Megjegyzések              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Egyéni    | Hálózaton keresztül csatlakozó |
| Csillag         | SMD2-1317 | AZ OPOS      |                       |
| HP           | QT457AA   | AZ OPOS      |                       |

## <a name="troubleshooting"></a>Hibaelhárítás
### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>Modern POS észleli a hardver állomás a kiválasztási listájában, de nem tudja befejezni a párosítás

**Megoldás:** az alábbi listában szereplő lehetséges meghibásodási pontok ellenőrzéséhez:

-   A Modern POS rendszert futtató számítógép megbízik a tanúsítvány, amely a számítógépen a hardver állomáson futó.
    -   Ellenőrizze a telepítő egy webböngészőben nyissa meg a következő URL-cím: https://&lt;számítógép neve&gt;:&lt;Port száma&gt;/HardwareStation/ping.
    -   Az URL-cím egy ping segítségével ellenőrizze, hogy a számítógépen elérhető, és a böngésző jelzi, hogy a tanúsítvány megbízható. (Például az Internet Explorer egy lakat ikon jelenik meg a címsorban. Ha erre az ikonra kattint, az Internet Explorer ellenőrzi, hogy a tanúsítvány megbízható jelenleg-e. Telepítheti a tanúsítványt a helyi számítógép által megjelenített a tanúsítvány adatainak megtekintése.)
-   A hardver állomás fut a számítógépen a hardver állomás által használt port a tűzfalon nyílik meg.
-   A hardver állomás megfelelően telepítve van a kereskedői számla adatait a telepítés, amely fut a hardver állomás telepítő végén kereskedő információk eszköz segítségével.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>Modern POS nem észleli a hardver állomás a kiválasztási listájában

**Megoldás:** a következő tényezők valamelyike okozhatja a hibát:

-   A hardver állomás megfelelően Headquarters nincs beállítva. Ez a témakör a korábbi lépések segítségével ellenőrizze, hogy a hardverprofil állomás és a hardver állomás helyesen adta-e.
-   A feladatok a csatorna beállítások frissítése még nem futtatták. Ebben az esetben a feldolgozással 1070 csatornák konfigurálásakor.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>Modern POS nem tükrözi az új készpénz fiók beállítások

**Megoldás:** az aktuális köteg bezárásához. Módosításokat a pénztárfiók, Modern POS nem frissíti az aktuális köteg lezárásáig.

### <a name="modern-pos-is-reporting-an-issue-with-a-retail-peripheral"></a>Modern POS jelentéséért van egy kiskereskedelmi perifériás

**Megoldás:** az alábbiakban néhány jellemző okai a problémát:

-   Győződjön meg arról, hogy bezárta-e a többi eszköz-illesztőprogram konfigurációs segédprogramok. Ha ezek a segédprogramok megnyitva, azok megakadályozhatja a Modern POS vagy a hardver állomás azt állítja, az eszköz.
-   Ha a kiskereskedelmi periféria több POS eszköz, győződjön meg arról, hogy a következő kategóriák valamelyikébe tartozik:
    -   Pénzfiók
    -   Bevételezési nyomtató
    -   Fizető terminál 

    A periféria nem tartozik egyik kategóriába, ha a hardver állomás nem lehetővé teszi, hogy a periféria POS több eszköz között.
-   Néha eszköz-illesztőprogramok okozhatnak a közös ellenőrző objektumok (CCOs) nem működik megfelelően. Ha nemrég eszköz telepítve van, de nem működik megfelelően, vagy más problémák merülnek fel, újratelepítésével a CCOs gyakran oldhatja meg a problémát. A CCOs letöltéséhez látogasson el a <http://monroecs.com/oposccos_current.htm>.
-   Ha gyakran módosítja perifériás tesztelésére és hibaelhárítására során, előfordulhat az IIS alaphelyzetbe állításához a gyorsítótár frissítése maga kivárása helyett. Az IIS alaphelyzetbe állításához kövesse az alábbi lépéseket:
    1.  A a **Start** menü, típus **CMD**.
    2.  A keresési eredményekben kattintson jobb gombbal a **parancssor**, majd **Futtatás rendszergazdaként**.
    3.  A a **parancssor** ablak, típus **iisreset/norestart**, és nyomja le az ENTER billentyűt.
    4.  Az IIS újraindítása után indítsa újra a Modern POS.
-   Változtatásokat hajt végre gyakori perifériákkal, ha gyakran is elindítani, és lépjen ki a POS-ügyfél, míg a dllhost folyamatban futnak a POS előző munkamenetről zavarhatja az aktuális munkamenetet. Ebben az esetben az eszköz lehet, hogy nem használható a dinamikus csatolású függvénytár (DLL) állomás kezeli az előző munkamenet bezárásáig. Zárja be a DLL-állomás, kövesse az alábbi lépéseket:
    1.  A a **Start** menü, típus **a Feladatkezelő**.
    2.  Kattintson a keresési eredmények **a Feladatkezelő**.
    3.  A Feladatkezelő a a **részletek** fülre, kattintson az oszlop fejlécére **neve**, a táblázat rendezése név szerint.
    4.  Görgesse lefelé, amíg meg nem találja a dllhost.exe.
    5.  Jelölje be a DLL-állomásokon, majd **feladat befejezése**.
    6.  A DLL-állomásokon bezárása után indítsa újra a Modern POS.


<a name="see-also"></a>Lásd még
--------

[Kiskereskedelmi perifériás szimulátor](retail-peripheral-simulator.md)


