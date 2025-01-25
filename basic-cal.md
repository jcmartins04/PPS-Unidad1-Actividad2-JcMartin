# Calculadora Documentada en Python

## Introducción
En este documento, se implementa una calculadora básica en Python que realiza las operaciones de suma, resta, multiplicación y división. Además, incluye validaciones adicionales para asegurar que los datos ingresados sean válidos utilizando las funciones `isNumber` y `mayorCero`.

## Implementación del código

```python
def suma(a, b):
    """Realiza la suma de dos números."""
    return a + b

def resta(a, b):
    """Realiza la resta de dos números."""
    return a - b

def multiplicacion(a, b):
    """Realiza la multiplicación de dos números."""
    return a * b

def division(a, b):
    """Realiza la división de dos números, manejando el caso de división por cero."""
    if b == 0:
        return "Error: División por cero"
    return a / b

def isNumber(valor):
    """Indica si el argumento introducido es un número o no."""
    try:
        float(valor)  # Intentar convertir a número
        return True
    except ValueError:
        return False

def mayorCero(numero):
    """Indica si el número pasado es mayor que cero."""
    if not isNumber(numero):
        return "Error: El valor no es un número."
    return float(numero) > 0

def calculadora():
    """Muestra un menú de opciones para realizar operaciones matemáticas."""
    print("Seleccione una operación:")
    print("1. Suma")
    print("2. Resta")
    print("3. Multiplicación")
    print("4. División")

    operacion = input("Ingrese el número de la operación (1/2/3/4): ")

    if operacion in ['1', '2', '3', '4']:
        num1 = input("Ingrese el primer número: ")
        num2 = input("Ingrese el segundo número: ")

        # Validar que ambos números sean válidos
        if not isNumber(num1) or not isNumber(num2):
            print("Error: Ambos valores deben ser números válidos.")
            return

        # Convertir a float después de validar
        num1 = float(num1)
        num2 = float(num2)

        # Realizar la operación seleccionada
        if operacion == '1':
            print("Resultado:", suma(num1, num2))
        elif operacion == '2':
            print("Resultado:", resta(num1, num2))
        elif operacion == '3':
            print("Resultado:", multiplicacion(num1, num2))
        elif operacion == '4':
            print("Resultado:", division(num1, num2))
    else:
        print("Operación no válida.")

if __name__ == "__main__":
    calculadora()
```

### Documentación de las funciones
Cada función en el módulo incluye un bloque de comentarios que explica su propósito:

1. **suma(a, b):**
   - Devuelve la suma de dos números.

2. **resta(a, b):**
   - Devuelve la resta de dos números.

3. **multiplicacion(a, b):**
   - Devuelve la multiplicación de dos números.

4. **division(a, b):**
   - Devuelve la división de dos números, o un mensaje de error si el divisor es cero.

5. **isNumber(valor):**
   - Verifica si el argumento introducido es un número.

6. **mayorCero(numero):**
   - Verifica si el número pasado como argumento es mayor que cero y devuelve un mensaje de error si no es un número.

---


## Ejemplo de ejecución

### Caso exitoso:
```
Seleccione una operación:
1. Suma
2. Resta
3. Multiplicación
4. División
Ingrese el número de la operación (1/2/3/4): 1
Ingrese el primer número: 5
Ingrese el segundo número: 3
Resultado: 8.0
```

### Caso con error de entrada:
```
Seleccione una operación:
1. Suma
2. Resta
3. Multiplicación
4. División
Ingrese el número de la operación (1/2/3/4): 2
Ingrese el primer número: abc
Ingrese el segundo número: 5
Error: Ambos valores deben ser números válidos.
```

## Conclusión
Este programa implementa una calculadora funcional que incluye validaciones robustas para manejar entradas incorrectas. Además, asegura que las operaciones matemáticas sean seguras y manejadas correctamente incluso en casos extremos.
