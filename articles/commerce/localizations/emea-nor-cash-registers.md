---
title: Pénztárgép funkciói Norvégia esetén
description: Ez a cikk áttekintést nyújt Microsoft Dynamics 365 Commerce a Norvégiában használható pénztárgép-funkciókról, és a funkciók beállításával kapcsolatos irányelveket tartalmaz.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2017-10-31
ms.openlocfilehash: 778a947f03866518219e9c0fa44660d66f19f53a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906699"
---
# <a name="cash-register-functionality-for-norway"></a>Pénztárgép funkciói Norvégia esetén

[!include[banner](../includes/banner.md)]

Ez a cikk áttekintést nyújt a Norvégiában használható pénztárgép funkciókról Dynamics 365 Commerce. A szolgáltatások beállítására vonatkozó irányelveket is tartalmaz. A funkció a következő részekből áll:

- A közös pénztári funkciók, amelyek minden ország vagy régió vevői számára érhetők el. Ilyen beállítás lehet például az, amellyel megelőzhető, hogy egy nyugta másolatát egynél több alkalommal is kinyomtatják.
- Norvégia-specifikus funkciók, például az értékesítési tranzakciók digitális aláírásai.

## <a name="overview-of-cash-register-functionality-for-norway"></a>Készpénzjegyzék-funkciók áttekintése Norvégia esetében

### <a name="common-pos-features"></a>Gyakori POS-funkciók

Ha tudni szeretne a vevők minden országának vagy régiójának POS-szolgáltatásairól, [tekintse meg a súgót Dynamics 365 Retail](../index.md).

Az összes ország vagy régió vevői számára korábban megvalósított és a vevők számára elérhetővé tett következő POS-honosítási funkciók mostantól külön Norvégiához használhatók:

- **Nagy betűméretű nyugta szövegmezőinek nyomtatása.** A Nyugtaformátum-tervező **Betűtípus**-méret paraméterével adhatja meg, hogy a nyugtaformátum egy mezőjében a nagy betűméretet használja. (A nagy betűméret körülbelül dupla a szokásos betűmérethez.) Ezzel a paraméterrel például nagy karaktereket nyomtathat egy nyugta másolatára a "Másolás" jelzővel.
- **A nyugtamásolatok nyomtatásának regisztrálása a POS auditálási eseménynaplójában.** A POS funkcióprofil **auditálási** paraméterének használatával engedélyezheti a nyugták másolati példányának nyomtatását és az egyéb PÉNZTÁRi auditálási események regisztrációját. A könyvvizsgálati eseményeket a csatorna-adatbázisban és a Headquartersban regisztrálják. A könyvvizsgálati eseményeket a Könyvvizsgálati **események lapon lehet** megtekinteni.
- **Annak megakadályozása, hogy egy nyugta másolatát egynél több alkalommal is kinyomtatják.** Ha a **POS** funkcióprofil auditálási paramétere engedélyezve van, **akkor** a Nyugtamásolat-példányok NYOMTATÁSának engedélyezése engedély szabályozza, hogy a nyugták másolatai nyomtathatók-e. Lehetőség van arra is, hogy egy nyugta másolatát egynél több alkalommal kinyomtatják.

Ezenkívül a következő POS funkció is meg van valósítva Norvégiához, de elérhetővé válik minden ország vagy régió vevői számára:

- **További események regisztrálása a POS naplózási eseménynaplójában.** Ha engedélyezve van **a POS** funkcióprofil Audit paramétere, a következő eseményeket regisztrálja a rendszer a POS naplózási eseménynaplójában:

    - Árellenőrzések
    - Adófelül felülbírálásai
    - Sormennyiségek helyesbítései
    - Tranzakciók törlése a csatorna-adatbázisból

### <a name="norway-specific-pos-features"></a>Norvégia-specifikus POS-funkciók

Az alábbi Norvégia-specifikus POS-funkciók engedélyezve vannak, ha **a POS funkcióprofilBAN az ISO-kód** paraméter értéke **Nem**.

#### <a name="digital-signing-of-sales-transactions"></a>Értékesítési tranzakciók digitális aláírása

Minden értékesítési tranzakció digitálisan van aláírva. Az aláírás létrehozása és rögzítése a POS tranzakciónaplóban a tranzakció véglegesített egyidejűleg történik. Az aláírás könyvvizsgálati célból exportált naplóban is elérhető.

