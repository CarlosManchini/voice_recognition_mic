## Sistema de Gravação e Reconhecimento de Fala

Este é um sistema simples de gravação e reconhecimento de fala em Python, desenvolvido com o uso das bibliotecas ipywidgets, pyaudio e Vosk. O sistema permite gravar áudio do microfone, transcrever a fala em texto e exibir o texto na saída.


## Observações

1. Antes de iniciar a gravação, você precisa identificar o número de índice do dispositivo de microfone que deseja usar. Para isso execute a célula de código abaixo para listar os dispositivos de áudio da sua máquina:

    ```python
    import pyaudio
    p = pyaudio.PyAudio()
    for i in range(p.get_device_count()):
        print(p.get_device_info_by_index(i))
    p.terminate()
    ```

2. Após a identificação do número do índice do microfone, localize `input_device_index` no código e altere o valor (aqui utilizei o **2**):

    ```python
    stream = p.open(format=AUDIO_FORMAT,
                    channels=CHANNELS,
                    rate=FRAME_RATE,
                    input=True,
                    input_device_index=2, # Aqui
                    frames_per_buffer=chunk)
    ```



