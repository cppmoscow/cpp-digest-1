# cpp-digest-1

Название: C++ Дайджест №1

Дата: 7 августа 2023 – 20 августа 2023

## Аннотация

Привет, Хабр! Сегодня я хочу вам представить подборку интересных новостей и материалов из мира C++ за прошедшие две недели.

Приятного чтения!

## ⚡️️ Новости и релизы

1. [Boost 1.83.0](https://www.boost.org/users/history/version_1_83_0.html) — Ряды библиотек Boost пополнились [Boost.Compat](https://www.boost.org/doc/libs/1_83_0/libs/compat/doc/html/compat.html), «‎репозиторием реализаций на C++11 стандартных компонентов, добавленных в более поздних стандартах»‎, однако на данный момент включающей реализации лишь `std::latch` и `std::shared_lock`.
2. [fmt 10.1.0](https://github.com/fmtlib/fmt/releases/tag/10.1.0) — Оптимизация `format_to` и `format_to_n`, увеличивающая производительность на 40-400% в бенчмарке конкатенации строк, другие улучшения и багфиксы.
3. [Meson 1.2.1](https://github.com/mesonbuild/meson/releases/tag/1.2.1) — Добавление поддержки C++23 и C++26, багфиксы и прочие изменения.
4. [Qt Creator 11.0.2](https://www.qt.io/blog/qt-creator-11.0.2-released) — Багфиксы.
5. [Visual Studio 2022 17.7](https://devblogs.microsoft.com/cppblog/whats-new-for-c-developers-in-visual-studio-2022-17-7/) — Добавление инструмента сравнения файлов, более быстрый запуск отладчиков  и поиск по файлам, интеграция [C++ Build Insights](https://devblogs.microsoft.com/cppblog/introducing-c-build-insights/), позволяющего легко отслеживать наиболее «‎дорогостоящие»‎ инклуды и другое.
6. [MSVC Address Sanitizer – One DLL for all Runtime Configurations](https://devblogs.microsoft.com/cppblog/msvc-address-sanitizer-one-dll-for-all-runtime-configurations/) — О нововведении Visual Studio 2022 version 17.7 Preview 3, упрощающем конфигурирование и использование MSVC Address Sanitizer.
7. [Introducing CMake Debugger in VS Code: Debug your CMake Scripts using Open-Source CMake Debugger](https://devblogs.microsoft.com/cppblog/introducing-cmake-debugger-in-vs-code-debug-your-cmake-scripts-using-open-source-cmake-debugger/) — Главное счастье и радость всех плюсовых разработчиков, пользующихся VS Code, теперь CMake скрипты можно будет так же дебажить, как и весь остальной код: с брейкпойнтами, стеком вызовов и просмотром значений переменных.

## 📝 Статьи

1. 🇷🇺 Habr: [Правильный if для ускорения работы](https://habr.com/ru/companies/stc_spb/articles/752974/) — О том, как мы можем помочь компилятору оптимизировать блоки `if`, если у нас нет `[[likely]]` и `[[unlikely]]` из C++20, но зато есть интринсик `__builtin_expect` (спойлер: пользователи msvc, у вас его нет).
2. 🇷🇺 Habr: [Seastar как платформа для опорной сети 5G и краткое сравнение с Boost.Asio, userver и другими](https://habr.com/ru/companies/yadro/articles/751830/) — Обзор [Seastar](https://seastar.io/), сетевого фреймворка с [_share-nothing_ архитектурой](https://github.com/scylladb/seastar/wiki/SMP) и [_lock-free cross-CPU communication_](https://www.scylladb.com/2018/02/15/memory-barriers-seastar-linux/), позволяющего из коробки линейно масштабировать производительность по количеству ядер.
3. 🇷🇺 Habr: [Как написать хороший генератор](https://habr.com/ru/articles/754314/) — Гайд по написанию эффективного и удобного в использовании (даже удобнее, чем `std::generator` из C++23) генератора на корутинах.
4. 🇷🇺 Habr: [Как я вошёл в клуб бага 323](https://habr.com/ru/articles/754730/) — Перевод статьи о 23-летнем баге №323, объединяющем целые поколения пользователей gcc и clang.
5. 🇷🇺 Habr: [Первые новинки C++26: итоги летней встречи ISO](https://habr.com/ru/companies/yandex/articles/753260/) — Обзор нововведений C++26, только-только принятых в стандарт: Hazard Pointer, Read-Copy-Update, множество доработок по `constexpr` и другое.
6. 🇷🇺 Habr: [Подводные камни C++. Решаем загадки неопределённого поведения, ч. 2](https://habr.com/ru/companies/ncloudtech/articles/755004/) — Продолжение серии статей об UB-проблемах и способах их решения, на этот раз о гонке данных, deadlock, семантике перемещения и use after move.
7. 🇷🇺 Habr: [Недостатки корутин в C++](https://habr.com/ru/companies/ruvds/articles/755246/) — Перевод статьи о рисках, связанных с переносом кодовых баз на использование корутин, потенциально способных привести к уменьшению безопасности и замедлению программы.
8. Bartlomiej Filipek: [Five Advanced Initialization Techniques in C++: From reserve() to piecewise_construct and More](https://www.cppstories.com/2023/five-adv-init-techniques-cpp/) — Обзор некоторых техник инициализации, начиная с всем знакомой `reserve()` + `emplace_back()` и заканчивая `constinit` и `make_unique_for_overwrite`, нововведениями C++20.
9. Andrey Upadyshev: [A case in optimizing auto-vectorized code](https://oliora.github.io/2023/08/07/Optimizing-auto-vectorized-code.html) — История о том, как проанализировав автоматически векторизованный компилятором код, автор смог улучшить его на 90%, векторизовав его уже вручную.
10. Sandor Dargo: [C++23: multidimensional operator[]](https://www.sandordargo.com/blog/2023/08/09/cpp23-multidimensional-subscription-operator) — О пользе принятого в C++23 многомерного `operator[]` и том, как с ним наш код изменится.
11. Sandor Dargo: [C++23: mdspan](https://www.sandordargo.com/blog/2023/08/15/cpp23-mdspan-mdsarray) — Обзор одного из нововведений C++23, очень гибкого и кастомизируемого многомерного аналога `std::span`.
12. Raymond Chen: [Inside STL: The array](https://devblogs.microsoft.com/oldnewthing/20230811-00/?p=108591), [Inside STL: The deque, design](https://devblogs.microsoft.com/oldnewthing/20230809-00/?p=108577), [Inside STL: The deque, implementation](https://devblogs.microsoft.com/oldnewthing/20230810-00/?p=108587), [Inside STL: The unordered_map, unordered_set, unordered_multimap, and unordered_multiset](https://devblogs.microsoft.com/oldnewthing/20230808-00/?p=108572), [Inside STL: The map, set, multimap, and multiset](https://devblogs.microsoft.com/oldnewthing/20230807-00/?p=108562) — Продолжение серии статей об особенностях реализации контейнеров стандартной библиотеки в libc++, libstdc++ и Microsoft's STL.
13. Raymond Chen: [Inside STL: Smart pointers](https://devblogs.microsoft.com/oldnewthing/20230814-00/?p=108597), [Inside STL: The shared_ptr constructor vs make_shared](https://devblogs.microsoft.com/oldnewthing/20230815-00/?p=108602), [Inside STL: The shared_ptr constructor and enable_shared_from_this](https://devblogs.microsoft.com/oldnewthing/20230816-00/?p=108608) — О фундаментальных особенностях реализации умных указателей, разнице между `std::shared_ptr(new S())` и `std::make_shared<S>()` и том, как работает `std::enable_shared_from_this`.
14. Raymond Chen: [What it means when you convert between different shared_ptrs](https://devblogs.microsoft.com/oldnewthing/20230817-00/?p=108611), [Phantom and indulgent shared pointers](https://devblogs.microsoft.com/oldnewthing/20230818-00/?p=108619) — О различных способах создания нового `std::shared_ptr` из уже имеющегося, и его пограничных состояниях, _phantom_ и _indulgent_. 
15. Daniel Lemire: [Transcoding UTF-8 strings to Latin 1 strings at 18 GB/s using AVX-512](https://lemire.me/blog/2023/08/12/transcoding-utf-8-strings-to-latin-1-strings-at-12-gb-s-using-avx-512/) — О том, как даже без _excessive cleverness_ AVX-512 позволяет ускорить трансформации строк, включая нетриваиальные, до 10 раз.
16. Marius Bancila: [How to convert an enum to string in C++](https://mariusbancila.ro/blog/2023/08/17/how-to-convert-an-enum-to-string-in-cpp/) — Пример реализации макроса для преобразования значений перечислений в строки.
17. Tristan Brindle: [Parameter Passing in Flux versus Ranges](https://tristanbrindle.com/posts/parameter-passing-in-flux-vs-ranges) — Обзор библиотеки [flux](https://github.com/tcbrindle/flux), замене диапазонов из C++20, и о том, как различается в них подход к передаче параметров в объекты адаптеров.
18. Arthur O’Dwyer: [Some C++20 ranges aren’t const-iterable](https://quuxplusone.github.io/blog/2023/08/13/non-const-iterable-ranges/) — Об одной из ловушек, подстерегающей неопытных пользователей C++20 Ranges, невозможности константного итерирования по некоторым из них.
19. Rainer Grimm: [C++23: The Small Pearls in the Core Language](https://www.modernescpp.com/index.php/c23-more-small-pearls/) — Продолжение серии статей о языковых [нововведениях C++23](https://www.modernescpp.com/index.php/c23-the-small-pearls-in-the-core-language/): `auto(x)` и `auto{x}`, многомерный `operator[]`, `static operator()` и `operator[]`.

## 📺 Видео

1. [Interview with Felix Jones: Game Dev, GBA Homebrew, constexpr and Minecraft](https://www.youtube.com/watch?v=PxkgX2MTmQ8) — Интервью с Феликсом Джонсом, техлидом Minecraft Bedrock Edition.
2. [C++ Weekly - Ep 388 - My constexpr Revenge Against Lisp](https://www.youtube.com/watch?v=NQEE0k9i7FA) — Обзор [cons_expr](https://github.com/lefticus/cons_expr), constexpr интерпретатора [Scheme](https://ru.wikipedia.org/wiki/Scheme)-подобного скриптового языка.
3. [C++ Weekly - Ep 389 - Avoiding Pointer Arithmetic](https://www.youtube.com/watch?v=YahYVRS1Ktg) — Обзор множества способов, как мы можем изголяться, лишь бы не использовать арифметику указателей, на простейшем примере.

## 🎙️Подкасты

1. CppCast: [Episode 367, Soagen](https://cppcast.com/soagen/) — О рефлексии, SIMD и [soagen](https://marzer.github.io/soagen/), утилите и библиотеке, упрощающей работу с [Structure-of-Arrays](https://en.wikipedia.org/wiki/AoS_and_SoA).
