
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
7z x mysuper.iso.7z
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
 <details close>
  <summary>Ошибка 1</summary>

![ubuntu load error 1](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/ubuntu_error.png)  

</details>


 <details close>
  <summary>Ошибка 2</summary>

 ![armbian load error 1](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/armbian_error.png)  
</details>

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
  <li>После выбора системы и первого запуска необходимо обновить систему .

  sudo apt-get update

  sudo apt-get upgrade

   </li>
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
насал использовать OS OrangePI5_ubuntu_jammy_desctop_xfce_linux_5.10.160.7z
но перешел на ubuntu-22.04.3-preinstalled-desktop-arm64-orangepi-5.img.xz v1.31, он по новее и браузер более новый, меньше падений, хотя есть.

<h4>Часть 2. "Подготовка инструментов"</h4>

<h5>1) проверка наличия драйвера для видеокарты </h5>
проверяем на наличие драйверов в системе 

```
dpkg -l | grep mali-g610
```

<details close>
  <summary>Вывод</summary>
  
 ![check-mali-installed](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/check-mali-installed.png)  

</details>

проверяем версию установленного драйвера 

```
apt-cache show mali-g610-firmware
```
 
<details close>
  <summary>Вывод</summary>
  
 ![mali-g610-firmware](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/mali-g610-firmware.png)  

</details>

 <h5>2) проверка наличия NPU библиотек</h5>
 Выполняем команду 

 ```
 find /usr/lib -name *librknn*
 ```

и у меня в системе "ubuntu-22.04.3-preinstalled-desktop-arm64-orangepi-5" их нет. А в системе "OrangePI5_ubuntu_jammy_desctop_xfce_linux_5.10" они есть, но они почему-то не подошли, мне пришлось их заново собирать.

поэтому используем надежный и проверенный способ, установку и сборку из репозитория. Для этих целей я скачал следующий репозиторий:

```
git clone --recurse-submodules -j8 https://github.com/rockchip-linux/rknpu2.git
```

после выкачивания выглядит все так, что библиотека librknn поставляется сразу в виде blob, см директорию:

```
rknpu2/runtime/RK3588/Linux/librknn_api/aarch64
```
посмотри информацию об библиотеке librknn

```
 readelf  -nh librknnrt.so
```
<details close>
  <summary>Вывод</summary>

 ![librknn_readelf](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/librknn_readelf.png)  
</details>

посмотрим ее зависимости:

```
 ldd  librknnrt.so
```


<details close>
  <summary>Вывод</summary>


 ![librknn_ldd](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/librknn_ldd.png)  
</details>

тут век ок, битых ссылок нет.

<h5>3) установка vscode </h5>
установка vs code прошла без особых проблем. заходим на официальный сайт, скачиваем сборку aarch64 и устанавливаем ее через dpkg -i или aptitude install.

<h5> 4)установка инструментов </h5>

```
apt-get install cmake clang gcc g++ gdb git docker mc meld  imagemagick pitivi  protobuf-compiler
```

Установка Gstreamer 


<a href="https://linux.how2shout.com/installing-gstreamer-on-ubuntu-22-04-or-20-04-lts-linux/">Gstreamer</a>


```
apt-get install  libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev libgstreamer-plugins-bad1.0-dev gstreamer1.0-plugins-base gstreamer1.0-plugins-good gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly gstreamer1.0-libav gstreamer1.0-tools gstreamer1.0-x gstreamer1.0-alsa gstreamer1.0-gl gstreamer1.0-gtk3 gstreamer1.0-qt5 gstreamer1.0-pulseaudio
```  

Установка Qt
```
sudo apt install  qtcreator qtbase5-dev qt5-qmake qtdeclarative5-dev
or
sudo apt install qtcreator qt6-base, qt6-base-dev or qt6-tools-dev

```


Установка OpenCV 

```
 sudo apt install libopencv-dev python3-opencv
```



<h4>Часть 3. "Сборка и запуск примеров rknn2"</h4>
 Перейдем к самому интересному, к сборке и запуску готового примера использования NPU ускорителя. 
Если вы еще не скачали rknn репозиорий то повторим это 

```
git clone --recurse-submodules -j8 https://github.com/rockchip-linux/rknpu2.git
```
Далее все достаточно просто, заходим внутрь папки rknpu2/examples/
Нас интересует пример rknn_yolov5_demo.
заходим внутри и там есть заранее заготовленный скрипт сборки build-linux_RK3588.sh, запускаем его.

<details close>
  <summary>Лог сборки</summary>

 ![librknn_ldd](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/rknn_yollo5_demo_build_progress.png)  
</details>


Отлично, пример собрался без дополнительной магии и докручивания. 
Перейдем к запуску. 
Из текущей директории переходи в новую папку install/rknn_yolov5_demo_Linux и там будет исполняемый файл, модель , и ,библиотека для NPU.
Все предусмотрительно скопировано скриптом в одну папку, это удобно.

<details close>
  <summary>Лог зпуска</summary>

 ![librknn_ldd](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/run_rknn_yollo5_demo.png)  
</details>

