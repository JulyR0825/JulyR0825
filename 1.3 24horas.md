import kotlinx.coroutines.*

fun main() = runBlocking {
    reloj24Horas() // Iniciar el reloj
}

suspend fun reloj24Horas() {
    var horas = 0
    var minutos = 0

    while (true) {
        // Imprimir en formato 24 horas (HH:MM)
        println(String.format("%02d:%02d", horas, minutos))

        // Aumentar un minuto
        minutos++

        // Si los minutos llegan a 60, reiniciar y aumentar la hora
        if (minutos == 60) {
            minutos = 0
            horas++
        }

        // Si las horas llegan a 24, reiniciar el reloj
        if (horas == 24) {
            horas = 0
        }

        // Esperar 1 segundo antes de actualizar (puedes cambiar el valor en milisegundos)
        delay(1000)
    }
}
