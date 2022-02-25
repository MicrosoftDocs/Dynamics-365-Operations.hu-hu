---
title: A B2B e-commerce webhelyekhez használt vevői számlafizetési mód konfigurálása
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni a vevői számla fizetési módját a következőben:Microsoft Dynamics 365 Commerce Ismerteti azt is, hogy a hitelkeretek hogyan befolyásolják a részszámla-kifizetések rögzítését a vállalat és vállalat között e-kereskedelmi webhelyeken.
author: josaw1
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0366f7b51ac138cc7305f98d5607c554440e6d34
ms.sourcegitcommit: 68114cc54af88be9a3a1a368d5964876e68e8c60
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2022
ms.locfileid: "8323355"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>A B2B e-commerce webhelyekhez használt vevői számlafizetési mód konfigurálása

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell konfigurálni a vevői számla fizetési módját a következőben:Microsoft Dynamics 365 Commerce Ismerteti azt is, hogy a hitelkeretek hogyan befolyásolják a részszámla-kifizetések rögzítését a vállalat és vállalat között e-kereskedelmi webhelyeken.

A kiskereskedők különböző típusú kifizetéseket fogadhatnak el e-kereskedelmi csatornán értékesített termékeikért és szolgáltatásaikért. Minden egyes fizetéstípust, amelyet egy kiskereskedő elfogad, konfigurálni kell a Dynamics 365 Commerce rendszer beállításakor. A B2B e-commerce webhelyeken támogatni kell a vevői számlához (vagy a "on-account") fizetési módot. 

## <a name="prerequisites"></a>Előfeltételek

1. Adja hozzá a vevői számlafizetési módot a Commerce központi felületéhez.
2. Társítsa a vevői számlafizetési módot egy e-kereskedelmi csatornához.
3. Győződjön meg arról, hogy **engedélyezve van a "On account"** **tulajdonság a Retail és Commerce \> Customers \>\>** Minden vevő fizetésének alapértelmezése a Commerce Headquarters szolgáltatásban.

    > [!NOTE]
    > Ha minden vevőnél engedélyezni kell a on-account **·** **fizetési módot,** a B2B webhelyhez társított csatorna alapértelmezett vevőjére beállíthatja a Számlán való engedélyezése tulajdonságot Igen beállítással. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>A vevői számlafizetési mód engedélyezése a Commerce webhelykészítőben 

A vevői számlafizetési mód Commerce webhelykészítőben való engedélyezéséhez kövesse az alábbi lépéseket.

1. Lépjen a **Webhelybeállítások \> Bővítmények** pontra.
1. Állítsa a **Vevői számlafizetések engedélyezése** tulajdonságot **Engedélyezve B2B vevők esetében** értékre. 
1. Válassza a **Mentés és közzététel** lehetőséget.

