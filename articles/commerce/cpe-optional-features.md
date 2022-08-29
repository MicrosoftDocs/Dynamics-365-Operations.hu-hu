---
title: Dynamics 365 Commerce tesztkörnyezet választható funkcióinak konfigurálása
description: Ez a cikk bemutatja, hogy hogyan konfigurálhatja a beérkezett üzenetek környezetében elérhető Microsoft Dynamics 365 Commerce opcionális funkciókat.
author: josaw1
ms.date: 06/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 4935f5f6ee17cba9c09eb79132119a7cbc08d9ad
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270355"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-sandbox-environment"></a>Dynamics 365 Commerce tesztkörnyezet választható funkcióinak konfigurálása

[!include [banner](includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan konfigurálhatja a beérkezett üzenetek környezetében elérhető Microsoft Dynamics 365 Commerce opcionális funkciókat.

## <a name="prerequisites"></a>Előfeltételek

Ha a tranzakciós e-mail funkciókat bemutatót szeretné látni, teljesülnie kell a következő előfeltételeknek:

- Elérhető e-mail kiszolgáló (Simple Mail Transfer Protocol \[SMTP-kiszolgáló\]), Microsoft Azure amely abból az előfizetésből használható, ahol a beérkezett üzenetek környezetét létesíti.
- A kiszolgáló teljes képzésű tartományneve (FQDN)/IP-címe, SMTP-portszáma és a hitelesítési adatok rendelkezésre állnak.

## <a name="configure-the-image-back-end"></a>A képháttér konfigurálása

### <a name="find-your-media-base-url"></a>A média alap URL-címének megkeresése

> [!NOTE]
> A művelet végrehajtása előtt be kell fejeznie a [Webhely beállítása a Commerce alkalmazásban](cpe-post-provisioning.md#set-up-your-e-commerce-sites) témakör lépéseit.

1. Jelentkezzen be a Commerce webhelykészítőbe azzal az URL-címmel, amelyet az e-kereskedelem inicializálásakor a létesítés során megadott (lásd: [E-kereskedelem inicializálása](provisioning-guide.md#initialize-e-commerce)).
1. Nyissa meg **a gyárat**, **a Kalandorort** vagy **a Kalandorék** üzleti webhelyét, amelybe dolgozni szeretne.
1. A bal oldali menüben válassza az **Médiatár** lehetőséget.
1. Válasszon ki egyetlen képeszközt.
1. A jobb oldali tulajdonságvizsgálóban keresse meg a **Nyilvános URL** tulajdonságot. Az érték egy URL. Egy példa:

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.

1. Cserélje le az URL-címben szereplő utolsó azonosítót (az előző példában **MA1nQC**) a következő karakterlánccal: **search?fileName=**. A csere után így néz ki a példa URL:

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    Ez az URL-cím a média alap URL-je. Jegyezze fel.

### <a name="update-the-media-base-url"></a>A média alap URL-cím frissítése

1. Bejelentkezés a Commerce központba.
1. A bal oldali menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Csatornaprofilok** lehetőséget.
1. Válassza ki a **Szerkesztés** opciót.
1. A **Profil tulajdonságai** alatt cserélje le a **Médiakiszolgáló alap URL-címe** tulajdonságot a korábban létrehozott média alap URL-címre.
1. Válassza ki a másik csatornát, az **scXXXXXXXXX** nevűt.
1. A **Profil tulajdonságai** területen kattintson a **Hozzáadás** gombra.
1. A hozzáadott tulajdonság esetében válassza a **Médiakiszolgáló alap URL-címe** lehetőséget tulajdonságkulcsként. A tulajdonságértékként adja meg a korábban létrehozott média alap URL-címét.
1. Válassza a **Mentés** lehetőséget.

## <a name="configure-and-test-the-email-server"></a>E-mail-kiszolgáló konfigurálása és tesztelése

> [!NOTE]
> Az itt megadott SMTP-kiszolgálónak vagy e-mail szolgáltatásnak elérhetőnek kell lennie a környezethez használt Azure-előfizetésből.

1. Bejelentkezés a Commerce központba.
1. A bal oldali menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> E-mail-paraméterek**.
1. Az **SMTP-beállítások** lapon a **Kimenő levelek kiszolgálója** mezőjébe írja be az SMTP-kiszolgáló vagy e-mail-szolgáltatás FQDN-nevét vagy IP-címét.
1. Írja be az **SMTP portszáma** mezőbe a port számát. (Ha nem a Secure Sockets Layer \[SSL\] protokollt használja, az alapértelmezett portszám **25**.)
1. Ha hitelesítés szükséges, írja be az értékeket a **Felhasználónév** és a **Jelszó** mezőkbe.
1. Válassza a **Mentés** lehetőséget.
1. Válassza a **Frissítés** lehetőséget.
1. A **Teszt-e-mail** lapon az **E-mail-szolgáltató** mezőben válassza ki az **SMTP** elemet.
1. A **Címzett** mezőbe írja be azt az e-mail címet, amelyre a teszt-e-mailt kézbesíteni kívánja.
1. Válassza a **Teszt-e-mail küldése** lehetőséget.

## <a name="configure-email-templates"></a>E-mail-sablonok konfigurálása

Az e-mail-sablont minden olyan tranzakciós eseményhez, amelyre e-maileket szeretne küldeni, frissíteni kell egy érvényes feladói e-mail-címmel.

1. Bejelentkezés a Commerce központba.
1. A bal oldali menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> Szervezeti e-mail-sablonok**.
1. Válassza ki a **Lista megjelenítése** lehetőséget.
1. A lista minden sablonja esetén hajtsa végre az alábbi lépéseket:

    1. A **Feladó e-mail címe** mezőbe írja be a feladó e-mail címét.
    1. Nem kötelező: A **Feladó neve** mezőben adja meg a feladó neveként használandó nevet.

1. Válassza a **Mentés** lehetőséget.

## <a name="customize-email-templates"></a>E-mail-sablonok testreszabása

Célszerű lehet testreszabni az e-mail sablonokat, hogy azok különböző képeket használhassanak. Előfordulhat, hogy frissíteni szeretné a sablonokban található hivatkozásokat, hogy a beérkezett üzenetek környezetére indulnak. Ez az eljárás leírja, hogyan lehet letölteni az alapértelmezett sablonokat, illetve hogyan szabhatja testre és frissítheti a sablonokat a rendszerben.

1. A webböngészőben töltse le a bemutató [Microsoft Dynamics 365 Commerce e-mail sablonokhoz használt zip fájlt](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) a helyi számítógépre. Ez a fájl a következő HTML-dokumentumokat tartalmazza:

    - Rendelés megerősítési sablon
    - Ajándékutalvány-sablon kiadása
    - Új rendeléssablon
    - Csomagrendelési sablon
    - Kitárolás rendelési sablon

1. A sablonokat a szöveg- vagy HTML-szerkesztő segítségével szabhatja testre. A támogatott tokenek [listáját a cikk](#supported-tokens-in-the-email-template) későbbi része tartalmazza.
1. Bejelentkezés a Commerce alkalmazásba.
1. A bal oldali menü használatával nyissa meg a **Modulok \> Szervezet felügyelete \> Beállítás \> Szervezeti e-mail-sablonok** elemet.
1. A bal oldali lista kibontásával megjelenítheti az összes sablont.
1. Minden testreszabni kívánt sablonhoz hajtsa végre az alábbi lépéseket:

    1. Válassza ki a sablont a listából.
    1. Az **E-mail-üzenet tartalma** területen válassza ki a megfelelő nyelvi verziót a listából. (Az alapértelmezett nyelv az **en-us**.)
    1. Az **E-mail-üzenet tartalma** alatt válassza a **Szerkesztés** lehetőséget. Megjelenik az **E-mail-sablon feltöltése** ablaktábla.
    1. Válassza a **Tallózás** lehetőséget, és keresse meg azt a HTML-fájlt, amely a testreszabott tartalommal rendelkezik.
    1. Válassza a **Feltöltés** elemet. A sablon fel lesz töltve a rendszerbe, és megjelenik egy előnézet.
    1. Válassza ki az **OK** lehetőséget.
    1. Opcionális: A sablon **Tárgy** tulajdonságának testreszabása.
    1. Válassza a **Mentés** lehetőséget.

### <a name="supported-tokens-in-the-email-template"></a>Az e-mail-sablonban támogatott tokenek

Ezeket a tokeneket az e-mail renderelése során a program lecseréli a vevőkre és a rendelésre vonatkozó tényleges értékekre.

#### <a name="sales-order"></a>Értékesítési rendelés

A következő tokenek érvényesek a teljes értékesítési rendelésre.

| A token neve | Token |
|-------------------|-------|
| Rendelésszám      | %salesid% |
| Vevő neve   | %customername% |
| Szállítási cím  | %deliveryaddress% |
| Számlázási cím   | %customeraddress% |
| Megrendelési dátum        | %shipdate% |
| Szállítási mód     | %modeofdelivery% |
| Kedvezmény          | %discount% |
| Áfa         | %tax% |
| Rendelés összesen       | %total% |

#### <a name="sales-line"></a>Értékesítési sor

A következő tokeneket cseréli ki a rendszer értékekre az egyes termékek esetében.

> [!NOTE]
> Tegye a **Terméklista – kezdés** tokent a HTML-blokk elejére, amely minden termékre megismétlődik, majd a blokk végén helyezze el a **Terméklista – befejezés** tokent.

| A token neve      | Token |
|------------------------|-------|
| Terméklista – kezdés   | \<!--%tablebegin.salesline% --\> |
| Terméklista – befejezés     | \<!--%tableend.salesline%--\> |
| Terméknév           | %lineproductname% |
| Leírás            | %lineproductdescription% |
| Mennyiség               | %linequantity% |
| Sor egységára        | %lineprice% (ellenőrzés) |
| sortétel összege        | %linenetamount% |
| sorkedvezmény          | %linediscount% |
| Szállítási dátum              | %lineshipdate% |
| Beszerzési mód     | %linedeliverymode% |
| szállítási cím       | %linedeliveryaddress% |
| A sor értékesítési egysége | %lineunit% |

## <a name="additional-resources"></a>További erőforrások

[Üzenetkészlet Dynamics 365 Commerce környezetének létesítása](provisioning-guide.md)

[Abox Dynamics 365 Commerce környezet konfigurálása](cpe-post-provisioning.md)

[BoPIS konfigurálásabox Dynamics 365 Commerce környezetben](cpe-bopis.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portál](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce-webhely](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
