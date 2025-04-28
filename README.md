michel@MichelUbuntu:~$ export GITHUB_TOKEN=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
michel@MichelUbuntu:~$ export GITHUB_USERNAME=MichelsonIU815
michel@MichelUbuntu:~$ export PACKAGE_MANAGER=apt
michel@MichelUbuntu:~$ export GPG_PACKAGE_NAME=gpg
michel@MichelUbuntu:~$ sudo $PACKAGE_MANAGER install xclip
[sudo] пароль для michel: 
Чтение списков пакетов… Готово
Построение дерева зависимостей… Готово
Чтение информации о состоянии… Готово         
Уже установлен пакет xclip самой новой версии (0.13-3).
Обновлено 0 пакетов, установлено 0 новых пакетов, для удаления отмечено 0 пакетов, и 147 пакетов не обновлено.
michel@MichelUbuntu:~$ alias gsed=sed
michel@MichelUbuntu:~$ alias pbcopy='xclip -selection clipboard'
michel@MichelUbuntu:~$ alias pbpaste='xclip -selection clipboard -o'
michel@MichelUbuntu:~$ cd ${GITHUB_USERNAME}/workspace
michel@MichelUbuntu:~/MichelsonIU815/workspace$ pushd .
~/MichelsonIU815/workspace ~/MichelsonIU815/workspace
michel@MichelUbuntu:~/MichelsonIU815/workspace$ source scripts/activate
michel@MichelUbuntu:~/MichelsonIU815/workspace$ go get github.com/aktau/github-release
go: go.mod file not found in current directory or any parent directory.
	'go get' is no longer supported outside a module.
	To build and install a command, use 'go install' with a version,
	like 'go install example.com/cmd@latest'
	For more information, see https://golang.org/doc/go-get-install-deprecation
	or run 'go help get' or 'go help install'.
michel@MichelUbuntu:~/MichelsonIU815/workspace$ go install github.com/aktau/github-release@latest
go: finding module for package github.com/voxelbrain/goptions
go: finding module for package github.com/dustin/go-humanize
go: finding module for package github.com/github-release/github-release/github
go: found github.com/dustin/go-humanize in github.com/dustin/go-humanize v1.0.1
go: found github.com/github-release/github-release/github in github.com/github-release/github-release v0.10.1
go: found github.com/voxelbrain/goptions in github.com/voxelbrain/goptions v0.0.0-20180630082107-58cddc247ea2
go: finding module for package github.com/kevinburke/rest/restclient
go: finding module for package github.com/tomnomnom/linkheader
go: found github.com/kevinburke/rest/restclient in github.com/kevinburke/rest v0.0.0-20240617045629-3ed0ad3487f0
go: found github.com/tomnomnom/linkheader in github.com/tomnomnom/linkheader v0.0.0-20180905144013-02ca5825eb80
michel@MichelUbuntu:~/MichelsonIU815/workspace$ git clone https://github.com/${GITHUB_USERNAME}/lab08 projects/lab09
Клонирование в «projects/lab09»...
remote: Enumerating objects: 120, done.
remote: Counting objects: 100% (120/120), done.
remote: Compressing objects: 100% (101/101), done.
remote: Total 120 (delta 18), reused 0 (delta 0), pack-reused 0 (from 0)
Получение объектов: 100% (120/120), 790.67 КиБ | 3.11 МиБ/с, готово.
Определение изменений: 100% (18/18), готово.
michel@MichelUbuntu:~/MichelsonIU815/workspace$ cd projects/lab09
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git remote remove origin
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab09
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ gsed -i 's/lab08/lab09/g' README.md
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ $PACKAGE_MANAGER install ${GPG_PACKAGE_NAME}
E: Не удалось открыть файл блокировки /var/lib/dpkg/lock-frontend - open (13: Отказано в доступе)
E: Невозможно получить блокировку внешнего интерфейса dpkg (/var/lib/dpkg/lock-frontend); у вас есть права суперпользователя?
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ sudo $PACKAGE_MANAGER install ${GPG_PACKAGE_NAME}
Чтение списков пакетов… Готово
Построение дерева зависимостей… Готово
Чтение информации о состоянии… Готово         
Уже установлен пакет gpg самой новой версии (2.4.4-2ubuntu17.2).
Обновлено 0 пакетов, установлено 0 новых пакетов, для удаления отмечено 0 пакетов, и 147 пакетов не обновлено.
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$  gpg --list-secret-keys --keyid-format LONG
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ gpg --full-generate-key 
gpg (GnuPG) 2.4.4; Copyright (C) 2024 g10 Code GmbH
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Выберите тип ключа:
   (1) RSA и RSA
   (2) DSA и Elgamal
   (3) DSA (sign only)
   (4) RSA (sign only)
   (9) ECC (подписание и шифрование) *по умолчанию*
  (10) ECC (только для подписи)
  (14) Существующий ключ с карты 
Ваш выбор? 1
длина ключей RSA может быть от 1024 до 4096.
Какой размер ключа Вам необходим? (3072) 4096
Запрошенный размер ключа - 4096 бит
Выберите срок действия ключа.
         0 = не ограничен
      <n>  = срок действия ключа - n дней
      <n>w = срок действия ключа - n недель
      <n>m = срок действия ключа - n месяцев
      <n>y = срок действия ключа - n лет
Срок действия ключа? (0) 1y
Ключ действителен до Вт 28 апр 2026 13:32:46 MSK
Все верно? (y/N) y

GnuPG должен составить идентификатор пользователя для идентификации ключа.

Ваше полное имя: Mikedr
Адрес электронной почты: m.a.dmitriyev@mail.ru
Примечание: i
Вы выбрали следующий идентификатор пользователя:
    "Mikedr (i) <m.a.dmitriyev@mail.ru>"

Сменить (N)Имя, (C)Примечание, (E)Адрес; (O)Принять/(Q)Выход? O
Необходимо получить много случайных чисел. Желательно, чтобы Вы
в процессе генерации выполняли какие-то другие действия (печать
на клавиатуре, движения мыши, обращения к дискам); это даст генератору
случайных чисел больше возможностей получить достаточное количество энтропии.
Необходимо получить много случайных чисел. Желательно, чтобы Вы
в процессе генерации выполняли какие-то другие действия (печать
на клавиатуре, движения мыши, обращения к дискам); это даст генератору
случайных чисел больше возможностей получить достаточное количество энтропии.
gpg: создан каталог '/home/michel/.gnupg/openpgp-revocs.d'
gpg: сертификат отзыва записан в '/home/michel/.gnupg/openpgp-revocs.d/4CC1632CDE6132F34C92FD89375C74C7AE5A71DA.rev'.
открытый и секретный ключи созданы и подписаны.

