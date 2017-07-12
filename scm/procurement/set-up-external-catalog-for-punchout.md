---
title: "Állítson be külső katalógust a PunchOut e-beszerzés számára"
description: "Ez a témakör egy külső katalógus (punchout-katalógus) használatát mutatja be, amelynek révén információt gyűjt egy szállítótól, hozzáadja egy igényléshez."
author: BibiSp
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 2d853cb963471f81d7a2a09a0f7913722de8a417
ms.contentlocale: hu-hu
ms.lasthandoff: 06/20/2017


---

# <a name="set-up-an-external-catalog-for-punchout-eprocurement"></a>Állítson be külső katalógust a PunchOut e-beszerzés számára

A külső katalógus segítségével biztosítható, hogy a Dynamics 365 for Finance and Operations Enterprise 2017. júliusi verziójában feldolgozott termék- és árinformációk pontosak és naprakészek legyenek. Az igénylés ezután jóváhagyható és beszerzési rendeléssé alakítható át, valamint leadhat egy rendelést a szállítónál.

Amikor a külső katalógus be van állítva, és egy alkalmazott egy igénylést készít elő, a rendszer felajánlja, hogy átirányítja egy külső webhelyre, egy külső katalógushoz, majd visszairányítja a külső webhelyen létrehozott bevásárlókosarat. Ez a kommunikáció cXML-protokollon alapul, amelyet be kell állítani a vásárló és az értékesítő szervezetek rendszerei között.

A kommunikáció beállításához a szállítójának bizonyos információkat kell megadnia annak érdekében, hogy ezeket a külső katalógus konfigurációjában felhasználhassa, többek között a következőket: Azonosító, a vevő vállalatának tartománya, például a DUNS és a DUNS-szám, hitelesítő adatok, valamint a szállító katalógusának URL-címe.

## <a name="setting-up-an-external-catalog"></a>Külső katalógus beállítása

A külső katalógusnak lehetővé kell tennie, hogy a beszerzési igénylésbe belépő alkalmazottat átirányítsa egy külső webhelyre a termék kiválasztása érdekében. Az alkalmazott által a külső katalógusből kiválasztott termékeket a rendszer visszairányítja a Dynamics 365 for Finance and Operations rendszerébe naprakész árinformációkkal, és innen hozzáadhatók a beszerzési igényléshez. A szándék nem az, hogy az alkalmazottak egy külső webhelyről rendelhessenek. A külső katalógus beállításakor győződjön meg arról, hogy a külső katalógus által hozzáférhető webhely célja az információgyűjtés, nem pedig valódi megrendelés leadása.

### <a name="to-set-up-an-external-vendor-catalog-complete-the-following-tasks"></a>Külső szállítói katalógus beállításához a következő feladatokat kell elvégeznie:

