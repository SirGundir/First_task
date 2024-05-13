
# Шпаргалка по git

В этой шпаргалке я покажу как создать репозиторий,<br>
подключить его к GitHub, делать комиты

---

## Создаем репозиторий

```
mkdir 'Название папки'
git init
```

## Подключаем к репозиторию GitHub

```
git remote add irigin "Ссылка на реп"
git branch -M main 
```

## Добавим файл и закомитим его

```
git add file.txt
git commit -m "Пояснение к коммиту"
```

## Теперь отправим коммит на GitHub реп

```
git push -u origin main
git push
```
### Команда 1 для первого раза, а команда 2 для последующих

----

## Новые команды 

```
git log
```
### Выводит список коммитов с их хэшем, автором и датой
Хэш - сжатый набор данных, в котором есть информация о коммите:<br>
* Дата коммита
* Ссылка на род коммит
* Содержимое файлов в репе

Для хэширования используется алгоритм SHA-1
В git есть информация соответствий, где по хэшу можно получить<br> информацию и коммите

### HEAD
Файл HEAD содержит ссылку на последний коммит

### Статусы файлов
В git есть 4 статуса:
* Untacked - git не отслеживает файл
* Tracked - файл отслеживается, довольно обширно
* Modified - файл не совпадает со своей преведущей версией,<br>то есть он был изменен
* Staged - файл находиться в списке на коммит

### Жизненный цикл файлов в git

```mermaid
graph LR;
	untracked -- "git add" --> staged+tracked
	staged+tracked -- "git commit" --> tracked
	tracked -- "Изменения" --> modified
	modified -- "git add" --> staged+tracked
	staged+tracked -- "Изменения" --> modified
