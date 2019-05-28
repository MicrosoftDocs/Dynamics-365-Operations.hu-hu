---
title: Szállítói együttműködés a vevőkkel
description: Ez a témakör leírja, hogyan használja a szállítói együttműködést a vevőkkel történő munkában a Microsoft Dynamics 365 for Finance and Operations rendszerben a beszerzési rendelésekkel kezelése és a bizományosi készlet figyelése során.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bd3967da105b3cec4a722ee8e04fac13c798feec
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567584"
---
# <a name="vendor-collaboration-with-customers"></a>Szállítói együttműködés a vevőkkel

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan használja a szállítói együttműködést a vevőkkel történő munkában a Microsoft Dynamics 365 for Finance and Operations rendszerben. A szállítók a következő munkaterületekről tudnak különböző üzleti folyamatokat végrehajtani:

- **Beszerzési rendelés visszaigazolása** – Figyelje meg a beszerzési rendeléseket (POk), és válaszoljon rájuk.
- **Szállítói ajánlattétel** – tekintse meg az ajánlatkéréseket (RFQk), és válaszoljon rájuk ajánlatok megadásával.
- **Szállító adatai** – Tekintse meg és frissítse a szállítók alapadatait.
- **Számlázás** – Használjon számlákat. Ez a témakör nem foglalkozik a **Számlázás** munkaterülettel. További tudnivalókért erről a munkaterületről lásd: [Szállítói együttműködési számlázás munkaterület](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md).

A szállítók is megfigyelhetik a bizományosi készlettel kapcsolatos adatokat.

## <a name="working-with-pos-in-the-purchase-order-confirmation-workspace"></a>A Beszerzési rendelések kezelése a visszaigazolási munkaterületben

A **Beszerzési rendelések visszaigazolási** munkaterülete lehetővé teszi, hogy válaszoljon a véleményezésre elküldött beszerzési rendelésekre. Lehetővé teszi a vevői műveletre várakozó beszerzési rendelések adatainak megtekintését, valamint a vevő által visszaigazolt, de még nyitva levő beszerzési rendelésekkel kapcsolatos információk megtekintését is.

A **Beszerzési rendelések visszaigazolási** munkaterülete három listát tartalmaz:

- **Beszerzési rendelések ellenőrzésre** – Ez a lista azokat a beszerzési rendeléseket jeleníti meg, amelyek a válaszára várnak. Miután válaszol, a beszerzési rendelés eltűnik a listáról. Ha a vevő új beszerzési rendelést küld még mielőtt az előző verzióra válaszolt volna, a legújabb verzió jelenik meg.
- **Várakozás vevői műveletre** – Ez a lista a már megválaszolt, de a vevő által még nem jóváhagyott beszerzési rendeléseket jeleníti meg. Ha elfogadja a beszerzési rendelést, akkor nyomon követheti azt a listában addig, amíg az állapota **Visszaigazolva** státuszra nem vált. Ha visszautasítja a beszerzési rendelést vagy módosításokkal fogadta el, itt figyelheti azt addig, amíg a vevő az új verziót el nem küldi.
- **Visszaigazolt beszerzési rendelések megnyitása** – Ez a lista megjeleníti az összes **Visszaigazolva** státuszú beszerzési megrendelését. Amikor a termékeket vagy szolgáltatásokat teljes mértékben bevételezte, a beszerzési rendelés eltűnik a listáról.

A következő oldalakat használhatja a beszerzési rendelések kezeléséhez:

