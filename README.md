# Класcификация эмоций с использованием трансформерами

В данном проекте содержится выполненное тех задание по классификации эмоций англоязычных твитов из [датасета](https://huggingface.co/datasets/dair-ai/emotion). Для доступа к gpu задание выполнено в google-collaboratory, в связи с чем всё содержится в одном юпитер ноутбуке.

Структура проекта:

* Emotion_classification.ipynb - ноутбук с решением и пояснениями;
* https://www.dropbox.com/s/lfn1isza8iy1bbc/data.zip - ссылка на скачивание данных для обучения и теста:
    1. merged_training.pkl - полный датасет до разделения ~400к;
    2. train.jsonl.gz - тренировочная часть выборки 16к; 
    3. test.jsonl.gz - тестовая часть выборки 2к; 
    4. validation.jsonl.gz - валидационная часть выборки 2к; 
    5. train_oversampled.jsonl.gz - предобработанная тренировочная выборка (устранён дисбаланс классов) ~32к;

* https://www.dropbox.com/s/sybzfsxucsozf6i/models.zip - ссылка на скачивание обученных в блокноте моделей:
    1. distilroberta-base_model.pickle - 1-я дообученная модель на основе distilroberta-base и кастомного классификатора;
    2. bert-base_uncased_model.pickle - дообученная модель с лидерборда на основе berta-base для классификации текстов;
    3. before_quantization_model.bin - модель перед квантизацией (та же bert-base_uncased_model.pickle на самом деле);
    4. dynamic_quantization - папка с дообученной моделью с лидерборда после квантизации с float32 до  int8 (инфренс только на cpu);

модели и данные отдельно скачивать не обязательно, они загружаются в пайплайне Emotion_classification.ipynb.