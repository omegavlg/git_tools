# Домашнее задание к занятию "`Инструменты Git`" - `Дедюрин Денис`

### Клонируем репозиторий
<img src = "img/01.png" width = 100%>

---
## 1. Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.
### Переходим в директорию клонированного репозитория и выполняем команду:
```
git log --oneline | findstr "^aefea"
```
Где:
```
git log --oneline выводит список коммитов с сокращёнными хешами и комментариями.
findstr "^aefea" фильтрует строки, начинающиеся с aefea.
```
<img src = "img/02.png" width = 100%>

Для получения полного хеша воспользуемся командой:
```
git show aefead2207
```
<img src = "img/03.png" width = 100%>

Вывод будет содержать полную информацию о коммите, включая его полный хеш, автора, дату и изменения, сделанные в этом коммите.

---
## 2. Какому тегу соответствует коммит 85024d3?
### Чтобы узнать какому тегу соответствует коммит 85024d3 выполним команду:
```
git show 85024d3 --no-patch
```
<img src = "img/04.png" width = 100%>
Видим что этому коммиту соответствует тег v0.12.23

---
## 3. Сколько родителей у коммита b8d720? Напишите их хеши.
### Чтобы узнать сколько родителей у коммита b8d720, выполним команду:
```
git log -1 --pretty=format:%P b8d720
```
<img src = "img/05.png" width = 100%>
Хеши родителей:

```
56cd7859e05c36c06b56d013b55a252d0bb7e158
9ea88f22fc6269854151c571162c5bcf958bee2b
```
---
## 4. Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами v0.12.23 и v0.12.24.
### Для того чтобы перечислить хеши и комментарии всех коммитов, которые были сделаны между тегами v0.12.23 и v0.12.24, выполним команду:
```
git log v0.12.23..v0.12.24 --oneline
```
<img src = "img/06.png" width = 100%>
Результат выполнения:
```
33ff1c03bb (tag: v0.12.24) v0.12.24
b14b74c493 [Website] vmc provider links
3f235065b9 Update CHANGELOG.md
6ae64e247b registry: Fix panic when server is unreachable
5c619ca1ba website: Remove links to the getting started guide's old location
06275647e2 Update CHANGELOG.md
d5f9411f51 command: Fix bug when using terraform login on Windows
4b6d06cc5d Update CHANGELOG.md
dd01a35078 Update CHANGELOG.md
225466bc3e Cleanup after v0.12.23 release
```