> [!NOTE]
> Az új webhelybeállítások csak az app.settings.json fájl frissítése után lépnek hatályba. A további tudnivalókat lásd itt: [SDK- és modultár-frissítések](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>A vevői számlás fizetési mód engedélyezése a B2B e-kereskedelmi webhely pénztároldalán

A vevői számlás fizetési mód B2B e-kereskedelmi webhely pénztároldalán való engedélyezéséhez kövesse az alábbi lépéseket.

1. A Commerce webhelykészítőben keresse meg és szerkessze a B2B e-kereskedelmi webhely pénztármodulját tartalmazó pénztároldalt vagy töredéket.
1. A **Fizetési szakasz tárolója** helyen válassza a **Modul hozzáadása** lehetőséget, majd adjon hozzá egy **Vevői számlafizetés** modult.
1. A **Vevői számlafizetés** modult úgy pozicionálja, hogy kijelöli a három pontot (**...**), majd a **Felfelé** vagy a **Lefelé** nyíl kiválasztásával állítsa be a pozíciót.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>A vevői számlafizetési mód engedélyezésének és közzétételének megerősítése

A vevői számlafizetési mód engedélyezésének megerősítéséhez kövesse az alábbi lépéseket.

1. Jelentkezzen be az e-kereskedelmi webhelyre.
1. Adjon hozzá egy terméket a kosárhoz.
1. Lépjen a pénztároldalra. Itt látnia kell az új **Vevői számla** fizetési módot.

## <a name="work-with-credit-limits"></a>Hitelkeretek

Ha a B2B webhelyen engedélyezve vannak a vevői számlakifizetési lehetőségek, akkor a szervezetek általában a hitelkeretekkel és a hitelkeret-egyenlegekkel kapcsolatos információkat kívánják látni a rendelésrögzítési folyamat során. A vevők hitelkeretét **a** **Commerce** Headquarters vevőrekordja Jóváírás és beszedési gyorslapján található Hitelkeret tulajdonság határozza meg. A B2B helyzetekben azonban az a rendelés, amely szerint a vevőhelyekről gyakran kell számlát kiszámlázni annak a szervezetnek a számára, amelyhez a vevő tartozik. Ezért a **vevőrekord** **Számla** és szállítás gyorslapján be kell állítania a Számla számla tulajdonságát a szervezet vevői számlaazonosítója számára. Ezt követően amikor a vevő rendelést aD fel a B2B telephelyre, a rendelés számlázása meg fog történik a szervezet számára. A B2B webhely a szervezet hitelkeretét is használja a vevőrekordban meghatározott hitelkeret helyett.

A B2B **webhelyen** megjelenő hitelkeret-számítás és egyenleg a Commerce Headquarters hitelkerettípus tulajdonságának beállításától függ. A tulajdonság helye attól függően változik, **·** **hogy** a Szolgáltatáskezelési munkaterületen engedélyezve van-e a Jóváíráskezelés funkció:

- Ha engedélyezve **van a** Jóváíráskezelés funkció, **·** **\>\>\> a tulajdonság a Jóváírás és beszedési beállítások beállításához használt Jóváírás és beszedési paraméterek Gyorslapon található.** 
- Ha a **Követeléskezelés** funkció nincs engedélyezve, **·** **\>\>\> akkor a tulajdonság a Kinnlevőségek – Beállítás Kinnlevőségek paraméterei között található, a Követeléskezelés paraméterei között.**

A Hitelkeret típus tulajdonság **által** támogatott értékek: **Nincs**, Egyenleg **,** **Egyenleg + szállítólevél vagy termékbevételezés**, valamint **Egyenleg + Mind**. Ezekről az értékekről a Hitelkeret [típusának értékeinél található további tájékoztatás](/dynamics365/supply-chain/sales-marketing/credit-limits-customers).

> [!NOTE]
> Javasoljuk **·** **, hogy a Hitelkeret típus tulajdonságát Egyenleg +** csomagolólevél vagy termékrendelés beállítására állítsa be, hogy a nyitott értékesítési rendelések ne számítsanak bele az egyenlegszámításba. Ezt követően, ha a vevők jövőbeni rendeléseket adnak fel, nem kell okkal befolyásolni az aktuális egyenlegüket.

A **számlarendelést** **befolyásoló** másik tulajdonság a vevőrekord Jóváírás és beszedés gyorslapján található kötelező hitelkeret-tulajdonság. Ha adott **vevők** esetében Igenre állítani ezt a tulajdonságot, a rendszer ráveheti a hitelkeret-ellenőrzésre, még akkor is, **·** **ha** a Hitelkeret típusa tulajdonság beállítása "Nincs" beállítással határozza meg, hogy a hitelkeret ellenőrzése egyik vevőnél sem történik meg.

Jelenleg olyan B2B helyek **is** használhatók, ahol engedélyezve van a Kötelező hitelkeret tulajdonság. Ha a tulajdonság engedélyezve van egy vevőrekordban, és a vevő rendelést ad fel, akkor a B2B webhely megakadályozza, hogy a fennmaradó hitelegyenlegnél nagyobb összeget fizessen meg a számlára történő fizetésre. Ha például a vevő fennmaradó hitelegyenlege $1,000, de a rendelés érdemes $1,200, akkor a vevő csak $1,000 fizethet a számla módszerével. Más fizetési módot kell használniuk az egyenleg kifizetésére. Ha egy **vevőrekordban** le van tiltva a Kötelező hitelkeret tulajdonság, akkor a vevő bármilyen összeget kifizethet a számlánkénti fizetési mód használatával. Bár a vevő rendeléseket ad fel, a rendszer nem engedélyezi ezeknek a rendeléseknek a teljesítését, ha túllépik a hitelkeretet. Ha **a** **·** **hitelkeretet minden olyan vevőnél ellenőriznie kell, akinél ez a hitelkeret-kifizetésre jogosult, akkor javasoljuk,** **hogy** a Hitelkeret típus tulajdonságát Az egyenleg + csomagolási bizonylat vagy termékkifizetés, a kötelező hitelkeret tulajdonságot pedig Nem beállításra állítsa.

A **Jóváírás és beszedési modul** új hitelkezelési funkciókat kínál. Ha be szeretné kapcsolni ezeket a funkciókat, engedélyezze **a** Jóváíráskezelés funkciót a Szolgáltatáskezelés **munkaterületen**. Az új lehetőségek egyike lehetővé teszi, hogy a blokkolási szabályok alapján az értékesítési rendeléseket visszatartsa a rendszer. A hitelkártya-vezető ezután további elemzés után kiadhatja vagy elutasíthatja a rendeléseket. Az értékesítési rendelések a Commerce rendelések esetében nem alkalmazhatóak, mivel az értékesítési rendelésekhez gyakran van előleg, **és** a jóváírás-kezelési funkció nem támogatja teljesen az előlegfizetési helyzeteket. 

Függetlenül attól, hogy engedélyezve van-e **a** Jóváíráskezelés funkció, ha a rendelés teljesítése során egy vevő egyenlege túllépi a hitelkeretet, az értékesítési rendelések nem fognak kivájni. Ehelyett a Commerce rendszer egy figyelmeztető üzenetet vagy hibaüzenetet generál, attól függően, **·** **hogy** a hitelkeret-gyorsjelentés hitelkeret-túlcsatlott mezőjében milyen érték jelenik meg.

Az **értékesítési rendelés fejlécében** található a Kihagyás a jóváíráskezelésből tulajdonságból, amely megakadályozza, hogy a Commerce értékesítési rendeléseket visszatartsa a rendszer az értékesítési rendelés fejlécében (**Retail és Commerce \> Customers All \> értékesítési rendelések**). Ha ez a tulajdonság a **Commerce** értékesítési rendeléseknél Igen (az alapértelmezett érték) értékre van állítva, a rendelések ki lesznek zárva a hitelkezelési munkafolyamatból. Bár a tulajdonság neve Kizárás a **jóváíráskezelésből**, a megadott hitelkeretet akkor is használja a rendszer a rendelés teljesítése során. A rendelések nem fognak felrakodni.

A commerce rendszer a zárolási szabályok alapján a commerce értékesítési rendeléseket zárolási szabályok alapján fel fogja függesni a jövőbeni Commerce kiadásokban. Ha nem támogatott, addig, amíg a Commerce értékesítési rendeléseket rá kell kényszerítenie az új jóváíráskezelési folyamatok végigvezetésére, a megoldásban a következő XML-fájlokat szabhatja testre Visual Studio. A fájlokban módosítsa úgy a logikát **, hogy a CredManExcludeSalesOrder** jelző Beállítása **Nem**. Ily módon **a** **Commerce** értékesítési rendelések esetén a Kizárás a jóváírásból tulajdonság alapértelmezés szerint Nem beállításra lesz állítva.

- RetailCreateCustomerOrderExtensions_CredMan_Extension.xml
- RetailCallCenterOrderExtensions_CredMan_Extension.xml

Ne feledje, **hogy ha a CredManExcludeSalesOrder** **jelző** nemre van állítva, és a B2B-vevők a pénztári alkalmazás használatával vásárolnak az üzletekből, akkor sikertelen lehet a készpénz- és áthozott tranzakciók feladása. Például a készpénzfizetési típusra egy blokkolási szabály vonatkozik, és a B2B vevő készpénzzel vásárolt néhány, az üzletben található cikkeket. Ebben az esetben az eredményül kapott értékesítési rendelés számlázása nem lesz sikeres, mert az fel lesz függve. Ennek megfelelően a feladás sikertelen lesz. Ezért javasoljuk, hogy a testreszabás megvalósítása után hajtsa végre a teljes tesztelést.

## <a name="additional-resources"></a>További erőforrások

[B2B e-kereskedelmi webhely beállítása](set-up-b2b-site.md)

[B2B üzleti partnerek kezelése vevőhierarchiák használatával](partners-customer-hierarchies.md)

[Üzleti partner felhasználóinak kezelése a B2B e-kereskedelmi webhelyeken](manage-b2b-users.md)

[Termékmennyiség-korlátok beállítása B2B e-kereskedelmi webhelyekhez](quantity-limits.md)

[SDK- és modulkönyvtár-frissítések](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
