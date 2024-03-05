# hse24_hw2

[Colab](https://colab.research.google.com/drive/1df0f657XJ7djniWxhgO2FU5TfXrGEmC2?usp=sharing)

Для исследования была выбрана клеточная линия BLaER1 и гистоновая метка H3K4me3.

## Анализ FastQC

HTML-выдача FastQC лежит в data

1-ая ChipSeq реплика | 2-ая ChipSeq реплика | Контроль
--- | --- | ---
[ENCFF391TRF](https://github.com/HpPpL/hse24_hw2/blob/main/data/ENCFF391TRF_fastqc.html) | [ENCFF989TVW](https://github.com/HpPpL/hse24_hw2/blob/main/data/ENCFF989TVW_fastqc.html) | [ENCFF259JCU](https://github.com/HpPpL/hse24_hw2/blob/main/data/ENCFF259JCU_fastqc.html)

### FastQC

ENCFF391TRF | ENCFF989TVW | ENCFF259JCU
--- | --- | ---
![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/ChipSeq_ENCFF391TRF.png) | ![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/ChipSeq_ENCFF989TVW.png) | ![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/ChipSeq_ENCFF259JCU.png)
![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/Pbsq_ENCFF391TRF.png) | ![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/Pbsq_ENCFF989TVW.png) | ![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/Pbsq_ENCFF259JCU.png)
![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/Psqs_ENCFF391TRF.png) | ![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/Psqs_ENCFF989TVW.png) | ![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/Psqs_ENCFF259JCU.png)
![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/Pbsc_ENCFF391TRF.png) | ![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/Pbsc_ENCFF989TVW.png) | ![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/Pbsc_ENCFF259JCU.png)
![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/PsGCc_ENCFF391TRF.png) | ![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/PsGCc_ENCFF989TVW.png) | ![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/PsGCc_ENCFF259JCU.png)
![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/PbNc_ENCFF391TRF.png) | ![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/PbNc_ENCFF989TVW.png) | ![image](https://github.com/HpPpL/hse24_hw2/blob/main/data/PbNc_ENCFF259JCU.png)

Подрезание не требуется, качество ридов хорошее. Но для практики в коде имеется посвященный этому блок.


## Таблица со статистикой по выравниванию на 14 хромосому

index | Общее число ридов | Выровнившиеся уникально | (%) | Выровнившиеся неуникально | (%) | Не выровнившиеся | (%)
--- | --- | --- | --- | --- | --- | --- | ---
ENCFF391TRF | 38513348 | 1469065 | 3.81% | 3603918 | 9.36% | 33440365 | 86.83%
ENCFF989TVW | 53332175 | 2197627 | 4.12% | 5674612 | 10.64% | 45459936 | 85.24%
ENCFF259JCU | 88755850 | 3855931 | 4.34% | 11652213 | 13.13% | 73247706 | 82.53%


## Диаграммы Эйлера-Венна

### Пересечение пиков 1 реплики и ENCODE

1 реплика с ENCODE | ENCODE с 1 репликой
--- | ---
![Intervene_venn_1](https://github.com/HpPpL/hse24_hw2/blob/main/data/Intervene_venn_1.png) | ![Intervene_venn 2](https://github.com/HpPpL/hse24_hw2/blob/main/data/Intervene_venn_2.png)

### Пересечение пиков 2 реплики и ENCODE


2 реплика с ENCODE | ENCODE и 2 репликой
--- | ---
![Intervene_venn 3](https://github.com/HpPpL/hse24_hw2/blob/main/data/Intervene_venn_3.png) | ![Intervene_venn 4](https://github.com/HpPpL/hse24_hw2/blob/main/data/Intervene_venn_4.png)


Количество пересечений довольно мало, это связано с тем, что выравнивание производилось только на одну хромосому. 

В базе данных ENCODE пики составлены для всех хромосом, поэтому их количество кратно больше. Отсюда и следует, что пересечение наших пиков с ENCODE и пересечение ENCODE с нашими пиками - вещи разные, в связи с чем и наблюдаются различные значения.
