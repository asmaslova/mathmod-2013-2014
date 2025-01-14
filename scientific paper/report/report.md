---
## Front matter
title: "Модель культуры Аксельрода"
subtitle: ""
author: "Маслова Анастасия Сергеевна"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Введение

Общественное мнение и культурная динамика определяются социальным влиянием, тенденцией индивидов становиться более похожими при взаимодействии, что является основным механизмом модели избирателя. Само по себе социальное влияние обычно приводит систему к монокультурному равновесию, в то время как различия между индивидами и группами сохраняются в реальном мире. Если люди склонны становиться более похожими в своих убеждениях, установках и поведении при взаимодействии, почему все такие различия в конечном итоге не исчезают? Социологи предложили множество механизмов для ответа на этот вопрос. Цель этой статьи - исследовать еще один механизм. 

Рассматриваемый здесь механизм имеет дело с тем, как люди действительно становятся более похожими по мере взаимодействия, но также дает объяснение того, почему тенденция к сближению прекращается, не достигнув завершения. Таким образом, он дает новый тип объяснения того, почему мы не все становимся похожими. Поскольку предлагаемый механизм может существовать наряду с другими механизмами, его можно рассматривать как дополняющий более старые объяснения, а не обязательно конкурирующий с ними [@axelrod:paper:bash]. В своей основополагающей статье политолог Роберт Аксельрод объясняет разнообразие культур как следствие гомофилии [@wiki:homophily:bash], которая представляет собой тенденцию чаще взаимодействовать с индивидами, которые более похожи. В модели Аксельрода акторы характеризуются конечным числом культурных особенностей. По словам самого Аксельрода, чем больше актер похож на соседа, тем больше вероятность того, что актер перенимает одну из черт соседа.


# Основная часть

## Биография

Роберт Аксельрод — американский политолог и экономист, профессор политических наук и государственной политики в Мичиганском университете, где работает с 1974 года, член Национальной АН США (1986), удостоен Национальной научной медали (2014) [@wiki:bio:bash]. В 1997 год он написал статью в журнале Journal of Conflict Resolution под названием "The dissemination of culture: a model with local convergence and global polarization" [@axelrod:paper:bash], где описал свою модель, иллюстрирующую, как локальная конвергенция может порождать глобальную поляризацию.

Модель Аксельрода оказала значительное влияние на научный мир, и несколько авторов подробно проанализировали модель и некоторые из ее структурных допущений. Также модель была расширена, модифицирована и использовалась в других контекстах: например, Собиратель (2002) исследует новые способы передачи и отбора культурных черт, Бхавнани (2003) изучает исторический процесс формирования гражданских сообществ, Гонсалес-Авелла и др. (2007) рассматривают влияние средств массовой информации на процессы распространения культуры, а Лейдесдорф (2001) исследует эволюцию конкурирующих технологий [@jasss:bash].

## Описание модели

В этой модели имеется квадратная решетка ячеек $L×L$. Каждая ячейка представляет стационарную особь, которая наделена определенной культурой. Культура индивида характеризуется списком $f$ черт, или измерений культуры (например, язык, религия, стиль одежды ...); для каждой черты существует набор $q$ черт, которые являются альтернативными значениями, которые может иметь эта черта. Все агенты имеют одинаковое значение для $f$, и все функции имеют одинаковое значение для $q$. Таким образом, культура человека $i$ представлена вектором $x_i$ из $f$ переменных, где каждая переменная принимает целое значение в диапазоне $[0, q - 1]$. Изначально индивидуумам присваивается случайная культура. Следовательно, параметр $q$, который определяет возможные черты в каждом культурном измерении, можно рассматривать как показатель начального беспорядка или культурного разнообразия в системе.

Временной этап в модели определяется следующими видами деятельности:

- Один агент $k$ (активный) выбирается случайным образом;
- Один из соседей агента $k$, обозначаемый как агент $r$ (пассивный), выбирается случайным образом;
- Агенты $k$ и $r$ взаимодействуют с вероятностью, равной их культурному сходству, $n_kr/f$, где $n_kr$ обозначает количество культурных особенностей, для которых агенты $k$ и $r$ обладают одинаковыми признаками. Взаимодействие заключается в том, что активный агент $k$ выбирает случайным образом один из признаков $f - n_kr$, по которым два агента различаются, и копирует признак пассивного агента $r$. Таким образом, агент $k$ приближается к культурным интересам агента $r$.

Описанный выше процесс продолжается до тех пор, пока не произойдет никаких культурных изменений. Это происходит, когда культуры каждой пары соседних агентов либо идентичны, либо совершенно различны.

Аксельрод исследует совокупное поведение этой модели, изучая пространственное распределение возникающих культурных регионов: наборов пространственно смежных агентов, разделяющих идентичный вектор культуры. Естественно, параметры $f$ и $q$ влияют на вероятность, с которой система эволюционирует к монокультуре (только один культурный регион) или к глобальной поляризации (несколько мультикультурных регионов).

