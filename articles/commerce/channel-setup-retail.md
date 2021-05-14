---
title: Kiskereskedelmi csatorna beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egy új kiskereskedelmi csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3f1f5dc2c8402d9b6b68a049f804932812eb74c0
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937534"
---
# <a name="set-up-a-retail-channel"></a>Retail-csatorna beállítása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet egy új kiskereskedelmi csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.

A Dynamics 365 Commerce rendszer támogatja a többszörös kiskereskedelmi csatornák használatát. Ezek a kiskereskedelmi csatornák lehetnek online áruházak, hívásközpontok és kiskereskedelmi áruházak (más néven rendes, nem online üzletek). A kiskereskedelmi üzletek csatornái saját fizetési módokkal, árcsoportokkal, (POS) pénztárgépekkel, bevételi és kiadási számlákkal, valamint munkatársakkal rendelkezhetnek. Az összes ilyen elemet be kell állítania, kiskereskedelmi üzlet csatornájának létrehozása előtt. 

A kiskereskedelmi csatorna létrehozása előtt győződjön meg arról, hogy követi a [csatorna előfeltételeit](channels-prerequisites.md).

## <a name="create-and-configure-a-new-retail-channel"></a>Új kiskereskedelmi csatorna létrehozása és konfigurálása

1. A navigációs ablaktáblán lépjen a **Modulok \> Csatornák \> Áruházak \> Minden áruház** részhez.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Név** mezőben adja meg az új csatorna nevét.
1. Az **Üzlet száma** mezőben adjon meg egy egyedi üzletszámot. A számnak alfanumerikusnak kell lennie, legfeljebb 10 karakterrel.
1. A **jogi személy** legördülő listában adja meg a megfelelő jogi személyt.
1. A **raktár** legördülő listában adja meg a megfelelő raktárat.
1. Az **Üzlet időzónája** mezőből válasszon egy megfelelő időzónát.
1. Az **Áfacsoport** legördülő listából válassza ki az üzlethez megfelelő áfacsoportot.
1. A **Pénznem** mezőben válassza ki a megfelelő pénznemet.
1. Az **Ügyfél címjegyzéke** mezőben adjon meg érvényes címjegyzéket.
1. Az **Alapértelmezett ügyfél** mezőben adjon meg egy érvényes alapértelmezett ügyfelet.
1. A **Funkcióprofil** mezőben válasszon ki egy funkcióprofilt, ha van ilyen.
1. Az **E-mail értesítési profilja** mezőben adjon meg egy érvényes e-mail-értesítési profilt.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő kép bemutatja egy új kiskereskedelmi csatorna létrehozását.

![Új kiskereskedelmi csatorna](media/channel-setup-retail-1.png)

A következő kép egy példát mutat a kiskereskedelmi csatornára.

![Kiskereskedelmi csatorna példája](media/channel-setup-retail-2.png)

## <a name="other-settings"></a>Egyéb beállítások

Számos egyéb választható beállítás érhető el, amely a kiskereskedelmi üzlet szükségletei alapján beállítható a **Kimutatás/zárás** és a **vegyes** szakaszok között.

Ezenkívül lásd [A pénztár (POS) képernyő-elrendezései](pos-screen-layouts.md) című részt további információért az alapértelmezett képernyő-elrendezés beállításáról a **Képernyő-elrendezés** szakaszban és a [Kiskereskedelmi hardverállomás konfigurálása és telepítése](retail-hardware-station-configuration-installation.md) című részt telepítési információért a **Hardverállomások** résszel kapcsolatban.

A következő kép egy példát mutat a kiskereskedelmi csatorna beállítási konfigurációjáról.

