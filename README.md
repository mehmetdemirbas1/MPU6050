# MPU6050
MPU6050, MEMS teknolojisini kullanan bir sensördür ve ivmeölçer (accelerometer), gyroskop (gyroscope) ve sıcaklık sensörünü bir arada barındırır. Bu proje, STM32 mikrodenetleyicisi kullanarak MPU6050 sensöründen veri okumayı ve filtrelemeyi sağlar. Projede temel olarak I2C haberleşme protokolü kullanılmıştır.

1. MPU6050_Init(I2C_HandleTypeDef *I2Cx)

MPU6050 sensörünü başlatır ve gerekli register ayarlarını yapar.

Giriş: I2C haberleşme yapısını işaret eden bir pointer.

Çıkış: Sensör başlatma durumu (0: Başarılı, 1: Başarısız).

2. MPU6050_Read_Accel(I2C_HandleTypeDef *I2Cx, MPU6050_t *DataStruct)

İvmeölçerden (accelerometer) x, y ve z eksenindeki ham ve işlenmiş verileri okur.

Giriş: I2C yapı pointer'ı, veri saklama yapısı.

Çıkış: İşlenmiş ivme değerleri.

3. MPU6050_Read_Gyro(I2C_HandleTypeDef *I2Cx, MPU6050_t *DataStruct)
4. 5. MPU6050_Read_All(I2C_HandleTypeDef *I2Cx, MPU6050_t *DataStruct)

Tüm sensör verilerini (ivmeölçer, gyroskop ve sıcaklık) bir kerede okur ve işlenmiş değerlere dönüştürür.

Giriş: I2C yapı pointer'ı, veri saklama yapısı.

Çıkış: Tüm sensör verileri.

6. Kalman_getAngle(Kalman_t *Kalman, double newAngle, double newRate, double dt)

Kalman filtresi kullanarak açıyı hesaplar.

Giriş: Kalman filtre yapısı, yeni açı, yeni hız ve zaman farkı (dt).

Çıkış: Filtrelenmiş açı değeri.

Kullanım Adımları

Bağlantı: MPU6050'nin I2C pinlerini STM32 mikrodenetleyicisine bağlayın.

Başlatma: MPU6050_Init() fonksiyonunu çağırarak sensörü başlatın.

Veri Okuma: Gerekli fonksiyonları kullanarak sensör verilerini okuyun ve işleyin.

Kalman Filtresi: Verileri filtrelemek için Kalman fonksiyonunu entegre edin.

Gereksinimler

STM32 mikrodenetleyicisi

I2C Haberleşme protokolü

MPU6050 sensör modülü

STM32CubeIDE veya uygun bir geliştirme ortamı

Ek Notlar

MPU6050'yi beslemek için 3.3V kullanılması önerilir.

Sensörden okunan ham veriler, uygun ölçeklendirme ve dönüştürme işlemleriyle SI birimlerine çevrilmelidir.

Daha kararlı sonuçlar için Kalman filtresi veya başka bir filtreleme yöntemi uygulanabilir.

Gyroskoptan x, y ve z eksenindeki ham ve işlenmiş verileri okur.

Giriş: I2C yapı pointer'ı, veri saklama yapısı.

Çıkış: İşlenmiş gyroskop değerleri.
