⚙️ Настройка

Откройте "webui-user.bat" в текстовом редакторе для изменения настроек.

✅ Рекомендуемые настройки:

Для большинства пользователей:

set COMMANDLINE_ARGS=--xformers

Для RTX 30/40 серии:

set COMMANDLINE_ARGS=--xformers --cuda-malloc --cuda-stream --pin-shared-memory

Для RTX 40/50 + максимальная скорость:

set COMMANDLINE_ARGS=--xformers --sage --cuda-malloc --cuda-stream

Для работы с API:

set COMMANDLINE_ARGS=--xformers --api --listen

Для вывода моделей SVDQ:

set COMMANDLINE_ARGS=--nunchaku

Доступ с других устройств:

set COMMANDLINE_ARGS=--listen --port 7860

Затем откройте в браузере: `http://ВАШ_IP:7860`

🔄 Обновление:

Для обновления используйте файл - update.bat, для обновления вручную:

1. Закройте WebUI (если запущен)

2. Откройте а блокноте - web-user.bat

3. Пропишите в нем в пустом месте - "git pull", сохраните и закройте текстовый документ и снова запустите - web-user.bat

4. Дождитесь завершения обновления.

📦 Установка моделей

✅ Где разместить модели:

webui/models/Stable-diffusion/ # Основные модели (.safetensors, .ckpt)

webui/models/Lora/ # LoRA модели

webui/models/VAE/ # VAE модели

webui/models/ESRGAN/ # Upscaler модели

webui/models/ControlNet/ # ControlNet модели

 Популярные источники моделей:

- [Civitai](https://civitai.com/)

- [Hugging Face](https://huggingface.co/)

- [CivitAI Models](https://github.com/Haoming02/sd-webui-forge-classic/wiki/Download-Models)

🎨 Поддерживаемые модели:

- Flux (Dev, Schnell, Krea, Kontext)

- Flux2 Klein (4B, 9B)

- SDXL (Stable Diffusion XL)

- SD 1.5 (Stable Diffusion 1.5)

- Qwen-Image и Qwen-Image-Edit

- Wan 2.2 (txt2vid, img2vid)

- Z-Image-Turbo и Z-image

- Lumina-Image-2.0

- Chroma

- ANIMA

- LoRAs, ControlNets, IP-Adapters

🔧 Решение проблем:

_Python не найден при запуске_

Решение: проверьте правильная версия python у вас установлена, при необходимости переустановите его.

Ошибка "Out of Memory"

Решения:

- Уменьшите разрешение изображения

- Используйте меньший Batch Size

- Для Flux: уменьшите "GPU Weight" в настройках

- Закройте другие программы, использующие GPU

### Медленная генерация

Решения:

- Убедитесь, что включен --xformers

- Попробуйте добавить --sage для ускорения

- Обновите драйверы NVIDIA

- Для RTX 30+: используйте CUDA оптимизации

Ошибки при установке пакетов:

Решения:

1. Удалите папку - venv

2. Запустите файл - installed

3. Запустите - web-user.bat снова

WebUI не открывается в браузере

Решения:

- Откройте вручную: `http://localhost:7860`

- Проверьте, не занят ли порт другой программой

- Измените порт в `webui-user.bat`: `--port 8080`

🆘 Получение помощи:

- Документация: [Forge Neo Wiki](https://github.com/Haoming02/sd-webui-forge-classic/wiki)

- Поддержка: [GitHub Issues](https://github.com/Haoming02/sd-webui-forge-classic/issues)

- Модели: [Download Models Guide](https://github.com/Haoming02/sd-webui-forge-classic/wiki/Download-Models)

📝 Дополнительные настройки:

✅ Использование моделей из другой установки

Если у вас уже есть модели в другом WebUI:

set COMMANDLINE_ARGS=--forge-ref-a1111-home "D:\path\to\automatic1111"

Пути к основным папкам (примеры):

set COMMANDLINE_ARGS=--ckpt-dir "С:\MODELS" --lora-dir "С:\LORA" --vae-dir "С:\VAE" --esrgan-models-path "С:\ESRGAN"

Путь к папке styles:

set COMMANDLINE_ARGS=--styles-file="styles\*.csv"

Темная тема:

set COMMANDLINE_ARGS=--theme=dark

Использование центральной папки с моделями

set COMMANDLINE_ARGS=--model-ref "D:\AI\Models"

Структура центральной папки:

D:\AI\Models/

├── Stable-diffusion/

├── Lora/

├── VAE/

└── ...

✅ Экспорт видео (требуется FFmpeg)

1. Скачайте [FFmpeg portable](https://www.gyan.dev/ffmpeg/builds/ffmpeg-git-essentials.7z)

2. Распакуйте в папку - ffmpeg рядом с run.bat

3. Добавьте в PATH через webui-user.bat:

set PATH=%~dp0ffmpeg\bin;%PATH%

Версия: 2.13

Дата: февраль 2026