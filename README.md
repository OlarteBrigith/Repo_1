# def bubble_sort(arr):
    """
    Ordena una lista en orden ascendente usando el algoritmo Bubble Sort.

    Args:
    arr (list of int): La lista a ordenar.

    Returns:
    list of int: La lista ordenada.
    """
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr

def ordenar_fila(matriz, fila_index):
    """
    Ordena una fila específica de la matriz en orden ascendente.

    Args:
    matriz (list of list of int): La matriz en la que se ordenará la fila.
    fila_index (int): El índice de la fila a ordenar.
    
    Returns:
    list of list of int: La matriz con la fila ordenada.
    """
    # Verifica si el índice de fila es válido
    if fila_index < 0 or fila_index >= len(matriz):
        raise IndexError("Índice de fila fuera de rango")
    
    # Ordena la fila especificada usando Bubble Sort
    matriz[fila_index] = bubble_sort(matriz[fila_index])
    return matriz

def imprimir_matriz(matriz):
    """
    Imprime la matriz en formato legible.

    Args:
    matriz (list of list of int): La matriz a imprimir.
    """
    for fila in matriz:
        print(fila)

# Definición de la matriz 3x3
matriz = [
    [3, 1, 2],
    [9, 5, 7],
    [6, 8, 4]
]

# Índice de la fila a ordenar (por ejemplo, la fila 1)
fila_a_ordenar = 1

# Mostrar la matriz original
print("Matriz original:")
imprimir_matriz(matriz)

# Ordenar la fila especificada
matriz_ordenada = ordenar_fila(matriz, fila_a_ordenar)

# Mostrar la matriz con la fila ordenada
print(f"\nMatriz después de ordenar la fila {fila_a_ordenar}:")
imprimir_matriz(matriz_ordenada)
