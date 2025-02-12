# Appendix A: Full Prompts for AI Solution Generation

The following table presents the full set of prompts used in the AI solution generation process. These prompts were applied to each problem in the dataset, with variations designed to introduce different challenges and complexities in the generated code.

| ID | Variant Type | Prompt |
|---|---|---|
| 0 | No Variants | "ignore all previous instructions. I want you to act like a Python Programmer. You will be provided with a problem statement delimited by triple quotes and you will provide me the Python Code solution. Do not provide any explanations. Do not respond with anything except the Python code. Do not provide any other programming language solution but only Python. `{problem_statement}`" |
| 1 | Variable Name Substitution | "ignore all previous instructions. I want you to act like a Python Programmer. You will be provided with a problem statement delimited by triple quotes and you will provide me the Python Code solution. Ensure that you change the variable names in the code for words without sense. Do not provide any explanations. Do not respond with anything except the Python code. Do not provide any other programming language solution but only Python. `{problem_statement}`" |
| 2 | Verbose Code | "ignore all previous instructions. I want you to act like a Python Programmer. You will be provided with a problem statement delimited by triple quotes and you will provide me the Python Code solution. Please provide the solution keeping it as long as possible. Do not provide any explanations. Do not respond with anything except the Python code. Do not provide any other programming language solution but only Python. `{problem_statement}`" |
| 3 | Concise Code | "ignore all previous instructions. I want you to act like a Python Programmer. You will be provided with a problem statement delimited by triple quotes and you will provide me the Python Code solution. Please provide the solution keeping it as short as possible. Do not provide any explanations. Do not respond with anything except the Python code. Do not provide any other programming language solution but only Python. `{problem_statement}`" |
| 4 | Dead Code Insertion | "ignore all previous instructions. I want you to act like a Python Programmer. You will be provided with a problem statement delimited by triple quotes and you will provide me the Python Code solution. Create 5 snippets of dead code and add them into the code. Do not provide any explanations. Do not respond with anything except the Python code. Do not provide any other programming language solution but only Python. `{problem_statement}`" |
| 5 | No Comments | "ignore all previous instructions. I want you to act like a Python Programmer. You will be provided with a problem statement delimited by triple quotes and you will provide me the Python Code solution. Ensure the code does not contain any comments. Do not provide any explanations. Do not respond with anything except the Python code. Do not provide any other programming language solution but only Python. `{problem_statement}`" |

# Appendix B: Examples of Code Variants

## Human-Written Code Examples

### Human 1 (Problem 160)

```python
def movimiento_robot(orientacion_actual:str, giro:str)->str:
    if (orientacion_actual=="S" and giro=="H") or (orientacion_actual=="W" and giro=="R") or (orientacion_actual=="E" and giro=="L") or (orientacion_actual=="N" and giro=="."):
        posx="N"
    elif (orientacion_actual=="W" and giro=="H") or (orientacion_actual=="N" and giro=="R") or (orientacion_actual=="S" and giro=="L") or (orientacion_actual=="E" and giro=="."):
        posx="E"
    elif (orientacion_actual=="N" and giro=="H") or (orientacion_actual=="W" and giro=="L") or (orientacion_actual=="E" and giro=="R") or (orientacion_actual=="S" and giro=="."):
        posx="S"
    else:
        posx="W"
    return posx
```

### Human 3 (Problem 160)

```python
def movimiento_robot(orientacion_actual: str, giro: str)->str:
    m1=""
    if orientacion_actual=="N"and giro=="L":
        m1="W"
    if orientacion_actual=="N"and giro=="R":
        m1="E"
    if orientacion_actual=="N"and giro=="H":
        m1="S"
    if orientacion_actual=="N"and giro==".":
        m1="N"
    if orientacion_actual=="W"and giro=="L":
        m1="S"
    if orientacion_actual=="W"and giro=="R":
        m1="N"
    if orientacion_actual=="W"and giro=="H":
        m1="E"
    if orientacion_actual=="W"and giro=="H":
        m1="E"
    if orientacion_actual=="S"and giro=="L":
        m1="E"
    if orientacion_actual=="S"and giro=="R":
        m1="W"
    if orientacion_actual=="S"and giro=="H":
        m1="N"
    if orientacion_actual=="S"and giro==".":
        m1="S"
    if orientacion_actual=="E"and giro=="L":
        m1="N"
    if orientacion_actual=="E"and giro=="R":
        m1="S"
    if orientacion_actual=="E"and giro=="H":
        m1="W"
    if orientacion_actual=="E"and giro==".":
        m1="E"
    return str(m1)
```

