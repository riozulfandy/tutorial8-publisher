1. How many data your publlsher program will send to the message broker in one run?

Program penerbit (publisher) akan mengirim 5 pesan ke message broker dalam satu kali eksekusi. Hal ini terjadi karena di dalam fungsi utama, metode `publish_event` dengan `UserCreatedEventMessage` dipanggil 5 kali.

2. The url of: `“amqp://guest:guest@localhost:5672”` is the same as in the subscriber program, what does it mean?

URL `amqp://guest:guest@localhost:5672` yang sama pada kedua program menandakan bahwa kedua program tersebut terhubung ke message broker yang sama. URL ini digunakan oleh program penerbit (publisher) untuk mengirim pesan ke antrean (queue). Di sisi lain, dalam program penerima (subscriber), URL ini digunakan untuk membuat pendengar (listener) yang akan mengambil data dari antrean pesan.


## RabbitMQ

![Running RabbitMQ](assets/images/image1.png)

## Lampiran screen show console

![Sending and processing event](assets/images/image2.png)


Setelah Publisher dijalankan, ia akan mengirim data yang telah dikodekan secara statis ke antrean pesan (message queue). Selanjutnya, Subscriber akan menerima data tersebut dari antrean pesan dan menampilkannya di konsol seperti yang terlihat pada gambar di atas.

## Lampiran monitoring chart based on publisher

![Monitoring chart based on publisher](assets/images/image3.png)


Berdasarkan lampiran di atas, terlihat adanya lonjakan yang menunjukkan peningkatan tingkat pesan (message rate) pada interval tertentu, yang disebabkan oleh eksekusi berulang cargo run pada Publisher. Ini menandakan bahwa setiap kali cargo run dijalankan, terjadi peningkatan tingkat pesan di RabbitMQ yang berperan sebagai antrean pesan (message queue).