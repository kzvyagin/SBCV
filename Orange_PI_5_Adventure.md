<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/kzvyagin/orange_pi_5">Orange PI 5 Adventure</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://github.com/kzvyagin">Konstantin Zvyagin</a> is licensed under <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"> <img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"></a></p>

<h4>Часть 1. "Загрузка"</h4>
Все началось с желания исследовать тему компьютерного зрения в области встраиваемых плат типо raspberry еще в далеких 2010-х. Тогда появлялись платы с все большим количеством ядер и все большей частой процессора. Однако мощность их на практике желала оставлять лучшего. Каждая фото обрабатывалось с заметным лагом, а об обработке видео небыло и речи. Пока железа подходящего небыло, я разработал небольшой курс "Введение в  компьютерное зрение и машинное обучение" познакомиться с ним можно по <a href="https://github.com/kzvyagin/introduction_to_cv_and_ml">ссылке</a>.  
Все изменись с появлением специализированных NPU предназначенных для нейронных сетей с помощью которых можно разрабатывать программы с использование компьютерного зрения, машинного обучения, вычислительной фотографии. Одной из интересных серий плат на данный момент это OrangePI, от OrangePI3 с процессором RK3568 и OrangePI5 с процессором RK3568. Оба они содержат NPU.
И вот наступает конец 2023 его года и я решил себе сделать новогодний подарок, заказал на avito плату OrangePI5 с 16 ю гигабайтами оперативной памяти. Почему не Ali ? Просто потому что Avito доставило за 5 дней перед новым годом, а Ali обещали за 30 дней =).
Конечно я решил подготовиться, изучил интернет на предмет что лучше устанавливать на SD карту, чем прошивать и как произвести первую настройку. Заказал расходные материалы в виде нескольких SD карт по 256 гигабайт , корпус, wifi usb свисток, переходник usb- lan (для своего ноутбука). 
Получив расходные материалы я сразу прошил SD карты, одну на Armbian вторую на классическую серверную прошивку ubuntu с сайта OrangePi.

 
<details close>
  <summary>Инструкция прошивки платы</summary>

Команды для распаковки образов:

```
7z x mysuper.iso.zx
zx --decompress mysuper.iso.zx
```
Команды для прошивки:
узнать куда примонтировалась sd карта 
```
dmesg
```
посмотреть разделы sd:
```
ls -l /dev/sd* или ls -l /dev/mmcblk*
```
вывод будет примерно следующим :
```
    /dev/mmcblk0
    /dev/mmcblk0p2
    /dev/mmcblk0p1
```
выбираем из указнных устройств корневой раздел:
```
/dev/mmcblk0 или /dev/sda 
```
далее переходим к прошивки
```
dd if=my_super_image.img of=/dev/sda bs=4M oflag=fsync status=progress
```
ждем, и после завершения обязательно запускаем команду sync перед извлечением карты
```
sync 
```
</details>


И счастливый стал ждать.
Плата пришла в обещанное время, спасибо сервису BoxBerry. Упакована надежно и добротно в две коробки. 
Придя домой я подключил монитор, клавиатуру и питание.  Однако меня ждало разочарование. На мониторе загрузка зависла... Далее была борьба с разными образами ОС и вариантами прошивки. Часа три я не понимал, или плата нерабочая, или я не тот образ записал (или не так). 
Я получал ошибки следующего вида:
 
![ubuntu load error 1](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/ubuntu_error.png)  

 ![armbian load error 1](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/armbian_error.png)  


Все без результатно. 
Я начал исследовать тему, почему это происходит и нашел два наиболее распространенных ответа:
* Блок питания должен быть достаточной мощности , желательно 60 w + 
* SD карта должна быть A1 класса , желательно sandisk или smartbuy. (мой случай)
  
Я сходил в магазин за новой картой памяти , стоит карточки такого класса конечно дорого. 64 гигабайта мне обошлись в 800 р. Блок питания у меня был.

После я вернулся домой и залил образ серверной ubuntu на новую sd карту. Сразу заметил скорость заливки значительно возросла. Поставив SD карту в плату я увидел экран долгожданной загрузки ОС :

 ![first boot](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/first_orange_pi5_boot.png)  

  
УРА ! Препятствия запуска платы пройдены !

<li> <a href="">Armbian</a></li>

На заметку:
<ul>
  <li>все образы имеют небольшой размер раздела ОС. для его расширения рекомендую воспользоваться программой gparted после заливки SD карты. GParted немного поругается, предложат что-то пофиксить в ФС (соглашаемся) и изменит размер на тот который вы хотите, я увеличил на все оставшиеся гигагбайты (примерно 50+) своей 64 гигабайтной sd кары. </li>
  <li>первый запуск и эксперименты лучше проводить на серверных образах  ОС, они меньше весят, а это значит что они быстрее заливаются на SD карту. Дополнительны бонус, они быстро грузятся и сразу отображают информацию о CPU и общей памяти на устройстве. </li>
  <li> Ссылки на ОС:
    <ul>
      <li> <a href="https://www.armbian.com/orangepi-5/">Armbian</a></li>
      <li> <a href="https://github.com/Joshua-Riek/ubuntu-rockchip/releases">Joshua-Riek</a></li>
      <li><a href="https://drive.google.com/drive/folders/1i5zQOg1GIA4_VNGikFl2nPM0Y2MBw2M0">Ubuntu</a> </li>
    </ul>
  </li>
   <li>Ссылка на офф сайт 
    <ul>
      <li><a href="http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/service-and-support/Orange-pi-5.html">OrangePi сайт</a></li>
      <li><a href="https://drive.google.com/file/d/13LJk85ueOup2HqbEhcY2UhUw5lwESth_/view">User manual</a></li>
      <li><a href="http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/details/Orange-Pi-5.html">Overview</a> </li>
    </ul>
  </li>
</ul>

Итого плата отлично запускается, все работает. 
Использую OS OrangePI5_ubuntu_jammy_desctop_xfce_linux_5.10.160.7z

<h4>Часть 2. "Подготовка инструментов"</h4>

- проверка наличия драйвера для видеокарты 
- проверка наличия npu библиотек
- установка vscode 
- установка инструментов 

<h4>Часть 3. "Сборка и запуск примеров rknn2"</h4>

<h4>Часть 4. "Сборка и запуск примера Neural Network Use Cases"</h4>

<h4>Часть 5. "Обработка потокового видео"</h4>
