# ITMO_Deep_learning

Курсовая работа

## Тема работы

"Реализация алгоритма анализа межслойной трансформации данных
внутри нейросетей посредством персистентных гомологий внутрислойных
многообразий для полносвязных нейронных сетей"

## План

Данная тема направлена на знакомство с внутренней геометрией
нейросетевых моделей – с тем, как данные трансформируются между слоями.
В частности, данная тема позволяет познакомиться с тем, какие внутренние
факторы могут влиять на способность/не способность нейросети обучиться
на имеющихся данных.
В связи с этим, рекомендуется следующая схема эксперимента:
1. Стоит подобрать простой датасет по задаче классификации (как более
простой для исследования геометрии в силу дискретности получаемого
расслоения) для данной архитектуры нейросетей:
- Для полносвязных нейросетей подойдёт какой-либо искусственно
сгенерированный датасет с простой геометрией (вроде двух немного
пересекающихся многомерных сфер)
2. Для данной задачи стоит построить две схематично похожие архитектуры
нейронки:
- Модель, которая достаточно выразительна для того, чтобы решить задачу
качественно.
- Модель, которая намеренно сделана такой, чтобы не иметь возможность
решить поставленную задачу (например, внутри посередине есть слой
слишком малой размерности – раза в 3-4 меньше входной размерности).
Конечно, не стоит делать её карикатурно плохой (например, добавлять слой с
одним нейроном) – это снизит показательность результатов. Также стоит
проследить, чтобы данная модель по глубине (количеству слоёв) не сильно
отличалась от «хорошей» (из первого пункта).
3. В процессе обучения архитектур стоит убедиться, что одна в среднем
уменьшает ошибку до приемлемой без переобучения, а другая застревает на
высоком значении.
4. В процессе обучения и после него следует (с не слишком высокой
частотой, конечно) отслеживать геометрию данных внутри нейросети теми
методами, что поставлены в теме (визуализацией либо персистентными
гомологиями). Более подробно, это значит, что нужно в конце выбранных
вами эпох делать следующий процесс:
- Сначала подаётся на вход нейросети тренировочный датасет и тестовый
датасет (по отдельности и вместе – всего три комбинации) и сохраняются
активации выделенных слоёв (на  выбор, но стоит иметь хотя бы по
одному замеру в начале, середине и конце модели).
- После применяется имеющиеся в теме методы для визуализации геометрии
полученных активаций.
В итоге получится отслеживание эволюции геометрии данных внутри
нейросетей – той, что обучается хорошо, и той, что не может обучиться. Её
нужно будет проанализировать. 
