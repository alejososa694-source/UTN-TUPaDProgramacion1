# UTN-TUPaDProgramacion1
Alejo Sosa
#Comienzo de la actividad 1: "Caja de kiosco"Simular una compra con validaciones y cálculo de total.Pedir nombre del cliente (solo letras, validar con .isalpha() en while).Pedir cantidad de productos a comprar (número entero positivo, validar con .isdigit() en while). Por cada producto (usar for): Pedir precio (entero, validar .isdigit()). Pedir si tiene descuento S/N (validar con while, aceptar s o n en cualquier mayuscula/minuscula). Si tiene descuento: aplicar 10% al precio de ese producto. Al final mostrar:Total sin descuentos.  Total con descuentos. Ahorro total. Promedio por producto (usar float y formatear con :.2f.
total_sin_descuento= 0
total_con_descuento= 0
nombre=""
cantidad_productos= 0
##pedimos el nombre al cliente
nombre= input("Ingrese su nombre por favor : ").strip()
cantidad_productos= input("Ingrese la cantidad de productos (en números)").strip()##quitamos los espacios con .strip()
while not nombre.isalpha(): ##Comprobamos si escribio con letras el usuario y si no fue el caso entramos al while
    print("Pudiste haberte equivocado en el nombre, debe de ser escrito en Letras y no en números")
    nombre= input("Te equivocaste en el nombre, ").strip()
while not (cantidad_productos.isdigit() and int(cantidad_productos if cantidad_productos.isdigit() else 0) > 0):##Validamos si el usuario ingreso la cantidad de productos en números y no en letras
    print(" Entrada inválida. Debe ser un número entero mayor a cero.")
    cantidad_productos = input("Inténtalo de nuevo. Ingresa la cantidad: ").strip()
##Convertimos a entero con total seguridad tras pasar el filtro
cantidad = int(cantidad_productos)
##mostramos en pantalla nombre y cantidad de productos
print(f" Registro exitoso. ¡Gracias {nombre}! Has pedido {cantidad} productos.")

for i in range(cantidad):##vamos por cada uno de los productos
    precios= input("Ingresa el precio de los productos: " ).strip()
    while not precios.isdigit() or int(precios) == 0:##Analizamos si los productos ingresados son números validos
      print("El valor de los productos debe de ser un valor entero o mayor a 0")
      precios= input("Escribe los valores de los productos: ").strip() 
    precio= int(precios)
descuentos= input("Estos productos, ¿cuentan con descuento?, Responder con (S/N)").strip().upper()
while not descuentos.isalpha() and descuentos!= "S" and descuentos!= "N":##Analizamos si el usuario ingreso un S o N
    print("Error debe de responder con S de Si o con N de No")
    descuentos=input("Estos productos, ¿cuentan con algun descuento? responder con S/N (Si o No): ").strip().upper()
total_sin_descuento = total_sin_descuento + precio

if descuentos== "S":##Si la respuesta es si realizamos el calculo correspondientes del descunto del 10%
    descuento = precio * 0.90
    precio_final = precio 
else:##Si no es asi calculamos el precio normal
    precio_final = precio 
    total_con_descuento= total_con_descuento + precio_final
ahorro = total_sin_descuento - total_con_descuento
promedio = total_con_descuento / cantidad
##Mostramos por pantalla los calculos y el nombre y la cantidad ingresada por el ususario
print("================================")
print(f"Cliente: {nombre}")
print(f"Cantidad de productos: {cantidad}")
print(f"Total sin descuentos: ${total_sin_descuento}")
print(f"Total con descuentos: ${total_con_descuento:.2f}")
print(f"Ahorro total: ${ahorro:.2f}")
print(f"Promedio por producto: ${promedio:.2f}")
#Fin de la actividad 1: #Comienzo de la actividad 1: "Caja de kiosco"Simular una compra con validaciones y cálculo de total.Pedir nombre del cliente (solo letras, validar con .isalpha() en while).Pedir cantidad de productos a comprar (número entero positivo, validar con .isdigit() en while). Por cada producto (usar for): Pedir precio (entero, validar .isdigit()). Pedir si tiene descuento S/N (validar con while, aceptar s o n en cualquier mayuscula/minuscula). Si tiene descuento: aplicar 10% al precio de ese producto. Al final mostrar:Total sin descuentos.  Total con descuentos. Ahorro total. Promedio por producto (usar float y formatear con :.2f.

