---
title: B2B üzleti partnerek kezelése vevőhierarchiák használatával
description: Ez a témakör azt ismerteti, hogyan lehet a vevői hierarchiákat használni az üzleti partnerek kezelésére a Microsoft Dynamics 365 Commerce vállalat és vállalat közötti (B2B) e-commerce webhelyeken.
author: josaw1
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d6e594cbb824a8b823912118e99b819585adc45e
ms.sourcegitcommit: 8bcb9c13eccb14e61c39ca6578d135b64090fad2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2022
ms.locfileid: "8313843"
---
# <a name="manage-b2b-business-partners-using-customer-hierarchies"></a>B2B üzleti partnerek kezelése vevőhierarchiák használatával

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet a vevői hierarchiákat használni az üzleti partnerek kezelésére a Microsoft Dynamics 365 Commerce vállalat és vállalat közötti (B2B) e-commerce webhelyeken.

A Commerce Headquartersban egy *vevőhierarchia-entitás* képviseli azokat az üzleti partnereket, amelyek a B2B e-commerce webhelyet fogják használni. Ahhoz, hogy a vevői hierarchiákat használni tudja az üzleti partnerek kezelésére, engedélyeznie kell a B2B e-commerce képességeket a Commerce Headquarters szolgáltatásban, majd meg kell határoznia a vevőhierarchia számsorozatát.

## <a name="enable-the-b2b-e-commerce-feature-in-commerce-headquarters"></a>A B2B e-commerce funkció engedélyezése a Commerce Headquarters szolgáltatásban

A B2B e-commerce **funkciók használatához először engedélyeznie kell a B2B eCommerce** képességek használatára vonatkozó funkciót a Commerce Headquarters szolgáltatásban.

1. Menjen a **Munkaterületek \> Funkciókezelés** lehetőségre.
1. A Mind **lapon** használja a szűrőmezőt **a Modul: Retail és Commerce kereséséhez**.
1. Keresse meg **a B2B eCommerce** képességek használatára lehetőséget, jelölje ki, **majd válassza ki az Engedélyezés lehetőséget** a jobb alsó sarokban.

## <a name="define-a-number-sequence-for-the-customer-hierarchy"></a>A vevőhierarchia számsorozatának meghatározása

A számsorozatokat az azonosítókat igénylő alapadatrekordok és tranzakciórekordok olvasható, egyedi azonosítóinak létrehozására használja a rendszer. Meg kell határoznia egy számsorozatot, amely a vevőhierarchia azonosítójának létrehozásához lesz használva. A számsorozatokkal kapcsolatos további információkat lásd: [Számsorozatok áttekintése](/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview).

A Commerce Headquartersban a vevők hierarchiája számsorozatának meghatározásához kövesse ezeket a lépéseket.

1. Ugrás a **Retail and Commerce \> Headquarters beállítási \> számsorozataihoz \>**
1. Hozzon létre egy új számsorozatot, vagy válasszon ki egy meglévő számsorozatot az újbóli felhasználás céljából.
1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce megosztott paraméterek** menüpontra.
1. Adja hozzá **a korábban létrehozott vagy** **korábban kiválasztott számsorozatot a Számsorozatok lapon a Vevőhierarchia azonosítójára való hivatkozáshoz**.

![A vevőhierarchia-azonosító hivatkozásában megadott számsorozat.](../media/NumberSequenceCustHierarchy.png)

## <a name="how-the-approval-process-works"></a>A jóváhagyási folyamat működése

Amikor egy üzleti partner csatlakozni kér egy B2B e-commerce webhelyhez, *a rendszer a kérést potenciális vevőként menti*. A Commerce Headquarters egy személye, például a kiskereskedelmi üzemeltetési vezető jóváhagyhatja vagy elutasíthatja a partneri kérelmeket. Az üzleti partnerek kérésének és [a potenciális vevők jóváhagyásának kezelésével kapcsolatos további tudnivalókat lásd Az üzleti partner felhasználóinak kezelése a B2B e-commerce webhelyeken](manage-b2b-users.md).

A potenciális vevő jóváhagyása után a rendszer két új vevőrekordot hoz létre:

- A Szervezet típusú vevőrekord **képviseli** azt a szervezetet, amely az üzleti partnerré való igénylést kéri.
- A Személy típusú vevőrekord **képviseli** azt a személyt, aki a kérelmet benyújtotta.

