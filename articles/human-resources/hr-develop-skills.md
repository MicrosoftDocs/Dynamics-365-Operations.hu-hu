---
title: Készségek konfigurálása
description: A dolgozó készségeit nyomon követheti a Dynamics 365 Human Resources rendszerben. Emellett megadhatja, hogy egy adott beosztáshoz milyen szakértelem szükséges.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a8025dd4000a3678e7f7eb7faebfa45852f0054570a2948dadbc21913c63f578
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732153"
---
# <a name="configure-skills"></a>Készségek konfigurálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A dolgozó készségeit nyomon követheti a Dynamics 365 Human Resources rendszerben. Emellett megadhatja, hogy egy adott beosztáshoz milyen szakértelem szükséges.

Nyomon követheti a szakértelmek például a következők:

- Felügyelet – képesség mások munkájának felügyelésére.
- Vezetés – az alkalmazottak és a vállalati területek vezetésének képessége.
- Tervezés – képesség az előrelátásra, az elképzelések utasításokba öntésére, és az utasítások átlátására.
- HTML - HTML-kódolás ismerete.

Ha még nem állított be készségtípusokat és minősítési modelleket, a készségek létrehozása előtt hozzá kell adnia néhányat.

A következő személyek adhatnak meg készséget a dolgozóknak:

- A dolgozók megadhatnak maguknak készségeket az Alkalmazotti önkiszolgáló rendszerben. Ezeket a készségeket a vezetőnek jóvák kell hagynia.
- A vezetők megadhatnak készségeket a munkavállalóikhoz. Létrehozhat olyan munkafolyamatot, amely automatikusan jóváhagyja ezeket a készségeket.

## <a name="create-a-skill-type"></a>Készségtípusok létrehozása

A készségtípusok olyan kategóriák, amelyekbe az egyes készségek tartoznak (például Adminisztráció vagy Értékesítés).

1. Az **Alkalmazotti fejlesztés** munkaterületen válassza a **Hivatkozások** lehetőséget.

2. A **Kompetencia beállítása** területen válassza ki a **Szakértelemtípusok** lehetőséget.

3. Válassza az **Új** lehetőséget.

4. Töltse ki a következő mezőket:

   - **Szakértelemtípus**: Adja meg a készségtípus nevét.
   - **Leírás**: Adja meg a készségtípus leírását.

5. Válassza a **Mentés** lehetőséget.

## <a name="create-a-rating-model"></a>Minősítési modell létrehozása

A minősítési modellek segítenek meghatározni a személy valós szakértelmi szintjét, az elérendő szintet vagy az adott beosztáshoz szükséges szintet. Egy értékelési modell minden szintjéhez tényező társul.

1. Az **Alkalmazotti fejlesztés** munkaterületen válassza a **Hivatkozások** lehetőséget.

2. A **Kompetencia beállítása** területen válassza a **Minősítési modellek** lehetőséget.

3. Válassza az **Új** lehetőséget.

4. Töltse ki a következő mezőket:

   - **Minősítés**: Adja meg a minősítési modell nevét, például **Készségek**.
   - **Leírás**: Adja meg a minősítési modell leírását, például **Szakértelem értékelései**.

5. A **Szintek** szakaszban válassza az **Új** lehetőséget. Minden egyes hozzáadni kívánt szintnél töltse ki a következő mezőket:

   - **Szint**: Adja meg a szint nevét.
   - **Leírás**: Adja meg a szint leírását.
   - **Szorzó**: Adjon meg egy szorzóértéket 0 és 9 között. A szorzók segítenek normalizálni a készségek különböző minősítési modelleket használó pontszámát. Minden szinthez egyedi szorzót kell megadni. A magasabb értékű szorzóval rendelkező szintek nagyobb súlyt képviselnek a minősítés modellben.

   Szükség szerint adjon hozzá további szinteket. Egy minősítési modellhez legfeljebb 10 minősítési szintet adhat meg.

6. Válassza a **Mentés** lehetőséget.

## <a name="create-a-skill"></a>Készségek létrehozása

Egy készség hozzárendelése, szakértelem-feltérképezési keresés vagy szakértelemprofil létrehozása előtt meg kell adnia a szakértelemre vonatkozó adatokat a **Szakértelmek** képernyőn. Minden egyes szakértelmhez kiválaszthatja a típust és a minősítési modellt.

1. Az **Alkalmazotti fejlesztés** munkaterületen válassza a **Hivatkozások** lehetőséget.

2. A **Kompetencia beállítása** területen válassza ki a **Szakértelmek** lehetőséget.

3. Válassza az **Új** lehetőséget.

4. Töltse ki a következő mezőket:

   - **Készség**: Adja meg a készség nevét.
   - **Leírás**: Adja meg a készség leírását.
   - **Minősítés**: A készséghez használandó minősítési modell kiválasztása.
   - **Szakértelemtípus**: Válasszon a szakértelemtípusok listájából.

5. Válassza a **Mentés** lehetőséget.

## <a name="see-also"></a>Lásd még

[Készségek megadása](hr-develop-enter-skills.md)<br>
[Készségek hozzárendelése](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]