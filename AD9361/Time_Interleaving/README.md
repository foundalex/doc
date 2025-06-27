Time interleaving (чередовние во времени) - заключается в мультиплексировании во времени выходов параллельного массива из М идентичных АЦП для достижения 
более высокой суммарной частоты дискретизации fs.

Метода калибровки Time Interleaved ADC делятся на два вида:
1. Foreground. Используется когда АЦП не включен в работу. При калибровке не учитывается температура
2. Background. 



Статьи:

1. A condensed Cramer’s rule - правило Крамера для работы с матрицами 
2. A_digital_background_calibration_method - калибровка с помощью LMS алгоритма. Используются матрицы Адамара.
3. A_scalable_bandwidth_mismatch - Foreground метод. Используется как аналоговая, так и цифровая калибровка TI-ADC
4. A_timing_mismatch_background_calibration - калибровка с помощью автокорреляции
5. All_digital_blind_background_calibration - калибровка по заранее известному сигналу. Используется  преобразование Гильберта и LMS - метод
6. All-Digital Background Calibration Technique - калибровка с помощью псевдо алиасинга
7. An Improved All-Digital Background Calibration - калибровка с помощью корреляции
8. Background_offset_and_gain_calibration_for_TIADC - использование референс канала ADC для калибровки смещения и усиления сигнала. Для генерации калибровочного сигнала используется LUT+DAC
9. Calibration_techniques_for_time_interleaved_sar_adc - книга, в которой калибровки single channel, multi channel ADC
10. Digital_calibration_for_gain_time skew_and_bandwidth - исходная статья. Калибровка с помощью LMS метода.
11. interleaving-adcs - статья от Analog Devices про TIADC
12. Joint_error_estimation_and_calibration - LS и RLS метод на примере ряда Вольтера
13. thesis_manar-augmented - книга по background калибровке
14. Time Interleaved Converter Arrays - начальная статья про калибровку timeleaving АЦП
15. Time-Interleaved_SAR_ADC_design_background_calibraton - калибровка аналогичная исходной статье offset и gain
16. Time-interleaved_SAR_UWB - калибровка с помощью компараторов
17. АЦП_с_чередованием_во_времени - статья от Analog Devices про TIADC на английском языке



Алгоритм работы 

1. Создаем fractional delay фильтр с задержкой i/M, где i - номер канала, M - общее количество каналов

    DFT такого фильтра равен 
    Hri(jw) = e^-jw * Ts * i/M                                                          (16)
2. Пропускаем через него выход АЦП0 (референсного канала)

    yri[n] = y0[n] * hri[k], где * - свертка, y0 - выход после ADC0                     (15)
3. Создаем матрицу сигнала. Порядок fractional delay фильтра N (73 или 5???). После каждой задержки фильтра сохраняем отсчеты. Получится матрица N x Ls, где Ls - количество семплов исходного сигнала

4. Подставляем в уравнение полученную матрицу

    h △g, △t, △w [k] = (y T ical o  y ical o)^-1 * y T ical o * yri                   (19)

5. h △g, △t, △w [k] - полученные коэффициенты фильтра. Делаем свертку исходного сигнала с данным фильтром и получим скорректированный сигнал

    y ical o,g,t,w [n] = y ical o[n] * h △g, △t, △w [k]                               (13)




