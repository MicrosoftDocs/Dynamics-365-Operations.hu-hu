## <a name="product-categories-to-msdyn_productcategories"></a>Az msdyn_productcategories termékkategóriái

Ez a sablon szinkronizálja az adatokat az Finance and Operations alkalmazások és a(z) Common Data Serviceközött.

Finance and Operations mező | Térkép típusa | Egyéb Dynamics 365 mező | Alapértelmezett érték
---|---|---|---
TERMÉKKATEGÓRIAHIERARCHIÁJÁNAKANEVE | = | msdyn_hierarchy.msdyn_name | 
AKATEGÓRIAMEGÖRÖKLIASZÜLŐTERMÉKATTRIBÚTUMAIT | >< | msdyn_isinheritingparentproductattributes | 
TERMÉKKATEGÓRIANEVE | = | msdyn_projectcategoryname | 
KÉZZELFOGHATÓTERMÉK | >< | msdyn_istangibleproduct | 
AKATEGÓRIAMEGÖRÖKLIASZÜLŐKATEGÓRIAATTRIBÚTUMAIT | >< | msdyn_isinheritingparentcategoryattributes | 
KATEGÓRIAKÓD | = | msdyn_code | 
KATEGÓRIALEÍRÁSA | = | msdyn_description | 
KATEGÓRIAKULCSSZAVAK | = | msdyn_keywords | 
KATEGÓRIANÉV | = | msdyn_name | 
MEGJEGYEZHETŐKATEGÓRIANÉV | = | msdyn_friendlycategoryname | 
SZÜLŐTERMÉKKATEGÓRIANEVE | = | msdyn_parentproductcategory.msdyn_name | 
TERMÉKKATEGÓRIAHIERARCHIÁJÁNAKANEVE | >> | msdyn_parentproductcategory.msdyn_hierarchy.msdyn_name | 
