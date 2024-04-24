1. How many data your publlsher program will send to the message broker in one run?

Program penerbit (publisher) akan mengirim 5 pesan ke message broker dalam satu kali eksekusi. Hal ini terjadi karena di dalam fungsi utama, metode `publish_event` dengan `UserCreatedEventMessage` dipanggil 5 kali.

2. The url of: `“amqp://guest:guest@localhost:5672”` is the same as in the subscriber program, what does it mean?

URL `amqp://guest:guest@localhost:5672` yang sama pada kedua program menandakan bahwa kedua program tersebut terhubung ke message broker yang sama. URL ini digunakan oleh program penerbit (publisher) untuk mengirim pesan ke antrean (queue). Di sisi lain, dalam program penerima (subscriber), URL ini digunakan untuk membuat pendengar (listener) yang akan mengambil data dari antrean pesan.