#Comienzo de la actividad 2:  Login con intentos + menú de acciones con validación estricta.Requisitos
#1. Definir credenciales fijas en el código:
usuario_correcto= "alumno"
clave_correcta= "python123"
intento= 0
##2. Permitir máximo 3 intentos para ingresar usuario y clave.
acceso= False
for intento in range(1, 4):
    usuario = input(f"Intento {intento}/3 - Usuario: ").strip()
    clave = input("Clave: ").strip()
    if usuario == usuario_correcto and clave == clave_correcta:##analizamos si las claves y el ususario coinciden
        print("Acceso concedido.")
        acceso = True
        break
    else:
        print("Error: credenciales inválidas.")

if not acceso:
    print("Cuenta bloqueada")
menu_activo= True
while menu_activo:##Abrimos El Menú
    print("============ Bienvenido al Menú ============")    
    print("""1) Ver estado de Inscripcion 
    2) Cambiar Clave
    3) Mensaje Motivacional
    4) Salir""")
    opcion=input("Ingrese aqui al apartado del menu que desee ingresar (1 - 4): ").strip()
    while not opcion.isdigit():##Vemos si el ususario coloco un número o otro caracter en la consola
        print("Error Ingrrse Un Número Valido (1 - 4): ")
        opcion=input("Ingrese la opcion a la que quiera acceder (1 - 4): ").strip()   
    opcion= int(opcion)##Convertimos opcion a entero
    while opcion < 1 or opcion > 4:##Vemos si la opcion ingresada es un número válido
        print("Error la opcion debe de estar dentro del rango: (1 - 4): ")
        opcion=input("Ingrese la opcion a la que quiera acceder (1 - 4): ").strip()  
        while not opcion.isdigit():##Vemos si la opcion ingresada es un número válido
            print("La opcion Ingrese un Valor Válido")
            opcion=input("opcion: ").strip()
        opcion = int(opcion)##Convertimos opcion en un entero
    ##comparamos si las opciones ingresadas son iguales a las opciones del menú y si es el caso ejecutamos lo pedido
    if opcion== 1:
        print("Inscripto")
    elif opcion== 2:
        clave_nueva= input("Ingrese La Nueva Contrseña Que Desea Ingresar: ").strip()
        confirmacion= input("Confirme la nueva clave: ").strip()
        if clave_nueva != confirmacion:
            print("Las Claves no coinciden debe de coincidir")
        elif len(clave_nueva) < 6:
            print("La Clave Nueva Debe De Ser Al Menos De 6 Caracteres")
        else:
            clave_correcta = clave_nueva
            print("Clave Actualizada")
    elif opcion== 3:
        print("Tu Puedes, Sigue Intentando, No Te Rindas <3")
    elif opcion== 4:
        menu_activo= False 
        print("Chauuu :)")
#Fin de la actividad 2: Login con intentos + menú de acciones con validación estricta.Requisitos

#Comienzo de la actividad 3: “Agenda de Turnos con Nombres (sin listas)”
# Variables del menú y turnos
# Variables iniciales de la agenda (vacías)
lunes1 = ""
lunes2 = ""
lunes3 = ""
lunes4 = ""

martes1 = ""
martes2 = ""
martes3 = ""

# 1. Pedir y validar nombre del operador
operador = input("Ingrese el nombre del operador: ").strip()
while not operador.isalpha() or operador == "":
    print("Error: El nombre debe contener solo letras y no estar vacío.")
    operador = input("Ingrese el nombre del operador: ").strip()

print(f"\n¡Bienvenido/a {operador} al Sistema de Turnos!")

opcion = 0

