
#  `STR` (STRING) METOTLARI  
---
# --- 1. HARF BOYUTU DEĞİŞTİRME METOTLARI ---

`name = "furkan aksoy"`

```Python
Print(name.upper())  # Çıktı : FURKAN AKSOY
# Tüm harfleri BÜYÜK yapar.
# Zaten büyük olan harflere veya harf dışı karakterlere (sayı, sembol) dokunmaz.
```
#upper
```python
print(name.lower())  # Çıktı : furkan aksoy
# Tüm harfleri küçük yapar.
# Zaten küçük olan harflere veya harf dışı karakterlere (sayı, sembol) dokunmaz.
```
#lower
```python
print(name.capitalize())  # Çıktı : Furkan aksoy
# Bir metnin (string) yalnızca ilk harfini büyük harfe, geri kalan tüm harflerini ise **küçük harfe** dönüştürü
```
#capitalize
```python
print(name.title())  # Çıktı : Furkan Aksoy
# bir metindeki (string) her kelimenin ilk harfini büyük harfe, kelimelerin geri kalan harflerini ise küçük harfe dönüştürür.
```
#title
```python
print(name.swapcase())  # Çıktı : FURKAN AKSOY
# Bir metin (string) içerisindeki büyük harfleri küçük harfe, küçük harfleri ise büyük harfe dönüştürür. Harf dışı karakterleri etkilemez.
```
#swapcase
```python
print(name.casefold())  # Çıktı : furkan aksoy
# lower() gibidir ama daha agresiftir; Almanca "ß" harfini "ss" yapmak gibi 
# farklı dillerdeki özel karakterleri de evrensel küçük harfe çevirir.
```
#casefold 

# --- 2. TEMİZLEME VE HİZALAMA METOTLARI ---

```python
ad = "   furkan aksoy   "
print(ad.strip())  # Çıktı : "furkan aksoy" 
# Bir metnin (string) hem başındaki hem de sonundaki boşlukları (veya belirtilen özel karakterleri) temizler. Metnin içindeki, yani kelimelerin arasındaki boşluklara dokunmaz.
```
#strip 
```python
ad = "   furkan aksoy   "
print(ad.lstrip())  # Çıktı :   "furkan aksoy   "  
print(ad.rstrip())  # Çıktı :   "   furkan aksoy"   
# Bir metnin (string) lstrip başındaki boşluğu rstrip sonundaki boşluğu temizler. Metnin içindeki, yani kelimelerin arasındaki boşluklara dokunmaz.
```
#lstrip #rstrip
```python
N = 5  # Toplam karakter uzunluğu (İstediğin sayıyı yazabilirsin)
metin = "42" # Soluna sıfır eklenecek metin

print(metin.zfill(N))  # Çıktı: "00042"
print("5".zfill(3))  # Çıktı : "005"
# Metnin sol tarafını sıfır koyarak N basamağa tamamlar.
# N = Toplam karakter olacak sayı.
```
#zfill
```python
N = 10  # Toplam karakter uzunluğu (İstediğin sayıyı yazabilirsin)
K = "-" # Boşlukları dolduracak karakter

print("test".center(N, "K")) # Çıktı: ---test---
print("metin".center(11, "t")) # Çıktı: tttmetinttt
# Metni N karakterlik alanda ortalar.
# N = Toplam karakter olacak sayı.
# K = Kalanı ne ile dolduracağın normal hartfler yada (/, *, - gibi).
```
#center
```python
print("metin".ljust(10, "-"))  # Çıktı: "metin-----"
# Metni belirtilen uzunluğa (10) tamamlayacak şekilde SOLA yaslar.
# Sağda kalan boşlukları belirtilen karakterle (-) doldurur.

print("metin".rjust(10, "-"))  # Çıktı: "-----metin"
# Metni belirtilen uzunluğa (10) tamamlayacak şekilde SAĞA yaslar.
# Solda kalan boşlukları belirtilen karakterle (-) doldurur.
```
#ljust #rjust
# --- 3. ARAMA VE SAYMA METOTLARI ---

