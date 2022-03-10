---
title: Első lépések az Brazíliára vonatkozó elektronikus számlázás használata során
description: Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az Első lépéseket a brazíliai elektronikus számlázás Finance és Supply Chain Management szolgáltatásban való használatát.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 82bbf806d207af0b15406e4bec516420db7f2c06
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7984853"
---
# <a name="get-started-with-electronic-invoicing-for-brazil"></a>Első lépések az Brazíliára vonatkozó elektronikus számlázás használata során 

[!include [banner](../includes/banner.md)]

Ez a témakör olyan információkat tartalmaz, amelyek bemutatják a brazil Elektronikus számlázással kapcsolatos első lépéseket. Ez a témakör végigvezeti a Regulatory Configuration Services (RCS) országfüggő konfigurációs lépésein, amelyek kiegészítik az [Első lépések az elektronikus számlázás használata során](e-invoicing-get-started.md) témakörben leírt lépéseket.

## <a name="country-specific-configuration-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Országspecifikus konfiguráció a brazil NF-e (BR) elektronikus számlázási funkcióhoz

A brazil **NF-e (BR) elektronikus számlázási funkció** egyes paraméterei alapértelmezett értékekkel vannak közzétéve. Tekintse át és szükség esetén frissítse az értékeket, hogy jobban megfeleljen az üzleti műveleti igényeknek, mielőtt telepítene az elektronikus számlázási funkciót a szolgáltatási környezetbe.

Ez a témakör az **Országspecifikus konfiguráció elektronikus számlázáshoz funkció** szakaszt egészíti ki az [Első lépések az elektronikus számlázási bővítmény használata során](e-invoicing-get-started.md) részben.