## AI-Generated Code Examples

### No Variants (Problem 160)

```python
def nueva_orientacion(orientacion_inicial, comando):
    orientaciones = ['N', 'E', 'S', 'W']
    indices = {'N': 0, 'E': 1, 'S': 2, 'W': 3}
    giros = {'L': -1, 'R': 1, 'H': 2, '.': 0}
    
    indice_actual = indices[orientacion_inicial]
    indice_nuevo = (indice_actual + giros[comando]) % 4
    
    return orientaciones[indice_nuevo]

# Ejemplos de llamadas a la función
print(nueva_orientacion("N", "R")) # "E"
print(nueva_orientacion("S", "H")) # "N"
print(nueva_orientacion("W", ".")) # "W"
```

### Variable Name Substitution (Problem 160)

```python
def trzn_cmlxps(initial_orientation, command):
    compass = {"N": 0, "E": 1, "S": 2, "W": 3}
    lkc_shp = {0: "N", 1: "E", 2: "S", 3: "W"}
    if command == "L":
        return lkc_shp[(compass[initial_orientation] - 1) % 4]
    elif command == "R":
        return lkc_shp[(compass[initial_orientation] + 1) % 4]
    elif command == "H":
        return lkc_shp[(compass[initial_orientation] + 2) % 4]
    elif command == ".":
        return initial_orientation
```

### Verbose Code (Problem 160)

```python
def robot_orientation(initial_orientation, command):
    orientations = ["N", "E", "S", "W"]
    orientation_index = orientations.index(initial_orientation)

    if command == "L":
        new_orientation_index = (orientation_index - 1) % 4
    elif command == "R":
        new_orientation_index = (orientation_index + 1) % 4
    elif command == "H":
        new_orientation_index = (orientation_index + 2) % 4
    elif command == ".":
        new_orientation_index = orientation_index
    else:
        raise ValueError("Invalid command")

    return orientations[new_orientation_index]

# Test cases
print(robot_orientation("N", "L"))
print(robot_orientation("N", "R"))
print(robot_orientation("N", "H"))
print(robot_orientation("N", "."))
print(robot_orientation("S", "L"))
print(robot_orientation("S", "R"))
print(robot_orientation("S", "H"))
print(robot_orientation("S", "."))
print(robot_orientation("E", "L"))
print(robot_orientation("E", "R"))
print(robot_orientation("E", "H"))
print(robot_orientation("E", "."))
print(robot_orientation("W", "L"))
print(robot_orientation("W", "R"))
print(robot_orientation("W", "H"))
print(robot_orientation("W", "."))
```

### Concise Code (Problem 160)

```python
def predict_orientation(initial, command):
    directions = "NESW"
    index = directions.index(initial)
    if command == "L":
        return directions[(index - 1) % 4]
    elif command == "R":
        return directions[(index + 1) % 4]
    elif command == "H":
        return directions[(index + 2) % 4]
    return initial
```

### Dead Code Insertion (Problem 160)

```python
def predict_orientation(initial_orientation, command):
    orientations = ['N', 'E', 'S', 'W']
    idx = orientations.index(initial_orientation)
    
    # Dead code snippet 1
    x = 10 * 5
    y = x + 20
    
    if command == 'L':
        idx = (idx - 1) % 4
    elif command == 'R':
        idx = (idx + 1) % 4
    elif command == 'H':
        idx = (idx + 2) % 4
    # Dead code snippet 2
    z = y - 10
    
    # Dead code snippet 3
    for i in range(10):
        pass
    
    # Dead code snippet 4
    dummy_list = [1, 2, 3]

    # Dead code snippet 5
    if False:
        pass
    
    return orientations[idx]

# Example usage:
initial_orientation = 'N'
command = 'R'
print(predict_orientation(initial_orientation, command))
```

### No Comments (Problem 160)

```python
def predict_orientation(initial_orientation, command):
    orientations = ["N", "E", "S", "W"]
    idx = orientations.index(initial_orientation)
    if command == "L":
        idx = (idx - 1) % 4
    elif command == "R":
        idx = (idx + 1) % 4
    elif command == "H":
        idx = (idx + 2) % 4
    return orientations[idx]

initial_orientation = "N"
command = "L"
print(predict_orientation(initial_orientation, command))
```
