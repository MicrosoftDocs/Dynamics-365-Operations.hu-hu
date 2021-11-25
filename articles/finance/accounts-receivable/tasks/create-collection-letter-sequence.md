---
title: Fizetésifelszólítás-sorozat létrehozása
description: Ezzel az eljárással létrehozhat egy beszedőlevél-sorozatot.
author: abruer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CollectionLetterCourse
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bfc5bd0b1228ef28631da8746b2eb60e4cf488c1
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/05/2021
ms.locfileid: "7753586"
---
# <a name="create-a-collection-letter-sequence"></a>Fizetésifelszólítás-sorozat létrehozása

[!include [banner](../../includes/banner.md)]

Ezzel az eljárással létrehozhat egy beszedőlevél-sorozatot. Ez a feladat az USMF bemutatócéget használja.

1. A Navigációs ablaktáblán ugorjon a **Modulok > Követelések és beszedések > Beállítás > Fizetésifelszólítás-sorozat beállítása** lehetőségre.
2. Kattintson az **Új** elemre.
3. A **fizetésifelszólítás-sorozat** mezőben adjon meg egy sorozatazonosítót, amely a sorozatot jelöli majd. Ezt akkor használja majd, ha feladási profilt állít be.
4. Írjon egy értéket a **Leírás** mezőbe.  A fizetési feltétel opcionális. Ha itt megad egy értéket, a fizetési felszólítási díj számlája ezeket a fizetési feltételeket használja a vevőhöz tárolt fizetési feltételek helyett.  
5. A **Fizetési felszólítás kódmezőjében** válassza ki az első elküldeni kívánt fizetési felszólítás kódját. A számlán szereplő határidő, a Napok mezőben megadott türelmi időszak és az ebben a sorban megadott értékek és egyéb információk alapján automatikusan létrehozza az első fizetési felszólítást a rendszer.  
6. Írjon egy értéket a **Leírás** mezőbe. A díj pénzneme alapértelmezetten a vevő pénzneme. Ez a pénznemkód eltérhet a számla pénznemétől.  
7. A sorozatban következő fizetési felszólítás hozzáadásához kattintson a **Hozzáadás** lehetőségre. Az első fizetési felszólítás sok esetben csak figyelmeztetés. Szükség esetén díjakat is hozzáadhat.  
8. A fizetési felszólítás kódmezőjében válassza ki a soron következő fizetési felszólítást.
9. Írjon egy értéket a **Leírás** mezőbe.
10. A **Fő számla mezőben** válassza ki a díjakhoz használni kívánt bevételi számlát.
11. Adja meg a fizetési felszólítás feladásakor felszámolt díjat.
12. A **Cikkáfacsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához. Válasszon a cikkhez áfacsoportot, ha a díj áfaköteles.  
13. A listában kattintson a kijelölt sorban lévő hivatkozásra.
14. A **Minimális késedelmes egyenleg** mezőbe írja be azt a minimális késedelmes egyenleget, amely a fizetési felszólítás elküldése előtt szükséges.
15. A **Napok** mezőben Adja meg a türelmi napok számát. Ez az esedékességi határidő utáni napok száma, amíg fizetési felszólítás hozható létre. A számításhoz használt határidő a fizetési felszólítás fizetésifelszólítás-sorozatban lévő helyzetétől függ:
    - A türelmi időszak az első fizetési felszólításhoz a számla esedékességéhez igazodik.
    - A 2. fizetési felszólítás türelmi időszaka az előző fizetési felszólítás feladásától és nyomtatásától függ, ami a Fizetési felszólítás kódjának frissítése mezőtől függ, a Kintlévőségek paraméterei oldalon.  
16. A sorozatban utolsó fizetési felszólítás hozzáadásához kattintson a **Hozzáadás** lehetőségre. Az egyes fizetésifelszólítás-sorozatokhoz max. öt fizetési felszólítási kódot lehet létrehozni.  
17. A **Fizetési felszólítás kódja** mezőben válassza ki a soron következő fizetési felszólítást.
18. Írjon egy értéket a **Leírás** mezőbe.
19. A **Fő számla** mezőben adja meg a kívánt értékeket.
20. A **Díj pénzneme** mezőben adjon meg egy számot.
21. A **Cikkáfacsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
22. A listában kattintson a kijelölt sorban lévő hivatkozásra.
23. Az **Egyenleg esedékessé válásának minimuma** mezőben adjon meg egy számot.
24. A **Napok** mezőbe írjon be egy számot.
25. A **Blokk** jelölőnégyzetet bejelölve leállíthatja a további szállításokat és további számlák kiállítását a vevőnek. A számla zárolásának feloldásához válassza a **Nem** szót a Vevők oldal Számlázás és szállítás felfüggesztve mezőjében.  
26. Bontsa ki a **Jegyzet** gyorslapot.
27. Írja be a fizetési felszólításon megjelentetni kívánt szöveget az adott fizetési felszólítási kód esetén. Ezt a szöveget több nyelvre lefordíthatja a Fordítás menüben a megjegyzés doboz felett.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