Ezen kívül a **Retail és Commerce \>\> Customer hierarchiákban új vevői hierarchiarekord jön létre**. Ennek a vevőhierarchia-rekordnak a következő tulajdonságai vannak:

- **Vevőhierarchia azonosítója** – a vevőhierarchia egyedi azonosítója. Ez az azonosító a Commerce megosztott paramétereiben megadott számsorozatot használja.
- **Név** – az üzleti partner szervezetének neve a beléptetési kérelemben megadottaknak megfelelően. Ez a mező szerkeszthető.
- **Cél** – ez a tulajdonság az előre meghatározott **B2B szervezet** értékre van beállítva.
- **Szervezet** – az üzleti partner szervezetének vevőazonosítója.

A felvett kérést **beküldött személy bekerül a Hierarchia** gyorslapra, **és** a rendszergazdai szerepkör lesz hozzájuk rendelve. Mivel a rendszergazda további felhasználókat ad hozzá az üzleti partner szervezetéhez a B2B webhelyen, a rendszer minden egyes felhasználóhoz új vevőrekordot hoz létre. A vevőrekord hozzáadódik az üzleti partnerhez kapcsolódó vevői hierarchiarekordhoz is, **és** a rendszer hozzárendeli a felhasználói szerepkört.

### <a name="examples"></a>Példák

Egy Sam J. nevű személy a Microsoft szervezet nevében be fog nyújtani egy, a hajóra vonatkozó kérést. A kérés jóváhagyása után két új vevői számla jön létre: **az** egyik A személy típusa a J. **Személy**, és az egyik a Microsoft szervezettípusa.

Mint azt a következő példa mutatja, egy új vevőhierarchia-rekord is létrejön. Ennek a rekordnak ugyanaz a neve, mint a szervezetnek (**Microsoft**),**és** a rendszergazdai szerepkör Sam J-hez van rendelve. Rendszergazdaként Sam J. hozzáadja a B2B **webhely összes többi Microsoft-felhasználóját ehhez a hierarchiához, és hozzárendeli a** felhasználót a hierarchiához. Ebben a példában Sush R. felhasználóként lett hozzáadva.

![Példa vevőhierarchia-rekordra](../media/CustomerHierarchy2.png)

Annak megállapításához, hogy a vevő vevői hierarchiához van-e társítva, nyissa meg a vevőrekordot. **A következő példában példaként megjelenik a Kiskereskedelmi gyorsábra B2B** **szakaszának** Vevőhierarchia-azonosító **mezője**, amely mutatja, hogy a vevő egy vevői hierarchia része-e, **és a B2B** rendszergazdai beállítás jelzi, hogy a vevő ennek a hierarchiának a rendszergazdája-e.

![Példa a B2B szakaszra egy vevőrekord Retail gyorsában, ahol a vevő hierarchiához van társítva, és rendszergazdaként van megadva.](../media/CustomerHierarchyMapping2.png)

A legtöbb esetben egy hierarchiában található összes vevőrekord tulajdonságértékének meg kell egyeznie. Például mivel minden üzleti partner felhasználójának hasonló árakat kell kapnia a termékekre, ezért az árcsoportnak és a társított konfigurációknak is egyezniük kell. A rendszer azonban nem érvényesíti ezt a konzisztenciát. Ezért a Commerce központi felületének adott felhasználói felelősek azért, hogy a tulajdonságértékek és konfigurációk egy adott hierarchiában lévő összes vevőre vonatkozóan megegyezzenek egymással.

A Commerce Headquarters felhasználói hierarchiák minden vevőrekordjának tulajdonságértékeit egymás mellett vizsgálhatja meg. Mint azt a következő példa mutatja, **használhatja** az Általános lehetőséget a **Hierarchia** gyorsgombok legördülő listájában, majd kiválaszthatja a vevőrekord bármelyik szakaszát, hogy a kapcsolódó tulajdonságokat mutassa. A felhasználók közvetlenül ebben a nézetben szerkeszthetik a tulajdonságértékeket. Ha egy rendszergazdai vevőrekord minden értékét át szeretné másolni az összes felhasználóhoz, **válassza** a Felülbírálás lehetőséget **a Hierarchia gyorslapon**.

![Példa vevőhierarchia-rekordra, amely a Felülbírálás gombot és a legördülő lista beállítását mutatja.](../media/HierarchyDetails2.png)

[!include [footer-include](../../includes/footer-banner.md)]
