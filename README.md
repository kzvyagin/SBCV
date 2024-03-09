# Single-board computer vision
<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/kzvyagin/SBCV">Single-board computer vision</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://github.com/kzvyagin">Konstantin Zvyagin</a> is licensed under <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"> <img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"></a></p>

<p>Доброго времени суток '%username' !</p>

 Рад приветствовать тебя на своей страничке посвященной изучению Orange PI. Тут я изучаю платы Orange PI на предмет использования NPU, GPU, CPU для обработки изображений, компьютерного зрения и вычислительной фотографии. 

 На данный момент у меня есть плата [Orange PI5](https://github.com/kzvyagin/SBCV/blob/main/OrangePi5/Orange_PI_5_Adventure.md). С нее и начнем.

Для справки:

ресурс для разметки своих датасетов для дальнейшего обучения yollo5 https://www.makesense.ai/. Он помогает разметить в нужном формате. 
## Структура репозитория

*	Файл **[AUTHORS.md](AUTHORS.md)** содержит список людей,
	которые принимали участие в&nbsp;подготовке материалов,
	предоставляемых данным репозиторием.
*	Файл **[board_list.md](board_list.md)** содержит список макетных плат содержащих NPU или иной AI ускоритель. Подходит для AI IOT для роботов, для создания беспилотных решений, для автоматизации производства, для умного города. Отладочные платы c NPU. ARM или RISKV макетные платы с NPU.
*	Файл **[cpu_with_npu_list.md](cpu_with_npu_list.md)** содержит список встраиваемых CPU with NPU или TPU или иными ИИ / AI модулями. Указаны основные характеристики, мощность NPU, наличие MCU, мощность CPU. Указаны, при наличии, github репозитории с исходными кодами примеров для NPU и  драйверами к NPU.   Для некоторых SOC CPU c NPU указаны ссылки на макетные платы для приобретения. Подходит для AI IOT для роботов, для создания беспилотных решений, для автоматизации производства, для умного города. Отладочные платы c NPU. ARM или RISKV макетные платы с NPU.
*	Директория **[OrangePi5](./OrangePi5)**
	содержит описание запуска нейронный сетей на NPU OrangePI5 с RK3588 в виде живого рассказа.
    *	Директория **[OrangePi5/images](./OrangePi5/imges)**
	содержит ресурсы фотографий и видео используемых в описании OrangePi5.

## Условия использования


Этот документ и&nbsp;учебно-методические материалы предоставляются в&nbsp;соответствии
с&nbsp;[Публичной лицензией Creative Commons с&nbsp;указанием авторства версии&nbsp;4.0 Международная](./LICENSE.CC-BY-4.0.ru.md).


Исходный код проектов приложений предоставляется в&nbsp;соответствии
с&nbsp;лицнзией [BSD-3 Clause](https://opensource.org/license/bsd-3-clause/).
