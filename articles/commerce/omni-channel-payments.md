---
title: Omnicsatornás kifizetések áttekintése
description: Ez a témakör áttekintést nyújt a csatorna kifizetésekről a következőben:Dynamics 365 Commerce
author: BrianShook
ms.date: 11/04/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom:
- "141393"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: AX 8.1.3
ms.openlocfilehash: a5cc0725b383ca6657bd19b9dd25b0c60b364467
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746125"
---
# <a name="omni-channel-payments-overview"></a>Omnicsatornás kifizetések áttekintése

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a témakör áttekintést nyújt a csatorna kifizetésekről a következőben:Dynamics 365 Commerce Tartalmaz egy átfogó listát a támogatott esetekről, a funkciókkal, a beállítással és a hibakereséssel kapcsolatos információkat, illetve néhány tipikus probléma leírását.

## <a name="key-terms"></a>Kulcsfogalmak

| Időszak | Leírás |
|---|---|
| Jogkivonat | Olyan adat-karakterlánc, amelyet a fizetési feldolgozó referenciaként ad meg. A jogkivonatok fizetési kártyaszámokat, fizetési jóváhagyásokat és korábbi fizetésrögzítéseket jelenthetnek. A jogkivonatok azért fontosak, mert segítenek az érzékeny adatok pénztár (POS) rendszerből való távoltartásában. Gyakran hivatkoznak hivatkoznak rá hivatkozásokként *is*. |
| Kártyajogkivonat | Olyan jogkivonat, amelyet a fizetés feldolgozója biztosít a pénztárrendszerben való tároláshoz. Kártyajogkivonatokat csak az azt megkapó kereskedő használhatja. A kártyajogkivonatokat időnként *kártyareferenciák* néven említik. |
| Jóváhagyási (auth) jogkivonat | Egyedu azonosító, amelyet a fizetés feldolgozója biztosít a válasz részeként, amelyet a pénztárrendszerbe küld, miután a pénztárrendszer jóváhagyási kérést hoz létre. A jóváhagyási jogkivonatot később is használhatják, ha a feldolgozót műveletek elvégzésére kérik fel, például a jóváhagyás visszavonására vagy visszafordítására. Ez a leggyakrabban azonban a pénzeszközöknek a rendelés teljesítése vagy a tranzakciók véglegesítése esetén történő rögzítéséhez használatos. A jóváhagyási jogkivonatokat időnként *jóváhagyási referenciák* néven említik. |
| Rögzítési jogkivonat | A fizetés feldolgozója által a pénztárrendszer számára biztosított referencia, amikor a fizetést véglegesítették vagy rögzítették. A rögzítési jogkivonat segítségével hivatkozni lehet a fizetés rögzítésére az ezt követő műveleteknél, például visszatérítési kéréseknél. | 
| Nincs jelen kártya | Olyan fizetési tranzakciókra hivatkozó kifejezés, amelyeknél a tényleges kártya nem jelenik meg. Ezek a tranzakciók előfordulhatnak például az e-kereskedelmi vagy a hívásközponti forgatókönyvekben. Az ilyen tranzakcióknak az esetében a fizetéssel kapcsolatos adatokat kézzel kell bevinni egy e-kereskedelmi webhelyre, egy hívásközponti folyamatba, illetve a pénztárba vagy a kifizetési terminálra. |
| Kártya jelen van | Olyan fizetési tranzakciókra utaló kifejezés, amelyeknél a tényleges kártya jelen van, és a Microsoft Dynamics 365 pénztárrendszerhez csatlakoztatott kifizetési terminálokon használják. |

## <a name="overview"></a>Áttekintés

Álalánosságban a *Többcsatornás fizetések* kifejezés azt a képességet írja le, amikor a rendelés létrehozása az egyik csatornán történik, a teljesítése pedig egy másik csatornán. A többcsatornás fizetés támogatásának kulcsa a fizetési adatok együtt a megrendelés többi adatával együtt való megőrzése, majd pedig ezen fizetési adatok használata a rendelés visszhívása vagy másik csatornán való feldolgozása esetén. Egy klasszikus példa a „Vásárlás online, átvétel az üzletben” eset. Ebben az esetben a fizetési részleteket hozzáadják, amikor a megrendelés online létrejön. Ezután a POS visszahívja őket, hogy a felvételkor felszámítsa a vevő kártyáját. 

