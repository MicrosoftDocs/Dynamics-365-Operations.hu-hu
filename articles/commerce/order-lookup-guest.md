---
title: Rendelés keresésének engedélyezése vendégpénztárak részére
description: Ez a témakör azt ismerteti, hogyan lehet engedélyezni a rendeléskeresést a vendég-pénztárnál Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 757e83887e318dd6aa54106fb78305f1d94e0f90
ms.sourcegitcommit: e25fe4228add88dd37f4f38ece86979e1c621f6a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2022
ms.locfileid: "9734267"
---
# <a name="enable-order-lookup-for-guest-checkouts"></a>Rendelés keresésének engedélyezése vendégpénztárak részére

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet engedélyezni a rendeléskeresést a vendég-pénztárnál Microsoft Dynamics 365 Commerce.

A vendégpénztárok rendeléskeresési funkciója lehetővé teszi, hogy a vendégfelhasználóként vásárló vevők megkeressenek rendeléseket. A rendeléskeresési képesség akkor hasznos, ha a vevők olyan műveleteket szeretnének végrehajtani, mint például a rendelésben szereplő termékek teljesítési állapotának ellenőrzése, a rendelés szállítási címének ellenőrzése, egy termék újrarendelése, vagy annak megerősítése, hogy melyik üzletben vehető át egy rendelés.

Azok a vevők, akik regisztrált felhasználóként rendeléseket adnak fel, bejelentkezéskor láthatják a rendelési adataikat, de azok a vevők, akik a vendégpénztárból rendeléseket adnak fel, nem láthatják őket. Ha viszont engedélyezve van a vendégpénztárok rendeléskeresési funkciója, a vevők számára egy olyan képernyőt biztosít, ahol a vendégként leadott rendeléseket kereshetik. Ezen a képernyőn a vevők megadhatják a rendelés-visszaigazolási azonosítót és a fizetéskor megadott e-mail-címet (nem kötelező).

Ezenkívül bármely rendeléssel kapcsolatos tranzakciós e-mailben lehet szerepeltetni egy olyan hivatkozást vagy gombot, amely a vevőt közvetlenül a rendelése rendelésadatait tartalmazó oldalra viszi. Ez a hivatkozás vagy gomb a regisztrált felhasználók és a vendégfelhasználók által elküldött rendeléseken egyaránt működni fog.

## <a name="turn-on-necessary-features-in-commerce-headquarters"></a>A Commerce központ szükséges funkcióinak bekapcsolása

Ha engedélyezni szeretné a vendégpénztári rendeléskeresést, be kell kapcsolnia a Commerce Headquarters **Munkaterületek \> Funkciókezelés** részében.

| Funkció | Alkalmazás célja |
|---------|---------|
| A Retail névtelenfelhasználó-keresési utasítás részleteit bekapcsoló funkció | Ez a funkció megjeleníti a felhasználói felületet a Commerce paraméterei között, így engedélyezni lehet a rendeléskeresési API-t a nem hitelesített felhasználók számára, és be lehet állítani, hogy hogyan jelenjenek meg a személyes adatok. |
| Erős csatornahivatkozás-azonosító generálásának engedélyezése | Ez a funkció egy biztonságos, 12 karakteres csatornahivatkozási azonosítót (rendelés-visszaigazolási azonosítót) generál, amely a rendelés keresésekor átadható a lekérdezési sztringben. |
| Egységes csatornahivatkozási azonosítóformátum létrehozása a csatornák között | Ez a funkció egy biztonságos csatornahivatkozási azonosítót hoz létre az olyan rendelésekhez, amelyeket az e-kereskedelmi webhelyen, a kiskereskedelmi pénztárban (POS) vagy egy hívásközpontban adtak le. A funkció bekapcsolása előtt be kell kapcsolni az **Erősebb csatornahivatkozási azonosító létrehozásának engedélyezése** funkciót. |

Miután bekapcsolta a **Kiskereskedelmi anonim felhasználói keresés rendelésadatainak bekapcsolása funkció** funkciót, engedélyeznie kell az API-t, ami támogatja a nem hitelesített rendeléskeresést a Commerce központban. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Vevői rendelések** menüpontra. A **Vevői rendelések** oldalon a **Rendeléskeresés** gyorslapon állítsa be a **Nem hitelesített rendeléskeresés engedélyezése** beállítást **Igen** értékre, ahogy az alábbi ábrán látható.

## <a name="manage-the-display-of-personal-data"></a>A személyes adatok megjelenítésének kezelése

