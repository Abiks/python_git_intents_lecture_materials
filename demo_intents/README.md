# Сборка виртуальной среды с помощью conda 

Инструкция писалась на компьютере с Linux Mint с использованием командной оболочки bash. 
На других ОС действия должны быть аналогичны (например, в Windows эти команды должны нормально сработать из Anaconda Prompt). 


* * *

создаем виртуальную среду, указывая ей имя и версию питона

    conda create --name demo_intents python=3.6

активируем ее

    conda activate demo_intents

заходим в папку demo_intents (где лежит презентация и ноутбуки)

    cd Путь/до/папки/demo_intents

устанавливаем зависимости (сперва через conda, потом через pip доустанавливаем недостающие)

    conda install --file intents_conda_requirements.txt
    pip install -r intents_pip_requirements.txt

регистрируем эту виртуальную среду как ядро jupyter

    python -m ipykernel install --user --name demo_intents --display-name "Python 3.6 [intent classification]"

скачиваем (либо просто линкуем) словарь английского языка для spacy

    python -m spacy download en_core_web_sm


* * *


(опционально) скачайте файлы и положите их в папку demo_intents (в ноутбуке есть закомментированные команды на скачивание, но они у вас могут не выполниться)

Сам датасет:

    http://files.deeppavlov.ai/datasets/snips_intents/train.csv

ELMO (файл .json содержит информацию для воспроизведения архитектуры нейросети, файл .hdf5 содержит значения весов): 

    https://s3-us-west-2.amazonaws.com/allennlp/models/elmo/2x4096_512_2048cnn_2xhighway/elmo_2x4096_512_2048cnn_2xhighway_options.json
    https://s3-us-west-2.amazonaws.com/allennlp/models/elmo/2x4096_512_2048cnn_2xhighway/elmo_2x4096_512_2048cnn_2xhighway_weights.hdf5


