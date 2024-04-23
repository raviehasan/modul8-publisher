1. How many data your publisher program will send to the message broker in one run? Jumlah data yang dikirimkan dapat dilihat dari file main.rs di folder publisher. Jika diperhatikan, terdapat 5 kali pemanggilan method publish_event(...). Kelima pemanggilan tersebut mengirimkan UserCreatedEventMessage sebagai parameternya. Kemudian, tidak ada looping, sehingga sekali run hanya akan terdapat 5 pemanggilan method publish_event(...). Maka dari itu, program publisher akan mengirimkan 5 data ke message broker in one run.


2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean? Baik program subscriber maupun publisher, keduanya terhubung pada satu server AMQP. “amqp://guest:guest@localhost:5672” akan digunakan untuk membuat new publisher queue. Server tersebut memiliki username "guest" dan password "guest". Hostname dari mesin tempat broker berjalan adalah localhost. Broker AMQP akan keep track connections pada port number 5672.

Running RabbitMQ as message broker screenshot:
![alt text](<images/Running RabbitMQ as message broker.png>)