A **Rendeléskeresés** gyorslapon, a **Vevői rendelések** oldalon a Commerce központban szerepel egy **Személyes adatok szerepeltetése a vendégrendelések keresésében** mező, amellyel szabályozható, hogy milyen személyes adatok jelenjenek meg a vevőknek. Ez a személyes adat tartalmazza a vevő szállítási címét és a vevő hitelkártyaszámának utolsó négy jegyét. Alapértelmezés szerint a személyes adatok nem jelennek meg a vevők számára, ha engedélyezve van a nem hitelesített rendeléskeresés. Az alábbi táblázat ismerteti a elérhető beállításokat.

| Beállítás | Eredmény |
|--------|--------|
| Soha | Az alapértelmezett érték. A rendeléskeresések nem tartalmaznak személyes adatokat. Ha regisztrált felhasználók olyan rendelést keresnek, amelyet a bejelentkezett felhasználóként hoztak létre, akkor láthatják a személyes adataikat. |
| Csak vendégrendelések | A személyes adatok a vevők által vendégként létrehozott rendelések rendeléskereséseinél jelennek meg. Ha egy rendelést egy regisztrált felhasználó hozott létre, akkor annak a felhasználónak be kell jelentkeznie, hogy lássa személyes adatait. |
| Minden rendelés | A személyes adatok az összes rendeléskeresésben megjelennek. |

> [!NOTE]
> Ezek a lehetőségek határozzák meg, hogy a névtelen vendég felhasználók számára mikor jelennek meg a személyes adatok, például a vevő címe és a vevő hitelkártyaszámának utolsó négy számjegye. A regisztrált vevők adatainak védelme érdekében javasoljuk, hogy **Csak a vendégrendelések** beállítást válassza. A legbiztonságosabb beállítás azonban a **Soha**.

Miután a Személyes adatok **behelyettesítése** a vendégrendelések keresési mezőjébe értékét módosítja, a Commerce Headquarters **1070-es feladatának (** csatornakonfigurációjának **) futtatásához a Retail and Commerce \> Retail and Commerce IT \> Distribution ütemezését kell futtatnia**.

## <a name="configure-the-order-lookup-module"></a>A rendeléskeresési modul konfigurálása

A Commerce modultár rendeléskeresési modulja a vendégfelhasználók által a rendelések keresésére használt képernyő megjelenítésére használható. A rendeléskeresési modul bármelyik olyan lap törzsében szerepeltethető, amely nem igényli a vevői bejelentkezést. A modul konfigurálására vonatkozó tudnivalókat lásd a [Rendeléskeresési modulban](order-lookup-module.md).

## <a name="configure-the-order-details-page"></a>A rendelés részleteit tartalmazó lap konfigurálása

Ahhoz, hogy a vendég felhasználók megtekinthetik a rendelési adataikat, az e-commerce webhelyen be kell állítani a rendelési adatokat úgy, hogy ne legyen szükség a bejelentkezésre. Ha ki kívánja kapcsolni a rendelési adatok oldalához szükséges bejelentkezési követelményeket, nyissa meg a lapot a Commerce webhelyszerkesztőben, **fanézetben válassza ki az Alapértelmezett oldal (kötelező)** lehetőséget, **és** törölje a jelet a Be kell jelentkezni szükséges jelölőnégyzetből a tulajdonságok ablaktábla alján.

## <a name="add-a-link-to-order-details-in-transactional-emails"></a>Rendelési részletekre mutató hivatkozás hozzáadása a tranzakciós e-mailekben

A rendeléshez kapcsolódó e-mailekben meg lehet adni egy hivatkozást vagy gombot, amely a vevőket a rendelésük részletes adatait tartalmazó lapra viszi. Ennek a hivatkozásnak vagy gombnak a hozzáadásához hozzon létre egy HTML-hivatkozást, amely az e-commerce webhely rendelési részleteire mutat, és adja át a rendelés visszaigazolási azonosítóját és az ügyfél e-mail címét URL-paraméterként, amint azt az alábbi példa mutatja.

`<a href="https://[domain]/[orderdetailspage]?confirmationId=%orderconfirmationid%&propertyName=email&propertyValue=%customeremailaddress%" target="_blank">View my order status</a>`

> [!NOTE]
> A rendeléskeresési funkció engedélyezéséhez győződjön meg arról, **·** **hogy az Ajánlatok kulcs engedélyezve van a Licenckonfiguráció konfigurációs** > **kulcsai kulcs alatt**.
>
>![Engedélyezni kell az Árajánlatok licenckulcs-konfigurációját.](./media/Quotations_License_Key_Configuration.png)

## <a name="additional-resources"></a>További erőforrások

[Rendeléskeresési modul](order-lookup-module.md)

[E-mail-értesítési profil beállítása](email-notification-profiles.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
