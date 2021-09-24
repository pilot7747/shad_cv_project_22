# Адская классификация автомобильных номеров

Этот репозиторий содержит стартовый код для проекта. В нем используются библиотеки Pytorch и Pytorch Lightning. 
Если вы с ними не знакомы, то посмотрите эти ссылки:
* https://pytorch.org/tutorials/beginner/blitz/cifar10_tutorial.html
* https://pytorch-lightning.readthedocs.io/en/latest/starter/new-project.html

Использовать данный стартовый код не обязательно. Если вы, например, предпочитаете Tensorflow, то вы можете его использовать, но в таком случае придется написать код с нуля.

**Задача**: обучить классификатор, отличающий автомобильные номера российского образца от всех остальных

**Вводные**: 
* Тренировочные данные: 1000 размеченных картинок и 8500 неразмеченных.
* [Ноутбук](https://github.com/btseytlin/shad_cv_project_21/blob/main/train_basic_classifier.ipynb) дообучает MobileNetV2 (2.3М параметров) на тысяче размеченных картинок.
* [Ноутбук для сабмита](https://github.com/btseytlin/shad_cv_project_21/blob/main/submit.ipynb) запускает обученную модель и генерирует `submit.csv` нужного формата.

## Условия
* Можно использовать любые методы ML при условии, что каждая индивидуальная модель не имеет больше параметров, чем MobileNetV2.
* Нельзя использовать внешние данные.
* Можно использовать модели предобученные на ImageNet.
* Нельзя использовать модели предобученные на других датасетах.
* Нельзя делиться разметкой, моделями, конфигами проекта в Толоке.
* Если что-то не разрешено, значит это запрещено. При сомнениях спросите у преподавателей курса.

## Сдача результатов
В течение соревнования вы получите сначала валидационный сет, и в самом конце тестовый. Валидационный сет будет использован для публичного лидерборда, а тестовый для приватного лидерборда.
Оценка будет выставляться на основании вашей позиции на приватноом лидерборде. У вас будет возможность сделать 3 сабмита в приватный лидерборд, для оценки будет использован лучший.

Кроме того, нужно будет отправить:
1. Сыллку на проект в Толоке.
2. Ссылку на код, который использовался для обучения и сабмита.

## Оценка
Максимум – 20 баллов. Из них 10 баллов зависят от качества модели, другие 10 баллов – от качества сборки проекта на Толоке. 

Метрика __качества модели__: f1 скор класса 1, качество проверяется на закрытом тестовом сете.
Оценка складывается из оценки за достижения порога в 0.4 и места на лидеборде.

0.4 на тестовом сете = 5 баллов 
Оценка за место на лидерборде = перцентиль скора сабмита деленный на 10 и округленный до десятка делить на два.

Например, при скоре 0.5 и первом месте оценка = 5 баллов за порог + round((100 перцентиль)/10)/2 - 5 = 5 + 5 = 10 баллов.

При скоре 0.5 и 30 перцентиле оценка = 5 + 2 = 7 баллов.

Such is the way.
