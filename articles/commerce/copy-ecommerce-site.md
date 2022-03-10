---
title: E-commerce webhely másolása
description: Ez a témakör azt ismerteti, hogyan lehet másolni egy meglévő e-commerce webhelyet a webhelyszerkesztő e-commerce Microsoft Dynamics 365 Commerce környezetei között, illetve között.
author: psimolin
ms.date: 03/03/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 284a33099fecc5a8e8d5d5d31612abab51735773
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2022
ms.locfileid: "8386911"
---
# <a name="copy-an-e-commerce-site"></a>E-commerce webhely másolása

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a témakör azt ismerteti, hogyan lehet másolni egy meglévő e-commerce webhelyet a webhelyszerkesztő e-commerce Microsoft Dynamics 365 Commerce környezetei között, illetve között.

Dynamics 365 Commerce A <a0/1><a2/1><a2/"<a2/<a2/a Webhelyek másolása és cloning a Commerce Webhelyszerkesztőben önkiszolgáló műveletként való másolását és cloningot támogatja. A telephelyek egyetlen e-kereskedelmi környezetbe vagy két e-kereskedelmi környezetbe másolhatók. A webhely másolási műveletét kezdeményező felhasználónak bérlő-rendszergazdának kell lennie mind a forrás, mind a cél e-commerce környezetben.

A hely másolási művelete a forráshely összes e-commerce tartalmát átmásolja. Ez a tartalom oldalakat, részleteket, sablonokat, URL-címeket és eszközöket foglal magában. Új hely csak akkor használható, ha az első futtatási tapasztalat (FRE) folyamattal inicializálni kell. A csatornák a Webhely-beállítási csatornák **webhelyszerkesztőben hozzárendelhetők és kezelhetők \>**.

A hely másolási műveletének időtartama elsősorban a forráshelyen található eszközök számától függ. Javasoljuk, hogy kivételesen nagy helyek esetén fontolja meg inkább a környezet másolási műveletét. (Ennek a műveletnek az adathorizhatósági műveletnek is nevezik).

> [!NOTE]
> - A forráshely csak olvasható lesz a hely másolási műveletének időtartamára.
> - A rendszer csak a közzétett dokumentumverziókat másolja át. Ha még nem tett közzé verziókat, akkor csak a legújabb verziókat másolja át a program.
> - A tartalom verzióelőzmények nem érhetők el a célhelyen.

## <a name="copy-a-site-within-an-e-commerce-environment"></a>Hely másolása e-kereskedelmi környezetbe

A következő lépésekkel másolhatja le a webhelyet az e-commerce környezetbe.

1. Jelentkezzen be a helyszerkesztőbe, annak a környezetnek a számára, ahol a másolási műveletet végre szeretné végezni.
1. Nyissa meg a webhelylista nézetet a **Jobb** felső sarkában lévő Hely kapcsoló kiválasztásával, **majd a Helyek kezelése lehetőség választásával**.
1. Keresse meg azt a helyet, amelyet másolni vagy másolni szeretne, és válassza ki azt a hely neve melletti jelölőnégyzet be jelölje be.
1. A munkaablakban válassza a Hely másolása **lehetőséget**.
1. Adja meg **az új webhely** nevét **a Webhely másolása párbeszédpanel Új** hely neve mezőjében. Az új hely nevének egyedinek kell lennie az e-commerce környezetben. A **Forrás bérlő és** **Forrás** webhely mezői automatikusan az aktuális bérlő és a kiválasztott telephely adataira vannak beállítva.
1. Válassza a Másolat **létrehozása lehetőséget**.

