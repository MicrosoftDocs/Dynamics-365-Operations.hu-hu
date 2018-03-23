---
title: "A Microsoft Dynamics 365 for Talent lehetőségeinek bővítése"
description: "Ha létrehozott bármilyen Microsoft PowerApps alkalmazást, ezeket az alkalmazásokat hivatkozásokkal indíthatja el a Microsoft Dynamics 365 for Talent alkalmazásból."
author: rschloma
manager: AnnBe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 51eb4288f5b6c732755007c1dcd8c4db090ccc0a
ms.contentlocale: hu-hu
ms.lasthandoff: 03/08/2018

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a>A Microsoft Dynamics 365 for Talent lehetőségeinek bővítése

[!include[banner](includes/banner.md)]

Ha létrehozott bármilyen Microsoft PowerApps alkalmazást, ezeket az alkalmazásokat hivatkozásokkal indíthatja el a Microsoft Dynamics 365 for Talent alkalmazásból. Az alkalmazásokhoz való hozzáférés beállításához szükséges bizonyos információk beállítása a Talent alkalmazásban egy konfigurációs lapon, amely a **Rendszerfelügyelet** munkaterületen nyitható meg.

## <a name="configuring-embedded-powerapps-within-talent"></a>Beágyazott PowerApps alkalmazások konfigurálása a Talent alkalmazásban
Használja a **Beágyazott Microsoft PowerApps beállítása** lapot a Talent alkalmazás oldalainak konfigurálásához a PowerApps alkalmazások indítására. A **Beágyazott Microsoft PowerApps beállítása** lap megnyitásához nyissa meg a **Rendszerfelügyelet** munkaterületet, majd nyissa meg a **Hivatkozások** lapot. Válassza a **Microsoft PowerApps** elemet a lehetőségek közül a **Setup** csoportban. 

Az alábbi információkat adhatja meg vagy állíthatja be ezen az oldalon: 

> - Jól felismerhető név vagy azonosító minden PowerApps alkalmazásnak.
> - Egyedi azonosító (GUID) minden alkalmazásnak, amelyet hozzáad valamelyik Talent oldalhoz. Az alkalmazásazonosító a PowerApps-oldalon érhető el, [powerapps.com](http://powerapps.com/). 
> - A lap, amelyről a felhasználók megnyithatnak egy alkalmazást vagy jelentést. Nem minden Talent-lap támogatja a beágyazott PowerAppst és a PowerBI-jelentéseket. 

 > [!NOTE]
 >  Adja meg az oldal belső nevét, és nem az oldal tetején megjelenő megjelenítendő nevet. A belső név megkereséséhez nyissa meg a lapot, amelynek a belső nevére van szüksége, és kattintson a jobb gombbal bárhová az oldalon. A menü megnyílásakor vigye az egérmutatót a **Képernyő adatai** elemre. A belső képernyőnév a **Képernyő adatai** elem mellett jelenik meg a menüben.
 
> - Adja meg az űrlap-vezérlőelemet, amelytől az alkalmazás be tudja beolvasni a környezeti adatokat. Például egy alkalmazás használhatja egy dolgozó adatait. Ha megadja a **Dolgozó** lapot a **Környezet** mezőben, a **Dolgozó** lap megnyílik az alkalmazás indításakor. A **Környezetmezőben** nem kötelező megadni bejegyzést. 
> - Állítsa be a párbeszédpanel méretét, amelyen a PowerApps alkalmazás futni fog. A párbeszédpanelek lehetnek „kicsik” vagy „nagyok” a felhasználói felületet optimalizálásához, amikor az alkalmazás telefonon vagy nagyobb eszközön fut. 

Megadhatja azt is, hogy az alkalmazás mely jogi személyek számára legyen elérhető, illetve minden jogi személy számára is elérhetővé teheti. Alapértelmezés szerint a PowerApps alkalmazások elérhetők minden jogi személy számára.

## <a name="opening-an-application"></a>Alkalmazás megnyitása
Ha beágyazott PowerApps alkalmazásokat állított be, az alkalmazásaira mutatóként megadott hivatkozásokat a rendszer hozzáadja a Talent lapjaihoz. Kattintson egy hivatkozásra egy alkalmazás megnyitásához. 