pub   rsa4096 2025-04-28 [SC] [годен до: 2026-04-28]
      4CC1632CDE6132F34C92FD89375C74C7AE5A71DA
uid                      Mikedr (i) <m.a.dmitriyev@mail.ru>
sub   rsa4096 2025-04-28 [E] [годен до: 2026-04-28]

michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ gpg --list-secret-keys --keyid-format LONG
gpg: проверка таблицы доверия
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
gpg: глубина: 0  достоверных:   1  подписанных:   0  доверие: 0-, 0q, 0n, 0m, 0f, 1u
gpg: срок следующей проверки таблицы доверия 2026-04-28
/home/michel/.gnupg/pubring.kbx
-------------------------------
sec   rsa4096/375C74C7AE5A71DA 2025-04-28 [SC] [годен до: 2026-04-28]
      4CC1632CDE6132F34C92FD89375C74C7AE5A71DA
uid               [  абсолютно ] Mikedr (i) <m.a.dmitriyev@mail.ru>
ssb   rsa4096/41A61A143D243D7B 2025-04-28 [E] [годен до: 2026-04-28]

michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ gpg -K ${GITHUB_USERNAME}
gpg: error reading key: Нет секретного ключа
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ gpg --list-secret-keys --keyid-format LONG
/home/michel/.gnupg/pubring.kbx
-------------------------------
sec   rsa4096/375C74C7AE5A71DA 2025-04-28 [SC] [годен до: 2026-04-28]
      4CC1632CDE6132F34C92FD89375C74C7AE5A71DA
uid               [  абсолютно ] Mikedr (i) <m.a.dmitriyev@mail.ru>
ssb   rsa4096/41A61A143D243D7B 2025-04-28 [E] [годен до: 2026-04-28]

michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ GPG_KEY_ID=$(gpg --list-secret-keys --keyid-format LONG | grep ssb | tail -1 | awk '{print $2}' | awk -F'/' '{print $2}')
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ GPG_SEC_KEY_ID=$(gpg --list-secret-keys --keyid-format LONG | grep sec | tail -1 | awk '{print $2}' | awk -F'/' '{print $2}')
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ gpg --armor --export ${GPG_KEY_ID} | pbcopy
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ pbpaste
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ open https://github.com/settings/keysgs/keys
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ Gtk-Message: 13:36:45.363: Not loading module "atk-bridge": The functionality is provided by GTK natively. Please try to not michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ open https://github.com/settings/keysttps://github.com/settings/keys
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ Gtk-Message: 13:37:02.090: Not loading module "atk-bridge": The functionality is provided by GTK natively. Please try to not michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git config user.signingkey ${GPG_SEC_KEY_ID}er.signingkey ${GPG_SEC_KEY_ID}
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git config user.signingkey ${GPG_SEC_KEY_ID}
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git config gpg.program gpg
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ test -r ~/.bash_profile && echo 'export GPG_TTY=$(tty)' >> ~/.bash_profile
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ echo 'export GPG_TTY=$(tty)' >> ~/.profile
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ cmake -H. -B_build -DCPACK_GENERATOR="TGZ"
-- [hunter] Initializing Hunter workspace (572541b3a9e2c1ccb0c0e552f6dc12219c0d6a0b)
-- [hunter]   https://github.com/cpp-pm/hunter/archive/v0.23.314.tar.gz
-- [hunter]   -> /home/michel/.hunter/_Base/Download/Hunter/0.23.314/572541b
CMake Error at Build/Hunter-prefix/src/Hunter-stamp/download-Hunter.cmake:170 (message):
  Each download failed!

    
    


gmake[2]: *** [CMakeFiles/Hunter.dir/build.make:99: Hunter-prefix/src/Hunter-stamp/Hunter-download] Ошибка 1
gmake[1]: *** [CMakeFiles/Makefile2:83: CMakeFiles/Hunter.dir/all] Ошибка 2
gmake: *** [Makefile:91: all] Ошибка 2

[hunter ** INTERNAL **] Build project failed
[hunter ** INTERNAL **] [Directory:/home/michel/MichelsonIU815/workspace/projects/lab09]

------------------------------ ERROR ------------------------------
    https://hunter.readthedocs.io/en/latest/reference/errors/error.internal.html
-------------------------------------------------------------------

CMake Error at cmake/HunterGate.cmake:88 (message):
Call Stack (most recent call first):
  cmake/HunterGate.cmake:98 (hunter_gate_error_page)
  cmake/HunterGate.cmake:347 (hunter_gate_internal_error)
  cmake/HunterGate.cmake:511 (hunter_gate_download)
  CMakeLists.txt:4 (HunterGate)


-- Configuring incomplete, errors occurred!
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ rm -rf ~/.hunter
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ cmake -H. -B_build -DCPACK_GENERATOR="TGZ" -DHUNTER_ROOT=/path/to/local/hunter
CMake Error at cmake/HunterGate.cmake:237 (file):
  directory

    "/path/to/local/hunter/_Base/Download/Hunter/0.23.314/572541b"

  creation failed (check permissions).
Call Stack (most recent call first):
  cmake/HunterGate.cmake:511 (hunter_gate_download)
  CMakeLists.txt:4 (HunterGate)


-- Configuring incomplete, errors occurred!
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ mkdir -p ~/hunter_download
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ cd ~/hunter_download
michel@MichelUbuntu:~/hunter_download$ wget https://github.com/cpp-pm/hunter/archive/v0.23.314.tar.gz
--2025-04-28 13:42:57--  https://github.com/cpp-pm/hunter/archive/v0.23.314.tar.gz
Распознаётся github.com (github.com)… 140.82.121.3
Подключение к github.com (github.com)|140.82.121.3|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа… 302 Found
Адрес: https://codeload.github.com/cpp-pm/hunter/tar.gz/refs/tags/v0.23.314 [переход]
--2025-04-28 13:42:57--  https://codeload.github.com/cpp-pm/hunter/tar.gz/refs/tags/v0.23.314
Распознаётся codeload.github.com (codeload.github.com)… 140.82.121.9
Подключение к codeload.github.com (codeload.github.com)|140.82.121.9|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа… 200 OK
Длина: 2725603 (2,6M) [application/x-gzip]
Сохранение в: ‘v0.23.314.tar.gz’