1. Az RCS-ben a **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
2. Az **Elektronikus számlázási funkciók** oldalon ellenőrizze, hogy be van-e jelölve a létrehozott **Brazil NF-e (BR)** Elektronikus számlázási funkciója.
3. A **Verziók** lapon ellenőrizze, hogy a **Piszkozat** verzió ki van-e választva.
4. A **Beállítások** lapon a rácson válassza a **Küldés**, majd a **Szerkesztés** lehetőséget.
5. Válassza a **Műveletek** lap **Műveletek** mezőcsoportjában az **(Előzetes verzió) XML-dokumentum aláírása** műveletet.
6. A **Paraméterek** mezőcsoportban válassza ki a **Tanúsítvány neve** lehetőséget, majd az **Érték** mezőbe írja be a Key Vault-paraméterhez társított tanúsítvány nevét.
7. Válassza a **Műveletek** lap **Műveletek** mezőcsoportjában az **(Előzetes verzió) XBrazil SEFAZ-szolgáltatás hívása** műveletet.
8. A **Paraméterek** mezőcsoportban válassza ki az **URL-cím** paramétert.
9. Szükség esetén az **Érték** mezőben ellenőrizze és frissítse az adott állam SEFAZ-dokumentációja által közzétett webszolgáltatások URL-címét, majd válassza a **Mentés** lehetőséget.
10. Az **Alkalmazhatósági szabályok** lap **Alkalmazhatósági szabály beállítása** mezőcsoportban szükség szerint ellenőrizze és frissítse az **Állapot** mező feltételeit ahhoz az államra vonatkozóan, amelyre a webszolgáltatások URL-címe hivatkozik.
11. Válassza a **Mentés** gombot, és zárja be az oldalt.
12. Az Elektronikus számlázási funkció telepítését a Szolgáltatási környezetbe lásd: [Első lépések az elektronikus számlázási bővítmény használata során](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Országspecifikus alkalmazásbeállítás konfigurációja a brazil NF-e (BR) elektronikus számlázási funkcióhoz

Mielőtt telepítene egy alkalmazást, végezze el ezeket a lépéseket a Finance vagy a Supply Chain Management kapcsolt alkalmazás beállításához.

Ez a témakör az **Alkalmazás országspecifikus konfigurációjának beállítása** szakaszt egészíti ki az [Első lépések az elektronikus számlázási bővítmény használata során](e-invoicing-get-started.md) részben.

1. Az RCS-ben a **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
2. Az **Elektronikus számlázás funkciók** oldalon ellenőrizze, hogy be van-e jelölve a **Brazil NF-e (BR)** Elektronikus számlázási funkciója.
3. A **Verziók** lapon ellenőrizze, hogy a **Piszkozat** verzió ki van-e választva.
4. A **Beállítások** lapon válassza ki az **Alkalmazásbeállítás** lehetőséget és a **Kapcsolódó alkalmazás** mezőben válassza ki azt az alkalmazást, ahová telepíteni szeretné.
5. A **Tábla neve** mezőben ellenőrizze, hogy ki van-e választva a **Pénzügyi bizonylat fejléce** lehetőség.
6. Válassza ki a **Választípusok** lehetőséget, majd válassza az **Új** lehetőséget.
7. A **Válasz típusa** mezőbe írja be a "Response" szót rögzített értékként, a **Leírás** mezőbe pedig a "Description" szót.
8. A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.
9. A **Modell-leképezés** mezőben válassza a **Modell-leképezés válaszüzenetből** **Válaszüzenet importálási formátuma (előzetes verzió)** lehetőséget, majd válassza a **Mentés** lehetőséget.
10. Válassza az **Új** lehetőséget és a **Válasz típusa** mezőbe írja be a "ResponseData" szót rögzített értékként, a **Leírás** mezőbe pedig a "Description" szót.
11. A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.
12. A **Modell-leképezés** mezőben válassza a **Válaszadatok importálása** **(Előzetes verzió) NF-e válaszadatok importálási formátuma (BR)** lehetőséget, majd válassza a **Mentés** lehetőséget.
13. Az alkalmazásbeállítás Finance vagy Suppy Chain kapcsolódó alkalmazásba való telepítéséhez lásd: [Első lépések az elektronikus számlázásban](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Országspecifikus konfiguráció a brazil NFS-e ABRASF Curitiba (BR) elektronikus számlázási funkcióhoz

A **brazil NFS-e ABRASF Curitiba (BR) elektronikus számlázási funkció** egyes paraméterei alapértelmezett értékekkel vannak közzétéve. Tekintse át és szükség esetén frissítse az értékeket, hogy jobban illeszkedjen az üzleti műveleti igényekhez, mielőtt telepítene az elektronikus számlázási funkciót a szolgáltatási környezetbe.

Ez a témakör az **Országspecifikus konfiguráció elektronikus számlázáshoz funkció** szakaszt egészíti ki az [Első lépések az elektronikus számlázási bővítmény használata során](e-invoicing-get-started.md) részben.

1. Az RCS-ben a **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
2. Az **Elektronikus számlázás funkciók** oldalon ellenőrizze, hogy be van-e jelölve a létrehozott **Brazil NFS-e ABRASF Curitiba (BR)** Elektronikus számlázási funkciója.
3. Ellenőrizze a **Verziók** lapon, hogy ki van-e választva a **Vázlat** verzió, és a **Beállítások** lap rácsán válassza a **Küldés** lehetőséget.
4. Jelölje be a **Szerkesztés** lehetőséget, és a **Műveletek** mezőcsoport **Műveletek** lapján válassza az **(Előzetes verzió) XML-dokumentum aláírása** első előfordulását.
5. A **Paraméterek** mezőcsoportban válassza ki a **Tanúsítvány neve** lehetőséget.
6. Az **Érték** mezőbe írja be a Key Vault-paraméterhez társított tanúsítvány nevét.
7. A **Műveletek** mezőcsoportban válassza ki az **(Előnézet) XML-dokumentum aláírása** második előfordulását.
8. A **Paraméterek** mezőcsoportban válassza ki a **Tanúsítvány neve** lehetőséget.
9. Az **Érték** mezőbe írja be a Key Vault-paraméterhez társított tanúsítvány nevét.
10. Válassza a **Műveletek** lap **Műveletek** mezőcsoportjában az **(Előzetes verzió) XBrazil SEFAZ-szolgáltatás hívása** műveletet.
11. A **Paraméterek** mezőcsoportban válassza ki az **URL-cím** paramétert.
12. Szükség esetén az **Érték** mezőben ellenőrizze és frissítse Curitiba város adóhatósága által közzétett webszolgáltatások URL-címét, majd válassza a **Mentés** lehetőséget.
13. A **Beállítások** lapon a rácson válassza a **Lekérdezés**, majd a **Szerkesztés** lehetőséget.
14. Válassza a **Műveletek** lap **Műveletek** mezőcsoportjában az **(Előzetes verzió) XBrazil SEFAZ-szolgáltatás hívása** műveletet.
15. A **Paraméterek** mezőcsoportban válassza ki az **URL-cím** paramétert.
16. Szükség esetén az **Érték** mezőben ellenőrizze és frissítse Curitiba város adóhatósága által közzétett webszolgáltatások URL-címét.
17. Válassza a **Mentés** gombot, majd zárja be az oldalt.
18. Az Elektronikus számlázási funkció telepítését a Szolgáltatási környezetbe lásd: [Első lépések az elektronikus számlázási bővítmény használata során](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Alkalmazásbeállítás országspecifikus konfigurációja a brazil NFS-e ABRASF Curitiba (BR) elektronikus számlázási funkcióhoz

Mielőtt telepítene egy alkalmazást, végezze el ezeket a lépéseket a Finance vagy a Supply Chain Management kapcsolt alkalmazás beállításához.

Ez a témakör az **Alkalmazás országspecifikus konfigurációjának beállítása** szakaszt egészíti ki az [Első lépések az elektronikus számlázási bővítmény használata során](e-invoicing-get-started.md) részben.

1. Az RCS-ben a **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
2. Az **Elektronikus számlázás funkciók** oldalon ellenőrizze, hogy be van-e jelölve a **Brazil NFS-e ABRASF Curitiba (BR)** Elektronikus számlázási funkciója.
3. Ellenőrizze a **Verziók** lapon, hogy ki van-e választva a **Vázlat** verzió, és a **Beállítások** lapon válassza az **Alkalmazás beállítása** lehetőséget.
4. Válassza ki a **Csatlakoztatott alkalmazás** mezőben azt az alkalmazást, ahová telepíteni szeretné.
5. A **Tábla neve** mezőben ellenőrizze, hogy ki van-e választva a pénzügyi bizonylat fejléce.
6. Válassza ki a **Választípusok** lehetőséget, majd válassza az **Új** lehetőséget.
7. A **Válasz típusa** mezőbe írja be az "ABRASFCuritibaSubmitResponse" szót rögzített értékként, a **Leírás** mezőbe pedig a "Description" szót.
8. A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.
9. A **Modell-leképezés** mezőben válassza a **Válaszüzenet importálása** **(Előzetes verzió) NFS-e ABRASF Curitiba válaszüzenet importálása (BR)** lehetőséget, majd válassza a **Mentés** lehetőséget.
10. Válassza az **Új** lehetőséget és a **Válasz típusa** mezőbe írja be az "ABRASFCuritibaSubmitResponseData" szót rögzített értékként, a **Leírás** mezőbe pedig a "Description" szót.
11. A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.
12. A **Modell-leképezés** mezőben válassza a **Válaszadatok importálása** **(Előzetes verzió) NFS-e ABRASF válaszadatok importálási formátuma (BR)** lehetőséget, majd válassza a **Mentés** lehetőséget.
13. Válassza az **Új** lehetőséget és a **Válasz típusa** mezőbe írja be az "ABRASFCuritibaInquireResponse" szót rögzített értékként, a **Leírás** mezőbe pedig a "Description" szót.
14. A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.
15. A **Modell-leképezés** mezőben válassza a **Válaszüzenet importálása** **(Előzetes verzió) NFS-e ABRASF Curitiba válaszüzenet importálása (BR)** lehetőséget.
16. Válassza a **Mentés** gombot, és zárja be az oldalt.
17. Az alkalmazásbeállítás Finance vagy Suppy Chain kapcsolódó alkalmazásba való telepítéséhez lásd: [Első lépések az elektronikus számlázásban](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat
Az **NF-e szövetségi – brazil elektronikus számla** és az **NFS-e – brazil szolgáltatás (város) elektronikus számla** funkcióinak engedélyezése korlátozott adatok küldését, többek között a szervezet adóregisztrációs azonosítóját is előírhatja. Ezek továbbítva lesznek az adóhatóság által kinevezett harmadik fél ügynökségekhez, az elektronikus számlák – kormányzati szervek webszolgáltatással való integrációhoz szükséges, előre meghatározott formátumban való – adott adóhatósághoz történő elküldése céljából. Rendszergazdaként engedélyezheti vagy kikapcsolhatja az **NF-e szövetségi – brazil elektronikus számla (BR)** és az **NFS-e – brazil szolgáltatás (város) elektronikus számla** funkciót. A következő lépések megmutatják ennek menetét: 

1. Menjen a **Szervezeti adminisztráció** > **Beállítás** > **Elektronikus dokumentumparaméterek** lehetőségre. 
2. Válassza ki a **Funkciók** lapon az **NF-e szövetségi – brazil elektronikus számla (BR)** vagy az **NFS-e – brazil szolgáltatás (város) elektronikus számla** funkciót tartalmazó sort, és válassza ki a funkciót. A külső rendszerekből ebbe a Dynamics 365 online szolgáltatásba importált adatok az [Adatvédelmi nyilatkozatunk](https://go.microsoft.com/fwlink/?LinkId=512132) hatálya alá tartoznak. További tájékoztatásért olvassa el az országspecifikus funkciók dokumentációja szakaszokban található Adatvédelmi nyilatkozatot.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus számlázás áttekintése](e-invoicing-service-overview.md)
- [Első lépések az elektronikus számlázási szolgáltatás adminisztrálása során](e-invoicing-get-started-service-administration.md)
- [Első lépések az elektronikus számlázási használata során](e-invoicing-get-started.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
