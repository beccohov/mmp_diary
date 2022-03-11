# Дневник ММП, 3 курс Бессонов Аркадий
<ul>
<li><b>24.10.21</b> - Исследование современных подходов к анализу ЭЭГ.</li>
<li><b>15.11.21-15.12.07</b> - Чтение статей и просмотр курсов, связанных с архитекрутой трансформеров и сетей для NLP, а также создание конспектов по ним.</li>
<li><b>25.11.21</b> - Консультация с научным руководителем для получения справки по теме курсовой работы.</li>
<li><b>06.12.21</b> - Создание презентации для доклада на семинаре.</li>
 <li><b>08.12.21</b> - Доклад на семинаре по теме "AST: Audio Spectrogram Transformer" (<a href="https://github.com/beccohov/mmp_diary/blob/main/Seminars/fall%202021/AST%20Audio.pdf"> Слайды доступны тут</a>)</li>
<li><b>08.12.21</b> - Выбор темы курсовой работы "Классификация эмоций / представление эмоций"</li>
 <li><b>21.12.21</b> - Начало изучения результатов статьи (<a href="https://github.com/beccohov/mmp_diary/blob/main/Articles/Audio/README.md#current_issue">ссылка на описание</a>) с целью воспроизведения результатов.</li>
 <li><b>24.12.21</b> - Поиск предобученной модели wav2vec и работа по воспроизведению архитектуры, использованной в <a href="https://github.com/beccohov/mmp_diary/blob/main/Articles/Audio/README.md#current_issue">статье</a>. </li>
 <li><b>02.02.22</b> - Тестирование и обучение реализаций моделей для классификации эмоций с помощью wav2vec2.0. </li>
 <li><b>16.02.22</b> - Предобученный на датасете для распознования эмоций на греческом языке Wav2Vec2.0 (CROSS-LINGUAL) на IEMOCAP достигает точности около 0.4397, что очень интересно - значит, модель способна выявлять эмоциональную окраску голоса, которая свойственна для человеческой речи независимо от языка. Более того, при анализе ошибочно классифицированных аудиозаписей видно, что ошибки свойственны коротким трудно распозноваемым для человека отрывкам фраз, а также фразам, эмоциональный оттенок которых зависит от языка (т.е без понимания слов распознать эмоцию сложно. Например - глубой вздох со словами "God, this is grat...". скорее всего для модели, знающей греческий язык и не дообученной явно для английского, понять, что в речи действительно метка "happiness" довольно сложно - как, впрочем, и для человека, не знающего английский.)  Так исключается переобучение под спикера на IEMOCAP (но может быть переобучение под греческий датасет - там unbalanced accuracy около 70-80).</li>
 <li><b>17.02.22</b> Модель Wav2vec с замороженными нижними слоями и предобученная на датасете для греческого языка, дообученная на датасете iemocap (c удалением некоторых классов, которых не было в исходном датасете) имеет точность около 0.6</li>

 <li><b>01.03.22</b> 
 Нашел более интересный датасет RAVDESS (интереснее потому, что там более эмоциональная речь и меньше ошибок в разметке + всего несколько текстов, что снижает переобучение и делает распознование менее зависимым от текста). А также датасет EMODB (немецкий язык), EMOVO (итальянский язык). Оба датасета похожи на RAVDESS тем, что эмоции на них понятнее и для человека, каждый образец представляет собой целостное предложение.
 </li>
<li><b>02.03.22-10.03.22</b> 
 Эксперименты с обучением модели wav2vec2.0 (large xlsr, english finetuned - ранее была греческая версия). Обучил модель на 5 фолдах, разделение в соответствие со  <a href="https://www.mdpi.com/2076-3417/12/1/327">статьей</a>, чтобы было удобнее сравнивать результаты. Далее в этом пункте все результаты приводятся при использовании этого подхода - независимо от обучающих данных используется для теста то же разбиение исходного датасета RAVDESS на 5 фолдов. При фиксированном seed на 6 эпохах я получаю среднюю точность модели 0.79432 (<a href="https://wandb.ai/beccohov/Wav2vec2MultilingualClassic/reports/Shared-panel-22-03-11-20-03-41--VmlldzoxNjc1ODYy?accessToken=bhvz0arbbw9nj23o1effcu4gerkqu9g3pvx22alksgnoegmgdpo79oxgyshbj8lk">ссылка на дашборд с результатом точности на валидации</a>), при тех же условиях и использовании двух датасетов для обучения (RAVDESS + EMODB, поскольку немецкий и английский в одной языковой группе) средняя точность модели 0.79916 (<a href="https://wandb.ai/beccohov/Wav2vec2MultilingualDouble/reports/Shared-panel-22-03-11-20-03-88--VmlldzoxNjc1ODgy?accessToken=m7tx9plz60lzas3vhlmqatfw0omynqd3ry9fbtp8fv6pqdfovcynw4lr77xc7bol">ссылка на дашборд с результатом точности на валидации</a>). При использовании трех датасетов средняя точность модели 0.79516 (<a href="https://wandb.ai/beccohov/Wav2vec2MultilingualThree/reports/Shared-panel-22-03-11-20-03-75--VmlldzoxNjc1ODc5?accessToken=srehwav2jz215kxfxl3vacvcf8zb1yu03o6sjuapz2elvpnhpbm4mywds45o9x5z">ссылка на дашборд с результатом точности на валидации</a>). Видно, что добавление данных существенно не меняет модель - значит, ёмкости модели достаточно для работы одновременно с тремя и более языками. При этом наибольшее улучшение (хотя оно тоже маленькое) наблюдается в случае с двумя датасетами. Возможно это связано с тем, что немецкий больше похож на английский, а итальсянский все же вносит "шум" в обучение. Конечно, для более строгого обоснования нужно провести больше экспериментов с разными сидами. Но я пока оставлю эту идею, чтобы далее проверить больше гипотез (время работы GPU ограничено :( ). Пока вижу несколько естественных направлений для дальнейшей работы - 
 </li>

 
 </ul>
 <br>

 <h2>Прочитанные статьи находятся тут:</h2>
 <ul>
  <li><a href="https://github.com/beccohov/mmp_diary/tree/main/Articles/Text">По работе с текстом</a></li>
  <li><a href="https://github.com/beccohov/mmp_diary/tree/main/Articles/Images">По работе с изображениями</a></li>
  <li><a href="https://github.com/beccohov/mmp_diary/tree/main/Articles/Audio">По работе с аудио</a></li>
  <li><a href="https://github.com/beccohov/mmp_diary/tree/main/Articles/Others">Остальное</a> </li>
 </ul>
