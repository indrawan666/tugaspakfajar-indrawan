```dart
void main() {
  // List
  List<int> numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  print('Isi List Angka: $numbers');
  print('');
  // Function untuk menghitung penjumlahan dan perkalian
  Map<String, dynamic> calculateSumAndProduct(List<int> nums) {
    int sum = 0;
    int product = 1;
    for (int number in nums) {
      sum += number;      // Penjumlahan semua elemen dalam list
      product *= number;  // Perkalian semua elemen dalam list
    }
    return {'sum': sum, 'product': product};
  }
  // Function untuk menghitung rata-rata
  double calculateAverage(int sum, int length) {
    return sum / length;  // Rata-rata elemen dalam list
  }
  // Function untuk menghitung penjumlahan kuadrat semua elemen dalam list
  int calculateSumOfSquares(List<int> nums) {
    int sumOfSquares = 0;
    for (int number in nums) {
      sumOfSquares += number * number;  // Penjumlahan kuadrat semua elemen dalam list
    }
    return sumOfSquares;
  }
  // Function dengan closure untuk mencari elemen tertentu
  Function checkElementExists(int target) {
    return (List<int> nums) {
      return nums.contains(target);
    };
  }
  // Function untuk mencetak elemen list dan indeksnya
  void printElementsWithIndices(List<int> nums) {
    print('Perulangan Menggunakan for:');
    for (int i = 0; i < nums.length; i++) {
      print('Indeks $i: ${nums[i]}');
    }
    print('');
  }
  // 1. Hitung penjumlahan, perkalian, dan rata-rata menggunakan function
  var results = calculateSumAndProduct(numbers);
  double average = calculateAverage(results['sum'], numbers.length);
  print('Hasil Operasi Aritmatika pada List:');
  print('Penjumlahan: ${results['sum']}');
  print('Perkalian: ${results['product']}');
  print('Rata-rata: $average');
  print('');
  // 2. Hitung penjumlahan kuadrat dan cetak hasilnya
  int sumOfSquares = calculateSumOfSquares(numbers);
  print('Penjumlahan kuadrat semua elemen: $sumOfSquares');
  print('');
  // 3. Cek apakah angka 7 ada dalam list menggunakan closure
  var checkNumberExists = checkElementExists(7);
  if (checkNumberExists(numbers)) {
    print('Angka 7 ditemukan dalam list.');
  } else {
    print('Angka 7 tidak ditemukan dalam list.');
  }
  print('');
  // 4. Cetak semua elemen dalam list beserta indeksnya
  printElementsWithIndices(numbers);
}

```


kesimpulan:
List: Digunakan untuk menyimpan angka-angka dalam numbers.

Aritmatika: Melibatkan penjumlahan, perkalian, rata-rata, dan penjumlahan kuadrat elemen dalam list.

Percabangan: Memeriksa apakah angka tertentu ada dalam list.

Perulangan: Mengiterasi elemen-elemen dalam list untuk operasi aritmatika dan pencetakan.

Function: Mengelompokkan tugas-tugas spesifik dalam fungsi.

Scope: Menentukan ruang lingkup variabel dalam fungsi.

Closure: Fungsi yang menangkap variabel dari lingkup sekitarnya untuk operasi tertentu