v0.23.314.tar.gz        100%[=============================>]   2,60M  2,38MB/s    за 1,1s    

2025-04-28 13:42:59 (2,38 MB/s) - ‘v0.23.314.tar.gz’ сохранён [2725603/2725603]

michel@MichelUbuntu:~/hunter_download$ tar xzf v0.23.314.tar.gz
michel@MichelUbuntu:~/hunter_download$ cmake -H. -B_build \
>     -DCPACK_GENERATOR="TGZ" \
>     -DHUNTER_ROOT=~/hunter_download/hunter-0.23.314
CMake Error: The source directory "/home/michel/hunter_download" does not appear to contain CMakeLists.txt.
Specify --help for usage, or press the help button on the CMake GUI.
michel@MichelUbuntu:~/hunter_download$ cd ~/MichelsonIU815/workspace/projects/lab09
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ cmake -H. -B_build \
>     -DCPACK_GENERATOR="TGZ" \
>     -DHUNTER_ROOT=~/hunter_download/hunter-0.23.314
CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_private_data.cmake:12 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:35 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_initialize.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:36 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


-- The C compiler identification is GNU 9.5.0
-- The CXX compiler identification is GNU 9.5.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- [hunter] Calculating Toolchain-SHA1
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- [hunter] Calculating Config-SHA1
-- [hunter] HUNTER_ROOT: /home/michel/hunter_download/hunter-0.23.314
-- [hunter] [ Hunter-ID: xxxxxxx | Toolchain-ID: d43c700 | Config-ID: c8a7791 ]
CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


-- [hunter] GTEST_ROOT: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Install (ver.: 1.11.0)
-- [hunter] Building GTest
loading initial cache file /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/cache.cmake
loading initial cache file /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/args.cmake
CMake Deprecation Warning at CMakeLists.txt:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- The C compiler identification is GNU 9.5.0
-- The CXX compiler identification is GNU 9.5.0
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
CMake Warning (dev) at /usr/share/cmake-3.28/Modules/ExternalProject.cmake:3195 (message):
  The DOWNLOAD_EXTRACT_TIMESTAMP option was not given and policy CMP0135 is
  not set.  The policy's OLD behavior will be used.  When using a URL
  download, the timestamps of extracted files should preferably be that of
  the time of extraction, otherwise code that depends on the extracted
  contents might not be rebuilt if the URL changes.  The OLD behavior
  preserves the timestamps from the archive instead, but this is usually not
  what you want.  Update your project to the NEW behavior or specify the
  DOWNLOAD_EXTRACT_TIMESTAMP option with a value of true to avoid this
  robustness issue.
Call Stack (most recent call first):
  /usr/share/cmake-3.28/Modules/ExternalProject.cmake:4418 (_ep_add_download_command)
  CMakeLists.txt:152 (ExternalProject_Add)
This warning is for project developers.  Use -Wno-dev to suppress it.

CMake Warning (dev) at /usr/share/cmake-3.28/Modules/ExternalProject.cmake:3195 (message):
  The DOWNLOAD_EXTRACT_TIMESTAMP option was not given and policy CMP0135 is
  not set.  The policy's OLD behavior will be used.  When using a URL
  download, the timestamps of extracted files should preferably be that of
  the time of extraction, otherwise code that depends on the extracted
  contents might not be rebuilt if the URL changes.  The OLD behavior
  preserves the timestamps from the archive instead, but this is usually not
  what you want.  Update your project to the NEW behavior or specify the
  DOWNLOAD_EXTRACT_TIMESTAMP option with a value of true to avoid this
  robustness issue.
Call Stack (most recent call first):
  /usr/share/cmake-3.28/Modules/ExternalProject.cmake:4418 (_ep_add_download_command)
  CMakeLists.txt:152 (ExternalProject_Add)
This warning is for project developers.  Use -Wno-dev to suppress it.

-- Configuring done (0.3s)
-- Generating done (0.0s)
-- Build files have been written to: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Build
[  6%] Creating directories for 'GTest-Release'
[ 12%] Performing download step (download, verify and extract) for 'GTest-Release'
-- Downloading...
   dst='/home/michel/hunter_download/hunter-0.23.314/_Base/Download/GTest/1.11.0/7b100bb/release-1.11.0.tar.gz'
   timeout='none'
   inactivity timeout='none'
-- Using src='https://github.com/google/googletest/archive/release-1.11.0.tar.gz'
-- [download 1% complete]
-- [download 2% complete]
-- [download 3% complete]
-- [download 4% complete]
-- [download 5% complete]
-- [download 6% complete]
-- [download 7% complete]
-- [download 8% complete]
-- [download 9% complete]
-- [download 10% complete]
-- [download 11% complete]
-- [download 12% complete]
-- [download 13% complete]
-- [download 15% complete]
-- [download 17% complete]
-- [download 20% complete]
-- [download 21% complete]
-- [download 23% complete]
-- [download 24% complete]
-- [download 25% complete]
-- [download 26% complete]
-- [download 31% complete]
-- [download 35% complete]
-- [download 38% complete]
-- [download 40% complete]
-- [download 46% complete]
-- [download 49% complete]
-- [download 51% complete]
-- [download 55% complete]
-- [download 57% complete]
-- [download 61% complete]
-- [download 67% complete]
-- [download 72% complete]
-- [download 74% complete]
-- [download 75% complete]
-- [download 76% complete]
-- [download 79% complete]
-- [download 80% complete]
-- [download 85% complete]
-- [download 86% complete]
-- [download 93% complete]
-- [download 96% complete]
-- [download 97% complete]
-- [download 98% complete]
-- [download 99% complete]
-- [download 100% complete]
-- verifying file...
       file='/home/michel/hunter_download/hunter-0.23.314/_Base/Download/GTest/1.11.0/7b100bb/release-1.11.0.tar.gz'
-- Downloading... done
-- extracting...
     src='/home/michel/hunter_download/hunter-0.23.314/_Base/Download/GTest/1.11.0/7b100bb/release-1.11.0.tar.gz'
     dst='/home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Source'
-- extracting... [tar xfz]
-- extracting... [analysis]
-- extracting... [rename]
-- extracting... [clean up]
-- extracting... done
[ 18%] No update step for 'GTest-Release'
[ 25%] No patch step for 'GTest-Release'
[ 31%] Performing configure step for 'GTest-Release'
loading initial cache file /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/cache.cmake
loading initial cache file /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/args.cmake
CMake Deprecation Warning at CMakeLists.txt:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- The C compiler identification is GNU 9.5.0
-- The CXX compiler identification is GNU 9.5.0
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
CMake Deprecation Warning at googlemock/CMakeLists.txt:45 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


