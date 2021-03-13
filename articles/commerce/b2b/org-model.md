---
title: Szervezeti modellezési hierarchiák létrehozása B2B szervezetek számára
description: Ez a témakör azt ismerteti, hogyan lehet szervezeti modellezési hierarchiákat létrehozni B2B szervezetek számára.
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 450efd595a1cc1b72b2e62afbdd4518bcca59cb0
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035915"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a>Szervezeti modellezési hierarchiák létrehozása B2B szervezetek számára

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet szervezeti modellezési hierarchiákat létrehozni B2B szervezetek számára a Microsoft Dynamics 365 Commerce rendszerben.

A Commerce központi felületén az üzleti partnereket a vevői és vevői hierarchiaentitások képviselik. Az üzleti partner szervezetét és felhasználóit vevőkként ábrázolja a rendszer, és a vevőhierarchiák segítségével társítja ezeket a vevőket egymáshoz.

Amikor jóváhagyják egy üzleti partner kérését egy B2B e-kereskedelmi webhelyhez való csatlakozásra, a rendszer a következő műveleteket hajtja végre:

- A rendszerben két új vevőrekord jön létre: az üzleti partner szervezetéhez egy **Szervezet típusa** vevőrekord, a kérelmezőhöz (tehát a kérelmet benyújtó üzleti partnerhez) pedig egy **Személy típusa** vevőrekord.
- Új vevőhierarchia jön létre a **Vevő \> Vevőhierarchia** pontban. Ennek a rekordnak a következő fejléctulajdonságai vannak:

    - **Vevőhierarchia azonosítója** – a vevőhierarchia egyedi azonosítója. Ez az azonosító a Commerce központi felületén a Commerce megosztott paramétereiben meghatározott számsorozatot használja.
    - **Név** – az üzleti partner szervezetének neve a beléptetési kérelemben megadottaknak megfelelően.
    - **Cél** – ez a tulajdonság az előre meghatározott **B2B szervezet** értékre van beállítva.
    - **Szervezet** – az üzleti partner vevőazonosítója.

A vevőhierarchia-rekord részletei:

- A kérelmező vevőrekordja a vevőhierarchiához van társítva.
- A rendszergazdai szerepkör a kérelmezőhöz van társítva.

Amikor a rendszergazda további felhasználókat ad hozzá egy B2B webhely üzleti partner szervezetéhez, a Commerce központi felületén minden felhasználóhoz létrejön egy új vevőrekord. A rendszer ezt a vevőrekordot az üzleti partnerhez kapcsolódó vevői hierarchiarekordhoz is hozzáadja, a szerepköre pedig felhasználó.

> [!NOTE]
> A legtöbb esetben egy hierarchiában található vevőrekordok megfelelő tulajdonságértékének meg kell egyeznie egymással. Például mivel minden üzleti partner felhasználójának hasonló árakat kell kapnia a termékekre, ezért az árcsoportnak és a társított konfigurációknak is egyezniük kell. A rendszer azonban nem érvényesíti ezt a konzisztenciát. Ezért a Commerce központi felületének adott felhasználói felelősek azért, hogy a tulajdonságértékek és konfigurációk egy adott hierarchiában lévő összes vevőre vonatkozóan megegyezzenek egymással.

A Commerce központi felületének felhasználói egymás mellé helyezve megtekinthetik a hierarchia összes vevőrekordjának tulajdonságértékeit. Válassza ki a megfelelő vevőrekord-tulajdonságokat a legördülő menü lapnevének kiválasztásával. A felhasználók közvetlenül megtekinthetik és szerkeszthetik az ebből a nézetből származó tulajdonságértékeket. Másik lehetőségként ha a rendszergazdai vevőrekord összes értékét szeretné alkalmazni az összes felhasználói vevőrekordra, a vevőhierarchia részletes adatai között válassza a **Felülbírálás** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[B2B e-kereskedelmi webhely beállítása](set-up-b2b-site.md)

[Üzleti partner típusú felhasználók kezelése a B2B e-kereskedelmi webhelyeken](manage-b2b-users.md)

[A B2B e-commerce webhelyekhez használt vevői számlafizetési mód konfigurálása](payment-method.md)

[Termékmennyiség-korlátok beállítása B2B e-kereskedelmi webhelyekhez](quantity-limits.md)
