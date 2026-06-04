# LP3.BlazorServer

Sistema de gestión académica desarrollado con **Blazor Server** para la asignatura **Lenguaje de Programación III**.

## Tecnologías

- **.NET 10** — Framework principal
- **Blazor Server** — UI interactiva con renderizado en servidor
- **ASP.NET Core Identity** — Autenticación y autorización
- **Entity Framework Core + SQLite** — Persistencia de datos
- **Arquitectura limpia** en capas (Domain, Application, Data, Shared)

## Estructura del proyecto

```
├── Domain/                  # Capa de dominio
│   ├── Entities/            #  Entidades: Estudiante, Curso, Matriculacion
│   ├── Enums/               #  Enumeraciones: EstadoEstudiante, TipoDocumento
│   └── Constants/           #  Reglas de dominio y validaciones
├── Data/                    # Capa de datos
│   ├── Repositories/        #  Repositorio genérico + repositorio específico
│   ├── Migrations/          #  Migraciones de EF Core
│   └── ApplicationDbContext #  Contexto de base de datos
├── Application/             # Capa de aplicación
│   └── Services/            #  Servicios con lógica de negocio
├── Shared/                  # Capa compartida
│   ├── DTOs/                #  Objetos de transferencia de datos
│   └── Extensions/          #  Métodos de extensión (Entidad ↔ DTO)
├── Components/              # Capa de presentación (Blazor)
│   ├── Pages/               #  Páginas: Home, Estudiantes, Auth, etc.
│   ├── Layout/              #  Layouts y navegación
│   └── Account/             #  Componentes de Identity
└── Program.cs               # Punto de entrada y configuración DI
```

## Funcionalidades

- **Autenticación** con Identity (registro, inicio de sesión)
- **CRUD de estudiantes** — buscar por matrícula, registrar, listar, editar y eliminar
- Arquitectura con inyección de dependencias y patrón **Repository** + **Service**

## Ejecución

```bash
dotnet restore
dotnet run
```

La aplicación estará disponible en `https://localhost:5001` (o el puerto configurado).