CMake Deprecation Warning at googletest/CMakeLists.txt:56 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- Found Python: /usr/bin/python3 (found version "3.12.3") found components: Interpreter 
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD - Success
-- Found Threads: TRUE  
-- Configuring done (0.6s)
-- Generating done (0.0s)
-- Build files have been written to: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Build/GTest-Release-prefix/src/GTest-Release-build
[ 37%] Performing build step for 'GTest-Release'
[ 12%] Building CXX object googletest/CMakeFiles/gtest.dir/src/gtest-all.cc.o
[ 25%] Linking CXX static library ../lib/libgtest.a
[ 25%] Built target gtest
[ 50%] Building CXX object googlemock/CMakeFiles/gmock.dir/src/gmock-all.cc.o
[ 50%] Building CXX object googletest/CMakeFiles/gtest_main.dir/src/gtest_main.cc.o
[ 62%] Linking CXX static library ../lib/libgtest_main.a
[ 62%] Built target gtest_main
[ 75%] Linking CXX static library ../lib/libgmock.a
[ 75%] Built target gmock
[ 87%] Building CXX object googlemock/CMakeFiles/gmock_main.dir/src/gmock_main.cc.o
[100%] Linking CXX static library ../lib/libgmock_main.a
[100%] Built target gmock_main
[ 43%] Performing install step for 'GTest-Release'
[ 25%] Built target gtest
[ 50%] Built target gmock
[ 75%] Built target gmock_main
[100%] Built target gtest_main
Install the project...
-- Install configuration: "Release"
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/custom
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/custom/README.md
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/custom/gmock-matchers.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/custom/gmock-generated-actions.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/custom/gmock-port.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/gmock-pp.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/gmock-port.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/gmock-internal-utils.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-cardinalities.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-more-actions.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-matchers.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-nice-strict.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-actions.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-more-matchers.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-function-mocker.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-spec-builders.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/libgmock.a
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/libgmock_main.a
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/pkgconfig/gmock.pc
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/pkgconfig/gmock_main.pc
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/cmake/GTest/GTestTargets.cmake
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/cmake/GTest/GTestTargets-release.cmake
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/cmake/GTest/GTestConfigVersion.cmake
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/cmake/GTest/GTestConfig.cmake
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-filepath.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-port.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-internal.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-string.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-param-util.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/custom
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/custom/gtest-port.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/custom/README.md
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/custom/gtest-printers.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/custom/gtest.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-port-arch.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-death-test-internal.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-type-util.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest_pred_impl.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-matchers.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest_prod.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-printers.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-death-test.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-typed-test.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-message.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-spi.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-test-part.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-param-test.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/libgtest.a
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/libgtest_main.a
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/pkgconfig/gtest.pc
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/pkgconfig/gtest_main.pc
loading initial cache file /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/args.cmake
CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/scripts/try-copy-license.cmake:5 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


[ 50%] Completed 'GTest-Release'
[ 50%] Built target GTest-Release
[ 56%] Creating directories for 'GTest-Debug'
[ 62%] Performing download step (download, verify and extract) for 'GTest-Debug'
-- verifying file...
       file='/home/michel/hunter_download/hunter-0.23.314/_Base/Download/GTest/1.11.0/7b100bb/release-1.11.0.tar.gz'
-- File already exists and hash match (skip download):
  file='/home/michel/hunter_download/hunter-0.23.314/_Base/Download/GTest/1.11.0/7b100bb/release-1.11.0.tar.gz'
  SHA1='7b100bb68db8df1060e178c495f3cbe941c9b058'
-- extracting...
     src='/home/michel/hunter_download/hunter-0.23.314/_Base/Download/GTest/1.11.0/7b100bb/release-1.11.0.tar.gz'
     dst='/home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Source'
-- extracting... [tar xfz]
-- extracting... [analysis]
-- extracting... [rename]
-- extracting... [clean up]
-- extracting... done
[ 68%] No update step for 'GTest-Debug'
[ 75%] No patch step for 'GTest-Debug'
[ 81%] Performing configure step for 'GTest-Debug'
loading initial cache file /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/cache.cmake
loading initial cache file /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/args.cmake
CMake Deprecation Warning at CMakeLists.txt:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- The C compiler identification is GNU 9.5.0
-- The CXX compiler identification is GNU 9.5.0
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
CMake Deprecation Warning at googlemock/CMakeLists.txt:45 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


CMake Deprecation Warning at googletest/CMakeLists.txt:56 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- Found Python: /usr/bin/python3 (found version "3.12.3") found components: Interpreter 
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD - Success
-- Found Threads: TRUE  
-- Configuring done (0.6s)
-- Generating done (0.0s)
-- Build files have been written to: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Build/GTest-Debug-prefix/src/GTest-Debug-build
[ 87%] Performing build step for 'GTest-Debug'
[ 12%] Building CXX object googletest/CMakeFiles/gtest.dir/src/gtest-all.cc.o
[ 25%] Linking CXX static library ../lib/libgtestd.a
[ 25%] Built target gtest
[ 37%] Building CXX object googletest/CMakeFiles/gtest_main.dir/src/gtest_main.cc.o
[ 50%] Building CXX object googlemock/CMakeFiles/gmock.dir/src/gmock-all.cc.o
[ 62%] Linking CXX static library ../lib/libgtest_maind.a
[ 62%] Built target gtest_main
[ 75%] Linking CXX static library ../lib/libgmockd.a
[ 75%] Built target gmock
[ 87%] Building CXX object googlemock/CMakeFiles/gmock_main.dir/src/gmock_main.cc.o
[100%] Linking CXX static library ../lib/libgmock_maind.a
[100%] Built target gmock_main
[ 93%] Performing install step for 'GTest-Debug'
[ 25%] Built target gtest
[ 50%] Built target gmock
[ 75%] Built target gmock_main
[100%] Built target gtest_main
Install the project...
-- Install configuration: "Debug"
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/custom
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/custom/README.md
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/custom/gmock-matchers.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/custom/gmock-generated-actions.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/custom/gmock-port.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/gmock-pp.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/gmock-port.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/internal/gmock-internal-utils.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-cardinalities.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-more-actions.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-matchers.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-nice-strict.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-actions.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-more-matchers.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-function-mocker.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gmock/gmock-spec-builders.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/libgmockd.a
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/libgmock_maind.a
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/pkgconfig/gmock.pc
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/pkgconfig/gmock_main.pc
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/cmake/GTest/GTestTargets.cmake
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/cmake/GTest/GTestTargets-debug.cmake
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/cmake/GTest/GTestConfigVersion.cmake
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/cmake/GTest/GTestConfig.cmake
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-filepath.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-port.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-internal.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-string.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-param-util.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/custom
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/custom/gtest-port.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/custom/README.md
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/custom/gtest-printers.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/custom/gtest.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-port-arch.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-death-test-internal.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/internal/gtest-type-util.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest_pred_impl.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-matchers.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest_prod.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-printers.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-death-test.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-typed-test.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-message.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-spi.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-test-part.h
-- Up-to-date: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/include/gtest/gtest-param-test.h
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/libgtestd.a
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/libgtest_maind.a
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/pkgconfig/gtest.pc
-- Installing: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/Install/lib/pkgconfig/gtest_main.pc
loading initial cache file /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest/args.cmake
CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/scripts/try-copy-license.cmake:5 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