Csak a készpénzes értékesítések tranzakciói vannak aláírva. Az alábbiakban néhány olyan tranzakció látható, amely ki van zárva az aláírási folyamatból:

- Előlegek (vevői számla letéte)
- Értékesítési rendelések előlegei (vevői rendelés letétje)
- Ajándékutalvány kibocsátása
- Nem értékesítési tranzakciók (float entry, fizetőeszköz-kivétel így tovább)

Az aláírt adatok egy szöveges karakterlánc, amely a következő adatmezőkből áll. Az adatmezőket pontosvessző választja el egymástól.

1. Ugyanannak a POS-nak az előző aláírása (az \[**első tranzakcióhoz 0-t**\] használ a rendszer.)
2. Tranzakció dátuma
3. Tranzakció időpontja
4. Egymást követő aláírt tranzakció száma
5. Tranzakció összege adóval együtt
6. Tranzakció összege adó nélkül

A digitális aláírási folyamat egy 1024 bites RSA-kulcsot használ, amely SHA-1 (RSA-SHA1-1024) kivonatolási funkcióval rendelkezik. A Commerce Scale Unit szolgáltatásra telepített tanúsítvány aláírásra használatos. A tanúsítvány (gyűjtés) egyedi azonosítója az aláírással együtt van rögzítve.

Az aláírást a rendszer az üzletadatbázisban és a központi adatbázisban tárolja, a tranzakció adataival együtt. A tranzakció **aláírása** **és a generáláshoz használt tranzakcióadatok az Üzlettranzakciók lap Pénzügyi tranzakciók gyorslapján nézett meg.**

#### <a name="receipts"></a>Bevételezések

A Norvégia bevételezései tartalmazhatnak további adatokat is, amelyek egyéni mezők használatával vannak megvalósítva:

- **Nyugtacím** – a bevételezési formátum elrendezéséhez hozzáadhat egy mezőt, amely azonosítja a nyugta típusát. Például az értékesítési nyugtán az "Értékesítési nyugta" szöveg fog szerepeljen.
- **Aláírt tranzakció sorszáma** – az aláírt tranzakció sorozatszáma megjelenhet a nyugtán, és a nyomtatott nyugtát digitális aláíráshoz társíthatja az adatbázisban.
- **Bevételezések összegei** – a bevételezési összegek egyéni mezői kizárják a nem értékesítési összegeket a tranzakció végösszegeiből. A nem értékesítési összegek a következő műveletek összegeit tartalmazzák:

    - Előlegek (vevői számla letéte)
    - Értékesítési rendelések előlegei (vevői rendelés letétje)
    - Ajándékutalvány kibocsátása
    - Ajándékutalványhoz adott fedezet hozzáadása

#### <a name="x-and-z-reports"></a>X- és Z-jelentések

Az X- és Z-jelentésekben szereplő adatok a norvég követelményeken alapulnak. Például a készpénzes **értékesítések** teljes összege csak a készpénzes értékesítési tranzakciók összegeit tartalmazza, és nem tartalmaz ajándékutalvány-műveleteket és előlegeket. Az összes készpénzes értékesítés cikkcsoportonként és fizetési módonként is megjelenik a listán. Ezenfelül a program **karbantartja** **és** kinyomtatja a végösszegek összesített végösszegét és a végösszegeket is.

#### <a name="saf-t-cash-register-audit-file"></a>SAF-T pénztárgép könyvvizsgálati fájlja

A POS tranzakciónaplót az előre meghatározott Standard Audit File - Tax (SAF-T) pénztárgép formátumban exportálhatja. A könyvvizsgálati fájl információkat tartalmaz a szervezetről, a szükséges alapadatokról (például cikkcsoportokról, cikkekről és adókódokról), a készpénzes értékesítési tranzakció adatairól, valamint az ilyen tranzakciók aláírásáról, a nem értékesítési események adatairól és a dátum végének jelentési adatairól.

A könyvvizsgálati fájl a következő esetekben exportálható:

- Üzletenként
- Minden üzlet
- Terminálonként
- Minden terminál

Az egyik jogi személytől egy másik jogi személy nevében is küldhet jelentést. Ebben az esetben az exportot az üzemi jogi személyből kell futtatni, és a jelentés feladójaként meg kell adni a jelentés jogi személyét.