# 2. Menú principal repetitivo
while opcion != 5:
    print("\n============ MENÚ PRINCIPAL ============")
    print("1) Reservar turno")
    print("2) Cancelar turno")
    print("3) Ver agenda del día")
    print("4) Ver resumen general")
    print("5) Cerrar sistema")
    
    opcion = input("Opción: ").strip()
    
    # Validar que la opción sea un número entero entre 1 y 5
    while not opcion.isdigit() or int(opcion) < 1 or int(opcion) > 5:
        print("Error: La opción debe ser elegida con números entre 1 y 5.")
        opcion = input("Opción: ").strip()
    
    opcion = int(opcion)
    # 1. RESERVAR TURNO
    if opcion == 1:
        print("\n--- RESERVAR TURNO ---")
        nombre = input("Ingrese su Nombre Para Registrarlo: ").strip()
        while not nombre.isalpha() or nombre == "":
            print("El nombre ingresado no puede estar vacío ni contener números.")
            nombre = input("Nombre: ").strip()

        dia = input("Elija el día (1=Lunes, 2=Martes): ").strip()
        while not dia.isdigit() or int(dia) < 1 or int(dia) > 2:
            print("Error: el día debe ser 1 o 2.")
            dia = input("Elija el día (1=Lunes, 2=Martes): ").strip()
        
        dia = int(dia)

        if dia == 1:
            if nombre == lunes1 or nombre == lunes2 or nombre == lunes3 or nombre == lunes4:
                print("Ese paciente ya tiene un turno reservado el Lunes.")
            else:
                if lunes1 == "":
                    lunes1 = nombre
                    print("Turno reservado: Lunes, turno 1")
                elif lunes2 == "":
                    lunes2 = nombre
                    print("Turno reservado: Lunes, turno 2")
                elif lunes3 == "":
                    lunes3 = nombre
                    print("Turno reservado: Lunes, turno 3")
                elif lunes4 == "":
                    lunes4 = nombre
                    print("Turno reservado: Lunes, turno 4")
                else:
                    print("No hay turnos disponibles para el Lunes.")

        elif dia == 2:
            if nombre == martes1 or nombre == martes2 or nombre == martes3:
                print("Ese paciente ya tiene un turno reservado el Martes.")
            else:
                if martes1 == "":
                    martes1 = nombre
                    print("Turno reservado: Martes, turno 1")
                elif martes2 == "":
                    martes2 = nombre
                    print("Turno reservado: Martes, turno 2")
                elif martes3 == "":
                    martes3 = nombre
                    print("Turno reservado: Martes, turno 3")
                else:
                    print("No hay turnos disponibles para el Martes.")

    # 2. CANCELAR TURNO
    elif opcion == 2:
        print("\n--- CANCELAR TURNO ---")
        dia = input("Elija el día (1=Lunes, 2=Martes): ").strip()
        while not dia.isdigit() or int(dia) < 1 or int(dia) > 2:
            print("Error: el día debe ser 1 o 2.")
            dia = input("Elija el día (1=Lunes, 2=Martes): ").strip()
        dia = int(dia)

        nombre = input("Ingrese el nombre del paciente a cancelar: ").strip()
        while not nombre.isalpha() or nombre == "":
            print("Error: El nombre debe contener solo letras.")
            nombre = input("Nombre paciente: ").strip()

        encontrado = False

        if dia == 1:
            if lunes1 == nombre:
                lunes1 = ""
                encontrado = True
            elif lunes2 == nombre:
                lunes2 = ""
                encontrado = True
            elif lunes3 == nombre:
                lunes3 = ""
                encontrado = True
            elif lunes4 == nombre:
                lunes4 = ""
                encontrado = True
        elif dia == 2:
            if martes1 == nombre:
                martes1 = ""
                encontrado = True
            elif martes2 == nombre:
                martes2 = ""
                encontrado = True
            elif martes3 == nombre:
                martes3 = ""
                encontrado = True

        if encontrado:
            print(f"El turno de {nombre} ha sido cancelado exitosamente.")
        else:
            print(f"No se encontró a ningún paciente llamado {nombre} reservado ese día.")

    # 3. VER AGENDA DEL DÍA
    elif opcion == 3:
        print("\n--- AGENDA DEL DÍA ---")
        dia = input("Elija el día a consultar (1=Lunes, 2=Martes): ").strip()
        while not dia.isdigit() or int(dia) < 1 or int(dia) > 2:
            print("Error: el día debe ser 1 o 2.")
            dia = input("Elija el día (1=Lunes, 2=Martes): ").strip()
        dia = int(dia)

        if dia == 1:
            print("Agenda del Lunes:")
            print(f"Turno 1: {lunes1 if lunes1 != '' else '(libre)'}")
            print(f"Turno 2: {lunes2 if lunes2 != '' else '(libre)'}")
            print(f"Turno 3: {lunes3 if lunes3 != '' else '(libre)'}")
            print(f"Turno 4: {lunes4 if lunes4 != '' else '(libre)'}")
        elif dia == 2:
            print("Agenda del Martes:")
            print(f"Turno 1: {martes1 if martes1 != '' else '(libre)'}")
            print(f"Turno 2: {martes2 if martes2 != '' else '(libre)'}")
            print(f"Turno 3: {martes3 if martes3 != '' else '(libre)'}")

    
    # 4. VER RESUMEN GENERAL
    elif opcion == 4:
        print("\n--- RESUMEN GENERAL ---")
        
        # Conteo Lunes
        ocupados_lunes = 0
        if lunes1 != "": ocupados_lunes += 1
        if lunes2 != "": ocupados_lunes += 1
        if lunes3 != "": ocupados_lunes += 1
        if lunes4 != "": ocupados_lunes += 1
        disponibles_lunes = 4 - ocupados_lunes

        # Conteo Martes
        ocupados_martes = 0
        if martes1 != "": ocupados_martes += 1
        if martes2 != "": ocupados_martes += 1
        if martes3 != "": ocupados_martes += 1
        disponibles_martes = 3 - ocupados_martes

        print(f"Lunes  -> Ocupados: {ocupados_lunes} | Disponibles: {disponibles_lunes}")
        print(f"Martes -> Ocupados: {ocupados_martes} | Disponibles: {disponibles_martes}")

        if ocupados_lunes > ocupados_martes:
            print("Día con más turnos reservados: Lunes")
        elif ocupados_martes > ocupados_lunes:
            print("Día con más turnos reservados: Martes")
        else:
            print("Ambos días tienen la misma cantidad de turnos reservados (Empate).")

    # 5. CERRAR SISTEMA
    elif opcion == 5:
        print(f"\n¡Gracias por utilizar la agenda de turnos, {operador}!")
        print("Cerrando el sistema... ¡Hasta luego!")