Az ebben a cikkben ismertetett valamennyi helyzet a Commerce rendszer szabványos fizetési szoftverfejlesztő csomagja (SDK) használatával valósítható meg. A [Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3) készen érkező megvalósítást biztosít az itt leírt összes esethez. 

### <a name="prerequisites"></a>Előfeltételek

Az ebben a cikkben ismertetett minden esetben szükség van egy olyan fizetési csatlakoztatóra, amely támogatja a csatorna-kifizetéseket. A beépített Adyen összekötőt is lehet használni, mivel támogatja a Fizetések SDK-n keresztül elérhetővé tett eseteket. Ha további információra van szüksége a fizetési összekötők alkalmazásáról és általánosságban a Retail SDLK-ról, akkor látogasson el a [Retail informatikai szakembereknek és fejlesztőknek – kezdőoldal](/dynamics365/unified-operations/retail/dev-itpro/dev-retail-home-page#payment-connectors) oldalra.

#### <a name="supported-versions"></a>Támogatott verziók

Az ebben a cikkben ismertetett fizetési Microsoft Dynamics 365 for Retail képességek a 8.1.3 verzió részeként jelentek meg. 

#### <a name="card-present-and-card-not-present-connectors"></a>„Kártya jelen van” és „Nincs jelen kártya” összekötők

A Fizetések SDK két alkalmazásfejlesztési felületre (API-ra) támaszkodik a fizetések feldolgozásához. Az API-k első csoportja az **iPaymentProcessor**. Ez a „Nincs jelen kártya” fizetési összekötők megvalósítására szolgál, amelyeket a hívásközpontokban és a Microsoft Dynamics e-kereskedelmi platformon használnak. Az **iPaymentProcessor** felülettel kapcsolatos további információkért tekintse meg a [Fizetési csatlakozó és fizetési eszköz alkalmazása](https://download.microsoft.com/download/e/2/7/e2735c65-1e66-4b8d-8a3c-e6ef3a319137/The%20Guide%20to%20Implementing%20Payment%20Connector%20and%20Payment%20Device_update.pdf) tanulmányt, amely a fizetésekkel foglalkozik. 

Az API-k második csoportja az **iNamedRequestHandler**. Ez támogatja a „Kártya jelen van” fizetési integrációk megvalósítását, amelyek a fizetési terminált használják. Az **iNamedRequestHandler** felülettel kapcsolatos további információért tekintse meg a [Fizetési integráció létrehozása fizetési terminálhoz](/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension) című részt. 

### <a name="setup-and-configuration"></a>Beállítás és konfigurálás

A következő összetevők és beállítási lépések szükségesek:

- **E-kereskedelmi integráció:** A Commerce szolgáltatással való integráció szükséges az olyan esetek támogatására, ahol a rendelés egy online áruházból származik. A Retail e-kereskedelem SDK csomaggal kapcsolatos további tudnivalókat lásd: [e-kereskedelmi platform szoftverfejlesztői készlet](/dynamics365/unified-operations/retail/dev-itpro/ecommerce-platform-sdk)(SDK). A bemutató környezetben a referencia-áruház támogatja a többcsatornás fizetési forgatókönyveket. 
- **Online fizetések konfigurációja:** Az online csatorna beállításának tartalmaznia kell egy olyan kifizetési összekötőt, amely frissítve van a többcsatornás fizetések támogatásához. Azt is megteheti, hogy a beépített kifizetési összekötőt használja. Az Adyen fizetési összekötő online áruházak számára történő konfigurálásával kapcsolatos további információkért lásd: [Adyen fizetési összekötő](/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3#e-commerce). Az eCommerce beállítási lépéseken kívül, amelyek ebben a cikkben le vannak írva, **az E-commerce** **paraméter** fizetési információinak mentésének engedélyezése beállítást True (Igaz) beállításra kell állítani az Adyen csatlakoztató beállításai között. 
- **Többcsatornás fizetési konfiguráció:** A háttérirodában lépjen a **Retail és Commerce \> Központi beállítás \> Paraméterek \> Commerce megosztott paraméterei**. Ezután a **Többcsatornás fizetések** lapon állítsa a **Többcsatornás fizetések használata** beállítást **Igen** értékre. A Commerce 10.0.12 és újabb verzióiban ez a beállítás a **Funkciókezelés** munkaterületen szerepel. Válassza ki a **Többcsatornás kifizetések** funkciót, majd kattintson az **Engedélyezés most** lehetőségre. 
- **Fizetési szolgáltatások:** A hívásközpont a **Fizetési szolgáltatások** oldalon szereplő alapértelmezett fizetési összekötőt használja a fizetések feldolgozásához. A „Vásárlás a hívásközpontban, átvétel az üzletben” és ehhez hasonló forgatókönyvek támogatása érdekében az alapértelmezett fizetési összekötőnek az Adyen fizetési összekötőnek kell lennie, vagy egy olyan fizetési összekötőnek, amely megfelel a többcsatornás fizetések megvalósítási követelményeinek.
- **Elektronikus átutalási szolgáltatás** : A fizetési terminálon keresztül történő fizetéseket be kell állítani az **Elektronikus átutalási szolgáltatás** gyorslapon a hardverprofilban. Az Adyen összekötő beépítetten támogatja a többcsatornás fizetési forgatókönyveket. Azok a fizetési összekötők, amelyek támogatják az **iNamedRequestHandler** felületet, szintén használhatók, ha támogatják a többcsatornás fizetéseket.
- **Fizetési összekötő elérhetősége** : Egy rendelés visszahívása során a rendeléssel együtt visszahívott fizetőeszközsorok tartalmazzák a rendeléshez társított jóváhagyások létrehozásához használt fizetési összekötő nevét. A rendelés teljesítése során a Fizetések SDK megpróbálja ugyanazt az összekötőt használni, amelyet az eredeti jóváhagyás létrehozására használtak. Ezért az ugyanazokkal a kereskedői tulajdonságokkal rendelkező fizetési összekötőnek elérhetőnek kell lennie a rögzítésre. 
- **Kártyatípusok:** A többcsatornás forgatókönyvek megfelelő működéséhez minden csatornának ugyanazzal a beállított fizetőeszközzel kell rendelkeznie, amely használható többcsatornás esetekhez. Ez a beállítás tartalmazza a fizetési mód azonosítóját és a kártyatípus azonosítóját. Ha például a **Kártyák** fizetőeszköztípus azonosítója **2** az online áruház beállításában, akkor a kiskereskedelmi üzlet beállításában is ugyanezzel az azonosítóval kell rendelkeznie. Ugyanez a követelmény vonatkozik a kártyatípus azonosítójára. Ha a **12**-es kártyaszámot állítják be a **VISA** értékhez az online áruházban, akkor ugyanezt az azonosítót kell beállítani a kiskereskedelmi üzletben. 
- A Retail Modern POS for Windows vagy Android beépített hardverállomással -vagy-
- Modern POS for iOS vagy Cloud POS csatlakoztatott, megosztott hardverállomással. 

### <a name="basic-principle-supporting-omni-channel-payments"></a>A többcsatornás fizetéseket támogató alapelv

A fizetési csatlakozók és a fizetési feldolgozók jogkivonatokat vagy referenciákat használnak, hogy hivatkozni tudjanak a kártyás fizetésekhez kapcsolódó interakciókra. Például fizetési jóváhagyás kérése során a rendszer biztosítja a jóváhagyás referenciáját. Ezért a jóváhagyás referenciáját később is le lehet kérni, amikor a fizetőeszközöket a teljesítés pillanatában rögzítik. Ez a jóváhagyás a kereskedő, a fizetési összekötő és a feldolgozó szempontjából egyedi. 

Ha az online létrehozott rendelést az üzletben veszik át, a rendelés ugyanezen fizetési adatait kell lekérni és használni. Amikor a rendszer megadja az eredeti adatokat egy olyan kérés részeként, amely egy fizetés az eredeti jóváhagyás alapján történő rögzítésére vonatkozik, akkor a fizetési feldolgozó kezelheti a kérést és rögzítheti a fizetést. 

Az online rendelés helyes referenciájának biztosítása érdekében elérhetőnek kell lennie ugyanannak a „kártya nincs jelen” fizetési összekötőnek, amely támogatja ugyanazt a feldolgozót. Ilyen módon a pénztárrendszer a „kártya jelen van” fizetésekhez egy feldolgozót használhat, ugyanakkor további fizetési összekötőkhöz is hozzáférhet, így olyan rendeléseket is teljesíthet, amelyeket más csatornákon, más fizetési feldolgozókkal hoztak létre. 

## <a name="supported-scenarios"></a>Támogatott esetek

A következő többcsatornás kifizetési forgatókönyvek támogatottak:

- Online vásárlás, felvétel az üzletben
- Vásárlás a hívásközpontban, felvétel az üzletben
- Vásárlás az „A” üzletben, felvétel a „B” üzletben
- Vásárlás az „A” üzletben, kiszállítás a vevőnek

    > [!NOTE]
    > A hívásközpontban a „normál” fizetési funkcióhoz hozzárendelt kifizetéseket az **Előre fizetés** = **Igen** értékre kell állítani, hogy az tükröződjön az esedékes összegben, amikor előhívják a rendelést a pénztárban. A „Normál” típusú nem előre fizetett fizetéseket nem ismeri fel a program, ha a rendelést a pénztárban előhívják. 

Az említett forgatókönyvek különböző változatai szintén támogatottak. Például egy online rendelés tartalmazhat olyan sorokat is, amelyeket kiszállítanak a vevőnek, és olyan sorokat is, amelyeket az üzletben vesznek fel. Minden rendelésteljesítési lehetőség támogatott a többcsatornás fizetéseken keresztül. 

Az alábbi szakaszok bemutatják az egyes forgatókönyvek lépései, valamint azt, hogy hogyan lehet lefuttatni a forgatókönyvet bemutató adatok segítségével. 

### <a name="buy-online-pick-up-in-store"></a>Online vásárlás, felvétel az üzletben

Az indítás előtt győződjön meg arról, hogy megtalálhatók a következő előfeltételek:

- Van egy referenciaüzlet, ahol konfigurált Adyen-összekötő található.
- A **Többcsatornás fizetések** beállítás értéke a **Commerce megosztott paraméterei** oldalon **Igaz**. A későbbi verziókban **ez** **a beállítás átkerül a Szolgáltatáskezelés munkaterületre, ahol kiválaszthatja a Szövegcsatorna fizetési** szolgáltatását, és rákattinthat az **Engedélyezés gombra.** 
- Az Adyen fizetési összekötő a houstoni pénztárgéphez van konfigurálva.
- A Retail Modern POS for Windows vagy Android beépített hardverállomással -vagy-
- Modern POS for iOS vagy Cloud POS csatlakoztatott, megosztott hardverállomással. 

Kövesse az alábbi lépéseket a forgatókönyv futtatásához.

1. A referenciaüzletben hozzon létre egy rendelést üzletben történő átvétellel. Ügyeljen arra, hogy a **Houston** üzletet válassza. 
2. Menjen végig a fizetési lépéseken, és fizessen egy tesztelésre használt hitelkártyaszám használatával. Tesztelésre használható hitelkártyaszámokat az [Adyen tesztkártyaszámok oldalon](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description) találhat.
3. A Commerce alkalmazásban a rendelések létrehozására a háttérirodában használja a **Rendelések szinkronizálása** kötegelt feladatot és a **P-001** felosztási ütemezést.
4. A pénztár üdvözlőoldalán válassza az **Átveendő rendelések** műveletet, hogy megtekintse az üzletben átveendő rendeléseket. 
5. Jelöljön ki egy vagy több sort abból a rendelésből, amely a referenciaüzletben lett létrehozva, majd válassza a **Felvétel** lehetőséget.

    A rendelést a rendszer lekéri a háttérirodából. 

6. Amikor a rendszer lekéri a rendelési sor részleteit a háttérirodából, és a többcsatornás fizetéshez használható kártyás fizetést észlel, akkor tájékoztatja Önt, hogy a fizetési mód elérhető.
7. Válassza a **Rendelkezésre álló fizetési mód** lehetőséget a tranzakció teljesítéséhez, és használja a referenciaüzletben megadott kártyaadatokat.

    A rendelési sorok betöltődnek a tranzakciós oldalon, és a fizetendő egyenleg 0 (nulla). 

8. Válassza ki a **Fizetések** lapot, ahol megtekintheti a fizetőeszköz sorát, amelyet az online rendelésből húzott ki a rendszer. 
9. A tranzakció befejezéséhez válassza ki a fizetési módot. 

### <a name="buy-in-call-center-pick-up-in-store"></a>Vásárlás a hívásközpontban, felvétel az üzletben

1. A Commerce alkalmazás **Ügyfélszolgálat** oldalán adja meg a **Karen Berg** nevet a keresési sávon, majd válassza a **Keresés** parancsot. 
3. Válassza a **Karen Berg** lehetőséget a keresési eredmények között.
4. Miután Karen betöltődött az **Ügyfélszolgálat** oldalon, válassza az **Új értékesítési rendelés** lehetőséget.
5. Az új értékesítési rendelés lapon válassza **Fejléc** elemet a rendelési fejléc megtekintéséhez. 
6. A **Rendelés fejléce** oldalon állítsa a webhelyet **Központi** értékre, a raktárat pedig **Houston** értékre.
7. A **Szállítás** lapon a **Szállítási mód** mezőben **60** szerepeljen a vevői átvételhez.
8. Válassza a **Sorok** elemet, majd adjon egy vagy több sort a rendeléshez. 
9. Válassza a **Befejezés** parancsot a rendelés befejezési folyamatának megnyitásához.
10. Görgessen a kifizetések szakaszhoz, válassza a **Hozzáadás** parancsot, majd válassza ki azt a sort, amelynél a fizetési mód típusa **Kártyák** értékre van állítva. 
11. Válassza a pluszjelet (**+**) a kártyás fizetés hozzáadásához. 
12. Adja meg a tesztelésre használható hitelkártya számát, amelyet az [Adyen tesztkártyaszám oldalon](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description) talált, majd nyomja meg az **OK** gombot.

    > [!NOTE]
    > Ha a megadott kártyaszámhoz tartozó kártya márkája különbözik a márkától, amelyet a fizetés indításakor kiválasztott, a fizetés ettől függetlenül végrehajtható. Azonban azokhoz a számlákhoz adja fel majd, amelyek a 10. lépésben kiválasztott kártyamárkához vannak rendelve.

12. Válassza ismét az **OK** gombot a **Rendelésteljesítési fizetések** párbeszédablak bezárásához.
13. Az **Értékesítési rendelés összegzése** lapon válassza a **Küldés** lehetőséget.
14. A pénztár üdvözlőoldalán válassza az **Átveendő rendelések** műveletet, hogy megtekintse az üzletben átveendő rendeléseket. 
15. Jelöljön ki egy vagy több sort abból a rendelésből, amely a referenciaüzletben lett létrehozva, majd válassza a **Felvétel** lehetőséget.

    A rendelést a rendszer lekéri a háttérirodából. 

16. Amikor a rendszer lekéri a rendelési sor részleteit a háttérirodából, és a többcsatornás fizetéshez használható kártyás fizetést észlel, akkor tájékoztatja Önt, hogy a fizetési mód elérhető.
17. Válassza a **Rendelkezésre álló fizetési mód** lehetőséget a tranzakció teljesítéséhez, és használja a referenciaüzletben megadott kártyaadatokat.

    A rendelési sorok betöltődnek a tranzakciós oldalon, és a fizetendő egyenleg 0 (nulla).

18. Válassza ki a **Fizetések** lapot, ahol megtekintheti a fizetőeszköz sorát, amelyet az online rendelésből húzott ki a rendszer. 
19. A tranzakció befejezéséhez válassza ki a fizetési módot. 

### <a name="buy-in-store-a-pick-up-in-store-b"></a>Vásárlás az „A” üzletben, felvétel a „B” üzletben

1. Indítsa el a houstoni üzlethez tartozó pénztárat.
2. A **Tranzakció** oldalon adja a Karen Berg elemet a tranzakcióhoz a számbillentyűzeten a **2001** értéket megadva.
3. Adjon egy vagy több sort a tranzakcióhoz.
4. Válassza a **Rendelések** elemet a rendelési beállítások megtekintéséhez.
5. Válassza az **Összes felvétele** elemet, majd amikor a rendszer felkéri, válassza a **Vevői rendelés** lehetőséget.
6. A keresési sávon adja meg a **Seattle** értéket, majd válassza átvételhez a **Seattle** üzletet. 
7. Az **OK** gombra kattintva elfogadja az aktuális dátumot a felvételi dátumként.
9. Válassza a **Fizetési kártya** elemet a fizetés indításához.
10. Terhelje a kártyás fizetést a letéthez esedékes összegre.
11. Teljesítse a letét fizetését a fizetési terminálon. 
12. A letét kifizetését követően válassza ki azt a lehetőséget, hogy a teljesítéshez ugyanaz a kártya legyen használatban, és várja meg, amíg a rendelés teljesül. Ha a letét 100%-át fizetik ki (a fenti 10. lépéstől), a pénzt azonnal rögzíti a rendszer a kártyával szemben, és a számlázáskor nem lesz elérhető engedélyezési token, mivel a fedezetet már rögzítették és kifizették.
13. Indítsa el a seattle-i üzlethez tartozó pénztárat.
14. A pénztár üdvözlőoldalán válassza az **Átveendő rendelések** műveletet, hogy megtekintse az üzletben átveendő rendeléseket. 
15. Jelöljön ki egy vagy több sort abból a rendelésből, amely a referenciaüzletben lett létrehozva, majd válassza a **Felvétel** lehetőséget.

    A rendelést a rendszer lekéri a háttérirodából. 

16. Amikor a rendszer lekéri a rendelési sor részleteit a háttérirodából, és a többcsatornás fizetéshez használható kártyás fizetést észlel, akkor tájékoztatja Önt, hogy a fizetési mód elérhető.
17. Válassza a **Rendelkezésre álló fizetési mód** lehetőséget a tranzakció teljesítéséhez, és használja a referenciaüzletben megadott kártyaadatokat.

    A rendelési sorok betöltődnek a tranzakciós oldalon, és a fizetendő egyenleg 0 (nulla).

18. Válassza ki a **Fizetések** lapot, ahol megtekintheti a fizetőeszköz sorát, amelyet az online rendelésből húzott ki a rendszer. 
19. A tranzakció befejezéséhez válassza ki a fizetési módot. 

### <a name="buy-in-store-a-ship-to-customer"></a>Vásárlás az „A” üzletben, kiszállítás a vevőnek

1. Indítsa el a houstoni üzlethez tartozó pénztárat.
2. A **Tranzakció** oldalon adja a Karen Berg elemet a tranzakcióhoz a számbillentyűzeten a **2001** értéket megadva.
3. Adjon egy vagy több sort a tranzakcióhoz.
4. Válassza a **Rendelések** elemet a rendelési beállítások megtekintéséhez.
5. Válassza az **Összes szállítása** elemet, majd amikor a rendszer felkéri, válassza a **Vevői rendelés** lehetőséget.
6. A szállítási mód lapon válassza ki a **Standard egynapos** beállítást, majd az **OK** gombra kattintva fogadja el a mai dátumot a szállítási dátumként. 
7. Az **OK** gombra kattintva elfogadja az aktuális dátumot a felvételi dátumként.
8. Válassza a **Fizetési kártya** elemet a fizetés indításához.
9. Terhelje a kártyás fizetést a letéthez esedékes összegre. 
10. Teljesítse a letét fizetését a fizetési terminálon. 
11. A letét kifizetését követően válassza ki azt a lehetőséget, hogy a teljesítéshez ugyanaz a kártya legyen használatban, és várja meg, amíg a rendelés teljesül. Ha a letét 100%-át fizetik ki (a fenti 9. lépéstől), a pénzt azonnal rögzíti a rendszer a kártyával szemben, és a számlázáskor nem lesz elérhető engedélyezési token, mivel a fedezetet már rögzítették és kifizették.

Amikor a rendelés kitárolása, csomagolása és számlázása megtörtént a háttérirodában, a pénztárnál megadott fizetési adatok segítségével rögzíti a rendszer a pénzeszközöket a vevőnek szállított árukért cserébe. 

## <a name="scenario-details"></a>Forgatókönyv részletei

A most ismertetett alapvető forgatókönyvek mellett számos fejlesztést végeztek a Fizetések SDK-n a többcsatornás fizetések támogatásához. 

### <a name="pos"></a>Pénztár

#### <a name="single-swipedip-for-customer-orders"></a>Egyetlen lehúzás/beillesztés a vevői rendelésekhez

Az többcsatornás fizetések funkció bevezetése előtt, amikor a letétet tartalmazó vevői rendeléseket a pénztárnál hozták létre, a vevőknek kétszer kellett lehúzniuk (vagy beilleszteniük) a kártyájukat: egyszer a letét fizetéséhez, egyszer pedig a kártya tokenné alakítása során az ezt követő rendelés teljesítéséhez. Ha a többcsatornás tokenné alakítás funkció be van kapcsolva, a vevőnek csak egyszer kell lehúznia a kártyáját, amellyel kifizetheti a letétet, és engedélyezheti az árukért fizetendő összeget, amit később teljesítenek. A teljesítés során az engedélyezett pénzeszközöket rögzítik. A többcsatornás tokenizáció funkció megvalósítása előtt csak egy ismétlődő kártyatoken került létrehozására az ezt követő rendelésteljesítéshez. Ennélfogva a függőben lévő teljesítéshez nyújtott pénzeszközök nem voltak engedélyezve, és mivel ezeket az összegeket nem tartották meg az adott beszerzésre vonatkozóan, kisebb a valószínűsége annak, hogy a későbbiekben rögzíteni tudják őket.

> [!NOTE]
> Az egy lehúzás nem támogatott a Retail 8.1.3-as verziójában. A 8.1.3-as verzió vevői rendelései ugyanazt a folyamatot használják, amelyet a többcsatornás tokenizációs funkció megvalósítása előtt. 

### <a name="cards-that-cant-issue-recurring-card-tokens"></a>Kártyák, amelyek nem tudnak ismétlődő kártyatokeneket kibocsátani

Néhány kártya nem használható többcsatornás fizetéshez, mert nem támogatják az ismétlődő kártyatokenek kiadását. Ha egy rendelést a pénztárnál hoz létre, és a letétet olyan kártyával fizetik ki, amely nem támogatja az ismétlődő kártyatokeneket, akkor a program a korábbi kártya tokenizációs folyamatát használja. Ebből következően egy olyan vevőnek, aki a kifizetést szeretné nyújtani a későbbi rendelés teljesítéséhez, be kell mutatnia egy második kártyát is. Ha a második kártya nem támogatja az ismétlődő kártyatokeneket, akkor a tokenizációs művelet elutasításra kerül, és a pénztárost a program kéri, hogy kérje meg a vevőt egy másik kártya biztosítására. 

### <a name="using-a-different-card"></a>Másik kártya használata

Az a vevő, aki az üzletbe való rendelésfelvételhez jön, egy másik kártya használatára van lehetőség. Amikor a pénztáros megkapja a **Rendelkezésre álló fizetési mód használata** kérést a rendelés felvételekor, megkérdezheti, hogy a vevő ugyanazt a kártyát kívánja-e használni. Ha a vevő elvesztette a rendelés létrehozásához használt kártyát, és egy másik kártyával szeretné kifizetni a rendelést, akkor a pénztáros kiválaszthatja **Másik fizetési mód használata** lehetőséget. Ha a vevő később visszatér, hogy további cikkeket felvegyen ugyanabból a rendelésből, ha az eredeti kártyengedélyezés még érvényes, a pénztáros megkérdezheti, hogy a vevő ugyanazt a kártyát szeretné-e használni.

### <a name="invalid-authorizations"></a>Érvénytelen engedélyezések

Ha a rendelés létrehozásához használt kártya már nem érvényes, amikor a termékeket kiválasztják a felvételhez, akkor a kifizetés rögzítési kérelme sikertelen lesz. A pénztár fizetési összekötő megpróbál új engedélyezést létrehozni, és ugyanazokkal a kártyaadatokkal rögzíteni. Ha az új engedélyezés vagy rögzítés sikertelen, a pénztáros értesítést kap arról, hogy a kifizetést nem sikerült feldolgozni. Ezután a pénztárosnak új kifizetést kell kérnie a vevőtől. 

### <a name="multiple-available-payments"></a>Több elérhető fizetés

Ha egy olyan rendelést, amelynél több fizetőeszköz és több sor van felvéve, akkor a pénztárosnak először a **Rendelkezésre álló fizetési mód használata** figyelmeztetés jelenik meg. Ha több kártya van, amikor a pénztáros kiválasztja a **Rendelkezésre álló fizetési mód használata** pontot, akkor a program addig rögzíti a meglévő fizetőeszköz-sorokat, amíg az aktuálisan felvett cikkek egyenlege nem teljesül. A pénztárosnak nem lesz lehetősége kijelölni azt a kártyát, amelyet a felvett áruknál használni kell. 

## <a name="related-articles"></a>Kapcsolódó cikkek

- [Kifizetésekkel kapcsolatos GYIK](/dynamics365/unified-operations/retail/dev-itpro/payments-retail)
- [Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3)
- [BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben](./cpe-bopis.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
