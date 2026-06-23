# TPI Programación 2

Aplicación de consola FOOD STORE desarrollada en Java.

## Requisitos

- **Linux:** Ubuntu 22.04 o superior / Fedora 40 o superior
- **Windows:** Windows 11
- **Java:** JDK 21

---

## Linux (Ubuntu)

### Instalar Java 21

```bash
sudo apt update
sudo apt install openjdk-21-jdk -y
```

### Revisar instalación

```bash
java -version
javac -version
```

Ambos comandos deben mostrar la versión 21.x.x.

Si `java -version` sigue mostrando Java 17, ejecutá `sudo update-alternatives --config java` y elegí `java-21-openjdk-amd64`, o revisá que `JAVA_HOME` en `~/.zshrc` apunte a `/usr/lib/jvm/java-21-openjdk-amd64`.

### Ejecutar el proyecto

Parate en la raíz del proyecto (la carpeta que contiene `src/`):

```bash
mkdir -p out
javac -d out $(find src -name "*.java")
java -cp out tpi.Main
```

En una sola línea:

```bash
mkdir -p out && javac -d out $(find src -name "*.java") && java -cp out tpi.Main
```

---

## Linux (Fedora)

### Instalar Java 21

```bash
sudo dnf install java-21-openjdk-devel -y
```

### Revisar instalación

```bash
java -version
javac -version
```

Ambos comandos deben mostrar la versión 21.x.x.

Si `java -version` sigue mostrando otra versión, ejecutá `sudo alternatives --config java` y elegí Java 21, o revisá que `JAVA_HOME` en `~/.zshrc` apunte a `/usr/lib/jvm/java-21-openjdk`.

### Ejecutar el proyecto

Parate en la raíz del proyecto (la carpeta que contiene `src/`):

```bash
mkdir -p out
javac -d out $(find src -name "*.java")
java -cp out tpi.Main
```

En una sola línea:

```bash
mkdir -p out && javac -d out $(find src -name "*.java") && java -cp out tpi.Main
```

---

## Windows 11

### Instalar Java 21

1. Descargá el JDK 21 desde [Adoptium](https://adoptium.net/) o [Oracle](https://www.oracle.com/java/technologies/downloads/).
2. Ejecutá el instalador y completá la instalación.
3. Durante la instalación, marcá la opción **Set JAVA_HOME variable** si está disponible.

### Revisar instalación

Abrí PowerShell o CMD y ejecutá:

```powershell
java -version
javac -version
```

Ambos comandos deben mostrar la versión 21.x.x.

Si no reconoce los comandos, agregá Java al PATH:

1. Buscá la carpeta de instalación (ejemplo: `C:\Program Files\Eclipse Adoptium\jdk-21.x.x-hotspot\bin`)
2. Configuración → Sistema → Acerca de → Configuración avanzada del sistema → Variables de entorno
3. En **Path**, agregá la ruta `\bin` del JDK

### Ejecutar el proyecto

Parate en la raíz del proyecto (la carpeta que contiene `src\`) en PowerShell:

```powershell
New-Item -ItemType Directory -Force -Path out
Get-ChildItem -Path src -Recurse -Filter *.java | ForEach-Object { $_.FullName } | ForEach-Object { javac -d out $_ }
java -cp out tpi.Main
```

O compilando todos los archivos de una vez (desde la raíz del proyecto):

```powershell
mkdir out -Force
javac -d out (Get-ChildItem -Path src -Recurse -Filter *.java | ForEach-Object { $_.FullName })
java -cp out tpi.Main
```

---

## Estructura del proyecto

```
.
├── src/
│   └── tpi/
│       ├── Main.java          # Punto de entrada
│       ├── AppContext.java
│       ├── entities/
│       ├── enums/
│       ├── exception/
│       ├── interfaces/
│       ├── repository/
│       ├── service/
│       └── ui/
└── out/                       # Clases compiladas (generada al compilar)
```

## Link al video de Youtube

https://youtu.be/q98aaIOwvXs