1. Beszerzési kategóriahierarchia beállítása. További információkért lásd: [Beszerzésikategória-hierarchiák irányelveinek beállítása](/https://ax.help.dynamics.com/en/wiki/set-up-policies-for-procurement-category-hierarchies/)
2. Regisztrálja a szállítót a Finance and Operations rendszerben. Mielőtt beállíthatná a külső gyártó katalógusához szükséges konfigurációkat, be kell állítania a szállítót és a szállítói kapcsolattartót a Microsoft Dynamics 365 rendszerben. A külső katalógus szállítóját is hozzá kell adni a kiválasztott beszerzési kategóriához. A szállítók Microsoft Dynamics 365 rendszerben történő regisztrálásával kapcsolatos további tudnivalókat lásd: [Szállítói együttműködés felhasználóinak kezelése](/procurement/manage-vendor-collaboration-users.md). A szállítónak a beszerzési kategóriához való hozzárendelésével kapcsolatos további tudnivalókat lásd: [Szállítók jóváhagyása konkrét beszerzési kategóriákra vonatkozóan](/https://ax.help.dynamics.com/en/wiki/approve-vendors-for-specific-procurement-categories/).
3. Győződjön meg arról, hogy a mértékegységek és a szállító által használt pénznem be van beállítva. A mértékegység létrehozásával kapcsolatos további tudnivalókat lásd: [Mértékegységek létrehozása](/https://ax.help.dynamics.com/en/wiki/manage-unit-of-measure/).
4. Állítsa be a külső szállítói katalógust a szállító külső katalógusának webhelye által előírt követelmények használatával. Az ezzel kapcsolatos további információkért tekintse meg a következő szakaszt.
5. Tesztelje a szállító külső katalógusának konfigurációit, hogy biztosítsa a beállítások érvényességét, valamint hogy hozzáférhet a szállítói külső katalógushoz. Használja a **Beállítások ellenőrzése** műveletet az ön által beállított beállításkérési üzenet ellenőrzéséhez. Az üzenet következményeként a szállítók külső katalóguswebhelyének meg kell nyílnia egy böngészőablakban. Az ellenőrzés során nem rendelhet cikkeket és szolgáltatásokat a szállítótól. Cikkek és szolgáltatások rendeléséhez egy beszerzési igénylésből kell hozzáférnie a szállítói katalógushoz.
6. Aktiválja a külső katalógust a **Katalógus aktiválása** gombra kattintva a **Külső katalógusok** lapon. A külső katalógust aktiválni kell, mielőtt az alkalmazottak használni kezdenék. A külső katalógust bármikor inaktiválhatja.


## <a name="4-configure-the-external-vendor-catalog"></a>(4) A külső szállítói katalógus konfigurálása

Ebben a szakaszban további tájékoztatást talál az előző szakasz 4. feladatával kapcsolatban.

1. Adjon egy nevet és leírást a szállító külső katalógusának. A beírt név megjelenik a külső katalógust jelölő bevásárlókocsiban, amely az igénylést létrehozó alkalmazottaknak megjelenik. Az alkalmazottak kattinthatnak a bevásárlókocsira a katalógusnak a szállító külső katalóguswebhelyén történő megnyitásához.
2. Adjon hozzá képet a **Külső katalógusbeli kép** művelettel. A kép megjelenik a külső katalógust jelölő bevásárlókocsiban, amely az igénylést létrehozó alkalmazottaknak megjelenik. Vegye figyelembe, hogy a kép szélességének és magasságának meg kell egyeznie. Ellenkező esetben a kép nem megfelelően jelenik meg.
3. Válassza ki, hogy a szállító külső katalóguswebhelye ugyanabban a böngészőablak jelenjen-e meg, mint amelyikben az alkalmazott az igénylést létrehozta, vagy pedig új ablakban nyíljon meg.
4. Válassza ki a katalógushoz tartozó szállítót. A **Jogi személyek** listában minden egyes jogi személyhez tartozik egy sor, ahol a szállító be van állítva. Annak érdekében, hogy a felhasználók csak bizonyos jogi személyek esetében igényelhessék közvetlenül a termékeket a szállítói katalógusból, másokban pedig nem, használhatja a **Hozzáférés megakadályozása** vagy a **Hozzáférés engedélyezése** gombot minden olyan jogi személy esetében, amelynél szeretné beállítani a katalógus elérhetőségét.
5. Az **Alapértelmezett lejárat (nap)** mezőben adja meg azon napok számát, amíg a külső katalógusból kapott árajánlatok érvényesek és használhatók maradnak a külső szállítótól történő beszerzéshez. Amikor létrehoz és lekér egy árajánlatot a szállító külső katalóguswebhelyéről, az árajánlat az aktuális rendszerdátumtól kezdve az ebben a mezőben megadott számú napig marad érvényes.
6. Kattintson a **Hozzáadás** gombra a beszerzési kategóriák külső katalógusnak történő megfeleltetésének elkezdéséhez. Ezután a Kategória neve listából válasszon egy kategóriát. A kategóriák listája olyan beszerzési kategóriaszabvány, amelynek a szállítót megfeleltette a rendszer a szállítóhoz tartozó minden jogi személy esetében.
[!NOTE]
A beszerzési irányelvek segítségével engedélyezheti vagy korlátozhatja a vevő jogi személyre vagy a fogadó üzemi egységre vonatkozó kategóriák hozzáférhetőségét. A külső katalógushoz történő kilépés megköveteli, hogy legalább egy olyan beszerzési kategóriához létezzen hozzáférési jogosultság, amely a katalógushoz van rendelve.
7. Állítsa be a szállítónak küldendő cXML beállításkérési üzenetet. Az automatikusan generált üzenetformátum a munkamenet elindításához szükséges minimális sablon. Töltse ki a címkék értékeit.

Bármikor újra betöltheti be a rendszer által generált üzenetsablont az **Üzenetformátum visszaállítása** lehetőségre kattintva. Vegye figyelembe, hogy az üzenetformátum visszaállításával az aktuális üzenetet az automatikusan generált üzenetformátum írja felül, amely üres címkéket tartalmaz.

### <a name="cxml-setup-message"></a>cXML beállítási üzenet
Az alábbiakban megtalálja a sablonban szereplő címkék leírását:

| Mező | Leírás | 
|---------|---------|
|< Fejléc >< Feladó >< Hitelesítési tartomány =”” >|A vevő vállalatának tartománya.|
|< Fejléc >< Feladó >< Hitelesítés >< Azonosító >< /Azonosító > | A vevő vállalatának azonosítója.|
|< Fejléc >< Címzett >< Hitelesítési tartomány =”” > | A szállító vállalatának tartománya.|
|< Fejléc >< Címzett >< Hitelesítés >< Azonosító >< /Azonosító> | A szállító vállalatának azonosítója.|
|< Fejléc >< Feladó >< Hitelesítési tartomány =”” > | A vevő vállalatának tartománya.|
|< Fejléc >< Feladó >< Hitelesítés >< Azonosító >< /Azonosító> | A vevő vállalatának azonosítója.|
|< Fejléc >< Feladó >< Hitelesítés >< SharedSecret >< /SharedSecret >|A vevő vállalatának közös titkos kulcsa.|
|< Request deploymentMode=”” >|A teszt vagy az éles telepítés.|
|< Kérelem >< PunchOutSetupRequest >< SupplierSetup >< URL >< /URL>|A szállító külső katalógus végpontjának URL-címe.|

### <a name="extrinsic-elements"></a>Külső elemek

A külső elem további információt jelent, például egy olyan felhasználónév, amely a külső katalógust használó felhasználónak felel meg. A külső elem beállítása a külső katalógus használatakor történik, és elküldhető a beállításkérési üzenetben.
Megtörténhet, hogy a szállítónál követelmény áll fenn egy a beállítási kérelemben levő külső elem fogadása tekintetében. Ebben az esetben hozzá kell adni a külső elemet a külső elemek listájához az **Üzenetformátum** részben a **Külső katalógus** lapon. Olyan nevet adjon a külső elemnek, amelyet a szállító felismer, és meg tudja feleltetni egy értéknek. A lehetséges értékek a következők: Felhasználónév, Felhasználói e-mail vagy Véletlenszerű érték.
A cXML-protokollal kapcsolatos további tudnivalókat lásd: http://cxml.org/

## <a name="post-back-message"></a>Visszajelzési üzenet
A visszajelzési üzenet a szállítótól kapott üzenet, amikor a felhasználó kilép a külső webhelyről, és visszatér a Finance and Operations rendszerbe. A visszajelzési üzenetek nem konfigurálhatók. Az üzenetek a cXML-protokoll definícióján alapulnak. Itt látható az a szöveg, amely az igénylési soron beérkező visszajelzési üzenet része lehet:

| Szállítótól kapott üzenet | Másolva a Finance and Operations rendszer igénylési sorába|
|------------------------------|----------------------------------------------------------|
|< ItemIn quantity=”” > |Mennyiség|
|< ItemIn>< ItemID >< SupplierPartID >< /SupplierPartID >|Külső cikkazonosító|
|< ItemDetail>< UnitPrice >< Pénznem=”” >| Pénznem|
|< ItemDetail >< UnitPrice >< Pénz >< /Pénz >| Egységár|
|< ItemDetail >< Description ShortName=”” >|Termék neve|
|< ItemDetail >< Leírás >< /Leírás >|Szerepel a cikk leírásában; Termék neve, ha nincs megadva a ShortName.|
|< ItemDetail >< UnitOfMeasure >< /UnitOfMeasure >|Egység|
|< ItemDetail >< Osztályozás >< /Osztályozás >|Szerepel a cikk leírásában|
|< ItemDetail >< Osztályozási tartomány =”” >|Szerepel a cikk leírásában|

## <a name="delete-an-external-catalog"></a>Külső katalógus törlése
Törölje a külső katalógust a lapon lévő Törlés művelettel.

A külső szállítói katalógus nem törölhető, ha egy terméket kért a külső szállítói katalógusból. Ehelyett a külső szállítói katalógus állapota inaktívra vált. Ha szeretné megszüntetni, de nem szeretné törölni a külső szállítói katalógus webhelyéhez való hozzáférést, állítsa a külső katalógus állapotát inaktívra.