## Математическое описание модели

Сеть представляет собой конечный связный граф $G$ с множеством вершин $V$ и множеством ребер $E$. Каждая вершина $x$ характеризуется вектором $X(x)$ из $F$ культурных признаков, каждый из которых предполагает $q$ возможных состояний:

$X(x) = (X^1(x), ..., X^F(x)) \text{, где}  X^i(x) \in  {1,2,...,q} \text{ для } i = 1,2,...,F$.

На каждом временном шаге вершина $x$ выбирается равномерно случайным образом из множества вершин вместе с одним из ее соседей $y$. Затем с вероятностью, равной доле общих признаков $x$ и $y$, выбирается один из признаков, для которых состояния различны (если таковые имеются), и состояние вершины $x$ устанавливается равным состоянию вершины $y$ для этого культурного признака. В противном случае ничего не происходит. Чтобы более обобщенно описать динамику Аксельрода как на конечных, так и на бесконечных графах, мы предполагаем, что система развивается в непрерывном времени, причем каждая пара соседних вершин взаимодействует со скоростью один, что приводит к тому, что одна из двух вершин, выбранных равномерно случайным образом, имитирует другую вершину в случае обновления. Это индуцирует марковский процесс непрерывного времени, состояние которого в момент времени $t$ является функцией $X_t$, которая отображает множество вершин графа в множество культур $\{{ 1, 2, . . . , q \}}^F$, и динамика которого описывается генератором $Ω_ax$, определенным на множестве цилиндрических функций с помощью формулы (рис. [-@fig:001]) [@lanchier:paper:bash].

![Формулы, описывающие модель Аксельрода](image/1.png){#fig:001}

## Применение модели

Модель Аксельрода нашла применение в различных областях, проливая свет на динамику распространения культуры и ее последствия, среди которых:

- Социальные науки и социология: Модель Аксельрода использовалась для изучения распространения концепций, идей и культурных особенностей внутри обществ. В нем дается представление о роли лидеров в инициировании инноваций и проблемах сопротивления переменам.

- Агентно-ориентированное моделирование: Модель Аксельрода служит основой для агентно-ориентированных моделей, исследующих распространение культуры. За счет учета социального влияния эти модели могут моделировать распространение культурных черт среди населения и анализировать возникновение различных культурных регионов.

- Формирование государства и политология: Исследователи применили модель Аксельрода для изучения формирования государств и эволюции политических институтов. Изучая, как культурные особенности взаимодействуют и влияют на политическую динамику, модель дает ценную информацию о коэволюции культурных групп.

- Общественное здравоохранение и коммуникационные стратегии: Принципы модели Аксельрода были адаптированы для изучения распространения информации, связанной со здоровьем, и разработки коммуникационных стратегий. Понимая динамику распространения культуры, исследователи могут разрабатывать эффективные стратегии, облегчающие использование научно обоснованной информации в здравоохранении.

- Информатика и моделирование: Модель Аксельрода использовалась в компьютерном моделировании для изучения распространения культурных черт в виртуальной среде. Эти модели позволяют исследователям наблюдать влияние различных параметров и механизмов на процесс распространения.

Стоит отметить, что область применения модели Аксельрода выходит за рамки этих примеров, поскольку исследователи адаптируют и расширяют модель в соответствии со своими конкретными областями исследований. Обеспечивая основу для понимания распространения культуры, модель продолжает способствовать более глубокому пониманию того, как идеи, верования и практика распространяются и эволюционируют в обществах.

# Вывод

Модель Аксельрода зарекомендовала себя как ценный инструмент для понимания распространения культуры внутри обществ. Моделируя взаимодействие и обмен культурными чертами, эта модель позволяет исследователям понять динамику культурной эволюции и появление отдельных культурных регионов. Применение модели Аксельрода охватывает различные дисциплины, включая социальные науки, информатику, общественное здравоохранение и политологию. Благодаря своему использованию в агент-ориентированном моделировании модель Аксельрода пролила свет на механизмы распространения культуры, подчеркнув роль социального влияния, влияния лидера и сопротивления переменам. Более того, его применение в государственном образовании и политологии дало представление о совместной эволюции культурных групп и влиянии культурных особенностей на политическую динамику. Модель Аксельрода также обладает потенциалом в области общественного здравоохранения, поскольку помогает исследователям понять распространение информации, связанной со здоровьем, и разработать эффективные коммуникационные стратегии. Кроме того, ее использование в компьютерном моделировании позволяет проводить виртуальные эксперименты для изучения влияния различных параметров на распространение культуры.

# Список литературы{.unnumbered}

::: {#refs}
:::