Следует отметить что скрип копирует библиотеку librknnrt.so в папку lib. И если спросить ldd у rknn_yolov5_demo то ссылка будет корректно указвать на lib/librknnrt.so.  

Ниже приведу результат обработки изображения.

<details close>
  <summary>Результат распознования автобуса</summary>
 ![librknn_ldd](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/out_bus.png)  
</details>

Ура! пример запускается. Время на обработку 1 ого изображения 640x640 при помощи inference yollo5 запущенного на NPU RK3588 примерно 20 милисекунд. Немного округлим в большую сторону и получи 21 милисекунд. Посчитаем общее количество кадров которое может обработать NPU c имеющимся inference yollo5. 
1000/21 = 47.6 кадров/сек без учета подготовки, копирования, прочих накладных расходов. Выглядит очень интересно при таком большом разрешении inference yollo5 640х640. Есть гипотеза что можно организовать потоковую обработку видео 24 кадра в секунду. Проверим это предположение в слудующих разделах нашего приключения. 

<h4>Часть 4. "Сборка и запуск примера Neural Network Use Cases"</h4>

Скачиваем репозиторий.

```
git clone https://gitlab.com/omprussia/demos/NeuralNetworksUseCases.git
```

Этот пример для OS Aurora. Придется собирать программу по кускам. 
Сборка NCNN
Идем в директорию NCNN и собираем там библиоткеку .

```
mkdir build 
cd build 
cmake ..
```


тут надо убедиться что все зависимости удовлетворены.
make -j8 
устанавливаем в opt для того чтобы библиотека не смешалась с системными библиотеками.
При этом для дальнейшей работы и сборки нам надо указывать корретный путь к h файлам и к библиотекам.


```
cmake --install . --prefix /opt/libs/
```

to be continued ...


<h4>Часть 5. "Обработка видео записи"</h4>

посмотрим что нужно для запуска примера обработка видео 
./rknn_yolov5_video_demo --help

```
./rknn_yolov5_video_demo --help

Usage: ./rknn_yolov5_video_demo <rknn_model> <video_path> <video_type 264/265>
```

таким образом нужно иметь модель, она есть в директории model, само видео в определенном формате. В конвертации нам поможет vlc

проверяем  формат видео 

```
mediainfo videorecorder_720p_HD.mp4
 
```
он у меня не подходящий , нужно конвертировать в 264/265

для этого устанавливаем ffmpeg , gstreamer ( см рецепт выше)),  vlc


```
sudo apt install ffmpeg vlc

```

конвертируем видео в h264
норамльный конвертер это тут  https://www.convertfiles.com/

```
ffmpeg -i videorecorder_720p_HD.mp4 -an -vcodec libx264 -crf 23 outfile.h264
```

Проверяем при помощи file что у файла нужный формат . Устраиваем просмотр при помощи vlc что все корректно сконвертиловалось. 

и видео не вопроизводиться vlc корректно и не лезет в обработку. 

возможно нужно привести формат в 640*640 h264 

Для быстрого перевода видео в нужный формат и размер я не нашел ничего лучше и стабильнее чем воспользоваться двумя интернет сервисами, один для изменеия размера видео , второй для переврда в h264.

для изменения размера использую этот ресурс 
https://clideo.com/ru/resize-video

для конвертации видео в h264 использую этот ресурс 

https://www.digitalofficepro.com/convert/mp4-to-h-264

Правильно сконверитированный фал для скачивания и проверки:

<details close>
  <summary>Файл h264 640*320:</summary>
 ![librknn_ldd](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/video_recorder_h264_640.264
)  
</details>



После преобразований получился файл удовлетворящий входным парамтрам стандртного примера rknn.
Запускаме его при помощи комадны 

```
  ./rknn_yolov5_video_demo model/RK3588/yolov5s-640-640.rknn mysupervideo.264 264
```

Вывод в консоль будет примерно следующем 

<details close>
  <summary>Вывод запуска yollo на видео</summary>

 ![librknn_ldd](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/rknn_yollo5_video_demo_run_progress.png
)  
</details>

Результат будет записан в эту-же папку в виде out.h264. Для его нормального проигрования конвертируем его обратно в mp4 или avi 

<details close>
  <summary>Результирующее видео с рапознаванием:</summary>

 ![librknn_ldd](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/video_recorder_h264_640_out.264
)  
</details>

Известные проблемы при запуске видео примера 

1) Пример виснет, лог в консол повисает, хотя остальная ОС работатет - не правильный формат фала или размер или мало питания на плате.
2) на вывод ползет что-то несурное заполняя весь вывод однообразными символами - неправильный формиат или размер видео 
3) для проверки формата видео файла используте программу mediainfo. Ниже вывод правильно сконвертированного файла:

<details close>
  <summary>Вывод mediainfo на правильно подготовленном файлом h246:</summary>

 ![librknn_ldd](https://raw.githubusercontent.com/kzvyagin/orange_pi_5/main/images/mediainfo_output_reference.png
)  
</details>


<h4>Часть 6. "Разработка собственного приложения"</h4>


<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/kzvyagin/orange_pi_5">Orange PI 5 Adventure</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://github.com/kzvyagin">Konstantin Zvyagin</a> is licensed under <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"> <img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"></a></p>
