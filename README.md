MPU6050 Kullanımı

Bu proje, MPU6050 IMU (Inertial Measurement Unit) sensörünü STM32 mikrodenetleyicisi ile kullanarak ivmeölçer, jiroskop ve sıcaklık verilerini okumayı sağlar.

Özellikler

MPU6050 sensörü ile iletişim: I2C haberleşmesi ile veri okuma

İvmeölçer ve Jiroskop verilerini işleme

Sıcaklık sensörü kullanımı

Kalman filtresi ile açısal verileri hesaplama

Gereksinimler

STM32 Mikrodenetleyici

MPU6050 Sensörü

HAL Kütüphanesi (STM32CubeMX ile oluşturulmuş projelerde kullanılır)

Dosya Açıklamaları

mpu6050.h

MPU6050_t ve Kalman_t yapılarını tanımlar.

MPU6050 sensöründen veri okumak için kullanılan fonksiyon prototiplerini içerir.

Kalman filtresi ile açısal hesaplamalar için fonksiyonları içerir.

mpu6050.c

MPU6050'nin başlatılması ve veri okunmasını sağlar.

MPU6050_Init(): Sensörü başlatır ve gerekli ayarlamaları yapar.

MPU6050_Read_Accel(): İvmeölçer verilerini okur.

MPU6050_Read_Gyro(): Jiroskop verilerini okur.

MPU6050_Read_Temp(): Sıcaklık verisini okur.

MPU6050_Read_All(): Tüm sensör verilerini okur ve Kalman filtresi uygular.