#Comienzo de la Actividad 4: Escape Room: La Bóveda
energia = 100
tiempo = 12
cerraduras_abiertas = 0
alarma = False
codigo_parcial = ""

# Contador para la regla anti-spam
forzar_seguidos = 0

personaje = input("Ingresa El Nombre De Tu Agente: ").strip()
while not personaje.isalpha() or personaje == "":
    print("El Nombre Ingresado Debe De Ser Escrito Únicamente En Letras")
    personaje = input("Ingresa El Nombre De Tu Agente: ").strip()

print(f"\n¡Bienvenido Agente {personaje}! La misión ha comenzado.")

# Ciclo principal del juego
while energia > 0 and tiempo > 0 and cerraduras_abiertas < 3 and not alarma:
    print("\n-------------------------------------------")
    print(f"Estado del Agente {personaje}:")
    print(f"Energía: {energia} | Tiempo: {tiempo} | Cerraduras abiertas: {cerraduras_abiertas}/3")
    print(f"Alarma: {'ACTIVADA' if alarma else 'Desactivada'} | Código parcial: '{codigo_parcial}'")
    print("-------------------------------------------")
    print("Menú de Acciones:")
    print("1. Forzar cerradura (-20 energía, -2 tiempo)")
    print("2. Hackear panel (-10 energía, -3 tiempo)")
    print("3. Descansar (+15 energía, -1 tiempo)")
    
    opcion = input("Elija una acción (1-3): ").strip()
    while not opcion.isdigit() or int(opcion) < 1 or int(opcion) > 3:
        print("Error: Debe ingresar un número válido entre 1 y 3.")
        opcion = input("Elija una acción (1-3): ").strip()
    
    opcion = int(opcion)

    # OPCIÓN 1: FORZAR CERRADURA
    if opcion == 1:
        forzar_seguidos += 1
        energia -= 20
        tiempo -= 2
        
        # Regla Anti-Spam: 3ra vez seguida
        if forzar_seguidos == 3:
            print("\n¡ALERTA! Forzaste la cerradura 3 veces seguidas y se trabó el mecanismo.")
            alarma = True
        else:
            # Riesgo de alarma por baja energía (< 40)
            if energia < 40:
                print("\n¡Advertencia! Tu energía es baja. Hay riesgo de activar la alarma.")
                riesgo = input("Elija un número de seguridad (1-3): ").strip()
                while not riesgo.isdigit() or int(riesgo) < 1 or int(riesgo) > 3:
                    print("Error: Ingrese un número entre 1 y 3.")
                    riesgo = input("Elija un número de seguridad (1-3): ").strip()
                
                if int(riesgo) == 3:
                    print("¡Elegiste la opción incorrecta! Se activó la alarma.")
                    alarma = True

            # Si no saltó la alarma por ninguna de las dos razones, se abre la cerradura
            if not alarma:
                cerraduras_abiertas += 1
                print("\n¡Éxito! Lograste forzar y abrir 1 cerradura.")

    
    # OPCIÓN 2: HACKEAR PANEL
    
    elif opcion == 2:
        forzar_seguidos = 0  # Corta la racha anti-spam
        energia -= 10
        tiempo -= 3
        
        print("\nHackeando panel...")
        for paso in range(4):
            codigo_parcial += "A"
            print(f"> Progreso del hackeo: {codigo_parcial}")
        
        if len(codigo_parcial) >= 8 and cerraduras_abiertas < 3:
            cerraduras_abiertas += 1
            print("¡Código descifrado! Se abrió 1 cerradura automáticamente.")