Az SAF-T pénztárgép formátuma az Elektronikus jelentés segítségével valósítható meg a Headquarters [alkalmazással](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md). 

## <a name="setting-up-commerce-for-norway"></a>A Commerce for Norway beállítása

Ez a szakasz a Norvégiához specifikus és ajánlott beállításokat írja le. A további tudnivalókat lásd a [súgóerőforrásokban Dynamics 365 Retail](../index.md).

A Norvégia-specifikus funkciók használatához a következő feladatokat kell elvégeznie:

- Állítsa az **Ország/régió** mezőt **NOR** (Norvégia) mezőre a jogi személy elsődleges címében.
- Állítsa AZ **ISO-kód** mezőt **NO** (Norvégia) értékre minden Norvégiában található üzlet POS-funkcióprofiljában.

A következő beállításokat kell megadni Norvégia esetében is.

### <a name="set-up-the-legal-entity"></a>A jogi személy beállítása

Győződjön meg róla, hogy meg van adva a jogi személy neve. Ez a név lesz nyomtatva az X- és A-Z-jelentésekre.

Ezenkívül a Bankszámla adatai **gyorscsoport** **Útvonalszám** mezőjében adja meg a szervezet számát.

### <a name="set-up-value-added-tax-vat-per-norwegian-requirements"></a>Áfa (áfa) beállítása norvég követelmények szerint


Létre kell hoznia áfakódokat, áfacsoportokat és cikkadócsoportokat. A termékekre és szolgáltatásokra vonatkozó áfaadatokat is be kell állítani. Az áfa beállításának és használatának további tudnivalókat lásd [: Áfa áttekintése](../../finance/general-ledger/indirect-taxes-overview.md).

Meg kell adnia az áfacsoportokat **is**, és engedélyeznie kell a Norvégiában található üzletekben az Árak tartalmazzák az áfa beállítást.

### <a name="set-up-functionality-profiles"></a>Funkcióprofilok beállítása

Engedélyeznie kell a könyvvizsgálatot, és be kell állítania a nyugtaszámozást.

### <a name="update-pos-permissions-groups-and-individual-permission-settings-for-store-workers"></a>POS-engedélycsoportok és egyéni engedélybeállítások frissítése az üzlet dolgozói számára

Állítsa a **Nyugták másolási engedélyének** nyomtatását megfelelő értékre:

- **Mindig megengedett** – a kezelő többször is kinyomtathatja a nyugta másolatát.
- **Csak egyszer engedélyezze** – a kezelő csak egyszer nyomtathatja ki a nyugta másolatát.
- **Csak egyszer engedélyezzen,** és csak akkor, ha elérhető a központ adatbázisa – a kezelő csak egyszer nyomtathat ki egy nyugtát, és csak akkor, Commerce Data Exchange ha a központ adatbázisa elérhető a Real-time Service szolgáltatás segítségével, így a rendszer ellenőrizheti, hogy a nyugtának egyetlen példányát sem nyomtatták ki korábban egyetlen üzletben sem.
- **Soha** – a kezelő nem nyomtathat nyugtát.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Egyéni mezők konfigurálása az értékesítési nyugták nyugtaformátumában való használhatóra

Adja hozzá **a Nyelv szöveglapon** a következő rekordokat a nyugtaelrendezések egyéni mezőinek címkéihez. Ne feledje, **hogy** **a táblázatban** látható nyelvazonosító, **szövegazonosító** és szöveg értékek példák. A beállításokat az igényeknek megfelelően módosíthatja.

| Nyelvazonosító | Szöveg                   | Szövegazonosító |
|-------------|------------------------|---------|
| hu       | Nyugta címe          | 900011  |
| hu       | Ajándékutalvány           | 900012  |
| hu       | Összesen (értékesítés)          | 900013  |
| hu       | Összes adó (értékesítés)      | 900014  |
| hu       | Összesen adóval (értékesítés) | 900015  |
| hu       | Adóösszeg (értékesítés)     | 900016  |
| hu       | Készpénztranzakció azonosítója    | 900017  |

Adja hozzá **a** következő rekordokat az Egyéni mezők lapon a nyugtaelrendezések egyéni mezőihez. A felirat **szövegazonosító értékeinek** meg **·** **kell felelniük a Nyelv szövegoldalán megadott szövegazonosító értékeknek.**