- **Beszerzési rendelések ellenőrzésre** – Ez az oldal ugyanazokat az adatokat tartalmazza, mint a **Beszerzési rendelések véleményezésre** lista a munkaterületben. A leírást lásd korábban a témakörben.
- **Beszerzési rendelés szállítójának visszaigazolási előzményei** – Ez az oldal a szállítóhoz küldött összes beszerzési rendelést, illetve azok mindegyik verzióját tartalmazza. Ezen felül az összes a szállító által küldött választ is tartalmazza.
- **Visszaigazolt beszerzési rendelések megnyitása** – Ez az oldal ugyanazokat az adatokat tartalmazza, mint a **Visszaigazolt beszerzési rendelések megnyitása** lista a munkaterületben. A leírást lásd korábban a témakörben.
- **Az összes visszaigazolt beszerzési rendelés** – Ez az oldal az összes visszaigazolt beszerzési rendelést tartalmazza. Az ezen a lapon található beszerzési rendelések olyan beszerzési rendeléseket is tartalmaznak, amelyeknél a termékek vagy a szolgáltatások már megérkeztek. Ezen lista segítségével követheti nyomon, hogy mely beszerzési rendelésekre küldhet számlákat.

### <a name="responding-to-pos"></a>Válaszolás beszerzési rendelésekre

A vevő által küldött beszerzési rendelések a **Beszerzési rendelések visszaigazolási** munkaterületén és a **Beszerzési rendelések véleményezésre** lapon jelennek meg. A beszerzési rendelés megnyitása után elfogadhatja, elutasíthatja vagy módosításokkal elfogadhatja azt. A beszerzési rendelés fejlécében vagy az egyes sorokhoz csatolva mellékletek lehetnek. Lehetősége van arra is, hogy adatokat csatoljon a válaszában a beszerzési rendelés fejlécében vagy az egyes sorokban. Például előfordulhat, hogy az egyik sorhoz helyettesítő cikket javasol.

A beszerzési rendelést PDF-fájlként megtekintheti nyomtatási előnézetben és ki is nyomtathatja az **Előnézet/nyomtatás** lehetőség használatával. A **Dimenziók megjelenítése** műveletet is használhatja a következő dimenzióoszlopok elrejtésére vagy megjelenítésére **Telephely**, **Raktár**, **Szín**, **Méret**, **Stílus**, és **Konfiguráció**. 

Ha az **Elfogadás módosításokkal** lehetőséget használja, akkor elfogadhatja vagy elutasíthatja az egyes sorokat. A sorokban az alábbi módosításokat lehet még végrehajtani:

- Módosíthatja a dátumokat vagy a mennyiségeket. A visszaigazolt szállítási dátum minden sorban való módosításához használja a **Szállítási dátum frissítése** lehetőséget a beszerzési rendelés fejlécében.
- Feloszthatja a sorokat eltérő szállítási dátumok vagy mennyiségek alapján.
- Helyettesíthet egy cikket. Írja be a cikkleírást és a cikkszámot a **Külső** mezőben a **Soradatok** szakaszban.

Nem módosíthatja az árképzési adatokat vagy a költségeket, de megjegyzések segítségével javasolhat módosításokat.

Ha a vevő a beszerzési rendelés új verzióját küldi el, ez rendelkezni fog egy verzió utótaggal, ami azt jelzi, hogy ez a korábban küldött beszerzési rendelés módosított változata. A **Beszerzési rendelés szállítói visszaigazolásának előzményei** lap segítségével nyomon követheti az egyes rendelések előzményeit.

## <a name="monitoring-consignment-inventory"></a>Bizományosi készlet figyelése

Bizományosi készlet használatakor a szállító együttműködési felület segítségével megtekintheti az adatokat a következő lapokon:

- **Bizományosi készletet használó beszerzési rendelések** – A bizományosi készletet használó beszerzési rendelések akkor jönnek létre, amikor az ügyfél lesz a készlet tulajdonosa. Ezek a bizományosi beszerzési rendelések csak ezen a lapon láthatók. Nem szerepelnek **Az összes visszaigazolt beszerzési rendelés** lapon.
- **Bizományosi készletből kapott termékek** – Ez a lap minden olyan tranzakciót listáz, amelynek során a termékek tulajdonjoga a készletet fogyasztó vállalatra ruházódott át. Ezt az információt a vevői számlák kibocsátására használhatja.
- **Aktuális bizományosi készlet** – Ez a lap megjeleníti a vállalata tulajdonában levő aktuális bizományosi készletet, amely aktuálisan a vevők raktárában van.