#   OPCIÓN 3: DESCANSAR
    elif opcion == 3:
        forzar_seguidos = 0  # Corta la racha anti-spam
        tiempo -= 1
        
        # Si la alarma está activa, descuenta 10 de energía extra
        if alarma:
            energia += 15 - 10
            print("\nDescansaste, pero la alarma encendida te causó estrés (-10 energía extra).")
        else:
            energia += 15
            print("\nDescansaste y recuperaste energía.")
        
        # Controlar que la energía no supere 100
        if energia > 100:
            energia = 100


# EVALUACIÓN DEL RESULTADO FINAL
print("\n================ FIN DEL JUEGO ================")

# Verificación de bloqueo especial por alarma
if alarma and tiempo <= 3 and cerraduras_abiertas < 3:
    print(f"DERROTA (Bloqueo): La alarma sonó y el sistema se bloqueó por completo. El agente {personaje} fue capturado.")
elif cerraduras_abiertas >= 3:
    print(f"¡VICTORIA! El agente {personaje} logró abrir las 3 cerraduras y escapar con éxito.")
elif energia <= 0 or tiempo <= 0:
    print(f"DERROTA: El agente {personaje} se quedó sin {'energía' if energia <= 0 else 'tiempo'}.")
elif alarma:
    print(f"DERROTA: La alarma fue activada y la bóveda se bloqueó.")
#Fin de la Actividad 4: Escape Room: La Bóveda

#Comienzo de la actividad 5: escape room
print("=== BIENVENIDO A LA ARENA ===")

# Paso 1: Configuración del Personaje
gladiador = input("Nombre del Gladiador: ").strip()
while not gladiador.isalpha() or gladiador == "":
    print("Error: Solo se permiten letras.")
    gladiador = input("Nombre del Gladiador: ").strip()

# Paso 2: Inicialización de Estadísticas (tipos exigidos)
vida_jugador = 100      # int
vida_enemigo = 100      # int
pociones = 3            # int
dano_pesado = 15        # int
dano_enemigo = 12       # int
turno_gladiador = True  # boolean

print(f"\n=== INICIO DEL COMBATE ===")

# Paso 3: Ciclo de Combate
while vida_jugador > 0 and vida_enemigo > 0:
    print(f"\n{gladiador} (HP: {vida_jugador}) vs Enemigo (HP: {vida_enemigo}) | Pociones: {pociones}")
    
    # 
    # TURNO DEL JUGADOR
    # 
    print("Elige acción:")
    print("1. Ataque Pesado")
    print("2. Ráfaga Veloz")
    print("3. Curar")
    
    opcion = input("Opción: ").strip()
    
    # Validación del menú
    while not opcion.isdigit() or int(opcion) < 1 or int(opcion) > 3:
        print("Error: Ingrese un número válido.")
        opcion = input("Opción: ").strip()
    
    opcion = int(opcion)

    # Acción A: Ataque Pesado
    if opcion == 1:
        if vida_enemigo < 20:
            dano_final = float(dano_pesado * 1.5)  # Golpe Crítico (float)
            print(f"¡GOLPE CRÍTICO! Atacaste con furia al enemigo por {dano_final} puntos de daño!")
        else:
            dano_final = float(dano_pesado)
            print(f"¡Atacaste al enemigo por {dano_final} puntos de daño!")
            
        vida_enemigo -= int(dano_final)

    # Acción B: Ráfaga Veloz
    elif opcion == 2:
        print(">> ¡Inicias una ráfaga de golpes!")
        for golpe in range(3):
            dano_golpe = 5
            vida_enemigo -= dano_golpe
            print(f"> Golpe conectado por {dano_golpe} de daño")

    # Acción C: Curar
    elif opcion == 3:
        if pociones > 0:
            vida_jugador += 30
            pociones -= 1
            print(f"Te has curado. Recuperaste 30 HP. Pociones restantes: {pociones}")
        else:
            print("¡No quedan pociones! Perdiste la oportunidad de curarte.")

    # 
    # TURNO DEL ENEMIGO (si sigue vivo)
    # 
    if vida_enemigo > 0:
        vida_jugador -= dano_enemigo
        print(f">> ¡El enemigo te atacó por {dano_enemigo} puntos de daño!")

# 
# PASO 4: FIN DEL JUEGO
# 
print("\n================ FIN DEL COMBATE ================")
if vida_jugador > 0:
    print(f"¡VICTORIA! {gladiador} ha ganado la batalla.")
else:
    print("DERROTA. Has caído en combate.")
#Fin de la actividad 5
