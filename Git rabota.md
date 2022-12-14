# Работа в программе контроля версий Git.

**Подготовка к работе с Git**

1. Скачиваем программы Git и Visual Studio Code на свой компьютер.
2. На ПК создаем папку в которой будем работать (например: lesson 1)

**Начало работы в Git**

1. Запускаем программу Visual Studio Code
2. Открываем папку (Lesson 1). 

```проводник -> открыть папку```

3. Создаем файл в нашей папке (например: Git rabota.md). Обязательно в конце указать расширение файла.
4. Запускаем терминал, в котором будем писать команды. 

```вид -> терминал```

5. Проверяем, что Git настроен, вводим комманду в поле терминала
```
git version
```
Появляеются данные о версии установленного Git (например git version 2.37.3.windows.1).

6. Делаем инициализацию 
```
git init
```

7. Проверяем текущий статус
```
git status
```
* On branch master - текущая ветка мастер.
* No commits yet - нет коммитов (сохранений)

**Запись изменений в репозиторий**

1. В нашем файле напишем текст (например: Начало работы с Git). 
2. Сохраним текст

* Сохранение:   ```ctrl + S```
* Автосохранение :  ```файл -> автосохранение```

3. Сделаем наш файл отслеживаемым, чтобы в нем cделать коммит (сохранение)
```
git add Git rabota.md
```
4. Сохраняем изменения, текущий статус. В кавычках "..." пишем что изменили.
```
git commit -m "создали новый файл"
```
**Проверка сохраненных (закоммиченных) версий**

1. Для просмотра сохраненных закоммиченных версий вводим команду
```
git log
```
2. Для перехода между сохраненными версиями вводим комманду
```
git checkout 435d
```
после пробела указать первые четыре символа нужного сохранения, к которому необходимо перейти.

**Сравнение изменений сохранений (коммитов)**

1. Для промотра разницы межу текущей и сохраненной версиями необходимо ввести комменду
```
git diff
```
**Добавление изображения**

1. Для добавления изображения в Git необходимо в папку где мы работаем переместить изображение, которое мы хртим добавить. Далее написать следующую команду:
```
![название изображения](имя файла)
```
При этом если имя файла цказано с ошибкой или файла не существует - на месте изображения появится название изображения указанное в квадратных скобках [...]

например:

![логотип Git] (Git_iso.jpg) - без пробелов между скобками

![логотип Git](Git_iso.jpg)

**Игнирирование файлов**

1. В нашу папку, где мы работаем, добавляем специальный файл ```.gitignore```

2. В файл ```.gitignore``` добавляем файл, который мы хотим игнорировать например ```Git_iso.jpg,``` чтобы Git его пропускал. После этого файл ```Git_iso.jpg``` будет подсвечен серым.

3. выполняем комманды ```git add .gitignore``` и закоммичиваем ```git commit -m```

**Работа с ветками**

1. Для создания новой ветки необходимо ввести комманду 
```
git branch new branch
```
например:
``` 
git branch branch_1
```
2. Для просмотра списка веток необходимо ввести комманду
```
git branch
```
3. Для перехода на другую ветку необходимо ввести комманду
```
git checkout new branch
```
например:
```
git checkout branch_1
```
4. Для слияния веток необходимо ввести комманду
```
git merge new branch
```
При этом новая ветка сольестя с той, в которой  мы сейчас находимся.

5. Для удаления ветки необходимо ввести комманду 
```
git branch -d new branch
```
например:
```
 git branch -d branch_1
 ```
6. Конфликты при слиянии веток.

Если при слиянии веток окажется, что в некоторых  пунктах (позициях) информация будет разной

Например: в ветке ```master``` в пункте 1 будет одна информация, а в ветке ```branch_2``` мы в этот пункт внесем изменения, то при слиянии веток программа выдаст конфликт.

Решения могут быть следующие:

* Accept Current Change - принять текущую версию.
* Accept Incoming Change - принять пришедшую версию тз другой ветки.
* Accept Both Canges - оставить оба варианта.
* Conpare Changes - сравнить варианты.