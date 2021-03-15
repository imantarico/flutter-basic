# PENGGUNAAN GRIDVIEW DI FLUTTER

Pada flutter untuk membuat tampilan grid view dapat menggunakan GridView widget. Penggunaan GridView di Flutter seperti penggabungan antara penggunaan ListView widget serta penggunaan row dan column widget. Berikut contoh sederhana Penggunaan GridView di flutter framework



>## Langkah 1: Buat Class yang menggunakan StatefulWidget

```dart
import 'package:flutter/material.dart';

void main() => runApp(Myapp());

class Myapp extends StatefulWidget {
  _MyappState createState() => _MyappState();
}

class _MyappState extends State<Myapp> {
  //deklarasi variabel
  final txtnamamhs = TextEditingController();
  final txtjkelamin = TextEditingController();
  
  Widget build(BuildContext context) {
    return MaterialApp(
        home: new Scaffold(
            appBar: new AppBar(title: Text("Belajar Pintar")),
            body: new ListView(
              children: <Widget>[
                new Container(
                  padding: EdgeInsets.all(10.0),
                  child: Column(
                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                    children: <Widget>[
                      TextField(
                        controller: txtnamamhs,
                        decoration: InputDecoration(hintText: 'Nama Mahasiswa'),
                      ),
                      TextField(
                        controller: txtjkelamin,
                        decoration: InputDecoration(hintText: 'Jenis Kelamin'),
                      ),
                      ElevatedButton(
                          child: Text("Tambah"),
                          onPressed: null),
                    ],
                  ),
                ),
                new Column(
                    // Isi List View
                )
              ],
            )));
  }
}
```
>## Langkah 2: Buat Listview Contructor untuk Getter (Pengambilan Data)

Letakkan program di bawah ini pada tempat deklarasi variabel
```dart
List<Widget> data = [];

onTambah() {
    setState(() {
      data.add(ListTile(
        leading: Icon(Icons.people),
        title: Text(txtnamamhs.text),
        subtitle: Text(txtjkelamin.text),
      ));
    });
  }
  ```
>## Langkah 3: Panggil Pada Design

ganti properties `ElevatedButton` dengan `onPressed: onTambah,`

masukkan Array kedalam ListView
```dart
new Column(
   children: data,
  )
```
