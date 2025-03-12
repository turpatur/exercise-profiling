# Adpro / Progjut / Prolan
## Modul 5 

1. What is the difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance?
   - JMeter menampilkan lamanya waktu untuk mendapatkan response, sedangkan IntelliJ Profiler juga menampilkan bagian kode mana saja yang berpengaruh pada waktu untuk mendapatkan response sehingga lebih mudah untuk mengoptimisasi kode.
2. How does the profiling process help you in identifying and understanding the weak points in your application?
   - Profiling membantu saya dalam mengudentifikasi bagian kode mana saja yang membuat aplikasi berjalan lambat dengan adanya detail-detail analisis profiler tersebut. Hal ini membuat saya tidak perlu menganalisis secara manual tentang bagian kode mana yang dapat dioptimisasi. 
3. Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?
   - Menurut saya, IntelliJ Profiler efejtuf untuk membantu menganalisis dan mengidentifikasi bottleneck karena meng-_highlight_ bagian kode mana yang menyebabkan lambatnya aplikasi dan juga durasi untuk mendapatkan response sehingga lebih mudah untuk mengidentifikasim bagian kode yang bermasalah dan dapat dioptimisasi. Misal, pada endpoint /all-students di-_highlight_ bagian kode mana yang berperan pada endpoint tersebut dan durasi untuk mendapatkan response pada method method dan juga line dalam method yang berperan pada endpoint tersebut. Hal ini membuat identifikasi kode bermasalah lebih mudah di IntelliJ Profiler. 
4. What are the main challenges you face when conducting performance testing and profiling, and how do you overcome these challenges
   - Menurut saya, tantangan utama dalam performance testing dan profiling adalah bagaimana untuk merefactor kodenya karena harus membuat kode berjalan lebih cepat dengan mempertahankan fungsinya. Selain itu, banyaknya detail pada profiler membuat saya bingung untuk mengambil infomrasi mana saja dari profiler yang relevan untuk refactoring karena bisa saja selain waktu eksekusi juga ada faktor lainnya. Cara saya untuk mengatasi hal tersebut adalah dengan memahami kode dan juga struktur data yang dipakainya agar bisa mengoptimisasi bagian kode tersebut agar bisa berjalan lebih cepat dan memakai memory lebih sedikit. Selain, itu saya juga mengambil waktu eksekusi sebagai poin utama dalam profiler untuk melakukan refactoring pada kode.
5. What are the main benefits you gain from using IntelliJ Profiler for profiling your application code?
   - IntelliJ Profiler sudah ada dalam IDE IntelliJ sehingga tidak perlu repot untuk meng_install_ dari luar IDE. Selain itu, karena analsisi dilakukan dalam IDE, saya bisa menghemat banyak waktu tanpa mengganti window. 
6. How do you handle situations where the results from profiling with IntelliJ Profiler are not entirely consistent with findings from performance testing using JMeter?
    - Biasanya hal yang berbeda adalah dalam waktu eksekusi dan juga durasi untuk mendapatkan response dan yang tidak konsisten juga terdapat pada angkanya yang tidak _matching_ 1:1. Cara saya untuk menangani hal ini adalah mencoba profiling dari kedua profiler berkali-kali dan membandingkan hasilnya. Apabila _gap_ dari hasil kedua profiler tidak terlalu jauh saya anggap valid. 
7. What strategies do you implement in optimizing application code after analyzing results from performance testing and profiling? How do you ensure the changes you make do not affect the application's functionality?
    - Pada aplikasi ini, karena menggunakan database, endpoint pada /all-student, /all-student-name, /highest-gpa seperti mendapatkan hasil dari suatu query dari SQL. JPARepository juga dapat melakukan parse method menjadi query SQL dan menurut saya hal ini yang menjadi kunci untuk refactoring pada kedua endpoint tersebut. Kemudian, untuk endpoint /all-student-name menggunakan StringBuilder dibandingkan String biasa karena sifatnya yang mutable sedangkan String immutable sehingga memakan lebih sedikit memory dan membuat aplikasi berjalan lebih cepat.

   [SCREENSHOTS]
   - Sebelum optimisasi
   - /all-student
     - ![Screenshot 2025-03-12 141647](https://github.com/user-attachments/assets/ee05eaa9-d12d-4394-8fe4-3aa2529a4132)
     - ![Screenshot 2025-03-12 142803](https://github.com/user-attachments/assets/a31bac0e-514f-495b-999c-a75f7cefd7e4)
   - /all-student-name
     -  ![Screenshot 2025-03-12 141327](https://github.com/user-attachments/assets/d636cd9c-38ab-482a-a028-70489e82fe31)
     -  ![Screenshot 2025-03-12 142833](https://github.com/user-attachments/assets/8aeed535-0260-4280-9042-92f33e8a4191)
   - /highest-gpa
     - ![Screenshot 2025-03-12 141915](https://github.com/user-attachments/assets/1db89d1d-511a-460e-8a4d-2b9848f21924)
     - ![Screenshot 2025-03-12 142847](https://github.com/user-attachments/assets/a5e461cf-a5a3-4367-8d7b-d483ee76889e)

- Setelah optimisasi
  - /all-student
    - ![Screenshot 2025-03-12 145718](https://github.com/user-attachments/assets/908261f2-7436-4715-a00d-7219ca5b1b6d)
    - ![Screenshot 2025-03-12 154136](https://github.com/user-attachments/assets/80a420fc-5b6a-4cd7-b660-383aef2421a8)
  - /all-student-name
    - ![Screenshot 2025-03-12 154947](https://github.com/user-attachments/assets/8aa71bb1-297c-4fc3-bc18-076a983a140f)
    - ![Screenshot 2025-03-12 155030](https://github.com/user-attachments/assets/ab9c19cd-ebc7-4f3d-9342-255a58ee667a)
  - /highest-gpa
    - ![Screenshot 2025-03-12 161805](https://github.com/user-attachments/assets/24c3cdfa-f638-4898-9d56-b2d7c83e5d82)
    - ![Screenshot 2025-03-12 161859](https://github.com/user-attachments/assets/773ce8ad-b8f3-4b65-a91e-ba09b242d406)


   - Kesimpulan
     - Waktu untuk melakukan request setelah melakukan optimisasi menurun signifikan untuk semua endpoint dan target untuk menurunkan durasi waktu untuk request sebanyak minimal 20% terpenuhi. 
  