[100%] Completed 'GTest-Debug'
[100%] Built target GTest-Debug
-- [hunter] Build step successful (dir: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Build/GTest)
-- [hunter] Cache saved: /home/michel/hunter_download/hunter-0.23.314/_Base/Cache/raw/d5307088880daf852fab772109534b36bb0ae5b8.tar.bz2
CMake Warning (dev) at CMakeLists.txt:15 (find_package):
  Policy CMP0144 is not set: find_package uses upper-case <PACKAGENAME>_ROOT
  variables.  Run "cmake --help-policy CMP0144" for policy details.  Use the
  cmake_policy command to set the policy and suppress this warning.

  CMake variable GTEST_ROOT is set to:

    /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Install

  Environment variable GTEST_ROOT is set to:

    /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Install

  For compatibility, find_package is ignoring the variable, but code in a
  .cmake module might still use it.
This warning is for project developers.  Use -Wno-dev to suppress it.

-- Found GTest: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Install/lib/cmake/GTest/GTestConfig.cmake (found version "1.11.0")  
-- Configuring done (28.1s)
-- Generating done (0.0s)
-- Build files have been written to: /home/michel/MichelsonIU815/workspace/projects/lab09/_build
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ cmake -H. -B_build -DCPACK_GENERATOR="TGZ"
CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_private_data.cmake:12 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:35 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_initialize.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:36 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:4 (HunterGate)


-- [hunter] Calculating Toolchain-SHA1
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- [hunter] Calculating Config-SHA1
-- [hunter] HUNTER_ROOT: /home/michel/hunter_download/hunter-0.23.314
-- [hunter] [ Hunter-ID: xxxxxxx | Toolchain-ID: d43c700 | Config-ID: c8a7791 ]
CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:14 (hunter_add_package)


-- [hunter] GTEST_ROOT: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Install (ver.: 1.11.0)
CMake Warning (dev) at CMakeLists.txt:15 (find_package):
  Policy CMP0144 is not set: find_package uses upper-case <PACKAGENAME>_ROOT
  variables.  Run "cmake --help-policy CMP0144" for policy details.  Use the
  cmake_policy command to set the policy and suppress this warning.

  CMake variable GTEST_ROOT is set to:

    /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Install

  Environment variable GTEST_ROOT is set to:

    /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Install

  For compatibility, find_package is ignoring the variable, but code in a
  .cmake module might still use it.
This warning is for project developers.  Use -Wno-dev to suppress it.

-- Configuring done (1.2s)
-- Generating done (0.0s)
-- Build files have been written to: /home/michel/MichelsonIU815/workspace/projects/lab09/_build
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ cmake --build _build --target package
gmake: *** Нет правила для сборки цели «package».  Останов.
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ rm -rf _build
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ cmake -H. -B_build -DCPACK_GENERATOR="TGZ"
-- [hunter] Initializing Hunter workspace (572541b3a9e2c1ccb0c0e552f6dc12219c0d6a0b)
-- [hunter]   https://github.com/cpp-pm/hunter/archive/v0.23.314.tar.gz
-- [hunter]   -> /home/michel/.hunter/_Base/Download/Hunter/0.23.314/572541b
CMake Error at Build/Hunter-prefix/src/Hunter-stamp/download-Hunter.cmake:170 (message):
  Each download failed!

    
    


gmake[2]: *** [CMakeFiles/Hunter.dir/build.make:99: Hunter-prefix/src/Hunter-stamp/Hunter-download] Ошибка 1
gmake[1]: *** [CMakeFiles/Makefile2:83: CMakeFiles/Hunter.dir/all] Ошибка 2
gmake: *** [Makefile:91: all] Ошибка 2

[hunter ** INTERNAL **] Build project failed
[hunter ** INTERNAL **] [Directory:/home/michel/MichelsonIU815/workspace/projects/lab09]

------------------------------ ERROR ------------------------------
    https://hunter.readthedocs.io/en/latest/reference/errors/error.internal.html
-------------------------------------------------------------------

CMake Error at cmake/HunterGate.cmake:88 (message):
Call Stack (most recent call first):
  cmake/HunterGate.cmake:98 (hunter_gate_error_page)
  cmake/HunterGate.cmake:347 (hunter_gate_internal_error)
  cmake/HunterGate.cmake:511 (hunter_gate_download)
  CMakeLists.txt:4 (HunterGate)


-- Configuring incomplete, errors occurred!
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ mkdir -p ~/hunter_download
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ cd ~/hunter_download
michel@MichelUbuntu:~/hunter_download$ wget https://github.com/cpp-pm/hunter/archive/v0.23.314.tar.gz
--2025-04-28 13:52:14--  https://github.com/cpp-pm/hunter/archive/v0.23.314.tar.gz
Распознаётся github.com (github.com)… 140.82.121.4
Подключение к github.com (github.com)|140.82.121.4|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа… 302 Found
Адрес: https://codeload.github.com/cpp-pm/hunter/tar.gz/refs/tags/v0.23.314 [переход]
--2025-04-28 13:52:15--  https://codeload.github.com/cpp-pm/hunter/tar.gz/refs/tags/v0.23.314
Распознаётся codeload.github.com (codeload.github.com)… 140.82.121.10
Подключение к codeload.github.com (codeload.github.com)|140.82.121.10|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа… 200 OK
Длина: 2725603 (2,6M) [application/x-gzip]
Сохранение в: ‘v0.23.314.tar.gz.1’

v0.23.314.tar.gz.1      100%[=============================>]   2,60M  2,31MB/s    за 1,1s    

