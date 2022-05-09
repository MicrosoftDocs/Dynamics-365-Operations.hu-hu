---
title: Állítsa be a számsorozatokat a kiskereskedelmi kimutatások számára.
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni a kiskereskedelmi kimutatások számára szükséges számsorozatokat Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: db47ca4ee8bac0d55b9a9c732183d2734bce660f
ms.sourcegitcommit: 9e1129d30fc4491b82942a3243e6d580f3af0a29
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8649177"
---
# <a name="set-up-number-sequences-for-retail-statements"></a>Állítsa be a számsorozatokat a kiskereskedelmi kimutatások számára.

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör azt ismerteti, hogyan kell konfigurálni a kiskereskedelmi kimutatások számára szükséges számsorozatokat Microsoft Dynamics 365 Commerce.

A kiskereskedelmi kimutatások kétféle típusát használják Dynamics 365 Commerce: 

- **A tranzakciós** kimutatásokat nagy gyakorisággal lehet létrehozni és feladva. Az üzlet minden nem pénzügyi tranzakcióját fel kell adni a központba Dynamics 365 Commerce. 
- **A pénzügyi** kimutatásokat naponta egyszer kell létrehozni és feladva. A kereskedelmi központba a p-feladaton keresztül feltöltött kiskereskedelmi áruházakból lezárt műszakokat tartalmaznak.

## <a name="configure-a-number-sequence-for-statement-posting"></a>Számsorozat konfigurálása kimutatásfeladáshoz

Miután befejezte egy kiskereskedelmi üzlet beállítását, a Commerce Headquarters szolgáltatásban be kell állítania egy egyedi számsorozatot, amely a kimutatások létrehozásánál lesz használva.

A következő lépések szerint konfigurálhatja a kimutatások commerce headquarters programba való feladására vonatkozó számsorozatot.

1. Válassza a **Szervezeti adminisztráció \> Számsorozatok \> Számsorozatok** lehetőséget.
1. Új **rekord \> létrehozásához válassza** az Új számsorozat lehetőséget.
1. Az Azonosító **gyorskódok** gombra írja **be a Számsorozat** kódja mezőben a számsorozat kódját.
1. Írjon be **egy nevet a Számsorozat** neve mezőbe.
1. Válassza a Hatókör **paraméterei** gyorsétét a **Hatókör** mezőBen az Üzemi egység **lehetőséget**.
1. Az Üzemi **egység mezőben** válassza ki azt az üzletet, amelynél használni fogja a számsorozatot.
1. A Szegmensek **gyors** oldalon határozza meg a szegmenseket.
1. A Hivatkozások **gyors** területen állítsa **a Terület mezőt** kiskereskedelmi **üzletre**.
1. Állítsa kimutatásszámra a Hivatkozás **mezőt**, majd válassza az **OK gombra**.**·**

    ![Azonosító, Hatókör paraméterei, Szegmensek és Hivatkozások gyorslap a Számsorozatok lapon.](media/retail-statements-num-seq-setup-01.png)

1. A Számfoglalás szakasz Általános gyorstája területén frissítse a Legkisebb és Legnagyobb mezőt úgy, **·** **·** **hogy azok megegyeznek a Szegmensek gyorsban megadott Alfanumerikus** **szegmens** hosszával.**·** **·**
1. A Teljesítmény **gyorsgombon ajánlott** **·** **az** Előzetes hely beállítást Igen, a Számok mennyisége **mezőt** pedig 25-re állítani.**·**

    ![Általános és Teljesítmény gyorslap a Számsorozatok lapon.](media/retail-statements-num-seq-setup-02.png)

1. A munkaablakban a Mentés gombra kattintva **mentse** a módosításokat, és zárja be az oldalt.
