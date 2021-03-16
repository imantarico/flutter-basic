# PENGGUNAAN GRIDVIEW DI FLUTTER

Pada flutter untuk membuat tampilan grid view dapat menggunakan GridView widget. Penggunaan GridView di Flutter seperti penggabungan antara penggunaan ListView widget serta penggunaan row dan column widget. 



>## Berikut contoh sederhana Penggunaan GridView di flutter framework

```dart
import 'package:flutter/material.dart';

final Color darkBlue = Color.fromARGB(255, 18, 32, 47);

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      theme: ThemeData.dark().copyWith(scaffoldBackgroundColor: darkBlue),
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        body: GridView.count(
          crossAxisCount: 3,
          children: <Widget>[
            FlutterLogo(),
            FlutterLogo(),
            FlutterLogo(),
            FlutterLogo(),
            FlutterLogo(),
          ],
        ),
      ),
    );
  }
}


```
>## Langkah 2: Buat Listview Contructor untuk Getter (Pengambilan Data)

GridView dasarnya merupakan CustomScrollView widget yang dapat di scroll (scrollable) sehingga tidak perlu khawatir apabila jumlah dari widget grid melebihi ukuran layar. Dalam GridView kita juga dapat menggunakan List.generate untuk membuat anakan widget sesuai dengan jumlah data array. Contohnya seperti ini
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