![Kiskereskedelmi csatorna konfigurálása – példa](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a>További csatornák beállítása

További cikkek szükségesek, amelyeket be kell állítani egy olyan csatornához, amely a Művelet ablaktáblán található a **Beállítás** szakaszban.

Az online csatorna beállításához szükséges további feladatok közé tartozik a fizetési módok, a készpénzbevallások, a szállítási módok, a bevételi/kiadási számlák, a szakaszok, a teljesítési csoport hozzárendelésének és a széfek beállítása.

A következő képen a kiskereskedelmi csatorna beállításainak különböző beállításai láthatók a **beállítás** lapon.

![Csatorna beállítása](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a>Fizetési módok beállítása

A fizetési módok beállításához a csatornán támogatott valamennyi fizetési típusnál kövesse az alábbi lépéseket.

1. A műveleti ablaktáblán válassza a **Beállítás** lapot, majd válassza ki a **Fizetési módokat**.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A navigációs ablakban válassza ki a kívánt fizetési módot.
1. Az **általános** szakaszban adjon meg egy **művelet nevét**, és adja meg a kívánt beállításokat.
1. Adja meg a fizetési típushoz szükséges további beállításokat.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő kép egy példát mutat a készpénzfizetési módra.

![Fizetési módok – példa](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a>Készpénzelszámolás beállítása

1. A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Készpénzelszámolást**.
1. A műveleti ablaktáblán válassza az **új** parancsot, majd hozza létre az összes vonatkozó **Érme** és **Bankjegy** címletet.

A következő kép egy példát mutat a készpénzelszámolásra.

![Készpénzelszámolások beállításai](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a>Szállítási módok beállítása

A konfigurált szállítási módokat a **Szállítási módok** kiválasztásával tekintheti meg a **Beállítás** lapon a Műveleti ablaktáblán.  

Szállítási mód módosításához vagy hozzáadásához kövesse az alábbi lépéseket.

1. A navigációs ablakban nyissa meg a **Modulok \> Készletkezelés \> Szállítási módok** elemet.
1. A műveleti ablaktáblán válassza az **Új** elemet új szállítási mód létrehozásához, vagy válasszon meglévő módot.
1. A **kiskereskedelmi csatornák** területen válassza a **sor hozzáadása** parancsot a csatorna hozzáadásához. Csatornák hozzáadása a szervezeti csomópontok használatával, nem pedig az egyes csatornák hozzáadásával egyszerűsítheti a csatornák hozzáadását.

A következő kép egy példát mutat a szállítási módra.

![Szállítási módok beállítása](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a>Bevételi/kiadási számla beállítása

A bevétel/kiadási számla beállításához kövesse az alábbi lépéseket.

1. A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Bevételi/kiadási számla**.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Név** mezőbe írjon be egy nevet.
1. A **Keresési név** mezőbe írjon be egy keresési nevet.
1. A **Számlatípus** részben adja meg a számlatípust.
1. Szükség szerint adjon meg szöveget a következőkhöz: **Üzenet 1. sora**, **Üzenet 2. sora**, **1. bizonylatszöveg** és **2. bizonylatszöveg**.
1. A **feladás** területen írja be a feladási adatokat.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő kép egy példát mutat egy bevételi/kiadási számlára.

![Bevételi/kiadási számlák beállítása](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a>Szakaszok beállítása

A szakaszok beállításához kövesse az alábbi lépéseket.

1. A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Szakaszok**.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **szakasz száma** mezőbe írja be a szakasz számát.
1. Adjon meg egy leírást a **Leírás** alatt.
1. A **szakaszméret** mezőbe írja be a szakaszméretet.
1. Szükség szerint adja meg az **Általános** és az **Értékesítési statisztikák** további beállításait.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="set-up-a-fulfillment-group-assignment"></a>Teljesítési csoport hozzárendelésének beállítása

A teljesítési csoport hozzárendelésének beállításához tegye a következőket.

1. A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Teljesítési csoport hozzárendelése**.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **teljesítési csoport** legördülő listából válassza ki a teljesítési csoportot.
1. Ha a **Leírás** legördülő listában adjon meg egy leírást.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget

A következő kép egy példát mutat be a teljesítési csoport hozzárendelésének beállítására.

![Teljesítési csoport hozzárendeléseinek beállítása](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a>Széfek beállítása

A széfek beállításához kövesse az alábbi lépéseket.

1. A Műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **széfek**.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Adja meg a széf nevét.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="ensure-unique-transaction-ids"></a>Egyedi tranzakcióazonosítók biztosítása

A Commerce 10.0.18-as verziójától kezdve a pénztár számára generált tranzakcióazonosítók egymást követőek, és a következő részekből állnak:

- Rögzített rész, amely az üzletazonosító és a terminálazonosító éke. 
- Követést jelző rész, ami egy számsorozat. 

Pontosabban a formátum a következő: *{store}-{terminal}-{numbersequence}*. 

Mivel a tranzakcióazonosítók offline és online módban is generálhatók, előfordult, hogy a rendszer ismétlődő tranzakcióazonosítókat hozott létre. Az ismétlődő tranzakcióazonosítók megszüntetése sok manuális adatjavítást igényel. 

A Commerce 10.0.19-es verziója esetén a tranzakcióazonosító formátuma frissült, hogy eltávolítsa a követést jelző részt, és egy 13-jegyű számot használ, amely az idő 1970 óta ezredmásodpercekben eltelt idő kiszámításával jött létre. Ezzel a módosítással az új tranzakcióazonosító-formátum: *{store}-{terminal}-{millisecondsSince1970}*. Ezzel a frissítéssel a tranzakcióazonosítók nem egymást követőek, és biztosítja, hogy a tranzakcióazonosítók mindig egyediek. 

> [!NOTE]
> A tranzakcióazonosítókat csak a belső rendszer használja, így nem szükséges, hogy egymást követők legyenek. Sok ország azonban megköveteli, hogy a nyugtaazonosítók egymást követőek legyenek.

Az új tranzakcióazonosító-formátum funkciót a **Funkciókezelés** munkaterületről lehet engedélyezni. 

Az új tranzakcióazonosítók engedélyezéséhez hajtsa végre a következő lépéseket:

1. A Commerce-központban lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre.
1. Szűrjön a „kiskereskedelem és kereskedelem” modulra.
1. Keressen rá **Az új tranzakcióazonosító engedélyezése a tranzakcióazonosítók ismétlődésének elkerülése érdekében** funkció nevére.
1. Válassza ki a funkciót, majd a jobb oldali ablaktáblán válassza az **Engedélyezés most** lehetőséget.  
1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.
1. Futtassa a **1070 csatornakonfiguráció** és a **1170 pénztár feladatrögzítő** feladatokat az engedélyezett funkció üzletekkel való szinkronizálása érdekében.
1. Miután a módosításokat elküldte az üzleteknek, a pénztárterminálokat be kell zárni, majd újra meg kell nyitni, hogy az új tranzakcióazonosító-formátumot használják. 

> [!NOTE]
> Az új tranzakcióazonosító-formátum funkció engedélyezése után nem tilthatja le ezt a funkciót. Ha le kell tiltani, forduljon a Commerce-ügyfélszolgálathoz.

## <a name="additional-resources"></a>További erőforrások

[Csatornák áttekintése](channels-overview.md)

[Csatorna beállításainak előfeltételei](channels-prerequisites.md)

[Online csatorna beállítása](channel-setup-online.md)

[Hívásközpont csatorna beállítása](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
