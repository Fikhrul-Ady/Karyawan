# Karyawan
## Latihan
1. Tampilkan data karyawan yang bekerja pada departemen yang sama dengan karyawan yang bernama Dika
   ```
   select nik, nama, id_dept
    -> FROM karyawan
    -> WHERE id_dept = (
    -> SELECT id_dept FROM karyawan
    -> WHERE nama = 'Dika');
   ```