## <a name="working-with-rfqs-in-the-vendor-bidding-workspace"></a>Ajánlatkérések kezelése a szállítói ajánlattételek munkaterületen

A **Szállítói ajánlattételek** munkaterület lehetővé teszi, hogy megtekintse azokat az ajánlatkéréseket, amelyek megválaszolására az ön cégét meghívták. Válaszolni is tud az ajánlatkérésekre. 

A munkaterület ezen kívül az összes megnyert és elvesztett ajánlatkérést is megmutatja. Ezenkívül, ha a rendszer az állami szektorra van beállítva, a munkaterület megjeleníti a nyilvánosan elérhető ajánlatkéréseket.

### <a name="viewing-rfqs"></a>Ajánlatkérések megtekintése

Nyissa meg a **szállítói ajánlattételek** munkaterületet a következő adatok eléréséhez:

- Válassza ki ezt: **Új eladásiár-meghívások**, ha meg szeretné tekinteni azokat az ajánlatkéréseket, amelyek megválaszolására az ön cégét meghívták. Itt megtekinthet egy ajánlatkérést és megkezdheti az ajánlattételi folyamatot. Megtekintheti azokat a módosított ajánlatkéréseket is, amelyekhez új ajánlatot kell benyújtani.
- Válassza ki ezt: **Visszaküldött ajánlatok**, ha meg szeretné tekinteni azokat az ajánlattételeket, amiket a vevő visszaküldött önnek, hogy ön több információt nyújthasson, vagy módosíthassa az ajánlatot.
- Válassza ki ezt: **Folyamatban lévő ajánlatok**, ha meg szeretné tekinteni azokat az ajánlattételeket, amiket ön vagy egy, az ön cégét képviselő kapcsolattartó kezel, de még nem küldte el.
- Válassza ki ezt: **Megítélt ajánlatok**, ha meg szeretné tekinteni, hogy mikor került legalább egy sortétel a vevőhöz.
- Válassza ki ezt: **Elvesztett ajánlatok**, ha meg szeretné tekinteni azokat az ajánlatokat, ahol mindegyik sor elutasításra került.
- Válassza ki az **Ajánlatkérések** hivatkozást, ha meg szeretné tekinteni az összes szállítói ajánlatkérés-meghívás listáját és az összes elküldött ajánlatot. Az **Ajánlatkérések** oldal felsorolja az összes ajánlatkérést, amelyben a szállító részt vett. Kereshet állapot szerint.
- Válassza ki az **Elutasított ajánlatok** hivatkozást, ha meg szeretné tekinteni az összes olyan ajánlatkérés listáját, ahol a szállító kapcsolattartója nem tett ajánlatot.

### <a name="working-with-rfqs-that-are-publicly-available"></a>Nyilvánosan elérhető ajánlatkérések kezelése

Az állami szektorban dolgozó emberek megtekinthetik azokat a nyitott és lejárt ajánlatkéréseket, amelyeket elérhetővé tettek a nyilvánosság számára.

- Válassza ki a **Nyitott közzétett ajánlatkérések** hivatkozást, ha meg szeretné tekinteni a nyilvánosság számára elérhető nyitott ajánlatkérések listáját. Egy nyitott ajánlatkérés olyan ajánlatkérés, amely még nem járt le. A lejárati dátumot és időpontot az Ajánlatkérés fejlécében találhatja meg.

    Ha önt ajánlani hívták, megtalálhatja ugyanazt az ajánlatkérést az **Új eladásiár-meghívások** oldalon. Bizonyos esetekben ön ajánlana egy nyitott ajánlatkérésen, de nem lett meghívva. Ebben az esetben lehet, hogy meg tudja hívni önmagát, feltéve, hogy a vevő engedélyezte az önmeghívást az Ajánlatkérési esetre.