2025-04-28 13:52:16 (2,31 MB/s) - ‘v0.23.314.tar.gz.1’ сохранён [2725603/2725603]

michel@MichelUbuntu:~/hunter_download$ tar xzf v0.23.314.tar.gz
michel@MichelUbuntu:~/hunter_download$ rm -rf _build ~/.hunter
michel@MichelUbuntu:~/hunter_download$ cmake -H. -B_build -DCPACK_GENERATOR="TGZ" -DHUNTER_ENABLED=ON
CMake Error: The source directory "/home/michel/hunter_download" does not appear to contain CMakeLists.txt.
Specify --help for usage, or press the help button on the CMake GUI.
michel@MichelUbuntu:~/hunter_download$ cd ~/MichelsonIU815/workspace/projects/lab09
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ rm -rf _build
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ cmake -H. -B_build \
>     -DCPACK_GENERATOR="TGZ" \
>     -DHUNTER_DISABLE=ON
CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:6 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:6 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:6 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:6 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:6 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:6 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:6 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:6 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:6 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:6 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:34 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:6 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_private_data.cmake:12 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:35 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:6 (HunterGate)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_initialize.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/Hunter:36 (include)
  cmake/HunterGate.cmake:540 (include)
  CMakeLists.txt:6 (HunterGate)


-- The C compiler identification is GNU 9.5.0
-- The CXX compiler identification is GNU 9.5.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- [hunter] Calculating Toolchain-SHA1
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- [hunter] Calculating Config-SHA1
-- [hunter] HUNTER_ROOT: /home/michel/hunter_download/hunter-0.23.314
-- [hunter] [ Hunter-ID: xxxxxxx | Toolchain-ID: d43c700 | Config-ID: c8a7791 ]
CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_config_sha1.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:9 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_toolchain_sha1.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:10 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_set_config_location.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_apply_gate_settings.cmake:13 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_calculate_self.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_finalize.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_cache_run.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_load_from_cache.cmake:6 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:22 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_create_cache_meta_directory.cmake:5 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:4 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


CMake Deprecation Warning at /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_lock_directory.cmake:4 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.
Call Stack (most recent call first):
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_make_directory.cmake:7 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_save_to_cache.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_download.cmake:26 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/projects/GTest/hunter.cmake:8 (include)
  /home/michel/hunter_download/hunter-0.23.314/cmake/modules/hunter_add_package.cmake:62 (include)
  CMakeLists.txt:15 (hunter_add_package)


-- [hunter] GTEST_ROOT: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Install (ver.: 1.11.0)
CMake Warning (dev) at CMakeLists.txt:16 (find_package):
  Policy CMP0144 is not set: find_package uses upper-case <PACKAGENAME>_ROOT
  variables.  Run "cmake --help-policy CMP0144" for policy details.  Use the
  cmake_policy command to set the policy and suppress this warning.

  CMake variable GTEST_ROOT is set to:

    /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Install

  Environment variable GTEST_ROOT is set to:

    /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Install

  For compatibility, find_package is ignoring the variable, but code in a
  .cmake module might still use it.
This warning is for project developers.  Use -Wno-dev to suppress it.

-- Found GTest: /home/michel/hunter_download/hunter-0.23.314/_Base/xxxxxxx/d43c700/c8a7791/Install/lib/cmake/GTest/GTestConfig.cmake (found version "1.11.0")  
-- Configuring done (2.1s)
-- Generating done (0.0s)
CMake Warning:
  Manually-specified variables were not used by the project:

    HUNTER_DISABLE


-- Build files have been written to: /home/michel/MichelsonIU815/workspace/projects/lab09/_build
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ ls -la CMakeLists.txt
-rw-rw-r-- 1 michel michel 916 апр 28 13:53 CMakeLists.txt
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ cmake --build _build --target package
[ 25%] Building CXX object CMakeFiles/print.dir/src/print.cpp.o
[ 50%] Linking CXX static library libprint.a
[ 50%] Built target print
[ 75%] Building CXX object CMakeFiles/demo.dir/demo/main.cpp.o
[100%] Linking CXX executable demo
[100%] Built target demo
Run CPack packaging tool...
CPack: Create package using TGZ
CPack: Install projects
CPack: - Run preinstall target for: print
CPack: - Install project: print []
CPack: Create package
CPack: - package: /home/michel/MichelsonIU815/workspace/projects/lab09/_build/print-0.1.0.0-Linux.tar.gz generated.
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git tag -s v0.1.0.0
fatal: нет описания метки?
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git tag -s v0.1.0.0 -m "Initial release version 0.1.0.0"
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ $ git tag -v v0.1.0.0
$: команда не найдена
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git tag -v v0.1.0.0
object 4c72dd4c29d67414745d94727d8a32a83e3c080c
type commit
tag v0.1.0.0
tagger MichelsonIU815 <dmtmikel@mail.ru> 1745838025 +0300

Initial release version 0.1.0.0
gpg: Подпись сделана Пн 28 апр 2025 14:00:25 MSK
gpg:                ключом RSA с идентификатором 4CC1632CDE6132F34C92FD89375C74C7AE5A71DA
gpg: Действительная подпись пользователя "Mikedr (i) <m.a.dmitriyev@mail.ru>" [абсолютное]
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git show v0.1.0.0
tag v0.1.0.0
Tagger: MichelsonIU815 <dmtmikel@mail.ru>
Date:   Mon Apr 28 14:00:25 2025 +0300

Initial release version 0.1.0.0
-----BEGIN PGP SIGNATURE-----

iQIzBAABCgAdFiEETMFjLN5hMvNMkv2JN1x0x65acdoFAmgPX8kACgkQN1x0x65a
cdoGJBAAoGSao3zHzAu9lhT3aXK/CRbR7vfLpgxRCgaXKxY0+VJzkt1hkNR8DTvD
yH3zF9C9EFD3B+RyLg45+0CPJBdv30cQtK1rJ94iWu+uzvRpxIFlZJcxrPyM2MPO
CzGmUHQcE96jhlvfFkN3F8WOBWUZt7Wyph2uZU/hg7yvsDmauLhB9/qEZUksxq3v
BCnr1ZCU0P/L5Q70wp6ftc/0OElBkLZcG20Jfw97jKY0KqddzjigNbQTzfpvbPms
gzunQ9fm9FnH0mdC0HQ3LRDRx9BMZIdNwmf7CrW8K2G3NoQqfQsw4fUJ9JfWiKTV
omMmvav6t60yk9zphs2sm/ARhdUB7EwQqRmGBLQcujA+rMx1vpl/xnkY5F0Mz2G4
LJfKwt1szDGJ6MuM4swOrDz4wValoYQ3uhcQG83Qu15vGYPchFTu3L8QFgoJ5qfq
ipqY6FOmd3dZjJxJmrqDde3M8D09ywftyTwgbZoPaCWwMzDv7JJyheqHjBlZJAsm
b1aVjxLQ1XZSlvauZ09nVymbtH9opl4WTcLgaVUt7qh45VcuDRGOQe27HN2iGKyd
25AZuGy3Lchijy3JrNPbFldUcxuINA1mEgewQcskqW+6y3LTq6K0xMqn7KNpf23J
Bn7wLuO45002gkkwgTKFYPK7SWE1uv1r+N4q4nQ4tbsEFv4bqU8=
=qs5y
-----END PGP SIGNATURE-----