Az adatok ellenőrzése után az értesítés azt jelzi, hogy a rendszer új másolati feladatot hozott létre a webhelyen. A feladat haladását a [**Bérlő – Feladatok lap jobb oldali ablakában követheti** nyomon](#monitor-the-site-copy-operation). Ha a másolási művelet sikeresen befejeződött, az új hely megjelenik a helyek listájában a webhelylista nézetben.

Az alábbi ábra a Webhely másolása **párbeszédpanelt** mutatja be a webhelyszerkesztőben.

![A Webhely másolása párbeszédpanel a Webhelyszerkesztőben](media/site-copy_1.png)

## <a name="copy-a-site-between-two-e-commerce-environments"></a>Hely másolása két e-commerce környezet között

Ha egy webhelyet két e-commerce környezet között kell másolni, kövesse ezeket a lépéseket.

1. Jelentkezzen be a helyszerkesztőbe a cél e-commerce környezetben.
1. A munkaablakban válassza a Hely másolása **lehetőséget**.
1. Adja meg **az új webhely** nevét **a Webhely másolása párbeszédpanel Új** hely neve mezőjében. Az új hely nevének egyedinek kell lennie az e-commerce környezetben.
1. A Forrás **bérlő mezőben** válassza ki a forrás bérlő nevét.
1. A Forráshely **mezőben** válassza ki a forráshelyet.
1. Válassza a Másolat **létrehozása lehetőséget**.

> [!NOTE]
> A bérlői rendszergazdai engedélyekre mind a forrás, mind a cél e-commerce környezetben szükség van.

Az adatok ellenőrzése után az értesítés azt jelzi, hogy a rendszer új másolati feladatot hozott létre a webhelyen. A feladat haladását a [**Bérlő – Feladatok lap jobb oldali ablakában követheti** nyomon](#monitor-the-site-copy-operation). Ha a másolási művelet sikeresen befejeződött, az új hely megjelenik a helyek listájában a webhelylista nézetben.

## <a name="monitor-the-site-copy-operation"></a>A hely másolási műveletének figyelése

A hely másolási műveletének előrehaladását a következő lépések szerint követheti.

1. Jelentkezzen be a helyszerkesztőbe a cél e-commerce környezetben.
1. A bal oldali ablakban válassza a Bérlő feladatok **lehetőséget**.
1. A Bérlő **– Feladatok** lapon keresse meg és válassza ki a listában a telephely másolási feladatot. A jobb oldalon megjelenik egy ablak, amely megjeleníti a kiválasztott feladat állapotát és részletes adatait.

A Folyamatban állapotú **feladat visszavonható**. Válassza ki a feladatot a listából, majd válassza a **Mégse** lehetőséget a munkaablakban.

Egy Sikertelen **vagy** **Befejeződött állapotú feladatot is megpróbálhat újrapróbálkozáskor.** Válassza ki a feladatot a listából, majd válassza az **Újrapróbálkozás** lehetőséget a munkaablakban.

> [!NOTE]
> A videoeszközök feldolgozása a hely másolási feladatának befejezése után folytatódhat.

Az alábbi ábra a **webhelyszerkesztő** Bérlői feladatok oldalának jobb oldali ablakára ábrázol egy példát.

![A feladat részletei a webhelyszerkesztő Bérlő feladatok lapján, a jobb oldali ablakban.](media/site-copy_2.png)

## <a name="initialize-a-new-site-by-using-the-fre-process"></a>Új hely inicializálása a FRE-folyamat használatával

Az új hely csak akkor használható, ha a FRE folyamattal inicializálni kell.

Ha a FRE folyamat segítségével inicializálni kell egy új helyet, kövesse ezeket a lépéseket.

1. Jelentkezzen be az új webhely webhelyszerkesztőbe.
1. Nyissa meg a webhelylista nézetet a **Jobb** felső sarkában lévő Hely kapcsoló kiválasztásával, **majd a Helyek kezelése lehetőség választásával**.
1. Keresse meg és válassza ki az inicializálni kívánt új helyet.
1. A Webhely **beállítása párbeszédpanel** Tartomány **kiválasztása** mezőjében válasszon ki egy tartományt. Az inicializálás során az e-commerce környezethez társított összes tartomány elérhető.
1. Az Alapértelmezett csatorna **kiválasztása mezőben** válassza ki a társított online áruházi csatornát. A kiválasztott csatorna biztosítja a szortimenteket és a Commerce Headquarters által tárolt egyéb adatokat.
1. Az Alapértelmezett **nyelv kiválasztása mezőben** válassza ki az alapértelmezett szerzője nyelvet. A kiválasztott online áruházi csatornához beállított összes nyelv kiválasztható.
1. Az Elérési **út** mezőben az érték az alaptartományból és egy tetszőleges URL-címből áll, amely beírható. Az URL-elérési utat üresen hagyhatja, ha a csatornát a tartomány gyökérkönyvtára alapján fogja kézbesíteni, vagy ha később szeretné megadni ezt az információt a Webhelyszerkesztő csatorna-konfigurációs nézetében. A hely elérési útjának egyedinek kell lennie az e-commerce környezetben.
1. Válassza ki az **OK** lehetőséget. A hely inicializálása a megadott adatokkal megszabadított adatokkal megszabadított, és való igazsal áll a webhelykezelés nézetére.

Az alábbi ábra a **Webhely** beállítása párbeszédpanelt mutatja be a webhelyszerkesztőben.

![A webhely párbeszédpanelének beállítása a Webhelyszerkesztőben.](media/site-copy_3.png)

## <a name="additional-resources"></a>További erőforrások

[Tartománynév konfigurálása](configure-your-domain-name.md)

[Új e-kereskedelmi bérlő telepítése](deploy-ecommerce-site.md)

[Dynamics 365 Commerce webhely társítása online csatornával](associate-site-online-store.md)

[Robots.txt fájlok kezelése](manage-robots-txt-files.md)

[URL-átirányítások tömeges feltöltése](upload-bulk-redirects.md)

[B2C-bérlő beállítása a Commerce-ben](set-up-b2c-tenant.md)

[Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)

[Több B2C-bérlő konfigurálása egy Commerce környezetben](configure-multi-b2c-tenants.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

[Helyalapú áruházészlelés engedélyezése](enable-store-detection.md)
