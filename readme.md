# Тренировочный проект для работы с Git.

---

## Инициализация папок и файлов.

---

1. Инициализировать репозиторий можно с помощью команды `git init`.
2. Проверить статус, или состояние, репозитория поможет команда `git status`.
3. Если вы ошиблись и случайно инициализировали не ту папку, можно «разгитить» её — удалить скрытую подпапку .git. `rm -rf .git`

## Добавление файлов в репозиторий.

---

1. Команда `git add` позволяет подготовить файл к сохранению.
2. Команда `git add --all` подготовит к сохранению сразу все файлы.
3. С помощью `git add .` можно добавить в репозиторий текущую папку со всеми файлами.

## Добавление коммита(приветствуется комментарий с описанием сделанных изменений).

---

1. Коммит можно сделать с помощью команды `git commit`.
2. Ключ -m позволяет присвоить коммиту сообщение. Помните, что такие сообщения должны быть информативными: чётко описывать изменения.
3. С помощью команды `git log` можно просмотреть историю коммитов.


## Загрузка на удалённый репозиторий. 

---

>Когда компьютеры обмениваются данными в сети, они следуют сетевым протоколам (англ. network protocols) — правилам >обмена данными между компьютерами.
>Один из наиболее распространённых сетевых протоколов — *SSH* (от англ. Secure Shell Protocol). Он обеспечивает >безопасный обмен данными в сети. С помощью этого протокола можно получать данные с удалённого компьютера или >отправлять их на него. Трафик шифруется, поэтому протокол безопасен.
>*SSH* использует пару ключей для обеспечения безопасности — публичный и приватный: 
>Приватный ключ (англ. private key) хранится только на вашем компьютере и не должен передаваться кому-либо ещё. Он >используется для расшифровки данных.
>Публичный ключ (англ. public key) доступен всем и используется для шифрования данных. Они могут быть расшифрованы >парным приватным ключом.
>Только вы можете расшифровать данные с помощью приватного ключа, но любой владелец публичного ключа может их для вас >зашифровать. Эти два ключа связаны и образуют SSH-пару. В будущем вы наверняка будете использовать их для >взаимодействия с *GitHub* и другими удалёнными серверами.

- Для генерации SSH-пары используйте команду:

`ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"`

либо команду:

`ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"`

Если ваш пк не поддерживает протокол шифрования указанный выше.

2. Укажите место хранения ключей. Простой вариант — сделать домашний каталог пользователя путём по умолчанию. Для этого нажмите `Enter`.

3. Программа запросит кодовую фразу (англ. passphrase) для доступа к SSH-ключу. Вы можете оставить поле пустым. Для этого нажмите `Enter`, а затем ещё раз `Enter` для подтверждения.

4. Готово! Теперь осталось проверить, что ключи действительно сгенерировались. Для этого вызовите эту команду:
 
`ls -a ~/.ssh`

Итого:
-SSH — протокол, который обеспечивает безопасный обмен данными в сети и использует для этого ключи.
-SSH-ключ — ваш виртуальный идентификатор в GitHub. Как ключ от квартиры, он позволяет получить доступ к GitHub-репозиторию. Также SSH используется для доступа к другим удалённым серверам.
-SSH-ключ состоит из двух частей — публичной и приватной. Публичный ключ зашифрует данные, а приватный — расшифрует. Приватным ключом ни в коем случае нельзя делиться, иначе любой сможет расшифровать все ваши данные!

## Привязка удалённого репозитория к локальному.

---

1. Привязать удалённый репозиторий к локальному — `git remote add`.
Перейдите на страницу удалённого репозитория, выберите тип SSH и скопируйте URL. Кнопка справа позволит сделать это мгновенно.

`git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git`

2. Убедиться, что репозитории связаны:

```
git remote -v
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (fetch)
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (push)
```

## Отправка изменений на удаленный репозиторий.

---

`git push -u origin main` <br> 

Если команда приведёт к ошибке, попробуйте заменить `main` на `master`.

---

*README.md* — текстовый файл, который можно создать командой **touch**, а затем редактировать так же, как и любой другой текстовый документ. Например, в блокноте.

Преимущество *README.md* в том, что средства командной работы (такие, как GitHub) могут отображать его содержимое в браузере в виде удобной разметки.

Для этого нужно не просто залить текст, но и настроить шрифт, заголовки и отступы с помощью **markdown**.

*Маркда́у*н — это специальный язык разметки.

Он позволяет красиво отформатировать текстовый документ.

---

## Пример вставки кода в файл

```JavaScript
function closure () {
	let count = 0; 
	return () => count++
};

let counter = closure()
let counter1 = closure()

console.log(counter()) //0
console.log(counter()) //1
console.log(counter()) //2
console.log(counter()) //3
console.log(counter()) //4
console.log(counter1()) //0
console.log(counter1()) //1
console.log(counter()) //5
```

[Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/ "Клик")