| Név                            | Típus    | Képaláírás-szöveg azonosítója |
|---------------------------------|---------|-----------------|
| Nyugta                    | Fogadás | 900011          |
| IsGiftCard                      | Fogadás | 900012          |
| SalesTotalExt                   | Fogadás | 900013          |
| TaxTotalExt                     | Fogadás | 900014          |
| TotalWithTaxExt                 | Fogadás | 900015          |
| AmountPerTaxExt                 | Fogadás | 900016          |
| CashTransactionSequentialNumber | Fogadás | 900017          |

> [!NOTE]
> Fontos, hogy a megfelelő egyéni mezőneveket adja meg a fenti táblázatban felsoroltak szerint. Helytelen egyéni mezőnév esetén hiányoznak az adatok a nyugtákból.

### <a name="configure-receipt-formats"></a>Nyugtaformátumok konfigurálása

Minden kötelező nyugtaformátumnál módosítsa a Nyomtatás viselkedése mező értékét Úgy, **·** **hogy** a nyugtaformátum esetében mindig nyomtass.

A Nyugtaformátum-tervezőben adja hozzá a következő egyéni mezőket a megfelelő nyugtaszakaszokhoz. A mezőnevek megfelelnek az előző szakaszban meghatározott nyelvszövegnek.

1. Fejléc:

    - **Nyugtacím** – ez a mező azonosítja a nyugta típusát.
    - **Készpénztranzakció azonosítója** – ez a mező az aláírt készpénztranzakció egymás utáni számát nyomtatja ki.

2. Sorok:

    - **Ajándékutalvány –** ez a mező az ajándékutalvány-kiadás vagy hozzáadás ajándékutalványhoz művelethez kapcsolódóként jelöli meg a nyugtasort.

3. Lábléc:

    - **Összesen (értékesítés)** – ez a mező a nyugta teljes készpénzes értékesítésének összegét nyomtatja ki. Az összeg nem tartalmazza az adót. Az előlegek és ajándékutalvány-műveletek nem tartoznak ide.
    - **Adó összesen (értékesítés)** – ez a mező a készpénzes értékesítések bevételezésének teljes adóösszegét nyomtatja ki. Az előlegek és ajándékutalvány-műveletek nem tartoznak ide.
    - **Adóval (értékesítés)** összesen – ez a mező a nyugta teljes készpénzes értékesítésének összegét nyomtatja ki. Az összeg tartalmaz adót. Az előlegek és ajándékutalvány-műveletek nem tartoznak ide.
    - **Adó összege (értékesítés)** – ez a mező kinyomtatja a bevételezés adóösszegét az áfakódonkénti készpénzes értékesítéshez. Az előlegek és ajándékutalvány-műveletek nem tartoznak ide.

A nyugtaformátumok beállításával [és tervezésával kapcsolatos további tudnivalókat lásd a Nyugtaformátumok beállításával és tervezésával kapcsolatban](../receipt-templates-printing.md).

### <a name="configure-the-saf-t-cash-register-export-format"></a>Az SAF-T pénztárgép exportformátumának konfigurálása

Az SAF-T pénztárgép konfigurációja letölthető a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból. További információ az Elektronikus jelentési konfigurációk [importálása oldalon található](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-import-ger-configurations.md). Le kell töltenie a következő konfigurációkat:

- **Kiskereskedelmi csatorna data.version.1** – az adatmodell konfigurációja.
- **DMM Retail csatorna data.version.1.14** – az adatmodell-hozzárendelés konfigurációja.
- **NO SAF T Cash Register.version.1.20** – a formátum konfigurációja.

A konfigurációk importálása **után az Elektronikus dokumentumok lap SAF-T** készpénzjegyzék-exportálási formátum mezőjében a **Commerce** **paraméterek** lapján válassza ki az importált formátumkonfiguráció nevét.

A szükséges alapadatokat előre meghatározott SAF-T szabványkódokként is le kell leképezni. A további tudnivalókat lásd a norvég adóhivatal által benyújtott SAF-T pénztárgép dokumentációjában. A hozzárendelés létrehozásához be kell állítania **az új SAF-T** pénztárgép-kód mezőt a következő lapokon:

- Cikkcsoportok
- Kifizetési módok
- Áfakódok

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

A Norvégia-specifikus funkciók engedélyezéséhez konfigurálnia kell a csatornaösszetevőkat. A további tudnivalókat lásd a telepítési [irányelvekben](emea-nor-fi-deployment.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
