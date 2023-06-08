import pyttsx3
import speech_recognition as sr
import yfinance as yf
import pywhatkit
import pyjokes
import webbrowser
import datetime
import wikipedia

# opciones de voz/idioma
id1 = "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech\Voices\Tokens\TTS_MS_ES-ES_HELENA_11.0"
id2 = (
    "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech\Voices\Tokens\TTS_MS_EN-US_ZIRA_11.0"
)


# escuchar microfono y devuelve el audio en texto
def tranasformar_audio_en_texto():
    # almacenar recognizer en variable
    r = sr.Recognizer()

    # configurar el microfono
    with sr.Microphone() as origen:
        # tiempo de espera
        r.pause_threshold = 0.8

        # informar que comenzo la grabacion
        print("Ya puedes hablar")

        # guardar audio
        audio = r.listen(origen, phrase_time_limit=5)

        try:
            # buscar en google
            pedido = r.recognize_google(audio, language="es")

            # prueba de que pudo ingresar
            print("Dijiste: " + pedido)

            # devolver pedido
            return pedido

        # si no lo comprende
        except sr.UnknownValueError:
            # prueba de que no comprendio el audio
            print("ups, no lo entendido")

            # devolver error
            return "Sigo esperando"

            # en caso de no resolver el pedido
        except sr.RequestError:
            # prueba de que no comprendio el audio
            print("ups, no hay servicio")

            # devolver error
            return "Sigo esperando"

            # error inesperado
        except:
            # prueba de que no comprendio el audio
            print("ups, algo ha salido mal")

            # devolver error
            return "Sigo esperando"


# funcion para que el asistente hable
def hablar(mensaje):
    # encender el motor de pyttsx3
    engine = pyttsx3.init()
    engine.setProperty("voice", id1)

    # pronuncia mensaje
    engine.say(mensaje)
    engine.runAndWait()


# informar el dia de la semana
def pedir_dia():
    # crear variable con datos de hoy
    dia = datetime.date.today()
    print(dia)

    # crear variable para el dia de la semana
    dia_semana = dia.weekday()
    print(dia_semana)

    # diccionario
    calendario = {
        0: "Lunes",
        1: "Martes",
        2: "Miércoles",
        3: "Jueves",
        4: "Viernes",
        5: "Sábado",
        6: "Domingo",
    }
    # decir el dia de la semana
    hablar(f"Hoy es {calendario[dia_semana]}")


# decir que hora es
def pedir_hora():
    # crear una variable con datos de la hora
    hora = datetime.datetime.now()
    hora = f"En este momento son {hora.hour} horas con {hora.minute} minutos y {hora.second} segundos"
    print(hora)

    hablar(hora)


# Saludo inicial
def saludo_inicial():
    # crear varible con datos de hora
    hora = datetime.datetime.now()
    if hora.hour < 6 or hora.hour > 20:
        momento = "Buenas noches"
    elif 6 >= hora.hour < 13:
        momento = "Buen día"
    else:
        momento = "Buenas tardes"

    # decir el saludo
    hablar(
        f"Hola, {momento}, soy Helena, tu asistente personal. Por favor, dime en que te puedo ayudar"
    )


# Funcion para hacer pedido
def pedir_cosas():
    # ativar el saludo inicial
    saludo_inicial()

    # variable de corte
    comenzar = True

    # loop central
    while comenzar:
        # activar el micro y guardar el pedido en un string
        pedido = tranasformar_audio_en_texto().lower()

        if "abre youtube" in pedido:
            hablar("Claro que si, estoy abriendo Youtube")
            webbrowser.open("https://www.youtube.com/")
            continue
        elif "abre google" in pedido:
            hablar("Ahora mismo, esoy abriendo Google")
            webbrowser.open("https://www.google.es/")
            continue
        elif "qué día es hoy" in pedido:
            pedir_dia()
            continue
        elif "qué hora es" in pedido:
            pedir_hora()
            continue
        elif "busca en wikipedia" in pedido:
            hablar("Buscando en Wikipedia")
            pedido = pedido.replace("busca en wikipedia", "")
            wikipedia.set_lang("es")
            resultado = wikipedia.summary(pedido, sentences=1)
            hablar("Wikipedia dice que: ")
            hablar(resultado)
            continue
        elif "busca en internet" in pedido:
            hablar("Ya voy")
            pedido = pedido.replace("busca en internet", "")
            pywhatkit.search(pedido)
            hablar("Esto es lo que encontré")
            continue
        elif "reproduce" in pedido:
            hablar("Buena idea, voy a reproducirlo")
            pywhatkit.playonyt(pedido)
        elif "broma" in pedido:
            hablar(pyjokes.get_joke("es"))
            continue
        elif "precio de las acciones" in pedido:
            accion = pedido.split("de")[-1].strip()
            cartera = {"Apple": "AAPL", "Amazon": "AMZN", "Google": "GOOGL"}
            try:
                accion_buscada = cartera[accion]
                accion_buscada = yf.Ticker(accion_buscada)
                precio_actual = accion_buscada.info["regularMarketPrevious"]
                hablar(f"La encontré, el precio de {accion} es {precio_actual} dolares")
                continue
            except:
                hablar("Perdón pero no la he encontrado")
                continue
        elif "adiós" in pedido:
            hablar("Me voy a descansar, cualquier cosa me avisas")
            break


pedir_cosas()
