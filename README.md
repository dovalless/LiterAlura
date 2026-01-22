# 📚 Challenge LiterAlura - Buscador de Libros

<div align="center">

**Aplicación Java para Consulta y Gestión de Libros desde API Externa**

[![Java](https://img.shields.io/badge/Java-17%2B-007396?style=for-the-badge&logo=openjdk&logoColor=white)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16.x-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Alura ONE](https://img.shields.io/badge/Alura_ONE-Challenge-00A86B?style=for-the-badge&logo=alura&logoColor=white)](https://www.aluracursos.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

[🎯 Descripción](#-descripción-del-proyecto) • 
[🚀 Características](#-características) • 
[🛠️ Tecnologías](#️-tecnologías-utilizadas) • 
[⚙️ Instalación](#️-instalación-y-configuración) • 
[📖 Uso](#️-uso-de-la-aplicación) • 
[🗄️ Base de Datos](#️-base-de-datos) • 
[👨‍💻 Autor](#️-autor)

</div>

---

## 📋 Descripción del Proyecto
**LiterAlura** es una aplicación desarrollada en Java que permite consultar libros y autores utilizando la API pública de **[Gutendex](https://gutendex.com/)**, un catálogo de libros del Proyecto Gutenberg. La aplicación cuenta con una interfaz de línea de comandos (CLI) interactiva que permite a los usuarios buscar, guardar y gestionar información literaria, almacenando los datos en una base de datos local para consultas posteriores.

### 🎯 Objetivos del Challenge
Este proyecto forma parte del **Challenge de la formación Backend de Alura Latam + Oracle ONE**, con los siguientes objetivos:
- Integrar una API externa (Gutendex) en una aplicación Java
- Implementar persistencia de datos con Spring Data JPA
- Crear una interfaz de usuario interactiva en consola
- Gestionar relaciones entre entidades (Libros ↔ Autores)
- Practicar principios de desarrollo backend y arquitectura limpia

### 🌟 Fuente de Datos
La aplicación utiliza la **API de Gutendex** que proporciona acceso a más de 60,000 libros electrónicos gratuitos del Proyecto Gutenberg, incluyendo metadatos completos como:
- Título, autores, idiomas, géneros
- Número de descargas, enlaces de descarga
- Información detallada de autores

---

## 🚀 Características

### 📊 Funcionalidades Principales
| Función | Descripción | Tipo |
|---------|-------------|------|
| **🔍 Búsqueda por Título** | Buscar libros por nombre en la API de Gutendex | Consulta Externa |
| **👨‍🏫 Búsqueda por Autor** | Encontrar libros por nombre de autor | Consulta Externa |
| **💾 Guardar Libros** | Almacenar libros consultados en base de datos local | Persistencia |
| **📚 Listar Libros Guardados** | Mostrar todos los libros almacenados localmente | Consulta Local |
| **👥 Listar Autores** | Mostrar autores de los libros guardados | Consulta Local |
| **🏷️ Listar por Idioma** | Filtrar libros por idioma (es, en, fr, etc.) | Filtrado |
| **📈 Estadísticas** | Mostrar métricas y estadísticas de la colección | Análisis |
| **📊 Top 10 Descargas** | Mostrar los libros más populares por descargas | Ranking |

### 🎨 Interfaz de Usuario
La aplicación presenta un **menú interactivo en consola** con las siguientes opciones:
```
╔══════════════════════════════════════╗
║        📚 LITERALURA - MENÚ          ║
╠══════════════════════════════════════╣
║ 1. 🔍 Buscar libro por título        ║
║ 2. 👨‍🏫 Buscar libro por autor         ║
║ 3. 📚 Mostrar libros guardados       ║
║ 4. 👥 Mostrar autores guardados      ║
║ 5. 🏷️ Mostrar libros por idioma      ║
║ 6. 📈 Ver estadísticas               ║
║ 7. 📊 Top 10 libros más descargados  ║
║ 8. 🚪 Salir                          ║
╚══════════════════════════════════════╝
```

### 💾 Persistencia de Datos
Cada libro consultado se almacena en la base de datos con la siguiente información:
- **Información del Libro:** Título, idioma, número de descargas, género
- **Información del Autor:** Nombre, año de nacimiento/muerte, biografía
- **Relaciones:** Un libro puede tener múltiples autores, un autor múltiples libros

---

## 🛠️ Tecnologías Utilizadas

### 🔧 Backend y Framework
| Tecnología | Versión | Propósito |
|------------|---------|-----------|
| **Java** | 17+ | Lenguaje principal de desarrollo |
| **Spring Boot** | 3.x | Framework para aplicación backend |
| **Spring Data JPA** | 3.x | Abstracción para persistencia de datos |
| **Hibernate** | 6.x | ORM para mapeo objeto-relacional |
| **Maven** | 3.8+ | Gestión de dependencias y build |

### 🗄️ Base de Datos
| Tecnología | Versión | Propósito |
|------------|---------|-----------|
| **PostgreSQL** | 16.x | Base de datos relacional principal |
| **H2 Database** | 2.x | Base de datos en memoria para testing |
| **Flyway** | 9.x | Migraciones de base de datos |

### 🔌 Integración Externa
| Tecnología | Propósito |
|------------|-----------|
| **Gutendex API** | Fuente de datos de libros y autores |
| **Jackson** | Serialización/deserialización JSON |
| **Spring Web** | Cliente HTTP para consumir API |

### 🧪 Testing y Calidad
| Herramienta | Propósito |
|-------------|-----------|
| **JUnit 5** | Testing unitario y de integración |
| **Mockito** | Mocking de dependencias |
| **Spring Boot Test** | Testing de contexto Spring |
| **Jacoco** | Cobertura de código |

### 📦 Dependencias Principales
```xml
<dependencies>
    <!-- Spring Boot Starters -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-jpa</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    
    <!-- Base de Datos -->
    <dependency>
        <groupId>org.postgresql</groupId>
        <artifactId>postgresql</artifactId>
        <scope>runtime</scope>
    </dependency>
    
    <!-- Utilities -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-validation</artifactId>
    </dependency>
    
    <!-- Testing -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
    </dependency>
</dependencies>
```

---

## ⚙️ Instalación y Configuración

### ✅ Prerrequisitos
- **Java JDK 17 o superior** ([Descargar](https://www.oracle.com/java/technologies/downloads/))
- **Maven 3.8+** ([Descargar](https://maven.apache.org/download.cgi))
- **PostgreSQL 16+** ([Descargar](https://www.postgresql.org/download/))
- **Git** ([Descargar](https://git-scm.com/downloads))

### 📥 Clonar y Configurar
```bash
# 1. Clonar el repositorio
git clone https://github.com/dovalless/LiterAlura.git
cd LiterAlura

# 2. Configurar base de datos PostgreSQL
sudo -u postgres psql -c "CREATE DATABASE literalura;"
sudo -u postgres psql -c "CREATE USER literalura_user WITH PASSWORD 'secure_password';"
sudo -u postgres psql -c "GRANT ALL PRIVILEGES ON DATABASE literalura TO literalura_user;"

# 3. Configurar archivo de propiedades
# Editar src/main/resources/application.properties:
spring.datasource.url=jdbc:postgresql://localhost:5432/literalura
spring.datasource.username=literalura_user
spring.datasource.password=secure_password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
```

### 🚀 Compilación y Ejecución
```bash
# Compilar el proyecto
mvn clean compile

# Ejecutar tests
mvn test

# Ejecutar la aplicación
mvn spring-boot:run

# O construir JAR y ejecutar
mvn clean package
java -jar target/literalura-1.0.0.jar
```

### 🐳 Usar con Docker (Opcional)
```dockerfile
# Dockerfile
FROM openjdk:17-jdk-slim
COPY target/literalura-1.0.0.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "/app.jar"]
```

```yaml
# docker-compose.yml
version: '3.8'
services:
  postgres:
    image: postgres:16
    environment:
      POSTGRES_DB: literalura
      POSTGRES_USER: literalura_user
      POSTGRES_PASSWORD: secure_password
    ports:
      - "5432:5432"
    volumes:
      - postgres_data:/var/lib/postgresql/data
  
  app:
    build: .
    environment:
      SPRING_DATASOURCE_URL: jdbc:postgresql://postgres:5432/literalura
      SPRING_DATASOURCE_USERNAME: literalura_user
      SPRING_DATASOURCE_PASSWORD: secure_password
    ports:
      - "8080:8080"
    depends_on:
      - postgres

volumes:
  postgres_data:
```

---

## 📖 Uso de la Aplicación

### 🎮 Inicio de la Aplicación
```bash
# Al ejecutar la aplicación, se mostrará el menú principal
==========================================
       BIENVENIDO A LITERALURA
==========================================
1. Buscar libro por título
2. Buscar libro por autor
3. Mostrar libros guardados
4. Mostrar autores guardados
5. Mostrar libros por idioma
6. Ver estadísticas
7. Top 10 libros más descargados
8. Salir
==========================================
Seleccione una opción:
```

### 🔍 Ejemplo: Buscar Libro por Título
```
Seleccione una opción: 1
Ingrese el título del libro: Don Quijote

🔍 Buscando "Don Quijote" en Gutendex...
✅ Encontrado: Don Quijote de la Mancha
👤 Autor: Miguel de Cervantes Saavedra
🗣️ Idioma: Español
📥 Descargas: 15,430
📚 Géneros: Novela, Aventura, Satírica

¿Desea guardar este libro? (S/N): S
✅ Libro guardado exitosamente en la base de datos.
```

### 👤 Ejemplo: Buscar por Autor
```
Seleccione una opción: 2
Ingrese el nombre del autor: Jane Austen

🔍 Buscando libros de Jane Austen...
📚 Libros encontrados:
1. Orgullo y prejuicio (1813) - 12,540 descargas
2. Sentido y sensibilidad (1811) - 9,870 descargas
3. Emma (1815) - 8,920 descargas

Seleccione un libro para guardar (0 para cancelar): 1
✅ "Orgullo y prejuicio" guardado exitosamente.
```

### 📊 Ejemplo: Ver Estadísticas
```
Seleccione una opción: 6

📈 ESTADÍSTICAS DE LA COLECCIÓN
================================
📚 Total de libros guardados: 42
👥 Total de autores únicos: 28
🗣️ Distribución por idioma:
   • Español: 15 libros (35.7%)
   • Inglés: 22 libros (52.4%)
   • Francés: 3 libros (7.1%)
   • Otros: 2 libros (4.8%)
📥 Promedio de descargas: 8,542
🏆 Libro más descargado: "Don Quijote" (15,430 descargas)
```

### 🏷️ Ejemplo: Filtrar por Idioma
```
Seleccione una opción: 5
Seleccione idioma:
1. Español (es)
2. Inglés (en)
3. Francés (fr)
4. Alemán (de)
5. Italiano (it)

Opción: 1

📚 LIBROS EN ESPAÑOL
====================
1. Don Quijote de la Mancha - Miguel de Cervantes
   📥 15,430 descargas | 🏷️ Novela, Aventura
   
2. Cien años de soledad - Gabriel García Márquez
   📥 12,890 descargas | 🏷️ Realismo mágico
   
3. La ciudad y los perros - Mario Vargas Llosa
   📥 8,760 descargas | 🏷️ Novela contemporánea
```

### 🗄️ Ejemplo: Listar Libros Guardados
```
Seleccione una opción: 3

📚 LIBROS GUARDADOS EN LA BASE DE DATOS
=======================================
1. [ID: 1] Don Quijote de la Mancha
   👤 Miguel de Cervantes Saavedra
   🗣️ Español | 📥 15,430 descargas
   💾 Guardado el: 2024-01-15

2. [ID: 2] 1984
   👤 George Orwell
   🗣️ Inglés | 📥 23,450 descargas
   💾 Guardado el: 2024-01-14

3. [ID: 3] Cien años de soledad
   👤 Gabriel García Márquez
   🗣️ Español | 📥 12,890 descargas
   💾 Guardado el: 2024-01-13
```

---

## 🗄️ Base de Datos

### 📊 Modelo de Entidades
```java
@Entity
public class Libro {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    
    private String titulo;
    private String idioma;
    private Integer descargas;
    
    @ManyToMany(fetch = FetchType.EAGER, cascade = CascadeType.ALL)
    @JoinTable(
        name = "libro_autor",
        joinColumns = @JoinColumn(name = "libro_id"),
        inverseJoinColumns = @JoinColumn(name = "autor_id")
    )
    private List<Autor> autores = new ArrayList<>();
    
    // Getters y setters
}

@Entity
public class Autor {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    
    private String nombre;
    private Integer anoNacimiento;
    private Integer anoFallecimiento;
    
    @ManyToMany(mappedBy = "autores")
    private List<Libro> libros = new ArrayList<>();
    
    // Getters y setters
}
```

### 🗂️ Estructura de Tablas
```sql
-- Tabla de libros
CREATE TABLE libro (
    id BIGSERIAL PRIMARY KEY,
    titulo VARCHAR(500) NOT NULL,
    idioma VARCHAR(10),
    descargas INTEGER,
    fecha_registro TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Tabla de autores
CREATE TABLE autor (
    id BIGSERIAL PRIMARY KEY,
    nombre VARCHAR(255) NOT NULL,
    ano_nacimiento INTEGER,
    ano_fallecimiento INTEGER
);

-- Tabla de relación muchos-a-muchos
CREATE TABLE libro_autor (
    libro_id BIGINT REFERENCES libro(id) ON DELETE CASCADE,
    autor_id BIGINT REFERENCES autor(id) ON DELETE CASCADE,
    PRIMARY KEY (libro_id, autor_id)
);
```

### 🔍 Consultas SQL Ejemplo
```sql
-- Libros más populares
SELECT titulo, descargas 
FROM libro 
ORDER BY descargas DESC 
LIMIT 10;

-- Autores con más libros
SELECT a.nombre, COUNT(la.libro_id) as total_libros
FROM autor a
JOIN libro_autor la ON a.id = la.autor_id
GROUP BY a.nombre
ORDER BY total_libros DESC;

-- Distribución por idioma
SELECT idioma, COUNT(*) as cantidad,
       ROUND(COUNT(*) * 100.0 / (SELECT COUNT(*) FROM libro), 2) as porcentaje
FROM libro
GROUP BY idioma
ORDER BY cantidad DESC;
```

---

## 🏗️ Arquitectura del Proyecto

### 📁 Estructura de Directorios
```
LiteralAlura/
├── src/main/java/com/literalura/
│   ├── Main.java                          # Clase principal
│   ├── model/                             # Entidades JPA
│   │   ├── Libro.java
│   │   ├── Autor.java
│   │   └── DTOs/                          # Objetos de transferencia
│   ├── repository/                        # Repositorios Spring Data
│   │   ├── LibroRepository.java
│   │   └── AutorRepository.java
│   ├── service/                           # Lógica de negocio
│   │   ├── LibroService.java
│   │   ├── AutorService.java
│   │   └── ConsumoAPI.java               # Cliente HTTP para Gutendex
│   ├── controller/                        # Controladores (si hay API REST)
│   └── principal/                         # Lógica de la interfaz CLI
│       └── Principal.java                 # Menú principal
├── src/main/resources/
│   ├── application.properties            # Configuración
│   └── data.sql                          (Opcional) Datos iniciales
└── src/test/java/                        # Tests
```

### 🔄 Flujo de la Aplicación
```
1. Usuario selecciona opción del menú
2. Principal llama al servicio correspondiente
3. Servicio consulta API de Gutendex o base de datos
4. Datos se procesan y transforman a DTOs
5. Resultados se muestran al usuario
6. Si es guardar, datos persisten vía Repository
```

### 🌐 Integración con Gutendex API
```java
@Service
public class ConsumoAPI {
    private final String API_URL = "https://gutendex.com/books/";
    
    public Optional<LibroDTO> buscarLibroPorTitulo(String titulo) {
        String url = API_URL + "?search=" + URLEncoder.encode(titulo, StandardCharsets.UTF_8);
        String json = consumirAPI(url);
        return procesarRespuesta(json);
    }
    
    public List<LibroDTO> buscarLibrosPorAutor(String autor) {
        String url = API_URL + "?search=" + URLEncoder.encode(autor, StandardCharsets.UTF_8);
        String json = consumirAPI(url);
        return procesarListaRespuesta(json);
    }
    
    private String consumirAPI(String url) {
        // Implementación con RestTemplate o WebClient
    }
}
```

---

## 🧪 Testing

### 🔬 Tests Unitarios
```java
@ExtendWith(MockitoExtension.class)
class LibroServiceTest {
    
    @Mock
    private LibroRepository libroRepository;
    
    @Mock
    private ConsumoAPI consumoAPI;
    
    @InjectMocks
    private LibroService libroService;
    
    @Test
    void buscarLibroPorTitulo_LibroExiste_RetornaLibroDTO() {
        // Given
        String titulo = "Don Quijote";
        LibroDTO libroMock = new LibroDTO(titulo, "Miguel de Cervantes", "es", 15430);
        
        // When
        when(consumoAPI.buscarLibroPorTitulo(titulo)).thenReturn(Optional.of(libroMock));
        Optional<LibroDTO> resultado = libroService.buscarLibro(titulo);
        
        // Then
        assertTrue(resultado.isPresent());
        assertEquals(titulo, resultado.get().getTitulo());
    }
}
```

### 🧪 Tests de Integración
```java
@DataJpaTest
@AutoConfigureTestDatabase(replace = AutoConfigureTestDatabase.Replace.NONE)
class LibroRepositoryTest {
    
    @Autowired
    private LibroRepository libroRepository;
    
    @Autowired
    private TestEntityManager entityManager;
    
    @Test
    void findByTituloContainingIgnoreCase_TituloExiste_RetornaLibro() {
        // Given
        Libro libro = new Libro("Don Quijote", "es", 15430);
        entityManager.persist(libro);
        
        // When
        Optional<Libro> resultado = libroRepository.findByTituloContainingIgnoreCase("quijote");
        
        // Then
        assertTrue(resultado.isPresent());
        assertEquals("Don Quijote", resultado.get().getTitulo());
    }
}
```

### 📊 Ejecución de Tests
```bash
# Ejecutar todos los tests
mvn test

# Ejecutar tests con cobertura
mvn test jacoco:report

# Ver reporte de cobertura
open target/site/jacoco/index.html
```

---

## 🚀 Despliegue

### ☁️ Opciones de Despliegue

#### 1. Ejecutable JAR (Recomendado para escritorio)
```bash
# Construir JAR con dependencias incluidas
mvn clean package -DskipTests

# El JAR estará en target/literalura-1.0.0.jar
# Ejecutar en cualquier máquina con Java 17+
java -jar literalura-1.0.0.jar
```

#### 2. Docker Container
```dockerfile
# Crear imagen Docker
docker build -t literalura-app .

# Ejecutar contenedor
docker run -it --name literalura \
  -e SPRING_DATASOURCE_URL=jdbc:postgresql://host.docker.internal:5432/literalura \
  -e SPRING_DATASOURCE_USERNAME=literalura_user \
  -e SPRING_DATASOURCE_PASSWORD=secure_password \
  literalura-app
```

#### 3. Servidor Linux con Systemd
```bash
# Crear servicio systemd
sudo nano /etc/systemd/system/literalura.service

# Contenido del servicio:
[Unit]
Description=LiterAlura Application
After=network.target postgresql.service

[Service]
User=appuser
WorkingDirectory=/opt/literalura
ExecStart=/usr/bin/java -jar literalura-1.0.0.jar
SuccessExitStatus=143
Restart=always

[Install]
WantedBy=multi-user.target
```

### 📈 Monitoreo y Logs
```properties
# application.properties - Configuración de logs
logging.level.com.literalura=DEBUG
logging.file.name=logs/literalura.log
logging.pattern.console=%d{yyyy-MM-dd HH:mm:ss} - %msg%n
logging.pattern.file=%d{yyyy-MM-dd HH:mm:ss} [%thread] %-5level %logger{36} - %msg%n
```

---

## 🤝 Contribuir

### 🎯 Guía de Contribución
1. **Fork el repositorio**
   ```bash
   git clone https://github.com/dovalless/LiterAlura.git
   ```

2. **Crear rama de feature**
   ```bash
   git checkout -b feature/nueva-funcionalidad
   ```

3. **Realizar cambios y commits**
   ```bash
   git add .
   git commit -m "feat: agregar búsqueda por género"
   ```

4. **Push y Pull Request**
   ```bash
   git push origin feature/nueva-funcionalidad
   ```

### 📝 Convenciones de Código
- **Nombre de clases:** PascalCase (`LibroService.java`)
- **Nombre de métodos:** camelCase (`buscarLibroPorTitulo()`)
- **Nombre de variables:** camelCase (`descargasTotales`)
- **Comentarios:** En español, claros y concisos
- **Documentación:** JavaDoc para métodos públicos

### 🔄 Mejoras Futuras
- [ ] Interfaz gráfica con JavaFX o Swing
- [ ] API REST para acceso externo
- [ ] Exportación a PDF/Excel de la colección
- [ ] Sistema de recomendaciones basado en géneros
- [ ] Sincronización en la nube entre dispositivos

---

## 👨‍💻 Autor

<div align="center">

**Darwin Manuel Ovalles Cesar**

<p align="center">
<a href="https://www.linkedin.com/in/darwin-manuel-ovalles-cesar-dev" target="_blank">
<img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="LinkedIn - Darwin Ovalles" height="40" width="50" />
</a>
<a href="https://github.com/dovalless" target="_blank">
<img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/github.svg" alt="GitHub - Darwin Ovalles" height="40" width="50" />
</a>
</p>

💼 **LinkedIn**: [darwin-manuel-ovalles-cesar-dev](https://www.linkedin.com/in/darwin-manuel-ovalles-cesar-dev/)  
🌐 **GitHub**: [@dovalless](https://github.com/dovalless)  
📧 **Contacto**: Disponible a través de LinkedIn  
🎓 **Certificaciones**: Java, Spring Boot, PostgreSQL, Alura ONE  

*"LiterAlura combina mi pasión por la literatura con el desarrollo de software. Este proyecto demuestra cómo podemos utilizar APIs públicas para crear herramientas útiles que conectan a las personas con el vasto mundo de los libros digitales gratuitos."*

**#Java #SpringBoot #PostgreSQL #API #Gutendex #Literatura #AluraONE**

</div>

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más detalles.

```
MIT License
Copyright (c) 2024 Darwin Manuel Ovalles Cesar

Permiso concedido, libre de cargo, a cualquier persona que obtenga una copia
de este software y los archivos de documentación asociados (el "Software"), 
para tratar en el Software sin restricción, incluyendo sin limitación los derechos
de usar, copiar, modificar, fusionar, publicar, distribuir, sublicenciar y/o vender
copias del Software, y permitir a las personas a quienes se les proporcione el Software
hacer lo mismo, sujeto a las siguientes condiciones:

El aviso de copyright anterior y este aviso de permiso se incluirán en todas
las copias o partes sustanciales del Software.
```

---

## 🙏 Agradecimientos

- **Alura Latam y Oracle ONE** - Por el desafío y la formación
- **Proyecto Gutenberg** - Por proporcionar acceso libre a la literatura
- **Gutendex API** - Por su excelente API gratuita de libros
- **Comunidad Java** - Por su continuo apoyo y recursos

<div align="center">

### ⭐ Si LiterAlura te resulta útil, considera darle una estrella en GitHub ⭐

### 📚 "Un libro abierto es un cerebro que habla; cerrado, un amigo que espera" 📚

**Desarrollado con 💙 para amantes de la literatura y el código**

---
*Challenge Alura ONE - Formación Backend*  
*Versión: 1.0.0 | Spring Boot 3.1.5 | Java 17 | PostgreSQL 16*  
*Última actualización: Enero 2024*

</div>
```
