# Tensorflow Object Detection API ile Koyun Tespit Etmek

https://github.com/tensorflow/models/tree/r1.13.0

Yukarıdan indirdiğiniz dosyaları models adı ile C:/tensorflow1 klasörünün altına atın.
Daha sonrasında benım yayınladığım kodları indirin ve C:/tensorflow1/models/research/object_detection dizinine atın.

## Anaconda Ortamında "Virtual Environment" Oluşturulması

`C:\>conda create -n tensorflow1` komutu ile virtual environment oluşturuyoruz.

`C:\>conda activate tensorflow1` komutu ile oluşturduğumuz virtual environmenta giriyoruz. Gerekli kurulumları burada yapacağız.

## Tensorflow Kurulumu

Bu kod Tensorflow'un 1.13.2 versiyonu ile çalışmaktadır. Diğer versiyonlarda problemler ile karşılaşılabilir.

`C:\>pip install --ignore-installed --upgrade tensorflow==1.13.2` komutu ile Tensorflow'u yükleyebiliriz.

Eğer gerekli donanıma ve driverlara sahipseniz Tensorflow GPU versiyonunu kurabilirsiniz.

`C:\>pip install --ignore-installed --upgrade tensorflow-gpu==1.13.2` komutu ile Tensorflow GPU versiyonunu yükleyebiliriz.

## Gerekli Paketlerin Kurulumları

`C:\>conda install -c anaconda protobuf`

`C:\>pip install pillow lxml cython jupyter matplotlib pandas opencv-python`

## Çevre Değişkenlerinin Ayarlanması

`C:\>set PYTHONPATH=C:\tensorflow1\models;C:\tensorflow1\models\research;C:\tensorflow1\models\research\slim`

## Protobufların Derlenmesi ve 'setup.py' Dosyasının Çalıştırılması

`C:\>cd C:\tensorflow1\models\research` komutu ile gerekli dizine gidelim.

Daha sonrasında aşağıdaki komut ile protobufları derleyelim.

`protoc --python_out=. .\object_detection\protos\anchor_generator.proto`

Ardından setup.py dosyasını çalıştıralım.

`C:\tensorflow1\models\research>python setup.py build`

`C:\tensorflow1\models\research>python setup.py install`

## Modelin Kullanımı

`C:\>cd C:\tensorflow1\models\research\object_detection` komutu ile gerekli dizine gidelim.

Bu dizinde bulunan "Object_detection_image.py" dosyası verilen resimde koyunları çerçeve içerisine alıp tanımlıyor. "Object_detection_video.py" dosyası ise videodan nesne tanıması gerçekleştiriyor. Webcam ile nesne tanıması yapmak için "Object_detection_webcam.py" dosyasını çalıştırmalısınız. Aşağıdaki komutlar ile Python dosyalarını çalıştırabilirsiniz.

`python Object_detection_webcam.py`
`python Object_detection_image.py`
`python Object_detection_video.py`


Bu dizinde bu kodların içindeki "IMAGE_NAME = 'koyun.jpg'" değişkenini değiştirerek istediğiniz dosyadan nesne tanıması gerçekleştirebilirsiniz.

