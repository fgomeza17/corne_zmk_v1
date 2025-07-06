# config/CMakeLists.txt
#
# Compila los .c propios que coloques en config/src
# y hace visibles los headers de config/include

# 1 Declaramos una pequeña biblioteca Zephyr
zephyr_library()

# 2 Lista de fuentes que quieres compilar
#    - screen.c es imprescindible; battery.c es opcional
zephyr_library_sources(
  src/screen.c
  # src/battery.c    # <-- descomenta si vas a tocar el widget de batería
)

# 3 Carpeta con tus cabeceras (.h)
zephyr_library_include_directories(
  include
)