```python
N = "u"  # Sayılmasını istediğin harf veya kelime
metin = "Umut"

print(metin.count(N))  # Çıktı: 1
# Belirtilen ifadenin metin içinde kaç kez geçtiğini sayar.
# Metin içindeki sayısal karakterleri de başarıyla sayar.
# Büyük ve küçük harfler birbirinden farklıdır (u ve U farkı gibi).
# N = Sayılacak olan karakter veya kelime.
```
#count
```python
N = "u"  # İki metotta da arama yönü farkını net görmek için "u" harfini seçtik
metin = "python kursu"

# --- find() -> Soldan (Baştan) Sağa arar ---
print(metin.find(N))     # Çıktı: 6  (Soldan sayınca ilk karşılaştığı "u" harfi 6. sıradadır)
print(metin.find("xyz")) # Çıktı: -1 (Metinde bulunamadığı için -1 verir)

# --- rfind() -> Sağdan (Sondan) Sola arar ---
print(metin.rfind(N))     # Çıktı: 11 (Sağdan saymaya başlar, karşılaştığı ilk "u" en sondaki 11. sıradadır)
print(metin.rfind("xyz")) # Çıktı: -1  (Metinde bulunamadığı için -1 verir)

# find(): Aranan ifadenin metindeki BAŞTAN başlayarak ilk karşılaştığı yerin indeksini (konumunu) verir.
# rfind(): Aranan ifadenin metindeki SONDAN başlayarak ilk karşılaştığı yerin indeksini (konumunu) verir.
# Büyük/küçük harfe duyarlıdırlar. Bulamazlarsa ikisi de -1 sonucunu döndürür.
# N = Konumu aranacak olan karakter veya kelime.
```
#find #rfind
```python
N = "u"  # İki metotta da arama yönü farkını net görmek için "u" harfini seçtik
metin = "python kursu"

# --- index() -> Soldan (Baştan) Sağa arar ---
print(metin.index(N))     # Çıktı: 6  (Soldan sayınca ilk karşılaştığı "u" harfi 6. sıradadır)
# print(metin.index("xyz")) # Çıktı: ValueError (Bulamazsa hata verir ve kodu durdurur!)

# --- rindex() -> Sağdan (Sondan) Sola arar ---
print(metin.rindex(N))     # Çıktı: 11 (Sağdan saymaya başlar, karşılaştığı ilk "u" en sondaki 11. sıradadır)
# print(metin.rindex("xyz")) # Çıktı: ValueError (Bulamazsa hata verir ve kodu durdurur!)

# index(): Aranan ifadenin metindeki BAŞTAN başlayarak ilk karşılaştığı yerin indeksini (konumunu) verir.
# rindex(): Aranan ifadenin metindeki SONDAN başlayarak ilk karşılaştığı yerin indeksini (konumunu) verir.
# Büyük/küçük harfe duyarlıdırlar. Bulamazlarsa ikisi de hata (ValueError) fırlatır ve kodu durdurur!
# N = Konumu aranacak olan karakter veya kelime.
```
#index






















print(metin.startswith("  "))# Metin iki boşlukla mı başlıyor? -> True/False
print(metin.endswith(".png"))# Metin ".png" ile mi bitiyor? -> True/False

# --- 4. DEĞİŞTİRME, PARÇALAMA VE BİRLEŞTİRME ---
print(metin.replace("2026", "2027")) # "2026" gördüğü yere "2027" yazar
print("elma,armut,muz".split(","))    # Virgüllerden bölüp LISTE yapar -> ['elma', 'armut', 'muz']
print("-".join(["a", "b", "c"]))       # Listedeki elemanları araya tire koyarak birleştirir -> "a-b-c"

# --- 5. KARAKTER İÇERİK KONTROLLERİ (True / False) ---
print("python".isalpha())   # Hepsi harf mi? (Boşluk veya sayı varsa False)
print("12345".isdigit())    # Hepsi rakam mı?
print("py30".isalnum())     # Hepsi harf ve/veya rakam mı? (Özel karakter yoksa True)
print("   ".isspace())      # Sadece boşluklardan mı oluşuyor?
print("abc".islower())      # Hepsi küçük harf mi?
print("ABC".isupper())      # Hepsi büyük harf mi?

# ==============================================================================
# NOT: Stringler "immutable" (değiştirilemez) olduğu için bu metotlar 
# orijinal 'metin' değişkenini bozmaz, hep yeni bir çıktı üretir.
# ==============================================================================