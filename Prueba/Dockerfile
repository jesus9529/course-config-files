# Etapa 1: Compilación usando Eclipse Temurin JDK 17
FROM eclipse-temurin:17-jdk AS build

# Directorio de trabajo en el contenedor
WORKDIR /app

# Copiar el código fuente desde la carpeta src
COPY src /app/src

# Compilar el archivo Java desde la carpeta src
RUN javac -d /app/classes /app/src/App.java

# Empaquetar la clase compilada en un archivo JAR
RUN jar -cvfe /app/HelloWorld.jar HelloWorld -C /app/classes .

# Etapa 2: Ejecución usando Eclipse Temurin JDK 17
FROM eclipse-temurin:17-jre

# Directorio de trabajo en la imagen de ejecución
WORKDIR /app

# Copiar el JAR desde la etapa de compilación
COPY --from=build /app/HelloWorld.jar /app/HelloWorld.jar

# Comando por defecto para ejecutar el JAR
ENTRYPOINT ["java", "-jar", "HelloWorld.jar"]
