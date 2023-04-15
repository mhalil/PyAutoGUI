PyAutoGUI fare ve klavye hareketleri ile uygulamaları kontrol etmemizi sağlayan bir kütüphanedir.
PyAutoGUI kütüphanesi ile fareyi hareket ettirme, istenilen yere tıklama, çift tıklama, kaydırma; klavyeden yazı yazma, komutlar gönderme; ekran görüntüsüne sahip olduğumuz buton, pencere ve simgeleri bulma ve bu gibi alanların üzerinde belirli işlemler yapabiliriz.

Bu repoda PyAutoGUI kütüphanesinin Temel Komutları anlatılmıştır.

# EKRAN KOMUTLARI;

Öncelikle **pyautogui** modülünü, çalışmamıza import edelim.

```python
import pyautogui
```

## size()

Ekran Boyutunu öğrenelim.

```python
print(pyautogui.size())  
```

> Çıktı:
> 
> ```python
> Size(width=1920, height=1080)
> ```

## ## onScreen(x, y)

Belirttiğimiz (0, 3000) Koordinatları, ekran sınırları içerisinde mi? Öğrenelim.

```python
print(pyautogui.onScreen(0, 3000))
```

> Çıktı
> 
> ```python
> False
> ```

# FARE HAREKETLERİ;

## position()

İmleç konumunu tespit et, **x** ve **y** değerlerini al, "a" ve "b" değişkenlerine ata. Değişkenleri ekrana yazdır.

```python
a, b = pyautogui.position()
print(a, b)
```

> Çıktı:
> 
> ```python
> 1583 259
> ```

İmleç konumunu doğrudan ekrana yazdır;

```python
print(pyautogui.position())
```

> Çıktı;
> 
> ```python
> Point(x=1577, y=229)
> ```

## moveTo(x, y)

İmleci X'te 100 ve Y'de 200 konumuna taşı.

```python
pyautogui.moveTo(100, 200)
```

İmleci X'te sabit tut ve Y'de 500 konumuna taşı.

```python
pyautogui.moveTo(x, 500)
```

İmleci X'te 600  konumuna taşı, Y'de mevcut (500 konumunda) sabit tut.

```python
pyautogui.moveTo(600, x)
```

imleci 2 saniye süre içinde X'te 100, Y'de 200 koordinatlarına taşı.

```python
pyautogui.moveTo(100, 200, 2)
```

## moveRel(x, y)

İmleci mevcut bulunduğu konumdan 50 pixel sağa (x ekseni yönünde) taşı

```python
pyautogui.moveRel(50, 0)
```

İmleci (fareyi) bulunduğu konumdan 50 pixel sola (-x ekseni yönünde) taşı

```python
pyautogui.moveRel(-50, 0)
```

## dragTo(x, y, button="right/left")

Farenin **sol tuşuna** basılı tutarak imleci X'te 750, Y'de 200 piksel konumuna sürükle.

```python
pyautogui.dragTo(750, 200, button="left")
```

 Farenin **sağ tuşuna** basılı tutarak **2 saniye içinde** imleci bulunduğu konumdan 30 pixel sağa sürükle.

```python
pyautogui.dragRel(30, 0, 2, button="right")
```

## click()

Hiç bir parametre girilmeden çalıştırılırsa bulunduğu konumda **farenin sol butonu** ile bir kez tıklar.

```python
pyautogui.click()
```

## click(x, y)

x'te 100, y'de 200 koordinatlarına git ve sonra sol tıkla.

```python
pyautogui.click(x=100, y=200)
```

## click(button='right')

Bulunduğu konumda ****farenin sağ butonu** ile tıklar.

```python
pyautogui.click(button='right') 
```

## click(clicks=...)

**Farenin sol butonu** ile çift (iki kez) tıklar.

```python
pyautogui.click(clicks=2)
```

## click(interval=...)

**Farenin sol butonu** ile çift tıklarken, tıklamalar arasında 0.25sn süre ile bekler.

```python
pyautogui.click(clicks=2, interval=0.25)
```

 **Farenin sağ butonu** ile üç kez tıklarken, tıklamalar arasında 0.25sn süre ile bekler. 

```python
pyautogui.click(button="right", clicks=3, interval=0.25)
```

## mouseDown() / mouseUp()

**Farenin sol butonuna** bas (mouseDown()) ve elini butondan çek (mouseUp())  

```python
pyautogui.mouseDown(); pyautogui.mouseUp()
```

## mouseDown(button='right / left')

Sağ / Sol butona bas.

```python
pyautogui.mouseDown(button='right')
```

## mouseUp()

(100,200) koordinatlarına gittikten sonra farenin sağ butonuna basmayı bırak.

```python
pyautogui.mouseUp(button='right', x=100, y=200)
```
## Diğer bahsedeceğimiz fare hareketleri;

## rightClick(x, y)
pyautogui.rightClick(x, y)

## middleClick(x, y)
pyautogui.middleClick(x, y)

## doubleClick(x, y)
pyautogui.doubleClick(x, y)

## tripleClick(x, y)
pyautogui.tripleClick(x, y)


# KLAVYE KONTROL İŞLEVLERİ;

## typewrite('...')

İmlecin bulunduğu konuma, anında "Merhaba Dünya" yazdırır.

```python
pyautogui.typewrite('Merhaba Dünya!')
```

Karakterler arası çeyrek (0.25) saniye bekleyerek "Merhaba Dünya" yazar.

```python
pyautogui.typewrite("Merhaba Dunya!", interval=0.25)
```

## KEYBOARD_KEYS

Özel tuşların listesine ulaşmak için aşağıdaki kodu çalıştırabilirsiniz.

```python
print(pyautogui.KEYBOARD_KEYS)
```

