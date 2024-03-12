[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YusufAltuntas/numpy-tutorial/blob/master/numpy-tutorial.ipynb)
![numpy icon](https://miro.medium.com/v2/resize:fit:720/format:webp/1*OUXGr3W72lDG0gSy88_kow.png)

## **1) Temel Bilgiler:**

### [**1.1 Numpy Nedir?**](#11-numpy-nedir)
   - Numpy'nin temel amacı
   - Neden numpy kullanmalıyız?
   - Numpy'nin Özellikleri
   - Python listeleri ile numpy dizileri arasındaki farklar

### [**1.2 Numpy Dizileri (Arrays)**](#12-numpy-dizileri-arrays)
   - [Numpy Arrayleri Nedir?](#121-numpy-array-nedir)
   - [Array Oluşturma](#122-array-oluşturma)
      - [np.zeros(), np.ones(), np.empty() vs.](#1221-npzeros-npones-npempty)
      - [np.arange(), np.linspace()](#1222-nparange-nplinspace)
      - [Random sayı üretimi: np.random.rand(), np.random.randn(), vs.](#1223-random-sayı-üretimi-nprandomrand-nprandomrandn)
   - [Array Özellikleri: Şekil, Boyut](#123-array-özellikleri-şekil-boyut)
   - [Dizilerin Veri Tipleri](#124-dizilerin-veri-tipleri)
   - [Dizilerin İndekslenmesi ve Dilimlenmesi](#125-dizilerin-i̇ndekslenmesi-ve-dilimlenmesi)

--- 


## **2) Temel İşlemler:**

### [**2.1 Dizi İşlemleri:**](#21-dizi-i̇şlemleri)
   - [Dizi Elemanlarına Erişim](#211-dizi-elemanlarına-erişim)
      - [Tek Bir Elemana Erişim](#2111-tek-bir-elemana-erişim)
      - [Dilimleme İle Erişim](#2112-dilimleme-i̇le-erişim)
      - [Koşullu İndeksleme](#2113-koşullu-i̇ndeksleme)
      - [Çok Boyutlu Dizilerde Erişim](#2114-çok-boyutlu-dizilerde-erişim)

   - [Aritmetik İşlemler](#212-aritmetik-i̇şlemler)
      - [Temel Aritmetik İşlemler](#2121-temel-aritmetik-i̇şlemler)
      - [Üstel ve Logaritmik İşlemler](#2122-üstel-ve-logaritmik-i̇şlemler)
      - [İleri Düzey İşlemler](#2123-i̇leri-düzey-i̇şlemler)

   - [Rastgele Sayılar Üretme](#213-rastgele-sayılar-üretme)
      - [np.random.rand()](#2131-nprandomrand)
      - [seed() Fonksiyonu](#2132-seed-fonksiyonu)
      - [np.random.randint()](#2133-nprandomrandint)
      - [np.random.randn()](#2134-nprandomrandn)
      - [np.random.choice()](#2135-nprandomchoice)

### [**2.2 Array Şekil Değiştirme**](#22-array-şekil-değiştirme)
   - [Dizinin Şeklini Değiştirme](#221-dizinin-şeklini-değiştirme)
      - [`reshape()` Fonksiyonu](#2211-reshape-fonksiyonu)
      - [`resize()` Fonksiyonu](#2212-resize-fonksiyonu)
      - [`reshape()` ve `-1` Kullanımı](#2213-reshape-ve--1-kullanımı)
      - [Düzleştirme: flatten() Fonksiyonu](#2214-düzleştirme-flatten-fonksiyonu)
      - [`ravel()` Fonksiyonu](#2215-ravel-fonksiyonu)

   - [Dizileri Birleştirme ve Ayırma](#222-dizileri-birleştirme-ve-ayırma)
      - [`concatenate()` Fonksiyonu](#2221-concatenate-fonksiyonu)
      - [`stack()` Fonksiyonu](#2222-stack-fonksiyonu)
      - [`vstack()` ve `hstack()` Fonksiyonları](#2223-vstack-ve-hstack-fonksiyonları)
      - [`split()` Fonksiyonu](#2224-split-fonksiyonu)
      - [`vsplit()` ve `hsplit()` Fonksiyonları](#2225-vsplit-ve-hsplit-fonksiyonları)


### [**2.3 Veri Tipi Dönüşümleri**](#23-veri-tipi-dönüşümleri)
   - [astype() Fonksiyonu](#231-astype-fonksiyonu)
   - [asarray() Fonksiyonu](#232-asarray-fonksiyonu)
   - [Veri Tipi Sınırlamaları ve İşlem Önerileri](#233-veri-tipi-sınırlamaları-ve-i̇şlem-önerileri)

### [**2.4 Fancy Indexing:**](#24-fancy-indexing)
   - [Tek Boyutlu Fancy Indexing](#241-tek-boyutlu-fancy-indexing)
   - [İki Boyutlu Fancy Indexing](#242-i̇ki-boyutlu-fancy-indexing)
   - [Maskelerle Indexleme](#243-maskelerle-indexleme)
      - [Boolean Maskelerle Indexleme](#2431-boolean-maskelerle-indexleme)
      - [Koşul İfadeleri ile Indexleme](#2432-koşul-i̇fadeleri-ile-indexleme)

### [**2.5 Array Operasyonları:**](#25-array-operasyonları)
   - [Broadcasting (Yayılma)](#251-broadcasting-yayılma)
      - [Yayılma Kuralları](#2511-broadcasting-kuralları)
      - [Örneklerle Yayılma Kullanımı](#2512-örneklerle-yayılma-kullanımı)
   - [Dizi Yineleme (Repeating)](#252-dizi-yineleme-repeating)
   - [İç Çarpım (dot product)](#253-i̇ç-çarpım-dot-product)
   - [İşlem fonksiyonları (np.sum(), np.prod(), np.mean() vs.)](#254-i̇şlem-fonksiyonları-npsum-npprod-npmean-vs)

---

## [**3. Lineer Cebir İşlemleri**](#3-lineer-cebir-i̇şlemleri)
   - [Matris çarpımı](#31-matris-çarpımı)
   - [Determinant ve ters matris hesaplama](#32-determinant-ve-ters-matris-hesaplama)


## [**4. Universal Functions (ufuncs):**](#4-universal-functions-ufuncs)

---

# **Temel Bilgiler**

## **1.1 Numpy Nedir?**

Numpy, Python programlama dili için temel bir kütüphanedir ve bilimsel hesaplama ve veri işleme için kullanılır. Numpy'nin temel amacı, Python'da veri işlemesi ve hesaplamaları yapmak için hızlı ve etkili bir şekilde çalışabilecek yüksek performanslı çok boyutlu diziler ve matematiksel işlevler sunmaktır.

### **Neden Numpy Kullanmalıyız?**

Numpy'nin kullanılmasının bazı avantajları şunlardır:
- **Hızlı ve Verimli İşlemler:** Numpy, C ve Fortran dilinde yazılmış alt seviye optimizasyonlar kullanır, bu da Python'da yavaş olan bazı işlemleri hızlandırır.
- **Diziler Üzerinde Hızlı İşlemler:** Numpy dizileri, Python listelerine göre daha hızlı ve verimli işlemler yapmak için optimize edilmiştir.
- **Geniş Fonksiyonellik:** Numpy, matematiksel işlevler, rastgele sayı üretimi, lineer cebir işlemleri gibi birçok faydalı fonksiyon ve işlev içerir.
- **Veri Analizi ve Bilimsel Hesaplama:** Numpy, veri analizi, bilimsel hesaplama, simülasyonlar ve modeller gibi çeşitli alanlarda yaygın olarak kullanılır.

### **Numpy'nin Özellikleri**

Numpy'nin bazı temel özellikleri şunlardır:
- **Çok Boyutlu Diziler (Arrays):** Numpy, çok boyutlu dizileri destekler. Bu, tek boyutlu vektörlerden çok boyutlu matrislere kadar geniş bir veri yelpazesini kapsar.
- **Matematiksel İşlevler:** Numpy, temel matematiksel işlevler (sin, cos, exp vb.) ve işlemler (toplama, çıkarma, çarpma, bölme vb.) için fonksiyonlar içerir.
- **Yüksek Performanslı Hesaplama:** Numpy, vektörize edilmiş işlemler ve alt seviye optimizasyonlar kullanarak yüksek performanslı hesaplamalar sağlar.
- **Geniş Kullanım Alanı:** Numpy, veri analizi, bilimsel hesaplama, makine öğrenmesi, görüntü işleme gibi birçok alanda kullanılır.

### **Python Listeleri ile Numpy Dizileri Arasındaki Farklar**

Numpy dizileri ile Python listeleri arasındaki temel farklar şunlardır:
1. **Performans:** Numpy dizileri, Python listelerine göre daha hızlı ve verimli işlemler yapar. Bu, özellikle büyük veri kümeleri üzerinde çalışırken belirgin hale gelir.
2. **Veri Tipi ve Boyut Kontrolü:** Numpy dizileri, elemanları aynı veri tipinde tutar ve sabit bir boyuta sahiptir. Bu, veri kümeleri üzerinde homojen işlemler yapmayı kolaylaştırır.
3. **Matematiksel İşlemler:** Numpy dizileri, matematiksel işlemler için optimize edilmiş vektörize edilmiş işlemleri destekler. Bu, Python listelerinden daha hızlı ve daha kolay matematiksel işlemler yapmayı sağlar.
4. **Bellek Yönetimi:** Numpy dizileri, veriyi daha etkin bir şekilde bellekte depolar ve işler. Bu, bellek kullanımını optimize eder ve verimliliği artırır.


| Numpy Dizileri                             | Python Listeleri                           |
|--------------------------------------------|--------------------------------------------|
| Numpy dizileri aynı türde verileri içerir. | Python listeleri farklı türde verileri içerebilir. |
| Numpy dizileri boyutları sabittir.        | Python listeleri dinamik boyutlara sahiptir. |
| Numpy dizilerinde vektörleştirilmiş işlemler yapılabilir, bu da performansı artırır. | Python listelerinde döngüler kullanılarak işlemler yapılır, bu performansı düşürebilir. |

---

## **1.2 Numpy Dizileri (Arrays)**

Numpy, Python'da bilimsel hesaplamalar yapmak için kullanılan temel bir kütüphanedir. En önemli özelliklerinden biri, çok boyutlu (çok boyutlu) dizilerle çalışabilme yeteneğidir. Bu çok boyutlu dizilere "Numpy array" denir.

---

### **1.2.1 Numpy Array Nedir?**

Numpy array, homojen veri tiplerinden oluşan bir grid yapısıdır. Bir numpy array, aynı türde veriler içerir ve boyutları sabittir. Numpy array'leri, Python listelerine benzerdir ancak daha etkin ve hızlıdır.

#### **Numpy Array Özellikleri**

1. **Homojen Veri Tipi:**
   - Numpy array'leri, aynı türde verileri içerir. Bu, veri işleme ve matematiksel operasyonlar için çok önemlidir çünkü her eleman aynı veri türüne sahiptir.

2. **Sabit Boyut:**
   - Numpy array'lerinin boyutları oluşturulduktan sonra değiştirilemez. Bu, bellek kullanımını optimize eder ve hızlı işlemler sağlar.

3. **Hızlı ve Verimli:**
   - Numpy, C altında derlenmiş bir kütüphanedir, bu da işlemlerin hızlı ve verimli bir şekilde yapılmasını sağlar. Büyük veri kümeleriyle çalışırken performans avantajı sağlar.

4. **Çok Boyutlu Yetenek:**
   - Numpy array'leri, tek boyutlu, iki boyutlu ve daha fazla boyutta olabilir. Bu, matematiksel ve bilimsel hesaplamalarda çok yönlü kullanım sağlar.

---

#### **Python Listeleri ile Numpy Arrayleri Arasındaki Farklar**

Numpy array'leri ve Python listeleri arasındaki ana farklar şunlardır:

- **Performans:**
   - Numpy array'leri, vektörleştirilmiş operasyonlar ve optimize edilmiş bellek kullanımı sayesinde Python listelerinden daha hızlıdır.
   
- **Veri Tipi Kontrolü:**
   - Numpy array'leri homojen veri tipleri içerirken, Python listeleri heterojen veri tipleri içerebilir.
   
- **Boyut Değiştirme:**
   - Numpy array'lerinin boyutları oluşturulduktan sonra değiştirilemezken, Python listelerinin boyutu dinamik olarak değiştirilebilir.

- **Matematiksel İşlemler:**
   - Numpy array'leri, matematiksel işlemleri vektörleştirme yeteneği ile desteklerken, Python listeleri bunu doğrudan desteklemez.

Bu farklar, Numpy'nin Python listelerine tercih edilmesinin temel nedenlerindendir. Numpy array'leri, bilimsel hesaplamalar, veri analizi ve makine öğrenimi gibi uygulamalarda yaygın olarak kullanılmaktadır.


---
### **1.2.2 Array Oluşturma**

Numpy kütüphanesi, çeşitli yöntemlerle array oluşturmayı sağlar. Bu yöntemler, farklı ihtiyaçlara göre farklı türde arrayler oluşturmanıza olanak tanır.

#### **1.2.2.1 `np.zeros()`, `np.ones()`, `np.empty()`**

Bu fonksiyonlar, belirli bir şekilde sıfırlar, birler veya boş değerler içeren arrayler oluşturur. Temel kullanımı aşağıdaki gibidir:

- `np.zeros(shape)`: Belirtilen boyutta sıfırlardan oluşan bir array oluşturur.
- `np.ones(shape)`: Belirtilen boyutta birlerden oluşan bir array oluşturur.
- `np.empty(shape)`: Belirtilen boyutta boş değerler içeren bir array oluşturur. Bu array'in değerleri, bellekteki mevcut duruma bağlı olarak değişkenlik gösterebilir.
---


```python
import numpy as np

zeros_array = np.zeros((2, 3))  # 2x3 boyutunda sıfırlardan oluşan array
print(zeros_array, "\n")
# Çıktı:
# [[0. 0. 0.]
#  [0. 0. 0.]]

ones_array = np.ones((3, 2))  # 3x2 boyutunda birlerden oluşan array
print(ones_array,"\n")
# Çıktı:
# [[1. 1.]
#  [1. 1.]
#  [1. 1.]]

empty_array = np.empty((2, 2))  # 2x2 boyutunda boş değerler içeren array
print(empty_array)
# Çıktı:
# [[4.67296746e-307 1.69121096e-306]
#  [8.34441742e-308 1.24611470e-306]]
```

    [[0. 0. 0.]
     [0. 0. 0.]] 
    
    [[1. 1.]
     [1. 1.]
     [1. 1.]] 
    
    [[2.  1. ]
     [1.5 0.5]]
    


---

#### **1.2.2.2 `np.arange()`, `np.linspace()`**

Bu fonksiyonlar, belirli bir aralıktaki sayılarla dolu arrayler oluşturur.

- `np.arange(start, stop, step)`: Belirli bir aralıktaki sayıları belirtilen adımlarla içeren bir array oluşturur.
- `np.linspace(start, stop, num)`: Belirli bir aralıktaki belirli sayıda eşit aralıklı sayıları içeren bir array oluşturur.

---


```python
import numpy as np

range_array = np.arange(0, 10, 2)  # 0'dan 10'a kadar 2'şer artan sayılar
print(range_array, "\n")
# Çıktı: [0 2 4 6 8]

linspace_array = np.linspace(0, 10, 5)  # 0'dan 10'a kadar 5 eşit aralıklı sayılar
print(linspace_array)
# Çıktı: [ 0.   2.5  5.   7.5 10. ]
```

    [0 2 4 6 8] 
    
    [ 0.   2.5  5.   7.5 10. ]
    


---
#### **1.2.2.3 Random Sayı Üretimi: `np.random.rand()`, `np.random.randn()`**

Bu fonksiyonlar, belirli bir boyutta rastgele sayılar içeren arrayler oluşturur.

- `np.random.rand(d0, d1, ..., dn)`: 0 ile 1 arasında uniform dağılımlı rastgele sayılar içeren bir array oluşturur.
- `np.random.randn(d0, d1, ..., dn)`: Ortalaması 0 ve standart sapması 1 olan normal dağılımlı rastgele sayılar içeren bir array oluşturur.

---


```python
import numpy as np

random_array_uniform = np.random.rand(2, 2)  # 2x2 boyutunda uniform dağılımlı rastgele sayılar
print(random_array_uniform,"\n")


random_array_normal = np.random.randn(2, 2)  # 2x2 boyutunda normal dağılımlı rastgele sayılar
print(random_array_normal)
```

    [[0.66083539 0.07326587]
     [0.11192756 0.91149177]] 
    
    [[ 0.14298326  1.20668909]
     [-0.69041712  0.67672093]]
    


---
### **1.2.3 Array Özellikleri: Şekil, Boyut**

Numpy array'lerinin şekli ve boyutu, array'in yapısını ve içerdiği veri miktarını tanımlar. Bu özellikler, array üzerinde işlem yaparken ve verileri manipüle ederken oldukça önemlidir.

---
#### **Array Şekli (Shape)**

Bir array'in şekli, her boyuttaki eleman sayısını içeren bir tuple'dır. Örneğin, bir 2x3 boyutundaki array'in şekli `(2, 3)` şeklinde ifade edilir.

---
#### **Array Boyutu (Dimension)**

Bir array'in boyutu, içerdiği boyut sayısını ifade eder. Örneğin, 2x3 boyutundaki bir array 2 boyutlu (2D) olarak kabul edilir.

---


```python
import numpy as np

# 2x3 boyutunda bir array oluşturalım
my_array = np.array([[1, 2, 3],
                    [4, 5, 6]])

print("Array Şekli (Shape):", my_array.shape)  # Çıktı: (2, 3)
print("Array Boyutu (Dimension):", my_array.ndim)  # Çıktı: 2
```

    Array Şekli (Shape): (2, 3)
    Array Boyutu (Dimension): 2
    

#### **Reshaping (Yeniden Şekillendirme)**

Numpy, `reshape()` fonksiyonu aracılığıyla mevcut bir array'in şeklini değiştirmenize olanak tanır. Bu işlem, array'in boyutunu değiştirmez, sadece şeklini yeniden düzenler.


```python
import numpy as np

# 2x3 boyutunda bir array oluşturalım
my_array = np.array([[1, 2, 3],
                    [4, 5, 6]])

# Array'in şeklini (2, 3)ten (3, 2)'ye çevirelim
reshaped_array = my_array.reshape((3, 2))

print("Yeniden Şekillendirilmiş Array:")
print(reshaped_array)
```

    Yeniden Şekillendirilmiş Array:
    [[1 2]
     [3 4]
     [5 6]]
    

* Yukarıdaki örnekte, `reshape()` fonksiyonu kullanılarak `my_array` adlı array'in şekli (2, 3)'ten (3, 2)'ye çevrildi.

#### **Array'in Boyutunu Değiştirme**

Numpy, `reshape()` fonksiyonu dışında array'in boyutunu değiştiren `resize()` fonksiyonunu da sağlar. Bu fonksiyon, mevcut array'i değiştirir ve istenen boyuta uyacak şekilde genişletir veya kısaltır.


```python
import numpy as np

# 2x3 boyutunda bir array oluşturalım
my_array = np.array([[1, 2, 3],
                    [4, 5, 6]])

# Array'in boyutunu (3, 4)'e değiştirelim
resized_array = np.resize(my_array, (3, 4))

print("Yeniden Boyutlandırılmış Array:")
print(resized_array)
```

    Yeniden Boyutlandırılmış Array:
    [[1 2 3 4]
     [5 6 1 2]
     [3 4 5 6]]
    

* Yukarıdaki örnekte, `resize()` fonksiyonu kullanılarak `my_array` adlı array'in boyutu (3, 4)'e değiştirildi.

### **1.2.4 Dizilerin Veri Tipleri**

Numpy dizileri, homojen veri tipleriyle (aynı tipte verileri içerir) çalışır. Bu, her bir öğenin aynı veri tipine sahip olması gerektiği anlamına gelir. Numpy, farklı türlerde veri tiplerini destekler ve her bir veri tipi farklı boyut ve işlemlere izin verir.

#### **Numpy Veri Tipleri:**

1. **int**: Tam sayılar.
2. **float**: Ondalık sayılar.
3. **complex**: Karmaşık sayılar.
4. **bool**: Mantıksal (Boolean) değerler.
5. **string**: Karakter dizileri.
6. **object**: Python nesneleri için genel veri tipi.
7. **datetime**: Tarih ve saat veri tipleri.

#### **Veri Tipi Belirtme**

Numpy, bir dizi oluştururken veya bir diziye dönüştürürken veri tipini belirlemenize izin verir. Bu, bellek kullanımını optimize etmenize ve beklenmeyen sonuçlardan kaçınmanıza olanak tanır.


```python
import numpy as np

# Diziyi oluştururken veri tipini belirleme
my_array = np.array([1, 2, 3], dtype=float)
print("Float tipinde dizi:", my_array)

# Dönüştürme işlemi sırasında veri tipini belirleme
converted_array = np.array([1, 2, 3], dtype=float)
print("Dönüştürülen dizi:", converted_array)
```

    Float tipinde dizi: [1. 2. 3.]
    Dönüştürülen dizi: [1. 2. 3.]
    



### **1.2.5 Dizilerin İndekslenmesi ve Dilimlenmesi**

Numpy dizileri, Python listelerine benzer şekilde indekslenir ve dilimlenir. Bu işlemler, belirli bir elemana erişmek veya belirli bir alt küme oluşturmak için kullanılır. Numpy, çok boyutlu dizilerle çalışırken bu işlemleri daha da güçlendirir.

#### **1.2.5.1 İndeksleme**

Numpy dizileri, 0'dan başlayarak indekslenir. Bir dizinin belirli bir elemanına erişmek için indeks numarasını kullanırız.


```python
import numpy as np

# 1D dizinin oluşturulması
arr = np.array([1, 2, 3, 4, 5])

# İndeksleme
print(arr[0])  # Çıktı: 1
print(arr[2])  # Çıktı: 3
```

    1
    3
    

#### **1.2.5.2 Dilimleme (Slicing)**

Dilimleme, bir dizinin belirli bir alt kümesini seçmek için kullanılır. Numpy dizilerinde dilimleme, Python listelerinden çok benzer şekilde çalışır. `[start:stop:step]` formülü kullanılır. Herhangi bir parametre belirtilmezse, varsayılan değerler kullanılır (başlangıç: 0, durdurma: son, adım: 1).


```python
import numpy as np

# 1D dizinin oluşturulması
arr = np.array([1, 2, 3, 4, 5])

# Dilimleme
print(arr[1:4])  # Çıktı: [2 3 4]
print(arr[:3])   # Çıktı: [1 2 3]
print(arr[::2])  # Çıktı: [1 3 5]
```

    [2 3 4]
    [1 2 3]
    [1 3 5]
    

#### **1.2.5.3 Çok Boyutlu Dizilerde İndeksleme ve Dilimleme**

Çok boyutlu dizilerde, her boyuta ait bir indeks veya dilimleme kullanabiliriz. Her boyut için indeksleme ve dilimleme işlemleri virgülle ayrılır.


```python
import numpy as np

# 2D dizinin oluşturulması
arr = np.array([[1, 2, 3],
                [4, 5, 6],
                [7, 8, 9]])

# İndeksleme ve Dilimleme
print(arr[0, 0])     # Çıktı: 1 (1. satırın 1. sütunu)
print(arr[1, 2])     # Çıktı: 6 (2. satırın 3. sütunu)
print(arr[:2, 1:])   # Çıktı: [[2 3]
                            #   [5 6]]
```

    1
    6
    [[2 3]
     [5 6]]
    

# **Temel İşlemler**

## **2.1 Dizi İşlemleri**

### **2.1.1 Dizi Elemanlarına Erişim**

Numpy dizilerinde, belirli elemanlara erişmek için çeşitli yöntemler bulunmaktadır. Bu yöntemler, tek bir elemana, belirli bir alt kümeye veya belirli bir koşulu sağlayan elemanlara erişmek için kullanılır. İşte farklı yöntemler ve örnekler:

#### **2.1.1.1 Tek Bir Elemana Erişim**

Tek bir elemana erişmek için, dizinin indeksini belirtiriz. Numpy dizileri, 0'dan başlayarak indekslenir.


```python
import numpy as np

# 1D dizi oluşturma
arr = np.array([1, 2, 3, 4, 5])

# Birinci elemana erişim
print("Birinci eleman:", arr[0])  # Çıktı: 1

# Beşinci elemana erişim
print("Beşinci eleman:", arr[4])  # Çıktı: 5
```

    Birinci eleman: 1
    Beşinci eleman: 5
    

---
#### **2.1.1.2 Dilimleme İle Erişim**

Dilimleme, belirli bir alt kümenin seçilmesini sağlar. Başlangıç ve bitiş indeksleriyle belirtilen dilimler kullanılarak erişim yapılır.

---


```python
import numpy as np

# 1D dizi oluşturma
arr = np.array([1, 2, 3, 4, 5])

# İkinci ve üçüncü elemanlara erişim
print("İkinci ve üçüncü elemanlar:", arr[1:3])  # Çıktı: [2 3]

# Tüm elemanlara erişim
print("Tüm elemanlar:", arr[:])  # Çıktı: [1 2 3 4 5]
```

    İkinci ve üçüncü elemanlar: [2 3]
    Tüm elemanlar: [1 2 3 4 5]
    

---
#### **2.1.1.3 Koşullu İndeksleme**

Koşullu indeksleme, belirli bir koşulu sağlayan elemanları seçmek için kullanılır.


---


```python
import numpy as np

# 1D dizi oluşturma
arr = np.array([1, 2, 3, 4, 5])

# 3'ten büyük elemanlara erişim
print("3'ten büyük elemanlar:", arr[arr > 3])  # Çıktı: [4 5]
```

    3'ten büyük elemanlar: [4 5]
    

#### **2.1.1.4 Çok Boyutlu Dizilerde Erişim**

Çok boyutlu dizilerde, her boyuta ait bir indeks veya dilimleme kullanılır.


```python
import numpy as np

# 2D dizi oluşturma
arr = np.array([[1, 2, 3],
                [4, 5, 6],
                [7, 8, 9]])

# İkinci satırın üçüncü elemanına erişim
print("İkinci satırın üçüncü elemanı:", arr[1, 2])  # Çıktı: 6

# İlk iki satırın tüm elemanlarına erişim
print("İlk iki satırın tüm elemanları:", arr[:2, :])  # Çıktı: [[1 2 3]
                                                        #        [4 5 6]]
```

    İkinci satırın üçüncü elemanı: 6
    İlk iki satırın tüm elemanları: [[1 2 3]
     [4 5 6]]
    

---

### **2.1.2 Aritmetik İşlemler**

Numpy dizileri, matematiksel işlemleri gerçekleştirmek için kullanılabilir. Bu işlemler, dizinin her elemanı üzerinde tek tek uygulanır veya iki dizinin karşılıklı elemanları arasında gerçekleştirilir. Numpy, bu işlemleri vektörize edilmiş hızlı işlemler olarak gerçekleştirir, bu da büyük veri setleri üzerinde verimliliği artırır.

---

#### **2.1.2.1 Temel Aritmetik İşlemler:**

1. **Toplama**: İki dizinin karşılıklı elemanlarını toplar.
2. **Çıkarma**: İki dizinin karşılıklı elemanlarını çıkarır.
3. **Çarpma**: İki dizinin karşılıklı elemanlarını çarpar.
4. **Bölme**: İki dizinin karşılıklı elemanlarını böler.


```python
import numpy as np

# İki dizi oluşturma
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])

# Toplama
result_addition = arr1 + arr2
print("Toplama:", result_addition)  # Çıktı: [5 7 9]

# Çıkarma
result_subtraction = arr1 - arr2
print("Çıkarma:", result_subtraction)  # Çıktı: [-3 -3 -3]

# Çarpma
result_multiplication = arr1 * arr2
print("Çarpma:", result_multiplication)  # Çıktı: [ 4 10 18]

# Bölme
result_division = arr1 / arr2
print("Bölme:", result_division)  # Çıktı: [0.25 0.4  0.5 ]
```

    Toplama: [5 7 9]
    Çıkarma: [-3 -3 -3]
    Çarpma: [ 4 10 18]
    Bölme: [0.25 0.4  0.5 ]
    

#### **2.1.2.2 Üstel ve Logaritmik İşlemler:**

Numpy, diziler üzerinde üstel ve logaritmik işlemleri gerçekleştirmek için de fonksiyonlar sağlar.

1. **Üs Alma**: `np.power()` fonksiyonu kullanılarak her elemanın bir üs alınır.

2. **Logaritma**: `np.log()` ve `np.log10()` fonksiyonları kullanılarak logaritmalar hesaplanır.


---


```python
import numpy as np

# Dizi oluşturma
arr = np.array([1, 2, 3])

# Üs alma (2^x)
result_power = np.power(arr, 2)
print("Üs alma (2^x):", result_power)  # Çıktı: [1 4 9]

# Logaritma (doğal logaritma)
result_log = np.log(arr)
print("Logaritma (doğal logaritma):", result_log)  # Çıktı: [0.         0.69314718 1.09861229]

# Logaritma (10 tabanında)
result_log10 = np.log10(arr)
print("Logaritma (10 tabanında):", result_log10)  # Çıktı: [0.         0.30103    0.47712125]
```

    Üs alma (2^x): [1 4 9]
    Logaritma (doğal logaritma): [0.         0.69314718 1.09861229]
    Logaritma (10 tabanında): [0.         0.30103    0.47712125]
    

#### **2.1.2.3 İleri Düzey İşlemler**

Numpy, dizilerde yaygın olarak kullanılan diğer matematiksel fonksiyonları da destekler, örneğin trigonometrik, hiperbolik, ters trigonometrik ve diğer özel fonksiyonlar.

---


```python
import numpy as np

# Dizi oluşturma
arr = np.array([0, np.pi/2, np.pi])

# Sinüs
result_sin = np.sin(arr)
print("Sinüs:", result_sin)  # Çıktı: [0.0000000e+00 1.0000000e+00 1.2246468e-16]

# Cosinüs
result_cos = np.cos(arr)
print("Cosinüs:", result_cos)  # Çıktı: [ 1.000000e+00  6.123234e-17 -1.000000e+00]

# Tanjant
result_tan = np.tan(arr)
print("Tanjant:", result_tan)  # Çıktı: [ 0.00000000e+00  1.63312394e+16 -1.22464680e-16]
```

    Sinüs: [0.0000000e+00 1.0000000e+00 1.2246468e-16]
    Cosinüs: [ 1.000000e+00  6.123234e-17 -1.000000e+00]
    Tanjant: [ 0.00000000e+00  1.63312394e+16 -1.22464680e-16]
    


---

### **2.1.3 Rastgele Sayılar Üretme**

Numpy, rastgele sayılar üretmek için `numpy.random` modülünü sağlar. Bu modül, farklı dağılımlara sahip rastgele sayılar üretmek için çeşitli fonksiyonlar içerir. Ayrıca, rastgele sayıların tekrar üretilebilir olmasını sağlamak için `seed()` fonksiyonu kullanılabilir.


---

#### **2.1.3.1 np.random.rand()**

`np.random.rand()` fonksiyonu, 0 ile 1 arasında uniform (eşit olasılıklı) dağılıma sahip rastgele sayılar üretir.




```python
# 0 ile 1 arasında uniform dağılıma sahip 3 rastgele sayı üretme
random_numbers = np.random.rand(3)
print(random_numbers)  # Örnek Çıktı: [0.891773   0.03942688 0.16983042]
```

    [0.80726368 0.1899492  0.98928982]
    


---
#### **2.1.3.2 seed() Fonksiyonu**

`np.random.seed()` fonksiyonu, rastgele sayı üretiminde kullanılan rastgele sayı üretecinin başlangıç durumunu belirler. Bu, aynı seed değeri kullanıldığında, aynı rastgele sayılar üretileceği anlamına gelir. Bu, rastgele sayılarla çalışırken tekrarlanabilirlik gerektiğinde yararlıdır.


```python
import numpy as np

# seed() fonksiyonu kullanarak başlangıç durumunu belirleme
np.random.seed(42)

# Aynı seed değeri kullanıldığında aynı rastgele sayılar üretilir
print(np.random.rand(3))  # Çıktı: [0.37454012 0.95071431 0.73199394]

# Farklı bir seed değeri kullanıldığında farklı rastgele sayılar üretilir
np.random.seed(123)
print(np.random.rand(3))  # Çıktı: [0.69646919 0.28613933 0.22685145]
```

    [0.37454012 0.95071431 0.73199394]
    [0.69646919 0.28613933 0.22685145]
    


---
#### **2.1.3.3 np.random.randint()**

`np.random.randint()` fonksiyonu, belirli bir aralıktan rastgele tam sayılar üretir.


```python
# 1 ile 10 arasında rastgele tam sayı üretme
random_integers = np.random.randint(1, 11, size=5)
print(random_integers)  # Örnek Çıktı: [6 3 3 7 4]
```

    [ 7  2  4 10  7]
    


---
#### **2.1.3.4 np.random.randn()**

`np.random.randn()` fonksiyonu, standart normal dağılıma (ortalaması 0, standart sapması 1) sahip rastgele sayılar üretir.


```python
# Standart normal dağılıma sahip 3 rastgele sayı üretme
random_normal_numbers = np.random.randn(3)
print(random_normal_numbers)  # Örnek Çıktı: [-0.987502   -0.55895427  0.77606027]
```

    [ 1.59530112 -1.78309431 -0.28645147]
    


---
#### **2.1.3.5 np.random.choice()**

`np.random.choice()` fonksiyonu, bir diziden rastgele örnekleme yapar.


```python
# Verilen bir diziden rastgele örnekleme yapma
arr = np.array([1, 2, 3, 4, 5])
random_sample = np.random.choice(arr, size=3, replace=False)
print(random_sample)  # Örnek Çıktı: [4 2 5]
```

    [5 3 2]
    

## **2.2 Array Şekil Değiştirme**

### **2.2.1 Dizinin Şeklini Değiştirme**


---
#### **2.2.1.1 `reshape()` Fonksiyonu**

`reshape()` fonksiyonu, bir dizinin şeklini belirli bir şekilde değiştirmek için kullanılır. Yeni şekil, orijinal dizinin eleman sayısına uygun olmalıdır.


```python
import numpy as np

# 1D diziyi 2x3 2D dizisine dönüştürme
arr1d = np.array([1, 2, 3, 4, 5, 6])
print("1d Dizi:",  arr1d, "\n")
arr2d = arr1d.reshape(2, 3)
print("2D Dizi:\n", arr2d)
```

    1d Dizi: [1 2 3 4 5 6] 
    
    2D Dizi:
     [[1 2 3]
     [4 5 6]]
    


---
#### **2.2.1.2 `resize()` Fonksiyonu**

`resize()` fonksiyonu, bir diziyi belirtilen şekilde değiştirir, ancak orijinal diziyi değiştirir.


```python
arr1d_ornek = np.array([1, 2, 3, 4, 5, 6])
print(arr1d_ornek, "\n")
# Orijinal diziyi değiştirerek yeniden boyutlandırma
arr1d_ornek.resize(2, 3)
print("Yeniden Boyutlandırılmış Dizi:\n", arr1d_ornek)
```

    [1 2 3 4 5 6] 
    
    Yeniden Boyutlandırılmış Dizi:
     [[1 2 3]
     [4 5 6]]
    


---
#### **2.2.1.3 `reshape()` ve `-1` Kullanımı**

`reshape()` fonksiyonunda bir boyut için `-1` kullanarak, o boyutun boyutunu otomatik olarak belirtebiliriz.


```python
print(arr1d, "\n")
# Orijinal diziyi 2D dizisine dönüştürme, -1 ile otomatik boyut belirleme
arr2d_auto = arr1d.reshape(2, -1)
print("Otomatik Boyutlandırılmış Dizi:\n", arr2d_auto)
```

    [1 2 3 4 5 6] 
    
    Otomatik Boyutlandırılmış Dizi:
     [[1 2 3]
     [4 5 6]]
    


---
#### **2.2.1.4 Düzleştirme: flatten() Fonksiyonu**

`flatten()` fonksiyonu, çok boyutlu bir diziyi düzleştirerek 1D diziye dönüştürür.


```python
print(arr2d, "\n")
# 2D diziyi düzleştirme
arr_flattened = arr2d.flatten()
print("Düzleştirilmiş Dizi:\n", arr_flattened)
```

    [[1 2 3]
     [4 5 6]] 
    
    Düzleştirilmiş Dizi:
     [1 2 3 4 5 6]
    


---
#### **2.2.1.5 `ravel()` Fonksiyonu**

`ravel()` fonksiyonu da düzleştirme işlemi yapar, ancak orijinal dizideki verilere bir referans sağlar.


```python
# 2D diziyi düzleştirme (ravel)
arr_raveled = arr2d.ravel()
print("Düzleştirilmiş Dizi (ravel):\n", arr_raveled)
```

    Düzleştirilmiş Dizi (ravel):
     [1 2 3 4 5 6]
    


---
### **2.2.2 Dizileri Birleştirme ve Ayırma**

Numpy, dizileri birleştirme ve ayırma işlemleri için çeşitli yöntemler sunar. Bu yöntemler, dizileri birleştirmek için `concatenate()` ve `stack()` gibi fonksiyonları içerirken, ayırma işlemleri için `split()` fonksiyonu kullanılır.


---
#### **2.2.2.1 `concatenate()` Fonksiyonu**

`concatenate()` fonksiyonu, belirtilen eksen boyunca iki veya daha fazla diziyi birleştirir.


```python
import numpy as np

# İki diziyi birleştirme
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])

result_concatenate = np.concatenate((arr1, arr2))
print("Birleştirilmiş Dizi:", result_concatenate)  # Çıktı: [1 2 3 4 5 6]
```

    Birleştirilmiş Dizi: [1 2 3 4 5 6]
    


---
#### **2.2.2.2 `stack()` Fonksiyonu**

`stack()` fonksiyonu, belirtilen eksen boyunca dizileri birleştirirken, yeni bir boyut ekler.


```python
# İki diziyi yığma (stacking)
result_stack = np.stack((arr1, arr2))
print("Yığılmış Dizi:\n", result_stack)
```

    Yığılmış Dizi:
     [[1 2 3]
     [4 5 6]]
    


---
#### **2.2.2.3 `vstack()` ve `hstack()` Fonksiyonları**

`vstack()` fonksiyonu, dikey olarak (satır bazında) dizileri birleştirirken, `hstack()` fonksiyonu, yatay olarak (sütun bazında) birleştirir.


```python
# Dikey olarak dizileri birleştirme (vstack)
result_vstack = np.vstack((arr1, arr2))
print("Dikey Birleştirilmiş Dizi:\n", result_vstack)

# Yatay olarak dizileri birleştirme (hstack)
result_hstack = np.hstack((arr1, arr2))
print("Yatay Birleştirilmiş Dizi:", result_hstack)
```

    Dikey Birleştirilmiş Dizi:
     [[1 2 3]
     [4 5 6]]
    Yatay Birleştirilmiş Dizi: [1 2 3 4 5 6]
    


---
#### **2.2.2.4 `split()` Fonksiyonu**

`split()` fonksiyonu, belirtilen bir diziyi verilen bir pozisyonda ayırır.


```python
arr = np.array([1, 2, 3, 4, 5, 6])
result_split = np.split(arr, [2, 4])
print("Ayrılmış Dizi:", result_split)  # Çıktı: [array([1, 2]), array([3, 4]), array([5, 6])]
```

    Ayrılmış Dizi: [array([1, 2]), array([3, 4]), array([5, 6])]
    


---
#### **2.2.2.5 `vsplit()` ve `hsplit()` Fonksiyonları**

`vsplit()` fonksiyonu, dikey olarak (satır bazında), `hsplit()` fonksiyonu ise yatay olarak (sütun bazında) bir diziyi ayırır.


```python
# Dikey olarak diziyi ayırma (vsplit)
arr_2d = np.array([[1, 2, 3], [4, 5, 6]])
result_vsplit = np.vsplit(arr_2d, 2)
print("Dikey Ayrılmış Dizi:\n", result_vsplit)

# Yatay olarak diziyi ayırma (hsplit)
result_hsplit = np.hsplit(arr_2d, 3)
print("Yatay Ayrılmış Dizi:", result_hsplit)
```

    Dikey Ayrılmış Dizi:
     [array([[1, 2, 3]]), array([[4, 5, 6]])]
    Yatay Ayrılmış Dizi: [array([[1],
           [4]]), array([[2],
           [5]]), array([[3],
           [6]])]
    

## **2.3 Veri Tipi Dönüşümleri**

Numpy, farklı veri tipleri arasında dönüşümler yapmak için çeşitli fonksiyonlar sağlar. Bu dönüşümler, bir veri tipini başka bir veri tipine dönüştürmek için kullanılır.

### **2.3.1 `astype()` Fonksiyonu**

`astype()` fonksiyonu, bir dizinin veri tipini belirtilen bir veri tipine dönüştürür.


```python
import numpy as np

# İlk olarak, bir float veri tipine sahip bir dizi oluşturalım
arr_float = np.array([1.1, 2.2, 3.3, 4.4])

# Dizinin veri tipini integer olarak dönüştürelim
arr_int = arr_float.astype(int)
print("Dönüştürülmüş Dizi (integer):\n", arr_int)

# Dizinin veri tipini string olarak dönüştürelim
arr_str = arr_float.astype(str)
print("Dönüştürülmüş Dizi (string):\n", arr_str)
```

    Dönüştürülmüş Dizi (integer):
     [1 2 3 4]
    Dönüştürülmüş Dizi (string):
     ['1.1' '2.2' '3.3' '4.4']
    

### **2.3.2 `asarray()` Fonksiyonu**

`asarray()` fonksiyonu, bir nesneyi diziye dönüştürür. Bu fonksiyon, belirtilen bir veri tipini de kabul eder.


```python
# Listeyi diziye dönüştürme ve veri tipini belirtme
arr_list = [1, 2, 3, 4, 5]
arr_array = np.asarray(arr_list, dtype=float)
print("Dönüştürülmüş Dizi:\n", arr_array)
```

    Dönüştürülmüş Dizi:
     [1. 2. 3. 4. 5.]
    


---

### **2.3.3 Veri Tipi Sınırlamaları ve İşlem Önerileri**

Numpy'de veri tipleri, hesaplama sırasında önemli bir rol oynar. Farklı veri tipleri, bellek kullanımı, performans ve sonuçların doğruluğu açısından farklı avantajlar ve sınırlamalar sunar. Bu nedenle, veri tiplerini doğru bir şekilde seçmek önemlidir.

#### **Veri Tipi Sınırlamaları**

Numpy'de yaygın olarak kullanılan bazı veri tipleri şunlardır:

- `int8`, `int16`, `int32`, `int64`: İşaretli tam sayılar.
- `uint8`, `uint16`, `uint32`, `uint64`: İşaretsiz tam sayılar.
- `float16`, `float32`, `float64`, `float128`: Ondalıklı sayılar.
- `bool`: Mantıksal (boolean) değerler.
- `complex64`, `complex128`, `complex256`: Karmaşık sayılar.

Her veri tipinin sınırlamaları vardır. Örneğin, daha küçük bir veri tipi daha az bellek kullanırken, daha büyük bir veri tipi daha büyük değerleri temsil edebilir ancak daha fazla bellek kullanır. Ayrıca, veri tipleri arasında dönüşüm yaparken, veri kaybına yol açabilirsiniz.

#### **İşlem Önerileri**

1. **Veri Tipi Seçimi**: Veri tipi seçerken, kullanılacak değerlerin aralığını ve hassasiyetini göz önünde bulundurmak önemlidir. Örneğin, integer yerine float veri tipini tercih etmek, daha geniş bir aralığı ve hassasiyeti sağlar, ancak daha fazla bellek kullanır.

2. **İşlem Hızı ve Bellek Kullanımı**: Büyük veri kümeleriyle çalışırken, veri tipi seçiminin işlem hızı ve bellek kullanımı üzerinde büyük bir etkisi olabilir. Daha küçük veri tipleri daha az bellek kullanırken, işlemler daha hızlı olabilir. Ancak, veri kaybı riski daha yüksektir.

3. **Veri Dönüşümleri**: İşlem sırasında, veri tipleri arasında dönüşümler yapılabilir. Ancak, bu dönüşümler veri kaybına yol açabilir. Bu nedenle, mümkünse, işlem yapmadan önce veri tiplerini dikkatlice seçmek önemlidir.

#### Örnekler

```python
import numpy as np

# Veri tiplerinin sınırlamaları
print("int16 Sınırları:", np.iinfo(np.int16))
print("float32 Sınırları:", np.finfo(np.float32))

# Veri tipi dönüşümleri ve işlem önerileri
arr_float32 = np.array([1.5, 2.5, 3.5], dtype=np.float32)
arr_int32 = arr_float32.astype(np.int32)
print("Dönüştürülmüş Dizi (int32):\n", arr_int32)
```

Bu örnekte, `np.iinfo()` ve `np.finfo()` fonksiyonları ile farklı veri tiplerinin sınırları gösterilmiş ve `astype()` fonksiyonu ile veri tipi dönüşümü yapılmıştır. Bu, veri tipi seçimi ve dönüşümleri konusunda dikkatli olmanın önemini vurgular.

---


---

## **2.4 Fancy Indexing**

Fancy indexing, Numpy dizilerini dilimlemek veya dizinin belirli elemanlarına erişmek için dizileri kullanma yöntemidir. Bu yöntemde, bir dizi veya liste kullanılarak dizinin belirli elemanlarına erişilir. Fancy indexing, basit indeksleme ve dilimleme yöntemlerine ek olarak daha esnek ve güçlü bir seçenektir.

### **2.4.1 Tek Boyutlu Fancy Indexing**

Tek boyutlu dizilerde, fancy indexing bir dizi veya liste kullanarak belirli elemanlara erişmek için kullanılır.


```python
import numpy as np

arr = np.array([10, 20, 30, 40, 50])

# Fancy indexing kullanarak belirli elemanlara erişme
indices = [0, 2, 4]
result = arr[indices]
print("Fancy Indexing Sonucu:", result)  # Çıktı: [10 30 50]
```

    Fancy Indexing Sonucu: [10 30 50]
    

### **2.4.2 İki Boyutlu Fancy Indexing**

İki boyutlu dizilerde, fancy indexing her boyut için ayrı bir dizi veya liste kullanılarak belirli elemanlara erişmek için kullanılır.


```python
# İki boyutlu dizide fancy indexing kullanma
arr_2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Belirli satır ve sütunları seçme
row_indices = [0, 2]
col_indices = [0, 2]
result_2d = arr_2d[row_indices][:, col_indices]
print("Fancy Indexing İle Seçilmiş Dizi:\n", result_2d)
```

    Fancy Indexing İle Seçilmiş Dizi:
     [[1 3]
     [7 9]]
    

### **2.4.3 Maskelerle Indexleme**

Maskelerle indexleme, bir koşula bağlı olarak dizinin belirli elemanlarına erişmek için kullanılır. Bu, koşula uyan veya uymayan elemanlara erişmek için kullanışlı bir yöntemdir.

#### **2.4.3.1 Boolean Maskelerle Indexleme**

Boolean maskeler, bir koşula bağlı olarak dizinin elemanlarını seçmek için kullanılır.


```python
# Boolean maskelerle indexleme
arr = np.array([1, 2, 3, 4, 5])

mask = arr > 2
result_masked = arr[mask]
print("Maskelenmiş Dizi:", result_masked)  # Çıktı: [3 4 5]
```

    Maskelenmiş Dizi: [3 4 5]
    

#### **2.4.3.2 Koşul İfadeleri ile Indexleme**

Koşul ifadeleri, belirli bir koşula uyan dizinin elemanlarına erişmek için kullanılır.


```python
# Koşul ifadeleri ile indexleme
arr = np.array([1, 2, 3, 4, 5])

result_condition = arr[arr > 2]
print("Koşula Uyan Elemanlar:", result_condition)  # Çıktı: [3 4 5]
```

    Koşula Uyan Elemanlar: [3 4 5]
    

## **2.5 Array Operasyonları**

### **2.5.1 Broadcasting (Yayılma)**

Numpy'nin yayılma (broadcasting) kavramı, farklı şekillere sahip diziler arasında element-wise işlemleri gerçekleştirmek için kullanılan bir özelliktir. Bu özellik, boyutları uygun hale getirerek, daha az boyuta sahip bir dizi ile daha büyük bir dizi arasındaki işlemleri gerçekleştirmeyi mümkün kılar.

Yayılma, Numpy'deki vektörize edilmiş işlemleri yaparken çok yaygın olarak kullanılır. Bir dizi ile skaler değerler arasında veya iki farklı şekle sahip diziler arasında işlem yapmak istendiğinde yayılma devreye girer. Bu durumda, Numpy, uygun boyutları otomatik olarak eşleştirir ve işlemi gerçekleştirir.

Örneğin, iki farklı boyuta sahip diziler arasında toplama işlemi yapmak istendiğinde, küçük boyuttaki dizi, büyük boyuttaki diziye yayılabilir ve işlem gerçekleştirilebilir.

Yayılmanın kullanımı, kodun daha temiz ve daha az karmaşık olmasını sağlar. Ayrıca, Python'un yaygın işlemlerini vektörize etmek için yaygın olarak kullanılır, bu da işlemlerin daha hızlı ve daha verimli olmasını sağlar.

Özetlemek gerekirse, Numpy'nin yayılma kavramı, farklı boyutlara sahip diziler arasında işlemleri kolaylaştıran ve vektörize etmeye olanak tanıyan bir özelliktir.


---

#### **2.5.1.1 Broadcasting Kuralları**

Numpy'de, broadcasting işlemlerinin gerçekleştirilmesi için belirli kurallar vardır. Bu kurallar, farklı şekillere sahip diziler arasında yayılma işlemlerini tanımlar ve uygun boyutları eşleştirmek için gereken adımları belirler.

##### **1. Boyut Uyumluluğu**

Broadcasting işlemleri yaparken, dizilerin boyutları karşılaştırılır. Her boyutta, iki dizi ya aynı boyuta sahip olmalıdır ya da biri boyutsuz olmalıdır. Eğer boyutlardan biri 1 ise, bu boyut, diğer diziye uyumlu hale getirilebilir.


```python
import numpy as np

# 3x3 boyutunda bir dizi
arr1 = np.ones((3, 3))

# 1 boyutunda bir dizi
arr2 = np.array([1, 2, 3])

# Broadcasting ile işlem
result = arr1 + arr2
print("Broadcasting Sonucu:\n", result)
```

    Broadcasting Sonucu:
     [[2. 3. 4.]
     [2. 3. 4.]
     [2. 3. 4.]]
    


---
##### **2. Boyut Uyumsuzluğunda Hata**

Eğer broadcasting işlemi için uygun boyut eşleşmeleri sağlanamıyorsa, Numpy hata verecektir. Bu durumda, dizilerin boyutlarını uyumlu hale getirmek veya işlemi gerçekleştirmek için başka bir yöntem kullanmak gerekir.

---


```python
import numpy as np

# 3x3 boyutunda bir dizi
arr1 = np.ones((3, 3))

# 2 boyutunda bir dizi
arr2 = np.array([1, 2])

# Broadcasting ile işlem (Hata alınır)
result = arr1 + arr2
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[50], line 10
          7 arr2 = np.array([1, 2])
          9 # Broadcasting ile işlem (Hata alınır)
    ---> 10 result = arr1 + arr2
    

    ValueError: operands could not be broadcast together with shapes (3,3) (2,) 



---
##### **3. Boyut Ekleme**

Broadcasting işlemi sırasında, boyut ekleme adımı gerçekleştirilir. Diziler arasındaki boyut farkı, eksik olan boyutlara 1 eklenerek tamamlanır.

---


```python
import numpy as np

# 3x3 boyutunda bir dizi
arr1 = np.ones((3, 3))

# 3 boyutunda bir dizi
arr2 = np.array([1, 2, 3])

# Broadcasting ile işlem
result = arr1 + arr2[:, np.newaxis]
print("Broadcasting Sonucu:\n", result)
```


---
#### **2.5.1.2 Örneklerle Yayılma Kullanımı**

Numpy'de yayılma (broadcasting) özelliği, farklı şekillere sahip diziler arasında element-wise işlemleri gerçekleştirmek için kullanılır. Bu özellik, boyutları uygun hale getirerek, daha az boyuta sahip bir dizi ile daha büyük bir dizi arasındaki işlemleri gerçekleştirmeyi mümkün kılar. İşte farklı yöntemlerle kullanılan yayılma örnekleri:


---
##### **1. Temel Yayılma**

Temel yayılma, iki dizinin boyutları aynı veya biri boyutsuzsa gerçekleşir. Bu durumda, element-wise işlem doğrudan uygulanabilir.

---


```python
import numpy as np

arr1 = np.array([[1, 2, 3], [4, 5, 6]])
arr2 = np.array([10, 20, 30])

# Temel yayılma ile işlem
result = arr1 + arr2
print("Temel Yayılma Sonucu:\n", result)
```


---
##### **2. Boyut Ekleme ile Yayılma**

Boyut ekleme ile yayılma, boyutları uyumlu hale getirerek işlem yapılmasını sağlar. Bu durumda, boyutları farklı olan diziler arasında yayılma işlemi gerçekleştirilebilir.

---


```python
# Boyut ekleme ile yayılma
arr1 = np.array([[1, 2, 3], [4, 5, 6]])
arr2 = np.array([10, 20, 30])

# Boyut ekleme ile işlem
result = arr1 + arr2[:, np.newaxis]
print("Boyut Ekleme ile Yayılma Sonucu:\n", result)
```


---
##### **3. Broadcasting Kuralı ile Yayılma**

Broadcasting kuralı, dizilerin uyumlu hale getirilmesi için gereken boyut eşleşmelerini belirler. Bu kuralı kullanarak, farklı boyutlara sahip diziler arasında yayılma işlemi gerçekleştirilebilir.

---


```python
# Broadcasting kuralı ile yayılma
arr1 = np.array([[1, 2, 3], [4, 5, 6]])
arr2 = np.array([1, 2])

# Broadcasting kuralı ile işlem
result = arr1 + arr2[:, np.newaxis]
print("Broadcasting Kuralı ile Yayılma Sonucu:\n", result)
```


---
### **2.5.2 Dizi Yineleme (Repeating)**

Numpy'de dizi yineleme, bir diziyi belirli bir eksen boyunca tekrarlayarak yeni bir dizi oluşturmayı sağlayan bir işlemdir. Bu işlem, dizinin belirli boyutlarındaki tekrarlarını oluşturur. Numpy'nin `repeat()` fonksiyonu veya `tile()` fonksiyonu ile gerçekleştirilir.

---


---
#### **1. `repeat()` Fonksiyonu ile Yineleme**

Numpy'de `repeat()` fonksiyonu, bir diziyi belirli sayıda tekrarlayarak yeni bir dizi oluşturur. Bu fonksiyon, belirtilen eksen boyunca tekrar sayısını ve tekrar edilecek diziyi alır.

---


```python
import numpy as np

# Bir dizi oluşturalım
arr = np.array([1, 2, 3])

# Diziyi tekrarlayalım
result = np.repeat(arr, 3)  # Her elemanı 3 kez tekrarla
print("repeat() Fonksiyonu ile Yineleme Sonucu:", result)  # Çıktı: [1 1 1 2 2 2 3 3 3]
```

    repeat() Fonksiyonu ile Yineleme Sonucu: [1 1 1 2 2 2 3 3 3]
    


---
#### **2. `tile()` Fonksiyonu ile Yineleme**

`tile()` fonksiyonu, bir dizinin belirli bir şekilde yinelemesini sağlar. Bu fonksiyon, belirtilen şekil boyunca diziyi kopyalar ve yeni bir dizi oluşturur.

---


```python
# Diziyi belirli bir şekilde yineleyelim
result_tile = np.tile(arr, 3)  # Diziyi 3 kez yatayda yinele
print("tile() Fonksiyonu ile Yineleme Sonucu:", result_tile)  # Çıktı: [1 2 3 1 2 3 1 2 3]
```

    tile() Fonksiyonu ile Yineleme Sonucu: [1 2 3 1 2 3 1 2 3]
    


---
### **2.5.3 İç Çarpım (Dot Product)**

Numpy'de iç çarpım (dot product), iki vektör arasında veya bir matris ile bir vektör veya iki matris arasında yapılan matematiksel bir işlemdir. İç çarpım, vektörlerin veya matrislerin elemanlarının çarpılması ve toplanmasıyla hesaplanır.


---
#### **1. İki Vektör Arasındaki İç Çarpım**

İki vektör arasındaki iç çarpım, vektörlerin elemanları arasında yapılan çarpma işlemlerinin toplanmasıyla hesaplanır.

---


```python
import numpy as np

# İki vektör oluşturalım
vec1 = np.array([1, 2, 3])
vec2 = np.array([4, 5, 6])

# İki vektör arasındaki iç çarpımı hesaplayalım
dot_product = np.dot(vec1, vec2)
print("İki Vektör Arasındaki İç Çarpım:", dot_product)  # Çıktı: 32
```

    İki Vektör Arasındaki İç Çarpım: 32
    


---
#### **2. Matris ve Vektör Arasındaki İç Çarpım**

Bir matris ile bir vektör arasındaki iç çarpım, matrisin satırlarıyla vektörün sütunlarının elemanları arasında yapılan çarpma işlemlerinin toplanmasıyla hesaplanır.

---


```python
# Bir matris ve bir vektör oluşturalım
matrix = np.array([[1, 2], [3, 4], [5, 6]])
vector = np.array([2, 3])

# Matris ve vektör arasındaki iç çarpımı hesaplayalım
dot_product_matrix_vector = np.dot(matrix, vector)
print("Matris ve Vektör Arasındaki İç Çarpım:", dot_product_matrix_vector)  # Çıktı: [ 8 18 28]
```

    Matris ve Vektör Arasındaki İç Çarpım: [ 8 18 28]
    


---
#### **3. İki Matris Arasındaki İç Çarpım**

İki matris arasındaki iç çarpım, matrislerin satırlarıyla sütunlarının elemanları arasında yapılan çarpma işlemlerinin toplanmasıyla hesaplanır.

---


```python
# İki matris oluşturalım
matrix1 = np.array([[1, 2], [3, 4]])
matrix2 = np.array([[5, 6], [7, 8]])

# İki matris arasındaki iç çarpımı hesaplayalım
dot_product_matrices = np.dot(matrix1, matrix2)
print("İki Matris Arasındaki İç Çarpım:\n", dot_product_matrices)
```

    İki Matris Arasındaki İç Çarpım:
     [[19 22]
     [43 50]]
    


---
## **2.5.4 İşlem Fonksiyonları (np.sum(), np.prod(), np.mean() vs.)**

Numpy'de, çeşitli işlem fonksiyonları mevcuttur. Bu fonksiyonlar, dizilerdeki elemanların toplamını, çarpımını, ortalama değerini ve diğer istatistiksel hesaplamaları gerçekleştirmek için kullanılır. En yaygın kullanılan işlem fonksiyonları arasında `np.sum()`, `np.prod()`, `np.mean()` ve benzerleri bulunur.


---
#### **1. `np.sum()` Fonksiyonu**

`np.sum()` fonksiyonu, bir dizinin elemanlarının toplamını hesaplamak için kullanılır.

---


```python
import numpy as np

# Bir dizi oluşturalım
arr = np.array([1, 2, 3, 4, 5])

# Dizinin elemanlarının toplamını hesaplayalım
total_sum = np.sum(arr)
print("Dizinin Toplamı:", total_sum)  # Çıktı: 15
```


---
#### **2. `np.prod()` Fonksiyonu**

`np.prod()` fonksiyonu, bir dizinin elemanlarının çarpımını hesaplamak için kullanılır.

---


```python
# Dizinin elemanlarının çarpımını hesaplayalım
total_product = np.prod(arr)
print("Dizinin Çarpımı:", total_product)  # Çıktı: 120
```


---
#### **3. `np.mean()` Fonksiyonu**

`np.mean()` fonksiyonu, bir dizinin elemanlarının ortalama değerini hesaplamak için kullanılır.

---


```python
# Dizinin elemanlarının ortalama değerini hesaplayalım
mean_value = np.mean(arr)
print("Dizinin Ortalaması:", mean_value)  # Çıktı: 3.0
```


---
#### **4. Diğer İşlem Fonksiyonları**

Numpy'de birçok işlem fonksiyonu bulunur ve bu fonksiyonlar çeşitli istatistiksel hesaplamaları yapmak için kullanılır. Bazı diğer yaygın işlem fonksiyonları şunlardır:
- `np.min()`: Dizinin minimum değerini bulur.
- `np.max()`: Dizinin maksimum değerini bulur.
- `np.std()`: Dizinin standart sapmasını hesaplar.
- `np.median()`: Dizinin ortanca değerini bulur.

Bu işlem fonksiyonları, Numpy'de veri analizi ve işlemlerinde sıkça kullanılır ve dizilerdeki verilerin çeşitli istatistiksel özelliklerini hesaplamak için önemlidir.

---

# **3. Lineer Cebir İşlemleri**


---
## **3.1 Matris Çarpımı**

Numpy'de matris çarpımı, iki matris arasındaki çarpma işlemidir. Matris çarpımı, lineer cebirde ve matris işlemlerinde sıkça kullanılan önemli bir işlemdir. Numpy'nin `np.dot()` fonksiyonu veya `@` operatörü ile matris çarpımı gerçekleştirilir.

---


---
### **`@` Operatörü ile Matris Çarpımı**

`@` operatörü, Numpy'de matris çarpımı için kullanılabilir. Bu operatör, iki matrisin çarpımını daha okunabilir bir şekilde ifade etmek için kullanılır.

---


```python
# @ operatörü ile matris çarpımını hesaplayalım
matrix_product_operator = matrix1 @ matrix2
print("Matris Çarpımı (@ operatörü ile):\n", matrix_product_operator)
```


---
## **3.2 Determinant ve Ters Matris Hesaplama**

Numpy'de, bir matrisin determinantı ve ters matrisi hesaplanabilir. Determinant, bir kare matrisin bir tür ölçüsüdür ve matrisin nasıl davrandığını anlamak için önemlidir. Ters matris ise, bir matrisin tersine çarpıldığında birim matrisi veren bir matristir.


---
### **3.2.1 Determinant Hesaplama**

Numpy'de, bir matrisin determinantını hesaplamak için `np.linalg.det()` fonksiyonu kullanılır.

---


```python
import numpy as np

# Bir kare matris oluşturalım
matrix = np.array([[1, 2], [3, 4]])

# Matrisin determinantını hesaplayalım
determinant = np.linalg.det(matrix)
print("Matrisin Determinantı:", determinant)
```

    Matrisin Determinantı: -2.0000000000000004
    


---
### **3.2.2 Ters Matris Hesaplama**

Numpy'de, bir matrisin tersini hesaplamak için `np.linalg.inv()` fonksiyonu kullanılır.

---


```python
# Matrisin tersini hesaplayalım
inverse_matrix = np.linalg.inv(matrix)
print("Matrisin Tersi:\n", inverse_matrix)
```

    Matrisin Tersi:
     [[-2.   1. ]
     [ 1.5 -0.5]]
    

# **4. Universal Functions (ufuncs):**


---
## **4.1 ufuncs Nedir?**

ufuncs (universal functions), Numpy'de evrensel işlevler olarak bilinen, dizi elemanlarında element-wise (eleman bazlı) işlemler gerçekleştiren işlevlerdir. Bu işlevler, Numpy dizilerindeki her bir elemana aynı işlemi uygulayarak hızlı ve verimli bir şekilde çalışır.

ufuncs'ler, matematiksel operasyonlar, trigonometrik fonksiyonlar, mantıksal operasyonlar ve diğer birçok işlem için kullanılabilir.


---
## **4.2 Matematiksel İşlemler**

Numpy'deki birçok matematiksel işlem, ufuncs kullanılarak gerçekleştirilir. Örneğin, toplama, çıkarma, çarpma, bölme gibi işlemler ufuncs aracılığıyla eleman bazlı olarak uygulanır.

---


```python
import numpy as np

# İki dizi oluşturalım
arr1 = np.array([1, 2, 3, 4])
arr2 = np.array([5, 6, 7, 8])

# Toplama işlemi
result_addition = np.add(arr1, arr2)

# Çarpma işlemi
result_multiplication = np.multiply(arr1, arr2)

print("Toplama İşlemi Sonucu:", result_addition)
print("Çarpma İşlemi Sonucu:", result_multiplication)
```


---
## **4.3 Trigonometrik Fonksiyonlar**

ufuncs, trigonometrik fonksiyonlar gibi matematiksel fonksiyonlar için de kullanılır.

---


```python
# Sinüs fonksiyonu
result_sin = np.sin(arr1)

# Kosinüs fonksiyonu
result_cos = np.cos(arr2)

print("Sinüs Fonksiyonu Sonucu:", result_sin)
print("Kosinüs Fonksiyonu Sonucu:", result_cos)
```


---
## **4.4 Mantıksal İşlemler**

Mantıksal işlemler de ufuncs aracılığıyla gerçekleştirilir.

---


```python
# Mantıksal ve işlemi
result_and = np.logical_and(arr1 > 2, arr2 < 7)

# Mantıksal veya işlemi
result_or = np.logical_or(arr1 > 2, arr2 < 7)

print("Mantıksal 've' İşlemi Sonucu:", result_and)
print("Mantıksal 'veya' İşlemi Sonucu:", result_or)
```
