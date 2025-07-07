# zmk-config/CMakeLists.txt
#
# Hace que los archivos fuente propios (p. ej. src/screen.c)
# se compilen junto a la app de ZMK.

cmake_minimum_required(VERSION 3.20.0)

# ZMK es una aplicación Zephyr; localiza Zephyr desde la variable de entorno
find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(zmk_config)

# ──────────────────────────────────────────────────────────────
# Añade tus fuentes.  Crea un directorio `src/` y copia ahí tu
# screen.c (y cualquier otro .c/.h que vayas creando).
# ──────────────────────────────────────────────────────────────
target_sources(app PRIVATE
    src/screen.c
)

# Si también colocas headers en src/, expón el path al compilador:
target_include_directories(app PRIVATE src)