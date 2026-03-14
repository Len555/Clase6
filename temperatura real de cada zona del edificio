# Se obtiene la temperatura actual de cada zona del edificio
# Esta funcion puede ser reutilizada si se agregan mas funciones especificas
def leer_sensores(zona):
    temperatura = float(input(f"Ingrese temperatura actual de la zona {zona}: "))
    return temperatura


# Función para calcular la temperatura óptima
# Se basa en la hora del día, ocupación y clima externo
# Se optimiza el consumo energetico del sistema 
def calcular_temperatura_optima(hora, ocupacion, clima_externo):

    if ocupacion == "si":
        if hora >= 8 and hora <= 18:
            temp_optima = 22
        else:
            temp_optima = 20
    else:
        temp_optima = 18

    if clima_externo < 10:
        temp_optima += 1

    return temp_optima

# Procedimiento para enviar señales al sistema HVAC
# (calefacción o refrigeración)

def ajustar_sistema(temp_actual, temp_optima):

    if temp_actual < temp_optima:
        print("Activar CALEFACCION")

    elif temp_actual > temp_optima:
        print("Activar REFRIGERACION")

    else:
        print("Temperatura correcta, no se realizan ajustes")


# Función para registrar consumo de energía
# Simulación simple de cálculo energético
def registrar_consumo(temp_actual, temp_optima):

    diferencia = abs(temp_actual - temp_optima)
    consumo = diferencia * 1.5

    return consumo

# PROGRAMA PRINCIPAL

zonas = int(input("Ingrese número de zonas del edificio: "))
hora = int(input("Ingrese la hora actual (0-23): "))
clima_externo = float(input("Ingrese temperatura externa: "))

ocupacion = input("¿El edificio está ocupado? (si/no): ")

consumo_total = 0

for zona in range(1, zonas + 1):

    print("\nProcesando zona:", zona)

    temp_actual = leer_sensores(zona)

    temp_optima = calcular_temperatura_optima(hora, ocupacion, clima_externo)

    ajustar_sistema(temp_actual, temp_optima)

    consumo = registrar_consumo(temp_actual, temp_optima)

    consumo_total += consumo

print("\nConsumo total estimado:", consumo_total)