- Válassza ki a **Lezárt közzétett ajánlatkérések** hivatkozást, ha meg szeretné tekinteni a nyilvánosság számára elérhető lezárt ajánlatkérések listáját. A lezárt ajánlatkérés egy olyan ajánlatkérés, ami már lejárt. A lejárati dátumot és időpontot az Ajánlatkérés fejlécében találhatja meg.

    A lezárt Ajánlatkérés megjeleníti az összes szállítói ajánlatot a sorok szintjéig. ahogy az ajánlatokat odaítélik vagy elutasítják, ez az információ megjelenik a lezárt Ajánlatkérésben. Az ajánlatban szereplő mellékletek is elérhetők.

**Megjegyzés:** Ez a funkció csak akkor érhető el, ha az állami szektor konfiguráció engedélyezve van.

### <a name="bidding"></a>Ajánlattétel

- Kattintson erre: **Ajánlat** egy ajánlat indítására az ajánlatkérésen.

    Ha a szerkesztés engedélyezve van az ajánlatkérés sorain és fejlécein található ajánlatmezők számára , akkor közvetlenül a sorrácsban adhatja meg az ajánlatát. Ezenkívül figyelembe kell vennie a további ajánlatadatokat is, amiket a soradatokban kell megadnia.

    Az ajánlat kezelésének megkezdésekor az megjelenik a **Folyamatban lévő ajánlatok** szakaszban.

    A lejárati dátum előtt bármikor mentheti az ajánlatot. Később visszatérhet az ajánlat befejezéséhez és elküldéséhez. Az ajánlat elküldése után visszahívhatja és módosíthatja azt a lejárati dátumig.

- Válassza ki ezt: **Alaphelyzetbe állítva az ajánlatkérésből** az ajánlat számára beírt adatok visszaállítására és az eredeti ajánlatkéréshez való visszatérésre. Visszaállíthatja a fejlécet vagy a sort.
- Válassza ki ezt: **Alternatíva megadása** vagy ezt: **Alternatíva eltávolítása** a sorrácsban az alternatívák kezeléséhez.

    Egyes ajánlatkérések engedélyezik az alternatív ajánlatokat. Csak **Kategória** típusú vonalak esetén adhat meg alternatív ajánlatokat, mert konkrét elemeket nem adhat hozzá alternatívaként. 

- Válassza ki ezt: **Ajánlatkérés melléklete** vagy ezt: **Ajánlatkérési sorok melléklete** a vevő által az ajánlatkéréshez csatolt mellékletek megnyitásához. Válassza ki ezt: **Ajánlat mellékletei** vagy ezt: **Ajánlat sorainak mellékletei**, ha mellékleteket kíván feltölteni az ajánlattal együtt

    Előfordulhat, hogy meg kell válaszolnia egy kérdőívet, mielőtt engedélyt nyer ajánlatok beküldésére.

- Válassza ki ezt: **Elutasítás**, ha nem szeretne ajánlat tenni. Miután kijelölte ezt: **Elutasítás**, nem vonhatja vissza a műveletet, és nem adhat meg ajánlatot.

Ha az Ajánlatkérés módosul, akkor meg kell adnia egy új ajánlatot. További információkat a módosításról az Ajánlatkérés oldal **Módosítások** lapján találhat. A módosított ajánlatkérések az **Új eladásiár-meghívások** oldalon jelennek meg.

## <a name="accessing-vendor-master-data-in-the-vendor-information-workspace"></a>Szállítói alapadatok elérése a szállítói adatok munkaterületen

Szállítóként hozzáférhet a vevő által a szállítói törzsnyilvántartásban fenntartott adatok egy részéhez. Ezáltal naprakészen tarthatja az információit. Az adatok frissítéséhez egy szállító rendszergazdai (külső) szerepkörrel kell rendelkeznie.

Az elérhető adatok tartalmazzák a szállító nevét, címeit, kapcsolattartási adatait, kapcsolattartóit és a hozzájuk tartozó kapcsolattartási adatokat, az azonosító számokat, az Adószámokat, a szállító által a vevőnek történő eladásra jóváhagyott beszerzési kategóriákat, illetve a tanúsítványokkal kapcsolatos tájékoztatást.

## <a name="additional-resources"></a>További erőforrások

[Szállítói együttműködés felhasználóinak kezelése](manage-vendor-collaboration-users.md)