commit 4c72dd4c29d67414745d94727d8a32a83e3c080c (HEAD -> main, tag: v0.1.0.0)
Author: MichelsonIU815 <dmtmikel@mail.ru>
Date:   Mon Apr 21 17:09:23 2025 +0300

    Add files via upload

diff --git a/logs/log.txt b/logs/log.txt
new file mode 100644
index 0000000..9557d36
--- /dev/null
+++ b/logs/log.txt
@@ -0,0 +1,4 @@
+text1
+text2
+text3
+<C-D>
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git push origin master --tags
error: src refspec master ничему не соответствует
error: не удалось отправить некоторые ссылки в «https://github.com/MichelsonIU815/lab09»
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git push origin main --tags
Username for 'https://github.com': MichelsonIU815
Password for 'https://MichelsonIU815@github.com': 
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/MichelsonIU815/lab09/'
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ github-release --version
github-release: команда не найдена
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ sudo apt install golang
[sudo] пароль для michel: 
Чтение списков пакетов… Готово
Построение дерева зависимостей… Готово
Чтение информации о состоянии… Готово         
Будут установлены следующие дополнительные пакеты:
  golang-1.22 golang-1.22-doc golang-1.22-go golang-1.22-src golang-doc golang-go golang-src
Предлагаемые пакеты:
  bzr | brz mercurial subversion
Следующие НОВЫЕ пакеты будут установлены:
  golang golang-1.22 golang-1.22-doc golang-1.22-go golang-1.22-src golang-doc golang-go
  golang-src
