# Karyawan
Nama    : Muhammad Fiqri Setyoadi

Kelas   : TI.22.A.2 

NIM     : 31210062 

## Latihan
1. Tampilkan data karyawan yang bekerja pada departemen yang sama dengan karyawan yang bernama Dika
   ```
   select nik, nama, id_dept
    -> FROM karyawan
    -> WHERE id_dept = (
    -> SELECT id_dept FROM karyawan
    -> WHERE nama = 'Dika');
   ```
<img width="960" alt="SS1" src="https://github.com/Fikhrul-Ady/Karyawan/assets/115645419/47bb80c1-4714-48d6-96bc-865e758ce8d5">

2. Tampilkan data karyawan yang gajinya lebih besar dari rata-rata gaji semua karyawan. urutkan menurun berdasarkan besaran gaji
   ```
    select nik, nama, id_dept, sup_nik, gaji_pokok
    -> FROM karyawan
    -> WHERE gaji_pokok > (
    -> SELECT AVG(gaji_pokok) FROM karyawan)
    -> ORDER BY gaji_pokok DESC;
    ```
   <img width="960" alt="SS2" src="https://github.com/Fikhrul-Ady/Karyawan/assets/115645419/61aed92c-0120-4e50-a0a8-2ffa895973c3">

3. Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di department yang sama dengan karyawan dengan nama yang mengandung huruf 'K'.
   ```
    select nik, nama
    -> FROM karyawan
    -> WHERE id_dept IN (
    -> SELECT id_dept FROM karyawan
    -> WHERE nama LIKE '%k%');
   ```
   <img width="960" alt="SS3" src="https://github.com/Fikhrul-Ady/Karyawan/assets/115645419/386b0115-40cb-49a6-8894-576c2343a476">

4. Tampilkan data karyawan yang bekerja pada departemen yang ada di kantor pusat.
   ```
   select karyawan.nik, karyawan.nama, karyawan.id_dept
    -> FROM karyawan
    -> JOIN departemen ON karyawan.id_dept = departemen.id_dept
    -> WHERE departemen.id_p = 'P01';
   ```
   <img width="960" alt="SS4" src="https://github.com/Fikhrul-Ady/Karyawan/assets/115645419/200fc639-2846-4205-bb07-937b0f91d6b1">

5. Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di department yang sama dengan karyawan dengan nama yang mengandung huruf 'K' dan yang gajinya lebih besar dari rata-rata gaji semua karyawan.
   ```
   select DISTINCT k1.nik, k1.nama
    -> FROM karyawan k1
    -> JOIN karyawan k2 ON k1.id_dept = k2.id_dept
    -> WHERE k1.gaji_pokok > (
    -> SELECT AVG(gaji_pokok) FROM karyawan
    -> WHERE nama LIKE '%k%');
   ```
    <img width="960" alt="SS5" src="https://github.com/Fikhrul-Ady/Karyawan/assets/115645419/b303ef91-ac0e-4f35-abbb-3f89e8419a22">


   

    
    
