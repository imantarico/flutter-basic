# PENGGUNAAN GRIDVIEW DI FLUTTER

Pada flutter untuk membuat tampilan grid view dapat menggunakan GridView widget. Penggunaan GridView di Flutter seperti penggabungan antara penggunaan ListView widget serta penggunaan row dan column widget. Berikut contoh sederhana Penggunaan GridView di flutter framework



># Penggunaan Gridview secara sederhana

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
Nilai tiga (3) pada crossAxisCount merupakan nilai untuk jumlah column pada grid. Sedangkan children merupakan widget turunan yang akan ditampilkan berjumlah lima logo Flutter dalam bentuk grid. Hasil code diatas akan menjadi seperti ini

GridView dasarnya merupakan CustomScrollView widget yang dapat di scroll (scrollable) sehingga tidak perlu khawatir apabila jumlah dari widget grid melebihi ukuran layar. Dalam GridView kita juga dapat menggunakan List.generate untuk membuat anakan widget sesuai dengan jumlah data array. Contohnya seperti ini

```dart
import 'package:flutter/material.dart';

final Color darkBlue = Color.fromARGB(255, 18, 32, 47);

void main() {
  runApp(BelajarGridView());
}

class BelajarGridView extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
          appBar: AppBar(
            title: Text("belajarFlutter.com"),
          ),
          body: GridView.count(
            crossAxisCount: 3,
            children: List.generate(9, (index) {
              return Container(
                child: Card(
                  color: Colors.deepPurpleAccent,
                ),
              );
            }),
          )),
    );
  }
}
  ```
  
Terdapat Lima cara yang dapat digunakan dalam penggunaan GridView di Flutter yaitu :
GridView
GridView.count
GridView.builder
GridView.custom
GridView.extent
Sebenarnya dari segi penggunaan ke-lima fungsi tersebut juga sangat mirip. Sebagai contoh kita akan menampilkan 2 column grid dengan 4 widget yang berisi logo flutter menggunakan semua jenis GridView yang ada.

># GridView.count
```dart
GridView.count(
  crossAxisCount: 2,
  children: <Widget>[
    FlutterLogo(),
    FlutterLogo(),
    FlutterLogo(),
    FlutterLogo(),
  ],
)
```
># GridView.bulder
```dart
GridView.builder(
  gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(crossAxisCount: 2),
  itemBuilder: (_, index) => FlutterLogo(),
  itemCount: 4,
)
```

># GridView.custom
```dart
GridView.custom(
  gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(crossAxisCount: 2),
  childrenDelegate: SliverChildListDelegate(
    [
      FlutterLogo(),
      FlutterLogo(),
      FlutterLogo(),
      FlutterLogo(),
    ],
  ),
)
```

># GridView.extent
```dart
GridView.extent(
  maxCrossAxisExtent: 400,
  children: <Widget>[
    FlutterLogo(),
    FlutterLogo(),
    FlutterLogo(),
    FlutterLogo(),
  ],
)
```

># GridView
```dart
GridView(
  gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(crossAxisCount: 2),
  children: <Widget>[
    FlutterLogo(),
    FlutterLogo(),
    FlutterLogo(),
    FlutterLogo(),
  ],
)
```



