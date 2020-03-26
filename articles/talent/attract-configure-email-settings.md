---
title: E-mail-beállítások megadása az Attract szolgáltatásban
description: Ez a témakör azt mutatja be, hogyan lehet beállítani az elküldött e-mailek beállításait a Microsoft Dynamics 365 Talent - Attract esetében.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: e641e3f0d1873d91be1a1dc9bc22eb734a2b21d5
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124727"
---
# <a name="configure-email-settings-in-attract"></a>E-mail-beállítások megadása az Attract szolgáltatásban

[!include [banner](includes/banner.md)]

A márkanév bizalmi kapcsolatot létesít, és segít felépíteni egy kapcsolatot a jelentkezők előtt, még mielőtt jelentkeznének a beosztásokra. A pozitív márkaértékelés vonzza a legjobb tehetséget, és növeli a meglévő alkalmazottak hűségét. Microsoft Dynamics 365 Talent: Attract lehetővé teszi az e-mailek konfigurálását, hogy azok tükrözzék a vállalat márkáját. Ennek megfelelően a pályázók számára a jelentkezési folyamat során egységes tapasztalatot lehet biztosítani.

Az Attract a következő műveletek végrehajtását teszi lehetővé:

- E-mailek beállításainak konfigurálása annak érdekében, hogy a vállalat Microsoft Exchange e-mail szolgáltatási fiókját használja a rendszer. Ily módon a jelentkezők tudják, hogy az e-mailek a vállalatától érkeznek. Beállíthatja például a beállításokat úgy, hogy a jelentkezők a `recruiting@contoso.com` címről kapjanak e-maileket, és ne a `contoso@microsoft.com` címről.
- E-mail értesítések konzisztens márkázásának létrehozásához globális fejlécet és láblécet kell megadni az összes e-mail sablonhoz. 

> [!NOTE]
> Annak konfigurálásához, hogy az Attract a vállalat e-mail szolgáltatási fiókját használja az e-mail küldéshez, szüksége van az átfogó felvételi bővítményre.

## <a name="connect-an-email-service-account"></a>E-mail szolgáltatási fiók csatlakoztatása

A vállalat e-mail szolgáltatási fiókjának csatlakoztatásával márkázott e-mail élményt nyújthat a beosztásra jelentkezőknek. Ha nem csatlakoztatja a vállalati fiókot, akkor az Attract az alapértelmezett Microsoft védjeggyel ellátott e-mail szolgáltatásfiók használatát.

1. Válassza ki a **Beállítások** gombot (fogaskerék-szimbólum a jobb felső sarokban), majd válassza a **Felügyeleti központ** lehetőséget.
2. Válassza ki az **E-mail beállítások** lapon, az **E-mail szolgáltatások fiókja** területén a **Vállalati számla összekapcsolása** beállítást.

    ![A vállalat e-mail szolgáltatási fiókjának csatlakoztatása az Attractban](./media/attract-admin-email-service-accounts.png)

    A megosztott e-mail fiókok létrehozásával kapcsolatos további tudnivalókat lásd: [Megosztott postaládák. Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)

3. Jelentkezzen be a Microsoft bejelentkezési ablakában a vállalati hitelesítő adatok segítségével.
4. Ha még nem állított be e-mail szolgáltatásfiókot, vagy ha újat szeretne hozzáadni, jelölje be az **Új szolgáltatásfiók hozzáadása** jelölőnégyzetet, majd adja meg az e-mail adatait. Ha már beállította a használni kívánt e-mail szolgáltatásfiókot, válassza ki.

Amikor az e-mail szolgáltatás fiókja sikeresen be van állítva, az **E-mail szolgáltatási fiókok** területen jelenik meg.

## <a name="disconnect-an-email-service-account"></a>E-mail szolgáltatási fiók lecsatlakoztatása

Ha azt szeretné, hogy ne használja a vállalat tartományát az e-mailes kommunikációban az Attract, akkor leválaszthatja az e-mail szolgáltatás fiókját.

1. Válassza ki a **Beállítások** gombot (fogaskerék-szimbólum a jobb felső sarokban), majd válassza a **Felügyeleti központ** lehetőséget.
2. Az **E-mail beállításai** lapon, az **E-mail szolgáltatások fiókjai** alatt, jelölje be a leválasztani kívánt e-mail szolgáltatásfiók melletti **További** gombot (három függőleges pont).
3. Válassza ki az **E-mail fiók lecsatlakoztatása** elemet.

    ![A vállalat e-mail szolgáltatási fiókjának lecsatlakoztatása](./media/attract-admin-disconnect-email-account.png)

4. Amikor a program megkérdezi, hogy jóváhagyja a műveletet, válassza a **Kapcsolat bontása** lehetőséget.

    ![A vállalat e-mail szolgáltatási fiókjának lecsatlakoztatásának megerősítése](./media/attract-admin-email-confirm-disconnect.png)

Ha nem csatlakoztat egy másik e-mail szolgáltatási fiókot, akkor az Attract a felhasználó által küldött e-maileket az alapértelmezett Microsoft védjeggyel ellátott e-mail szolgáltatási fiókból küldi.

## <a name="configure-email-template-settings"></a>E-mail sablonbeállítások megadása

A vállalat emblémáját és egyéb adatait a saját e-mail címének márkás fejlécként is feltöltheti. Az adatvédelmi irányelvekre és a felhasználási feltételekre mutató hivatkozásokat is megadhat az e-mailek élőlábában.

> [!NOTE]
> Meg kell felelnie adott ország vagy régió alkalmazandó jogszabályainak, illetve azon ország vagy régió jogszabályainak, amelyben az e-mail címzettje él. Ezek a jogszabályok tartalmazzák a levélszemét-ellenes szabályokat is.

1. Válassza ki a **Beállítások** gombot (fogaskerék-szimbólum a jobb felső sarokban), majd válassza a **Felügyeleti központ** lehetőséget.
2. Az **E-mail beállításai** lap **E-mail sablon beállításai** részén húzza az e-mail fejlécként használni kívánt képet a kép mezőbe, vagy kattintson a kép mezőbe a fájl tallózásához. Egy meglévő kép lecseréléséhez először az **Eltávolítást** kell kiválasztania mellette. A képnek JPEG, JPG, PNG vagy SVG formátumúnak kell lennie. A képek ajánlott szélessége 25 és 800 képpont között van, és 25 és 150 képpont között magasnak kell lennie. A fejléc maximális fájlmérete 1 megabájt (MB).

    ![Kép hozzáadása a vállalat e-mail fejlécéhez](./media/attract-admin-email-header.png)

3. **Az ön Adatvédelmi irányelve a kommunikációra vonatkozóan** alatt adjon meg egy linket a vállalat adatvédelmi politikájához. **Az ön Felhasználási feltételei a kommunikációra vonatkozóan** alatt adja meg a vállalat felhasználási feltételeire mutató hivatkozást.

    ![Hivatkozás hozzáadása a vállalat adatvédelmi irányelvéhez és felhasználási feltételeihez az e-mail élőlábjához](./media/attract-admin-email-footer.png)

4. Az e-mail sablon beállításainak mentéséhez válassza a **Mentés** lehetőséget.
