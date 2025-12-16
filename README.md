# 🍦 Bad Dopo Cream

<div align="center">

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Swing](https://img.shields.io/badge/Swing-GUI-blue?style=for-the-badge)
![MVC](https://img.shields.io/badge/Pattern-MVC-green?style=for-the-badge)

**Un emocionante juego de arcade desarrollado en Java donde controlas un helado que debe recolectar frutas mientras evita enemigos peligrosos.**

[Características](#-características) • [Instalación](#-instalación) • [Cómo Jugar](#-cómo-jugar) • [Arquitectura](#-arquitectura) • [Niveles](#-niveles)

</div>

---

## 📖 Descripción

**Bad Dopo Cream** es un juego de acción y estrategia inspirado en los clásicos arcades. El jugador controla un helado que debe recolectar todas las frutas del nivel mientras esquiva enemigos y utiliza bloques de hielo como estrategia defensiva.

El juego cuenta con:
- 🎮 **4 modos de juego** diferentes
- 🎯 **3 niveles** con dificultad progresiva
- 🍨 **3 sabores de helado** jugables
- 👾 **4 tipos de enemigos** con comportamientos únicos
- 🍇 **5 tipos de frutas** con mecánicas especiales
- ⏱️ **Sistema de tiempo** límite por nivel

---

## ✨ Características

### Modos de Juego
| Modo | Descripción |
|------|-------------|
| **Player** | Un jugador contra el juego |
| **PvsP** | Dos jugadores cooperativos |
| **PvsM** | Jugador contra máquina inteligente |
| **MvsM** | Máquina vs máquina (demostración de IA) |

### Tipos de Helado
- 🍦 **Vainilla** - El clásico helado cremoso
- 🍓 **Fresa** - Helado rosado y dulce
- 🍫 **Chocolate** - Rico helado de cacao

### Mecánicas del Juego
- **Movimiento en 4 direcciones** (↑ ↓ ← →)
- **Crear bloques de hielo** para bloquear enemigos
- **Romper bloques de hielo** con efecto dominó
- **Recolectar frutas** para ganar puntos y completar niveles

---

## 🚀 Instalación

### Requisitos Previos
- **Java JDK 8** o superior
- **IDE** (Eclipse, IntelliJ IDEA, VS Code) o terminal

### Compilación y Ejecución

#### Opción 1: Desde Terminal

```bash
# Navegar al directorio del proyecto
cd ProyectoFinalPoobParcial

# Compilar el proyecto
javac -d bin -sourcepath src src/BadDopoCream/presentacion/BadDopoCreamGUI.java

# Ejecutar el juego
java -cp bin BadDopoCream.presentacion.BadDopoCreamGUI
```

#### Opción 2: Desde IDE
1. Importar el proyecto en tu IDE favorito
2. Configurar el source folder como `src`
3. Ejecutar la clase `BadDopoCreamGUI.java` ubicada en `BadDopoCream.presentacion`

---

## 🎮 Cómo Jugar

### Controles Jugador 1
| Tecla | Acción |
|-------|--------|
| `↑` | Mover arriba |
| `↓` | Mover abajo |
| `←` | Mover izquierda |
| `→` | Mover derecha |
| `Espacio` | Crear/Romper bloque de hielo |

### Controles Jugador 2 (Modo PvsP)
| Tecla | Acción |
|-------|--------|
| `W` | Mover arriba |
| `S` | Mover abajo |
| `A` | Mover izquierda |
| `D` | Mover derecha |
| `C` | Crear/Romper bloque de hielo |

### Controles Generales
| Tecla | Acción |
|-------|--------|
| `P` | Pausar/Reanudar juego |
| `ESC` | Volver al menú |

---

## 🎯 Niveles

### Nivel 1 - Principiante
- **Frutas:** 8 Uvas + 8 Plátanos (estáticas)
- **Enemigos:** 1 Troll + 1 Maceta
- **Obstáculos:** Ninguno
- **Dificultad:** ⭐

### Nivel 2 - Intermedio
- **Frutas:** 8 Cerezas + 8 Piñas (móviles)
- **Enemigos:** 1 Troll + 1 Calamar Naranja
- **Obstáculos:** Baldosas Calientes (derriten bloques de hielo)
- **Dificultad:** ⭐⭐

### Nivel 3 - Experto
- **Frutas:** 10 Cactus (alternando púas)
- **Enemigos:** 1 Maceta + 1 Narval
- **Obstáculos:** 9 Fogatas (eliminan al helado)
- **Dificultad:** ⭐⭐⭐

---

## 👾 Enemigos

| Enemigo | Comportamiento | Peligrosidad |
|---------|----------------|--------------|
| **Troll** | Movimiento aleatorio | ⚠️ Bajo |
| **Maceta** | Persigue al helado | ⚠️⚠️ Medio |
| **Calamar Naranja** | Persigue y rompe bloques | ⚠️⚠️⚠️ Alto |
| **Narval** | Patrulla y embiste al detectar | ⚠️⚠️⚠️⚠️ Muy Alto |

---

## 🍇 Frutas

| Fruta | Puntos | Comportamiento |
|-------|--------|----------------|
| **Uva** | 50 pts | Estática |
| **Plátano** | 100 pts | Estática |
| **Cereza** | 150 pts | Se teletransporta cada 20 segundos |
| **Piña** | 200 pts | Huye del helado |
| **Cactus** | 250 pts | Alterna púas (peligroso cuando tiene púas) |

---

## 🏗️ Arquitectura

El proyecto sigue el patrón de diseño **MVC (Modelo-Vista-Controlador)**:

```
BadDopoCream/
├── controladores/          # Controlador MVC
│   └── Controlador.java    # Gestiona eventos y comunicación
│
├── dominio/                # Modelo - Lógica del juego
│   ├── Juego.java          # Orquestador principal
│   ├── Nivel.java          # Configuración de niveles
│   ├── Nivel1.java         # Nivel fácil
│   ├── Nivel2.java         # Nivel medio
│   ├── Nivel3.java         # Nivel difícil
│   ├── MaquinaAutomatica.java  # IA para modos automáticos
│   │
│   ├── componentes/        # Entidades del juego
│   │   ├── Componente.java # Clase base abstracta
│   │   ├── helados/        # Tipos de helados
│   │   ├── enemigos/       # Tipos de enemigos
│   │   ├── frutas/         # Tipos de frutas
│   │   └── obstaculos/     # Fogatas y baldosas
│   │
│   ├── tablero/            # Sistema del tablero
│   │   ├── Tablero.java    # Matriz de celdas
│   │   ├── Celda.java      # Casilla individual
│   │   ├── TipoCelda.java  # Tipos de celda
│   │   └── BloqueHielo.java # Bloques creados
│   │
│   └── utilidades/         # Clases de apoyo
│       ├── Posicion.java   # Coordenadas X,Y
│       ├── Direccion.java  # Direcciones de movimiento
│       ├── EstadoJuego.java # Estados del juego
│       └── Temporizador.java # Control de tiempo
│
└── presentacion/           # Vista - Interfaz gráfica
    ├── BadDopoCreamGUI.java # Ventana principal
    ├── TableroPanel.java    # Panel de dibujo
    └── recursos/            # Imágenes y assets
```

---

## 🤖 Inteligencia Artificial

El juego incluye un sistema de IA con **3 perfiles de comportamiento**:

| Perfil | Estrategia |
|--------|------------|
| **Hungry** | Busca frutas agresivamente, ignora peligros |
| **Fearful** | Prioriza la supervivencia, huye de enemigos |
| **Expert** | Balance entre recolección y seguridad |

---

## 📋 Reglas del Juego

1. ✅ **Victoria:** Recolectar todas las frutas del nivel
2. ❌ **Derrota:** Ser tocado por un enemigo, fogata o cactus con púas
3. ⏱️ **Tiempo:** 3 minutos máximo por nivel
4. ❄️ **Bloques:** Usar estratégicamente para atrapar enemigos
5. 🎯 **Puntuación:** Se acumula al recolectar frutas

---

## 🛠️ Tecnologías Utilizadas

- **Lenguaje:** Java SE 8+
- **GUI:** Java Swing/AWT
- **Patrón:** MVC (Model-View-Controller)
- **Paradigma:** Programación Orientada a Objetos

---

## 👨‍💻 Autor

**Camilo Aguirre**

- 📧 Universidad escuela colombiana de ingenieria julio garavito 
- 📅 Proyecto Final - POOB (Programación Orientada a Objetos)
- 📆 Diciembre 2025

---

## 📄 Licencia

Este proyecto fue desarrollado con fines educativos como proyecto final del curso de Programación Orientada a Objetos.

---

<div align="center">

**¡Disfruta jugando Bad Dopo Cream! 🍦❄️**

*No dejes que los enemigos derritan tu diversión*

</div>
