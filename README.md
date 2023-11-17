# En-busca-del-amor
Juego de la vibora
 # Función para verificar la colisión con los bordes y reiniciar juego si es necesario
    global puntaje
    if (
        cabeza.xcor() < -280
        or cabeza.xcor() > 280
        or cabeza.ycor() < -280
        or cabeza.ycor() > 280
    ):
        time.sleep(0.5)
        cabeza.goto(0, 0)
        cabeza.direction = 'Stop'
        for segment in cuerpo:
            segment.goto(1000, 1000)
        cuerpo.clear()
        puntaje = 0
        print_text()
def bite():
    # Función para verificar la colisión con el cuerpo y reiniciar juego si es necesario
    global puntaje
    for segment in cuerpo:
        if cabeza.distance(segment) < 20:
            time.sleep(0.5)
            cabeza.goto(0, 0)
            cabeza.direction = 'Stop'
            for segment in cuerpo:
                segment.goto(1000, 1000)
            cuerpo.clear()
            puntaje = 0
            print_text()      
