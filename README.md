# lab01

1. Скачайте библиотеку boost с помощью утилиты wget

$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz

2. Разархивируйте скаченный файл в директорию ~/boost_1_69_0

$ tar -xvf boost_1_69_0.tar.gz

![image](https://github.com/vladosfpv/lab01/assets/57360144/09a87270-7196-4dbe-a179-5d089c158e19)

3. Подсчитайте количество файлов в директории ~/boost_1_69_0 не включая вложенные директории

$ ls -l | grep "^-" | wc -l

![image](https://github.com/vladosfpv/lab01/assets/57360144/8cd3d334-4e36-4def-8b06-b146cb35f448)

4. Подсчитайте количество файлов в директории ~/boost_1_69_0 включая вложенные директории

$ ls -l -R | wc -l

![image](https://github.com/vladosfpv/lab01/assets/57360144/774fcacd-30aa-4953-9c87-6d2a5aeb4f26)

5. Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp)

$ ls -l -R | grep -c *.hpp
$ ls -l -R | grep -c *.cpp
$ ls -l -R | grep -v *.hpp | grep -v *.cpp | grep -v 'итого' | wc -l

![image](https://github.com/vladosfpv/lab01/assets/57360144/845d4f72-82e0-4a3e-973f-df7f25da8efc)

6. Найдите полный пусть до файла any.hpp внутри библиотеки boost

$ find $PWD -type f -name any.hpp

![image](https://github.com/vladosfpv/lab01/assets/57360144/2e20b444-3a8a-4eb3-8652-65d5e4e296d8)

7. Выведите в консоль все файлы, где упоминается последовательность boost::asio

$ grep -R -l "boost::asio"

![image](https://github.com/vladosfpv/lab01/assets/57360144/02102645-ed05-4935-9af9-1a6f860208f2)

8. Скомпилирутйе boost

$ ./bootstrap.sh --prefix=boost_output
$ ./b2 install

![image](https://github.com/vladosfpv/lab01/assets/57360144/4fb3700f-2448-41f0-ac94-320f570f7d3f)

9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs

$ mv ~/boost_1_69_0/boost_output/lib ~/boost-libs

![image](https://github.com/vladosfpv/lab01/assets/57360144/cfa7f807-cdc7-47af-b63e-51e0e03745e0)

10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории

$ du -h -a

![image](https://github.com/vladosfpv/lab01/assets/57360144/c3d17f75-51ff-45a1-b1ac-3f6f68771789)

11. Найдите топ 10 самых "тяжёлых"

$ du -h -a | sort -r -h | head -n 10

![image](https://github.com/vladosfpv/lab01/assets/57360144/03deed00-2edf-4105-b542-ee2cad51a9ee)
