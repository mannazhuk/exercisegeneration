# Генерация упражнений для уроков русского как иностранного по заданному тексту
Преподаватель сам выбирает в тексте лексику, которую хочет вынести в упражнения, поэтому мы генерируем в итоге, опираясь на список слов.

Мы сфокусировались на одном типе упражнений - заполнение пропусков. По сути мы генерируем короткий текст, а потом ставим пропуски.

Для качественой генерации нужно верно определить уровень сложности исходного текста (A1-C2), чтобы сгенерированое упражнение соответствовало этому уровню (допускается сделать упражнение на один уровень легче).

Мы брали списки слов из текстов из учебников, поэтому определение уровня исходного текста не делали, а текст упражнения классифицировали по уровню.

Общая схема такая:
1. Создание классификатора для определения уровня сложности исходного или сгенерированного текстов.
   Мы можем обойтись без дообучения, то есть получить [эмбеддинги текстов](https://github.com/mannazhuk/exercise_generation/blob/ae84a0ea421ecb46a0ec0436e109928be31298bc/%D0%9F%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5%20%D1%8D%D0%BC%D0%B1%D0%B5%D0%B4%D0%B4%D0%B8%D0%BD%D0%B3%D0%BE%D0%B2%20%D0%BD%D0%B0_%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D0%B5%20TinyBert.ipynb) и подать их разным [классификаторам](Классификаторы_sberbank_airuBert_large.ipynb).
   Или мы можем [дообучить](Bert_for_sequence_classification.ipynb) модель.
Фрагмент исходного датасета с текстами [здесь[(https://github.com/mannazhuk/exercise_generation/blob/bc1d860a37b01c53ed49889302d37da0a6c1b425/RuFoLa_corpus.csv). Здесь можно скачать эмбеддинги текстов, полученные с помощью ruRoberta-large;
Итоговая лучшая модель - RKI_sber_bert_large

3. Генерируем упражнения с Llama2, затем обучаем ее и снова генерируем упражнения.

4. Получаем тексты и оцениваем их качество.

5. Создаем упражнение
