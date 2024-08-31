# VidMetrics

VidMetrics - это инструмент для анализа видео, использующий несколько подходов и библиотек для определения физиологических параметров, таких как сердечный ритм и дыхание.

## Используемые библиотеки и подходы

1. **[PyVHR](https://github.com/phuselab/pyVHR)** - библиотека для анализа сердечного ритма из видеороликов.
2. **[GazeTracking](https://github.com/antoinelame/GazeTracking/tree/master)** - библиотека для отслеживания взгляда.
3. Подход, основанный на анализе открытой области лба для определения среднего значения зелёного канала внутри неё (основан на идее из [CV2_heartbeat_breathing_detection](https://github.com/QiuZhaopeng/CV2_heartbeat_breathing_detection/tree/main)). Идея заключается в том, что при увеличении количества кислорода в крови во время вдоха увеличивается поглощение зелёного света, что должно отражаться как падение графика, а для выдоха - наоборот, рост.

## Установка зависимостей

Для установки всех зависимостей потребуется Anaconda. Вы можете скачать Miniconda [здесь](https://docs.anaconda.com/miniconda/). После установки, если вы не добавили Anaconda в PATH, используйте Anaconda Prompt для создания среды и установки зависимостей, а также для запуска скрипта.

### Шаги по установке:

1. Перейдите в директорию со скачанным проектом:

   ```bash
   cd <путь к директории с проектом>
   ```
   
2. Установите все зависимости, выполнив следующую команду:

   ```bash
   conda env create -f environment.yml
   ```
   
    Эта команда создаст среду в Anaconda с именем vidMetrics.


3. Активируйте созданную среду:
   
   ```bash
   conda activate vidMetrics
   ```
   
## Запуск инструмента
### Запуск в интерактивном режиме

Для запуска скрипта используйте следующую команду:

   ```bash
   python main.py
   ```

Скрипт запустится в интерактивном режиме, где вы сможете ввести путь к видеофайлу.

### Запуск с передачей пути к видеофайлу в качестве параметра

Вы также можете передать путь к видеофайлу напрямую при запуске скрипта:

   ```bash
   python main.py <путь к видеофайлу>
   ```

Поддерживаются как абсолютные, так и относительные пути. Видео должно иметь расширение .mp4.

## Результаты

Результаты анализа будут сохранены в папку /results/<название видео> относительно скрипта. Если папка уже существует, к её имени будет добавлен уникальный номер, чтобы избежать перезаписи данных.
