# QuizerBot

Bot de Telegram desarrollado en Python para jugar cuestionarios interactivos. Incluye un modo quiz con una respuesta correcta y un modo poll con preguntas de selección múltiple, además de guardar el progreso y las recompensas de los usuarios.

## Funciones

- `/start`: inicia el bot y registra al usuario.
- `/quiz`: envía preguntas con una respuesta correcta y una explicación.
- `/poll`: envía preguntas tipo encuesta, con posibilidad de varias respuestas.
- `/creditos`: muestra información sobre los desarrolladores.
- Guarda datos de usuarios, preguntas respondidas y recompensas en archivos de texto.

## Requisitos

- Python 3.8 o superior
- Un bot creado mediante [BotFather](https://t.me/BotFather)

## Instalación

1. Clona el repositorio y entra en su carpeta:

   ```bash
   git clone <URL_DEL_REPOSITORIO>
   cd QuizerBot
   ```

2. Crea y activa un entorno virtual:

   ```bash
   python -m venv venv
   ```

   En Windows PowerShell:

   ```powershell
   .\venv\Scripts\Activate.ps1
   ```

3. Instala las dependencias:

   ```bash
   pip install -r requirements.txt
   ```

4. Configura el token del bot en `generalVariable/constant.py`, en la variable `CONSTANT.MY_TOKEN_BOT`.

   No publiques el token ni lo subas al repositorio. Si el token actual fue expuesto, revócalo y genera uno nuevo desde BotFather.

## Ejecución

Desde la raíz del proyecto, con el entorno virtual activo:

```bash
python main.py
```

El bot utiliza `run_polling()`, por lo que debe permanecer ejecutándose para recibir mensajes.

## Estructura del proyecto

```text
QuizerBot/
├── main.py                         # Punto de entrada
├── requirements.txt                # Dependencias
├── controller/                     # Handlers y respuestas de Telegram
├── game/                           # Lógica de quiz, poll y créditos
│   ├── database/                   # Datos persistentes de usuarios
│   └── questions/                  # Preguntas de cada modo
└── generalVariable/                # Constantes y variables generales
```

## Añadir preguntas

Las preguntas se encuentran en:

- `game/questions/question_quiz.py` para el modo `/quiz`.
- `game/questions/question_poll.py` para el modo `/poll`.

Respeta el formato de las preguntas existentes para mantener compatibles los campos de opciones, respuesta correcta, explicación y configuración de la encuesta.

## Dependencia principal

El proyecto utiliza `python-telegram-bot` (`20.0a4`) para comunicarse con la API de Telegram.