---
title: B2B e-kereskedelmi webhely beállítása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy B2B e-kereskedelmi webhelyet a Microsoft Dynamics 365 Commerce alkalmazásban.
author: josaw1
ms.date: 12/03/2021
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
ms.openlocfilehash: 171e518258e9600bd7526cf52e3e456d272e6bce
ms.sourcegitcommit: 5f5a8b1790076904f5fda567925089472868cc5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891385"
---
# <a name="set-up-a-b2b-e-commerce-site"></a>B2B e-kereskedelmi webhely beállítása

[!include [banner](../../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

A vállalatok közötti (B2B) e-kereskedelmi webhelyek néhány olyan kulcsfontosságú lehetőséget kínálnak, amelyek optimalizálják a munkafolyamatot egy B2B-felhasználó számára. Ez a témakör azt mutatja be, hogyan lehet beállítani egy B2B e-kereskedelmi webhelyet a Microsoft Dynamics 365 Commerce alkalmazásban. Végigmegy a modulokon és a webhelybeállításokon, amelyeket a B2B-specifikus helyzetek engedélyezéséhez kell konfigurálni.

## <a name="prerequisites"></a>Előfeltételek

- A B2B e-kereskedelmi webhely beállításához engedélyeznie és konfigurálnia kell néhány meghatározott funkciót a Commerce központi felületén a témakörben leírt módon.
- Az alaptevékenységeket, például a termékfelderítést, a termék részletes oldalait, a kosarat és a pénztárat ugyanazok a modulok működtetik, mint amelyek a cég és ügyfél (B2C) között működő e-kereskedelmi webhelyeken használatosak. A webhelykészítőknek ismerniük kell minden olyan modult, amelyet a Dynamics 365 Commerce támogat. A további tudnivalókat lásd itt: [Modultár-frissítések](../starter-kit-overview.md).
- Ez a témakör abból indul ki, hogy a webhelykészítő ismeri a Commerce webhelykészítő alapjait, a sablonokat, a töredékeket és az oldalakat, hogy így engedélyezhesse a B2B funkciókat az e-kereskedelmi webhelyeken.

## <a name="site-level-settings"></a>Webhelyszintű beállítások

A webhelyszintű beállításokat a webhelykészítőben a **Webhelybeállítások \> Bővítmények** pontban érheti el. A B2B helyzetekben a következő két webhelyszintű beállítás érvényes:

- **Vevői számlafizetések engedélyezése** – ez a tulajdonság lehetővé teszi a felhasználók számára, hogy vevői számlák segítségével fizessék ki a rendeléseket. A rendelkezésre álló értékek a következők: **Engedélyezve B2B vevők esetében**, **Engedélyezve B2C vevők esetében**, **Engedélyezve minden vevő esetében** és **Letiltva minden vevő esetében**. Ha a B2B webhely támogatja a vevői számlákat, akkor az **Engedélyezve B2B vevők esetében** lehetőséget kell kiválasztania.
- **Rendelési mennyiségi korlátok engedélyezése** – ez a tulajdonság lehetővé teszi az egyes termékek vagy kategóriák esetében megrendelhető cikkek számának korlátozását. A rendelkezésre álló értékek a következők: **Engedélyezve B2B vevők esetében**, **Engedélyezve B2C vevők esetében**, **Engedélyezve minden vevő esetében** és **Letiltva minden vevő esetében**.

> [!NOTE]
> Ha a modultár legújabb verziójára frissít, további lépéseket kell követnie ahhoz, hogy a korábban leírt webhelybeállítások elérhetők legyenek a környezetében. További tájékoztatás: [Az app.settings.json fájl frissítése](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="create-business-partner-sign-up-pages"></a>Üzleti partner regisztrációs lapjainak létrehozása

Ahhoz, hogy a felhasználó üzleti partnerré váljon, előbb be kell nyújtania egy üzletipartner-kérelmet. A B2B kezdőlapján elérhető az üzletipartner-kérelmezési oldalra mutató hivatkozás, így a felhasználók kezdeményezhetik a folyamatot. Miután a felhasználók elküldték az üzletipartner-kérelmet, visszaigazolást kapnak a kérelem benyújtásáról. 

### <a name="create-a-business-partner-request-page"></a>Üzleti partnerhez való kérelemoldal létrehozása

Az üzleti partnereknek szánt kérelmezési oldal **Partnerregisztráció** modulja használatával a felhasználók kezdeményezhetik, hogy üzleti partnerek legyenek. Ezzel a modullal összegyűjtheti a regisztrációs folyamathoz szükséges felhasználói adatokat. Ezenkívül az **Üzleti fiók címe** modullal rögzítheti a felhasználó címét.

Az üzletipartner-kérelem oldal webhelykészítőben való beállításához és konfigurálásához kövesse az alábbi lépéseket.

1. Hozzon létre **Regisztráció** nevű sablont. Ennek a sablonnak a következő modulokat kell tartalmaznia:

    - Partnerregisztráció
    - Webhely-navigációs eszköz
    - Fejléc
    - Lábléc
    - Tartalomblokk
    - Szövegterület
    - Termékgyűjtemény

1. Az **Üzletipartner-kérelem** nevű oldal létrehozásához használja a **Regisztráció** sablont.
1. A **Fejléc** helyen adja hozzá a webhely fejlécével előre konfigurált fejlécrészletet.
1. A **Lábléc** helyen adja hozzá a webhely láblécével előre konfigurált láblécrészletet.
1. A **Fő** helyen adjon hozzá egy **Tároló** modult. A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre.
1. Adja hozzá a **Tároló** helyen az **Útvonalkövetés** modult. A modul tulajdonságai panel **Hivatkozások** pontján konfigurálja a kezdőlapra mutató hivatkozást, és adja meg a **Kezdőlap** lehetőséget hivatkozási szövegként.
1. A **Tároló** helyen adjon hozzá egy **Partnerregisztráció** modult az **Útvonalkövetés** modul alatt. A modultulajdonságok panel **Fejléc** pontban írja be a következő szöveget: **Legyen üzleti partner**.
1. A **Partnerregisztráció** helyen adjon hozzá egy **Üzleti fiók címe** modult.
1. A **Tároló** helyen adjon hozzá egy **Szövegterület** modult az **Partnerregisztráció** modul alatt. Itt meghatározhatja a regisztrációs folyamat feltételeit.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Az oldal URL-címének közzététele.

### <a name="create-a-business-partner-request-confirmation-page"></a>Üzleti partnerhez való kérelem-visszaigazolási oldal létrehozása

Az üzleti partner kérelmének benyújtása után egy visszaigazolási oldalnak kell megjelennie a felhasználó számára, nyugtázva a kérelem elküldését. 

A kérelem-visszaigazolási oldal webhelykészítőben való beállításához és konfigurálásához kövesse az alábbi lépéseket.

1. A korábban létrehozott **Üzleti partner visszaigazolása** nevű oldal létrehozásához használja a **Regisztráció** sablont.
1. A **Fejléc** helyen adja hozzá a webhely fejlécével előre konfigurált fejlécrészletet.
1. A **Lábléc** helyen adja hozzá a webhely láblécével előre konfigurált láblécrészletet.
1. A **Fő** helyen adjon hozzá egy **Tároló** modult. A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre.
1. A **Tároló** helyen adjon hozzá egy **Tartalomblokk** modult. A modultulajdonságok panelben a **Fejléc** pontban írja be a következőt: **Kérelem elküldve**. A **Rich Text** mezőbe írja be a következőt: **Sikeresen elküldte a kérelmét**. A **Hivatkozások** pontban konfigurálja a kezdőlapra mutató hivatkozást, és adja meg a **Vissza a vásárláshoz** lehetőséget hivatkozási szövegként.
1. Adjon hozzá **Tároló** modult, és adjon hozzá egy **Termékgyűjtemény** modult.
1. Konfigurálja a **Termékgyűjtemény** modult az adott oldalon bemutatni kívánt ajánlási vagy kategórialistával.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Az oldal URL-címének közzététele.

Ha a kérelem-visszaigazolási oldalhoz hivatkozást szeretne hozzáadni a webhelykészítőben, kövesse az alábbi lépéseket.

1. Lépjen a korábban létrehozott **Üzletipartner-kérelem** oldalra, és válassza a **Szerkesztés** lehetőséget. 
1. Válassza ki a **Partnerregisztráció** modulhelyet. A tulajdonságok panelben a **Regisztráció visszaigazolási oldalára mutató hivatkozás** pontban konfigurálja a korábban létrehozott üzletipartner-kérelem oldalra mutató hivatkozást. 
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

### <a name="add-a-business-partner-request-link-to-the-home-page"></a>Üzletipartner-kérelem hivatkozásának hozzáadása a kezdőlaphoz

Miután létrehoza az üzletipartner-kérelem regisztrációs és visszaigazolási oldalt, a kezdőlapon lévő hivatkozáson keresztül elérhetővé kell tenni a regisztrációs oldalt. Ezt a feladatot úgy tudja végrehajtani, hogy a kezdőlap bármelyik **Tartalomblokk** moduljához hozzáadja a hivatkozást.

Ha az üzletipartner-kérelemre mutató hivatkozást szeretne hozzáadni a webhelykészítőben a kezdőlaphoz, kövesse az alábbi lépéseket.

1. Lépjen a webhelye kezdőlapjára, és válassza ki a **Szerkesztés** lehetőséget.
1. Válasszon ki egy **Tartatalomblokk** modulhelyet. Konfigurálja a korábban létrehozott üzletipartner-kérelem oldalra hivatkozást a modul tulajdonságai ablak **Hivatkozások** elemében, és írja be a **Regisztráció üzleti partnerként** lehetőséget vagy a hivatkozás szövegéhez hasonló szöveget. Adjon hozzá egy megfelelő képet.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="account-management-landing-page"></a>A fiókkezelés érkezési oldala

A számlakezelési céloldal tartalmaz minden olyan fiókkezelési információt, amely mind a B2B, mind a B2C e-kereskedelmi webhelyekhez szükséges. Csak bejelentkezett felhasználók tekinthetik meg ezt az oldalt.

A B2B számlakezelés céloldalának a webhelykezelőben való létrehozásához és konfigurálásához kövesse ezeket a lépéseket.

1. Hozzon létre **Számlakezelés** nevű sablont. Ennek a sablonnak a következő modulokat kell tartalmaznia:

    - Fejléc
    - Lábléc
    - Webhely-navigációs eszköz
    - Fiók üdvözlő csempéje
    - Fiók általános csempéje
    - Fiók címének csempéje
    - Fiók kívánságlista csempéje
    - Fiók címének csempéje
    - Fiókhoz tartozó hűségprogram csempéje
    - Számla vevői egyenlege csempe
    - Számla rendeléssablonjai csempe
    - Szervezeti felhasználók
    - Vállalkozás szervezeti listája
    - Vevői számlaegyenleg
    - Rendeléssablonsorok
    - Rendeléssablon-lista
    - Fiókszámla csempéje
    - Számlák listája
    - Számla részletei

1. A **Számlakezelés** sablon használatával **Saját fiók** nevű oldalt hozhat létre.
1. A **Fejléc** helyen adja hozzá a webhely fejlécével előre konfigurált fejlécrészletet.
1. A **Lábléc** helyen adja hozzá a webhely láblécével előre konfigurált láblécrészletet.
1. A **Fő** helyen adjon hozzá egy **Tároló** modult. A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre. 
1. Adja hozzá a **Tároló** helyen az **Útvonalkövetés** modult. A modul tulajdonságai panel **Hivatkozások** pontján konfigurálja a kezdőlapra mutató hivatkozást, és adja meg a **Kezdőlap** lehetőséget hivatkozási szövegként.
1. A **Tároló** helyen adjon hozzá egy **Üdvözlő csempe** modult. A modultulajdonságok panelben a **Fejléc** pontban írja be a következőt: **Üdvözöljük!**.
1. A **Fő** helyen adjon hozzá egy másik **Tároló** modult (**Tároló 2**). A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre. Állítsa a **Gyermekek láthatók** értékét **Kettő** értékre. 
1. A **Tároló 2** helyen adjon hozzá egy **Fiók általános csempe** modult. A modultulajdonságok panelben a **Fejléc** pontban írja be a következőt: **Saját profil**. A **Hivatkozások** pontban konfigurálja a **Saját profil** oldalra mutató hivatkozást. 
1. A **Tároló 2** helyen adjon hozzá még egy **Fiók általános csempe** modult. A modultulajdonságok panelben a **Fejléc** pontban írja be a következőt: **Rendelési előzmények**. A **Hivatkozások** pontban konfigurálja a rendelési előzmények oldalra mutató hivatkozást.
1. A **Fő** helyen adjon hozzá egy másik **Tároló** modult (**Tároló 3**). A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre. Állítsa a **Gyermekek láthatók** értékét **Kettő** értékre. 
1. A **Tároló 3** helyen adjon hozzá egy **Fiókcím csempe** modult. A modultulajdonságok panelben a **Fejléc** pontban írja be a következőt: **Saját cím**. A **Hivatkozások** pontban konfigurálja a **Saját cím** oldalra mutató hivatkozást. 
1. A **Tároló 3** helyen adjon hozzá egy **Fiók kívánságlista csempéje** modult. A modultulajdonságok panelben a **Fejléc** pontban írja be a következőt: **Saját kívánságlista**. A **Hivatkozások** pontban konfigurálja a **Saját kívánságlista** oldalra mutató hivatkozást.
1. A **Fő** helyen adjon hozzá egy másik **Tároló** modult (**Tároló 4**). A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre. Állítsa a **Gyermekek láthatók** értékét **Kettő** értékre. 
1. A **Tároló 4** helyen adjon hozzá egy **Szervezeti felhasználók** modult. A modultulajdonságok panelben a **Fejléc** pontban írja be a következőt: **Szervezeti felhasználók**. 
1. A **Tároló 4** helyen adjon hozzá egy **Fiók vevői egyenleg csempéje** modult. A modultulajdonságok panelben a **Fejléc** pontban írja be a következőt: **Számlahitel**. 
1. A **Fő** helyen adjon hozzá egy másik **Tároló** modult (**Tároló 5**). A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre. Állítsa a **Gyermekek láthatók** értékét **Kettő** értékre. 
1. A **Tároló 5** modulban adjon hozzá egy **Számla rendeléssablonok csempéje** modult. A modultulajdonságok panelben a **Fejléc** pontban írja be a következőt: **Rendeléssablonok**. 
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

> [!NOTE] 
> A 13–18. lépésben hozzáadott szakaszok egy része nem fog megjelenni a „valós megjelenésű” (WYSIWYG) vásznon a webhelykészítőben, mert ehhez bejelentkezett B2B-fiókra van szükség.

## <a name="create-and-configure-customer-balance-pages-and-modules"></a>Vevőiegyenleg-oldalak és modulok létrehozása és konfigurálása 

A vevői számlák használhatók a rendelések kifizetésére. A vevői számla rendelkezésre álló egyenlege megtekinthető a felhasználó számlakezelési lapján.

### <a name="create-a-customer-balance-page"></a>Vevőiegyenleg-oldal létrehozása 

Mielőtt a bejelentkezett B2B-felhasználók megtekinthetnék a vevői egyenlegüket, létre kell hoznia egy vevőiegyenleg-oldalt. 

Ha vevőiegyenleg-oldalt szeretne létrehozni a webhelykészítőben, hajtsa végre az alábbi lépéseket.

1. A korábban létrehozott **Számlakezelés** sablon használatával hozzon létre egy **Vevői egyenleg** nevű oldalt.
1. A **Fejléc** helyen adja hozzá a webhely fejlécével előre konfigurált fejlécrészletet.
1. A **Lábléc** helyen adja hozzá a webhely láblécével előre konfigurált láblécrészletet.
1. A **Fő** helyen adjon hozzá egy másik **Tároló** modult (**Tároló 3**). A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre. Állítsa a **Gyermekek láthatók** értékét **Kettő** értékre.
1. Adja hozzá a **Tároló** helyen az **Útvonalkövetés** modult. A modul tulajdonságai panel **Hivatkozások** pontján konfigurálja a számlakezelési céloldalra mutató hivatkozást, és adja meg a **Saját fiók** lehetőséget hivatkozási szövegként.
1. A **Tároló** helyen adjon hozzá egy **Vevői egyenleg csempéje** modult. A modultulajdonságok panelben a **Fejléc** pontban írja be a következőt: **Számlaegyenleg**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Az oldal URL-címének közzététele.
1. Lépjen a korábban létrehozott számlakezelési oldalra (**Saját számla**).
1. A **Vevői egyenleg csempe** modul tulajdonságok paneljében adjon hozzá egy, a vevőiegyenleg-oldalra mutató hivatkozást. 
1. Mentse és tegye közzé az oldalt.

Létrehozta a vevőiegyenleg-oldalt, és a felhasználók a számlakezelési oldakról érhetik el.

### <a name="configure-a-checkout-page-so-that-the-customer-balance-can-be-used-as-a-form-of-payment"></a>Pénztároldal konfigurálása úgy, hogy a vevői egyenleg használható legyen fizetési módként

A **Vevői számla – Fizetés** modul szükséges a vevői egyenleg fizetési módként történő használatához. Ezt a modult fizetési módként hozzá kell adni a pénztároldalhoz. A pénztároldalak és a fizetéshez szükséges modulok konfigurálásával és a fizetés részletes adataival kapcsolatos tudnivalókat lásd: [Pénztármodul](../add-checkout-module.md).

Miután konfigurált egy pénztároldalt, hozzá kell adnia a **Vevői számla – Fizetés** modult a fizetési szakaszhoz, majd mentenie és közzé kell tennie az oldalt. A B2B-felhasználók ezután bejelentkezhetnek az e-kereskedelmi webhelyre, és a fizetés során a rendelésekre alkalmazhatják a rendelkezésre álló vevői egyenlegüket.

Ezenkívül a **Webhelykészítő \> Bővítmények** pontban meg kell győződnie arról, hogy a **Vevői számlafizetések engedélyezése** tulajdonság beállítása **Engedélyezve B2B vevők esetében** legyen.

## <a name="create-order-template-pages"></a>Rendeléssablon-oldalak létrehozása

A B2B e-kereskedelmi webhelyhez két rendeléssablon-oldal is beállítható: egy rendeléssablon-listaoldal és egy rendeléssablon-soroldal.

A rendeléssablonok listaoldalán az elérhető rendeléssablonok listája látható. A **Rendeléssablonok listája** modul segítségével lehet beállítani. A rendeléssablonok listaoldalán sablonokat hozhat létre és törölhet, valamint a sablonban található cikkeket hozzáadhatja a kosárhoz.

A rendeléssablon sorait tartalmazó lap oldal a rendeléssablonok listaoldalán kiválasztott rendeléssablon adatait jeleníti meg. A **Rendeléssablonok sorai** modul segítségével lehet beállítani. Amikor egy felhasználó kiválasztja a sablon nevét a rendeléssablonok listaoldalán, megjelenik a rendeléssablon sorait tartalmazó oldal, és megjeleníti a sablon részletes adatait. Ezt követően a felhasználó megtekintheti és szerkesztheti a sablonban található cikkeket.

### <a name="create-an-order-templates-list-page"></a>Rendeléssablonok listaoldalának létrehozása

Ha rendeléssablon-listaoldalt szeretne létrehozni a webhelykészítőben, hajtsa végre az alábbi lépéseket.

1. A korábban létrehozott **Számlakezelés** sablon használatával hozzon létre egy **Rendeléssablonok** nevű oldalt.
1. A **Fejléc** helyen adja hozzá a webhely fejlécével előre konfigurált fejlécrészletet.
1. A **Lábléc** helyen adja hozzá a webhely láblécével előre konfigurált láblécrészletet.
1. A **Fő** helyen adjon hozzá egy **Tároló** modult. A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre.
1. Adja hozzá a **Tároló** helyen az **Útvonalkövetés** modult. A modul tulajdonságai panel **Hivatkozások** pontján konfigurálja a számlakezelési céloldalra mutató hivatkozást, és adja meg a **Saját fiók** lehetőséget hivatkozási szövegként.
1. A **Tároló** helyen adjon hozzá egy **Rendeléssablonok listája** modult.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Az oldal URL-címének közzététele.
1. Lépjen a korábban létrehozott számlakezelési oldalra (**Saját számla**).
1. A **Számlarendelési sablonok csempe** modul tulajdonságok ablakában, a **Hivatkozások** pontban konfigurálja a most létrehozott rendeléssablonok listaoldalára mutató hivatkozást.
1. Mentse és tegye közzé az oldalt.

Létrehozta a rendeléssablon-oldalt, és a felhasználók a számlakezelési oldakról érhetik el.

### <a name="create-an-order-template-lines-page"></a>Rendeléssablonok soroldalának létrehozása

Ha rendeléssablon-soroldalt szeretne létrehozni a webhelykészítőben, hajtsa végre az alábbi lépéseket.

1. A korábban létrehozott **Számlakezelés** sablon használatával hozzon létre egy **Rendeléssablon-sorok** nevű oldalt.
1. A **Fejléc** helyen adja hozzá a webhely fejlécével előre konfigurált fejlécrészletet.
1. A **Lábléc** helyen adja hozzá a webhely láblécével előre konfigurált láblécrészletet.
1. A **Fő** helyen adjon hozzá egy **Tároló** modult. A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre.
1. Adja hozzá a **Tároló** helyen az **Útvonalkövetés** modult. A modul tulajdonságai panel **Hivatkozások** pontján konfigurálja a számlakezelési céloldalra mutató hivatkozást, és adja meg a **Saját fiók** lehetőséget hivatkozási szövegként.
1. A **Tároló** helyen adjon hozzá egy **Rendeléssablonok sorai** modult.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Az oldal URL-címének közzététele.

## <a name="onboard-business-partner-users"></a>Üzleti partner felhasználóinak beléptetése

A szervezet felhasználói oldal lehetővé teszi egy üzleti partner rendszergazdája számára, hogy további felhasználókat adjon hozzá az adott szervezetből a B2B e-kereskedelmi webhelyhez. A **Vállalkozás szervezeti listája** modul segítségével lehet beállítani. A szervezet felhasználóinak oldalán a rendszergazda felhasználókat adhat hozzá és távolíthat el, számlaegyenlegeket határozhat meg, és kimutatásokat kérhet egy felhasználóval kapcsolatban.

Ha szervezeti felhasználókkal kapcsolatos oldalt szeretne létrehozni a webhelykészítőben, hajtsa végre az alábbi lépéseket.

1. A korábban létrehozott **Számlakezelés** sablon használatával hozzon létre egy **Szervezeti felhasználók** nevű oldalt.
1. A **Fejléc** helyen adja hozzá a webhely fejlécével előre konfigurált fejlécrészletet.
1. A **Lábléc** helyen adja hozzá a webhely láblécével előre konfigurált láblécrészletet.
1. A **Fő** helyen adjon hozzá egy **Tároló** modult. A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre.
1. Adja hozzá a **Tároló** helyen az **Útvonalkövetés** modult. A modul tulajdonságai panel **Hivatkozások** pontján konfigurálja a számlakezelési céloldalra mutató hivatkozást, és adja meg a **Saját fiók** lehetőséget hivatkozási szövegként.
1. A **Tároló** helyen adjon hozzá egy **Vállalkozás szervezeti listája** modult. A modultulajdonságok panelben a **Fejléc** pontban írja be a következőt: **Szervezeti felhasználók**.
1. A **Vállalkozás szervezeti listája** modul tulajdonságai panelben engedélyezze a **Táblarendezés** és **Táblalapozás** tulajdonságokat. Állítsa a lapozási szám értékét a következőre: **5**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Az oldal URL-címének közzététele.
1. Lépjen a korábban létrehozott számlakezelési oldalra (**Saját számla**).
1. A **Szervezeti felhasználók csempéje** modul tulajdonságok ablakában, a **Hivatkozások** pontban konfigurálja a most létrehozott szervezeti felhasználók oldalára mutató hivatkozást. 
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="create-invoice-pages"></a>Számlaoldalak létrehozása

A számlák listaoldalán látható az összes elérhető számla listája. A **Számlalista** modul segítségével lehet beállítani. A felhasználók a számlalistaoldalról fizethetnek ki vagy kérhetnek le számlákat. 

A számla részletező lapja a számlák listaoldalán kiválasztott számla részleteit jeleníti meg. A **Számla részletei** modul segítségével lehet beállítani. Amikor egy felhasználó kiválasztja a számlaazonosítót a számla listaoldalán, megjelenik a számla részletei oldal, és megjeleníti a számla részletes adatait.

### <a name="create-an-invoices-list-page"></a>Számlalistaoldal létrehozása

Ha számlalistaoldalt szeretne létrehozni a webhelykészítőben, hajtsa végre az alábbi lépéseket.

1. A korábban létrehozott **Számlakezelés** sablon használatával hozzon létre egy **Számlalista** nevű oldalt.
1. A **Fejléc** helyen adja hozzá a webhely fejlécével előre konfigurált fejlécrészletet.
1. A **Lábléc** helyen adja hozzá a webhely láblécével előre konfigurált láblécrészletet.
1. A **Fő** helyen adjon hozzá egy **Tároló** modult. A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre.
1. Adja hozzá a **Tároló** helyen az **Útvonalkövetés** modult. A modul tulajdonságai panel **Hivatkozások** pontján konfigurálja a számlakezelési céloldalra mutató hivatkozást, és adja meg a **Saját fiók** lehetőséget hivatkozási szövegként.
1. A **Tároló** helyen adjon hozzá egy **Számlalista** modult. A modultulajdonságok panelben a **Fejléc** pontban írja be a következőt: **Számlák**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Az oldal URL-címének közzététele.
1. Lépjen a korábban létrehozott számlakezelési oldalra (**Saját számla**).
1. A **Fiók számlái csempe** modul tulajdonságok ablakában, a **Hivatkozások** pontban konfigurálja a most létrehozott számlalistaoldalra mutató hivatkozást. 
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

### <a name="create-an-invoice-details-page"></a>Számlarészletező oldal létrehozása

Ha számlarészletező oldalt szeretne létrehozni a webhelykészítőben, hajtsa végre az alábbi lépéseket.

1. A korábban létrehozott **Számlakezelés** sablon használatával hozzon létre egy **Számla részletei** nevű oldalt.
1. A **Fejléc** helyen adja hozzá a webhely fejlécével előre konfigurált fejlécrészletet.
1. A **Lábléc** helyen adja hozzá a webhely láblécével előre konfigurált láblécrészletet.
1. A **Fő** helyen adjon hozzá egy **Tároló** modult. A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre.
1. Adja hozzá a **Tároló** helyen az **Útvonalkövetés** modult. A modul tulajdonságai panel **Hivatkozások** pontján konfigurálja a számlakezelési céloldalra mutató hivatkozást, és adja meg a **Saját fiók** lehetőséget hivatkozási szövegként. Ezután állítson be egy, a számlák listaoldalára mutató hivatkozást, és adja meg hivatkozási szövegként a **Számlalisták** szöveget.
1. A **Tároló** helyen adjon hozzá egy **Számla részletei** modult.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Az oldal URL-címének közzététele.

## <a name="add-a-quick-add-module-to-the-cart-page"></a>Gyorshozzáadási modul hozzáadása a kosároldalhoz

A gyorshozzáadási modul segítségével gyorsan hozzá lehet adni több cikket a kosárhoz a cikkazonostó (más néven termékraktározási egység \[SKU\] azonosítók) használatával. A gyors hozzáadási modul felkerül a webhely kosároldalára.

A gyorshozzáadási modulnak a kosároldalhoz való hozzáadásához a Commerce webhelykészítő felületén hajtsa végre az alábbi lépéseket.

1. Menjen a **Sablonok** lapra, és válassza ki a webhely kosarának lapsablonját.
1. Válassza ki a **Szerkesztés** opciót.
1. Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.
1. Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Gyors hozzáadás** modult, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Menjen az **Oldalak** lapra, és válassza ki a webhely kosarát.
1. Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.
1. A **Tároló** modul tulajdonságlapján a **Szélesség** tulajdonságot állítsa **Tároló kitöltése** értékre.
1. Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Gyors hozzáadás** modult, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

> [!NOTE] 
> A gyorshozzáadás modul a Commerce 10.0.17-es verziójának kiadásaként érhető el. Ha a Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt. Az utasításokat lásd itt: [SDK- és modultár-frissítések](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="add-a-bulk-purchase-module-to-a-product-details-page"></a>Tömeges beszerzési modul hozzáadása egy termék részletei laphoz

A PDP-lapon található tömeges beszerzési modul mátrixalapú tapasztalatokat biztosít, amellyel a beszerző gyorsan hozzáadhatja a termék több változatát a kosárhoz. Ha egy helyfelhasználónak ugyanannak a terméknek több változatát kell rendelnie, ez a tapasztalat nem teszi szükségesné a termékdimenziók kombinációjának kiválasztását, a mennyiséget, a változatot a kosárba adhatja, majd megismételheti a folyamatot a termékdimenziók más kombinációinál.

A commerce webhelyszerkesztőben a tömeges beszerzési modulnak a PDP-hez való hozzáadásához kövesse ezeket a lépéseket.

1. Menjen **a Sablonok** pontra, és válassza ki a webhely PDP-sablonját.
1. Válassza ki a **Szerkesztés** opciót.
1. Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.
1. Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A Modul hozzáadása párbeszédpanelen válassza ki a Tömeges beszerzés **modult, majd kattintson az OK** **·** **gombra**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Menjen az **Oldalak** lapra, és válassza ki a webhely PDP-ját.
1. Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.
1. A Tároló modul tulajdonságok ablakában, a Szélesség mezőben válassza **a** **·** **Kitöltési tároló** lehetőséget.
1. Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A Modul hozzáadása párbeszédpanelen válassza ki a Tömeges beszerzés **modult, majd kattintson az OK** **·** **gombra**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

> [!NOTE] 
> A tömeges beszerzési modul a Commerce rendszer 10.0.24-es verziójának kiadásában érhető el. Ha a Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt. Az utasításokat lásd itt: [SDK- és modultár-frissítések](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](../starter-kit-overview.md)

[SDK- és modultár-frissítések](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file)

[Szerkesztési oldal áttekintése](../authoring-home-overview.md)

[Sablonok és elrendezések áttekintése](../templates-layouts-overview.md)

[Töredékek használata](../work-with-fragments.md)

[Új webhelyoldal hozzáadása](../add-new-page.md)

[Pénztármodul](../add-checkout-module.md)

[Tartalomblokk-modul](../add-hero-module.md)

[Termékgyűjtési modul](../product-collection-module-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