> Çıktı;
> 
> ```python
> ['\t', '\n', '\r', ' ', '!', '"', '#', '$', '%', '&', "'", '(', ')', '*', '+', ',', '-', '.', '/', '0', '1', '2', '3', '4', '5', '6', '7', '8', '9', ':', ';', '<', '=', '>', '?', '@', '[', '\\', ']', '^', '_', '`', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', '{', '|', '}', '~', 'accept', 'add', 'alt', 'altleft', 'altright', 'apps', 'backspace', 'browserback', 'browserfavorites', 'browserforward', 'browserhome', 'browserrefresh', 'browsersearch', 'browserstop', 'capslock', 'clear', 'convert', 'ctrl', 'ctrlleft', 'ctrlright', 'decimal', 'del', 'delete', 'divide', 'down', 'end', 'enter', 'esc', 'escape', 'execute', 'f1', 'f10', 'f11', 'f12', 'f13', 'f14', 'f15', 'f16', 'f17', 'f18', 'f19', 'f2', 'f20', 'f21', 'f22', 'f23', 'f24', 'f3', 'f4', 'f5', 'f6', 'f7', 'f8', 'f9', 'final', 'fn', 'hanguel', 'hangul', 'hanja', 'help', 'home', 'insert', 'junja', 'kana', 'kanji', 'launchapp1', 'launchapp2', 'launchmail', 'launchmediaselect', 'left', 'modechange', 'multiply', 'nexttrack', 'nonconvert', 'num0', 'num1', 'num2', 'num3', 'num4', 'num5', 'num6', 'num7', 'num8', 'num9', 'numlock', 'pagedown', 'pageup', 'pause', 'pgdn', 'pgup', 'playpause', 'prevtrack', 'print', 'printscreen', 'prntscrn', 'prtsc', 'prtscr', 'return', 'right', 'scrolllock', 'select', 'separator', 'shift', 'shiftleft', 'shiftright', 'sleep', 'space', 'stop', 'subtract', 'tab', 'up', 'volumedown', 'volumemute', 'volumeup', 'win', 'winleft', 'winright', 'yen', 'command', 'option', 'optionleft', 'optionright']
> ```

## press("...")

 **Enter** tuşuna bas.

```python
pyautogui.press("enter")
```

**F1** tuşuna bas.

```python
pyautogui.press("f1")
```

**Sol ok** tuşuna bas.

```python
pyautogui.press("left")
```

**typewrite()** fonksiyonu gibi birden fazla tuşa **press()** fonksiyonu ile bas.

```python
pyautogui.press(['left', 'left', 'left'])
```

Yukarıdaki kod, bizi şu şekilde kod yazmaktan kurtarıyor.

```python
pyautogui.press('left')
pyautogui.press('left')
pyautogui.press('left')
```

## keyDown('...')

**Shift** tuşuna basılı tut.

```python
pyautogui.keyDown('shift')
```

## keyUp('...')

**Shift **tuşuna basmayı bırak.

```python
pyautogui.keyUp('shift')
```

## hotkey('...', '...')

**Ctrl+Shift+Esc** kısayol tuşlarına bas.

```python
pyautogui.hotkey('ctrl', 'shift', 'left')
```

Shift+Home kısayol tuşlarına bas.

```python
pyautogui.hotkey('shift', 'home')
```

# MESAJ KUTUSU İŞLEVLERİ;

## alert()

**Metin, başlık ve tek bir buton**dan oluşan bir ileti kutusu gösterir. Butona tıklandıktan sonra buton (button) metnini döndürür.

```python
print(pyautogui.alert(text='Buraya metin', title='Başlık', button='OK'))
```

Belirtilen butonlar, metin ve başlıktan oluşan metin kutusu. Butonlar birden fazla olabilir. Butonlara tıklandığında sonuç olarak tıklanan butonun (buttons) metnini gönderir.

```python
print(pyautogui.confirm(text='Buraya metin', title='Başlık', buttons=['OK', 'Cancel']))
```

## prompt()

“**Ok**” ve “**Cancel**” butonlarının bulunduğu metin kutusu. “**Ok**” butonuna tıklandığında sonuç olarak **girilen metni**, “**Cancel**” butonuna tıklandığında **None** değerini döndürür.

```python
print(pyautogui.prompt(text='Metninizi yazın...', title='Başlık'))
```

## password()

“**Ok**” ve “**Cancel**” butonlarının bulunduğu metin kutusu. **prompt()** fonksiyonundan tek farkı yazılan metinler “*****” olarak görüntülenir. “**Ok**” butonuna tıklanır ise metni, “**Cancel**” butonuna tıklanır ise None değerini **sonuç** olarak döndürür.

```python
print(pyautogui.password(text='Burası metin', title='Başlık', mask='*'))
```

# EKRAN GÖRÜNTÜ İŞLEVLERİ;

## screenshot('...')

**Ekran görüntüsünü almak** için kullanacağımız fonksiyondur. Bu işlemi python konsolunda yaptığınızda fotoğrafı python’nun yüklü olduğu dizine kaydeder.

```python
resim = pyautogui.screenshot('ekran_goruntum.png')
```

## region=(a,b,c,d)

Ekranının sadece **belirli bir kısmının** görüntüsünü almak isteyince "**region**" argümanını/parametresini kullanacağız. Burada vereceğimiz değerilerin ilk ikisi **x, y başlangıç koordinatını** daha sonra vereceğimiz iki değer ise ilki **x ekseni boyunca (sağa doğru) genişliğini, ikincisi ise y ekseni boyunca (aşağı doğru) yüksekliğini** belirtir.

```python
resim = pyautogui.screenshot("goruntu.png", region=(20, 50, 100, 500))
```

