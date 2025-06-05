# README.md — Kotlin Test con Assert y Documentación

Este archivo contiene ejemplos de tests en Kotlin con **JUnit5** utilizando los siguientes asserts:

- `assertFalse(valor)`
- `assertTrue(valor)`
- `assertNotEquals(valorEsperat, valorCalculat)`
- `assertEquals(valorEsperat, valorCalculat)`
- `assertArrayEquals(valorEsperat, valorCalculat)`
- `assertNull(valor)`
- `assertNotNull(valor)`
- `assertSame(valorEsperat, valorCalculat)`
- `assert(valor) { missatge }`

Todos los ejemplos tienen documentación arriba de cada test para explicar su función (formato societario).

---

```kotlin
import org.junit.jupiter.api.Test
import org.junit.jupiter.api.assertThrows
import kotlin.test.*

class AssertExamplesTest {

    /**
     * ✅ assertTrue: Verifica que una condición es verdadera.
     */
    @Test
    fun `verifica que 2 + 2 es igual a 4`() {
        assertTrue(2 + 2 == 4)
    }

    /**
     * ✅ assertFalse: Verifica que una condición es falsa.
     */
    @Test
    fun `verifica que 2 + 2 no es igual a 5`() {
        assertFalse(2 + 2 == 5)
    }

    /**
     * ✅ assertEquals: Compara dos valores esperados y calculados.
     */
    @Test
    fun `verifica que el resultado sea igual al esperado`() {
        val esperat = 10
        val calculat = 5 + 5
        assertEquals(esperat, calculat)
    }

    /**
     * ✅ assertNotEquals: Verifica que dos valores no sean iguales.
     */
    @Test
    fun `verifica que los valores no sean iguales`() {
        val esperat = 8
        val calculat = 4 + 4 + 1
        assertNotEquals(esperat, calculat)
    }

    /**
     * ✅ assertArrayEquals: Compara dos arrays elemento por elemento.
     */
    @Test
    fun `verifica que dos arrays sean iguales`() {
        val esperat = intArrayOf(1, 2, 3)
        val calculat = intArrayOf(1, 2, 3)
        assertContentEquals(esperat, calculat)
    }

    /**
     * ✅ assertNull: Verifica que un valor es nulo.
     */
    @Test
    fun `verifica que el valor sea null`() {
        val valor: String? = null
        assertNull(valor)
    }

    /**
     * ✅ assertNotNull: Verifica que un valor no sea nulo.
     */
    @Test
    fun `verifica que el valor no sea null`() {
        val valor: String? = "Kotlin"
        assertNotNull(valor)
    }

    /**
     * ✅ assertSame: Verifica que dos variables referencien el mismo objeto.
     */
    @Test
    fun `verifica que dos referencias apunten al mismo objeto`() {
        val obj1 = "Hola"
        val obj2 = obj1
        assertSame(obj1, obj2)
    }

    /**
     * ✅ assert con mensaje personalizado: Verifica que una condición es verdadera y muestra un mensaje si falla.
     */
    @Test
    fun `verifica que una condición se cumpla con mensaje personalizado`() {
        val edad = 18
        assert(edad >= 18) { "La edad debe ser mayor o igual a 18" }
    }
}
