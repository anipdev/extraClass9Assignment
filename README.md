Aplikasi ini dapat berkomunikasi antara client dan server menggunakan gRPC. Server memiliki satu metode RPC, SayHello, yang menerima parameter name dari client dan mengembalikan balasan berupa pesan sapaan.

## Instalasi dan Penggunaan

### 1. Clone Project

Clone atau salin kode ini ke dalam direktori lokal Anda.

    git clone https://github.com/anipdev/extraClass9Assignment
    cd extraClass9Assignment

### 2. Install Dependensi

Install Go dan Protocol Buffer sesuai dengan OS Anda, dengan mengikuti dokumentasi berikut ini:

Instalasi Go: https://golang.org/dl/

Instalasi Protocol Buffers: https://developers.google.com/protocol-buffers

Install plugin Go untuk Protocol Buffers:

    go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
    go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest

### 3. Kompilasi File Protobuf

Jalankan perintah berikut untuk mengonversi file greet.proto menjadi kode Go:

    protoc --go_out=. --go_opt=paths=source_relative --go-grpc_out=. --go-grpc_opt=paths=source_relative greet.proto

### 4. Jalankan Server

Jalankan server dengan perintah berikut:

    go run ./server/main.go

Server akan berjalan pada port 50051.

### 5. Jalankan Client

Setelah server berjalan, Anda dapat menjalankan client untuk mengirimkan nama dan menerima balasan.

    go run ./client/main.go --name="anip"

Output yang diharapkan pada sisi client:

    Greeting: Hello, anip!

Pada sisi server

    2025/05/20 19:23:00 Received: anip