Обновлено 0 пакетов, установлено 8 новых пакетов, для удаления отмечено 0 пакетов, и 147 пакетов не обновлено.
Необходимо скачать 45,8 MB архивов.
После данной операции объём занятого дискового пространства возрастёт на 228 MB.
Хотите продолжить? [Д/н] y
Пол:1 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 golang-1.22-doc all 1.22.2-2ubuntu0.3 [107 kB]
Пол:2 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 golang-1.22-src all 1.22.2-2ubuntu0.3 [19,7 MB]
Пол:3 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 golang-1.22-go amd64 1.22.2-2ubuntu0.3 [25,9 MB]
Пол:4 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 golang-1.22 all 1.22.2-2ubuntu0.3 [5 702 B]
Пол:5 http://archive.ubuntu.com/ubuntu noble/main amd64 golang-src all 2:1.22~2build1 [5 078 B]
Пол:6 http://archive.ubuntu.com/ubuntu noble/main amd64 golang-go amd64 2:1.22~2build1 [43,9 kB]
Пол:7 http://archive.ubuntu.com/ubuntu noble/main amd64 golang-doc all 2:1.22~2build1 [2 788 B]
Пол:8 http://archive.ubuntu.com/ubuntu noble/main amd64 golang amd64 2:1.22~2build1 [2 736 B]
Получено 45,8 MB за 18с (2 558 kB/s)                                                         
Выбор ранее не выбранного пакета golang-1.22-doc.
(Чтение базы данных … на данный момент установлено 228207 файлов и каталогов.)
Подготовка к распаковке …/0-golang-1.22-doc_1.22.2-2ubuntu0.3_all.deb …
Распаковывается golang-1.22-doc (1.22.2-2ubuntu0.3) …
Выбор ранее не выбранного пакета golang-1.22-src.
Подготовка к распаковке …/1-golang-1.22-src_1.22.2-2ubuntu0.3_all.deb …
Распаковывается golang-1.22-src (1.22.2-2ubuntu0.3) …
Выбор ранее не выбранного пакета golang-1.22-go.
Подготовка к распаковке …/2-golang-1.22-go_1.22.2-2ubuntu0.3_amd64.deb …
Распаковывается golang-1.22-go (1.22.2-2ubuntu0.3) …
Выбор ранее не выбранного пакета golang-1.22.
Подготовка к распаковке …/3-golang-1.22_1.22.2-2ubuntu0.3_all.deb …
Распаковывается golang-1.22 (1.22.2-2ubuntu0.3) …
Выбор ранее не выбранного пакета golang-src.
Подготовка к распаковке …/4-golang-src_2%3a1.22~2build1_all.deb …
Распаковывается golang-src (2:1.22~2build1) …
Выбор ранее не выбранного пакета golang-go:amd64.
Подготовка к распаковке …/5-golang-go_2%3a1.22~2build1_amd64.deb …
Распаковывается golang-go:amd64 (2:1.22~2build1) …
Выбор ранее не выбранного пакета golang-doc.
Подготовка к распаковке …/6-golang-doc_2%3a1.22~2build1_all.deb …
Распаковывается golang-doc (2:1.22~2build1) …
Выбор ранее не выбранного пакета golang:amd64.
Подготовка к распаковке …/7-golang_2%3a1.22~2build1_amd64.deb …
Распаковывается golang:amd64 (2:1.22~2build1) …
Настраивается пакет golang-1.22-doc (1.22.2-2ubuntu0.3) …
Настраивается пакет golang-1.22-src (1.22.2-2ubuntu0.3) …
Настраивается пакет golang-src (2:1.22~2build1) …
Настраивается пакет golang-1.22-go (1.22.2-2ubuntu0.3) …
Настраивается пакет golang-1.22 (1.22.2-2ubuntu0.3) …
Настраивается пакет golang-go:amd64 (2:1.22~2build1) …
Настраивается пакет golang-doc (2:1.22~2build1) …
Настраивается пакет golang:amd64 (2:1.22~2build1) …
Обрабатываются триггеры для man-db (2.12.0-4build2) …
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ go install github.com/github-release/github-release@latest
go: finding module for package github.com/dustin/go-humanize
go: finding module for package github.com/voxelbrain/goptions
go: finding module for package github.com/kevinburke/rest/restclient
go: finding module for package github.com/tomnomnom/linkheader
go: found github.com/dustin/go-humanize in github.com/dustin/go-humanize v1.0.1
go: found github.com/voxelbrain/goptions in github.com/voxelbrain/goptions v0.0.0-20180630082107-58cddc247ea2
go: found github.com/kevinburke/rest/restclient in github.com/kevinburke/rest v0.0.0-20240617045629-3ed0ad3487f0
go: found github.com/tomnomnom/linkheader in github.com/tomnomnom/linkheader v0.0.0-20180905144013-02ca5825eb80
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ echo 'export PATH="$PATH:$(go env GOPATH)/bin"' >> ~/.bashrc
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ source ~/.bashrc
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ github-release --version
github-release v0.10.1
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ github-release info -u ${GITHUB_USERNAME} -r lab09
error: no tags available for MichelsonIU815/lab09
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git tag -a v0.1.0 -m "First release"
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git push origin v0.1.0
Username for 'https://github.com': MichelsonIU815
Password for 'https://MichelsonIU815@github.com': 
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/MichelsonIU815/lab09/'
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git fetch --tags
remote: Enumerating objects: 159, done.
remote: Counting objects: 100% (159/159), done.
remote: Compressing objects: 100% (132/132), done.
remote: Total 159 (delta 42), reused 0 (delta 0), pack-reused 0 (from 0)
Получение объектов: 100% (159/159), 799.98 КиБ | 1.79 МиБ/с, готово.
Определение изменений: 100% (42/42), готово.
Из https://github.com/MichelsonIU815/lab09
 * [новая ветка]     main       -> origin/main
 * [новая метка]     v1.0.0     -> v1.0.0
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ git push origin v0.1.0
Username for 'https://github.com': ;
Password for 'https://%3B@github.com': 
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/MichelsonIU815/lab09/'
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ github-release info -u ${GITHUB_USERNAME} -r lab09
tags:
- v1.0.0 (commit: https://api.github.com/repos/MichelsonIU815/lab09/commits/a51e770b42a0f0402ba42356a24e49ff901407d3)
releases:
- v1.0.0, name: '', description: 'first release', id: 215151656, tagged: 28/04/2025 at 11:12, published: 28/04/2025 at 11:22, draft: ✗, prerelease: ✗
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ github-release release \
>     --user ${GITHUB_USERNAME} \
>     --repo lab09 \
>     --tag v0.1.0.0 \
>     --name "libprint" \
>     --description "my first release"
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ export PACKAGE_OS=`uname -s` PACKAGE_ARCH=`uname -m` 
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ export PACKAGE_FILENAME=print-${PACKAGE_OS}-${PACKAGE_ARCH}.tar.gz
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ github-release upload \
>     --user ${GITHUB_USERNAME} \
>     --repo lab09 \
>     --tag v0.1.0.0 \
>     --name "${PACKAGE_FILENAME}" \
>     --file _build/*.tar.gz
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ github-release info -u ${GITHUB_USERNAME} -r lab09
tags:
- v1.0.0 (commit: https://api.github.com/repos/MichelsonIU815/lab09/commits/a51e770b42a0f0402ba42356a24e49ff901407d3)
- v0.1.0.0 (commit: https://api.github.com/repos/MichelsonIU815/lab09/commits/a51e770b42a0f0402ba42356a24e49ff901407d3)
releases:
- v1.0.0, name: '', description: 'first release', id: 215151656, tagged: 28/04/2025 at 11:12, published: 28/04/2025 at 11:22, draft: ✗, prerelease: ✗
- v0.1.0.0, name: 'libprint', description: 'my first release', id: 215151869, tagged: 28/04/2025 at 11:12, published: 28/04/2025 at 11:23, draft: ✗, prerelease: ✗
  - artifact: print-Linux-x86_64.tar.gz, downloads: 0, state: uploaded, type: application/octet-stream, size: 4.0 kB, id: 250105112
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$  wget https://github.com/${GITHUB_USERNAME}/lab09/releases/download/v0.1.0.0/${PACKAGE_FILENAME}
--2025-04-28 14:25:10--  https://github.com/MichelsonIU815/lab09/releases/download/v0.1.0.0/print-Linux-x86_64.tar.gz
Распознаётся github.com (github.com)… 140.82.121.3
Подключение к github.com (github.com)|140.82.121.3|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа… 302 Found
Адрес: https://objects.githubusercontent.com/github-production-release-asset-2e65be/971938463/14908937-57b0-4067-8111-cd60effd4cec?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=releaseassetproduction%2F20250428%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250428T112510Z&X-Amz-Expires=300&X-Amz-Signature=1161931f45baf70769845959c5e639590744c9a7c68c0703c11a65e8632b0285&X-Amz-SignedHeaders=host&response-content-disposition=attachment%3B%20filename%3Dprint-Linux-x86_64.tar.gz&response-content-type=application%2Foctet-stream [переход]
--2025-04-28 14:25:10--  https://objects.githubusercontent.com/github-production-release-asset-2e65be/971938463/14908937-57b0-4067-8111-cd60effd4cec?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=releaseassetproduction%2F20250428%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250428T112510Z&X-Amz-Expires=300&X-Amz-Signature=1161931f45baf70769845959c5e639590744c9a7c68c0703c11a65e8632b0285&X-Amz-SignedHeaders=host&response-content-disposition=attachment%3B%20filename%3Dprint-Linux-x86_64.tar.gz&response-content-type=application%2Foctet-stream
Распознаётся objects.githubusercontent.com (objects.githubusercontent.com)… 185.199.108.133, 185.199.109.133, 185.199.110.133, ...
Подключение к objects.githubusercontent.com (objects.githubusercontent.com)|185.199.108.133|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа… 200 OK
Длина: 4013 (3,9K) [application/octet-stream]
Сохранение в: ‘print-Linux-x86_64.tar.gz’

print-Linux-x86_64.tar. 100%[=============================>]   3,92K  --.-KB/s    за 0s      

2025-04-28 14:25:11 (20,2 MB/s) - ‘print-Linux-x86_64.tar.gz’ сохранён [4013/4013]

michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ tar -ztf ${PACKAGE_FILENAME}
print-0.1.0.0-Linux/bin/
print-0.1.0.0-Linux/bin/demo
michel@MichelUbuntu:~/MichelsonIU815/workspace/projects/lab09$ 

