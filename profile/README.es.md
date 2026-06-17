# AymurAI

Idioma: [English](README.md) | **Español**

AymurAI es una aplicación de código abierto que utiliza inteligencia artificial para facilitar la anonimización y el análisis estructurado de resoluciones judiciales vinculadas con casos de violencia de género en América Latina.

El proyecto ayuda a equipos judiciales a procesar resoluciones, revisar predicciones de modelos, anonimizar información sensible y curar datasets estructurados para investigación, transparencia y toma de decisiones institucionales.

AymurAI integra:

- Una **interfaz web** servida desde el backend.
- Una **aplicación de escritorio para Windows**.
- Un **backend FastAPI**.
- Pipelines de machine learning para:
  - anonimización de documentos;
  - extracción de información estructurada para datasets públicos.

Conocé más en [aymurai.info](https://www.aymurai.info).

## Qué hace AymurAI

AymurAI actualmente soporta dos flujos principales:

1. **Anonymizer**
   - Detecta entidades e información sensible en documentos judiciales.
   - Permite revisión y corrección manual.
   - Genera documentos anonimizados.

2. **Data-public**
   - Extrae información estructurada de resoluciones judiciales.
   - Permite validación humana.
   - Ayuda a construir datasets sobre casos de violencia de género.

El sistema está diseñado para documentos judiciales en español y fue desarrollado en colaboración con equipos feministas, técnicos y judiciales de América Latina.

## Funcionalidades principales

AymurAI incluye una experiencia integrada de backend y frontend.

Principales funcionalidades:

- Aplicación web incluida en el backend, disponible en `/`.
- API pública montada bajo `/api`.
- Documentación Swagger disponible en `/api/docs`.
- Procesamiento de documentos PDF y DOCX.
- Anonimización de PDF preservando el layout.
- Anonimización de DOCX con exportación a ODT.
- Políticas configurables de anonimización y desambiguación.
- Imagen Docker de producción con modelos y frontend incluidos.
- Aplicación de escritorio para Windows (opcional).

## Inicio rápido con Docker

La forma recomendada de ejecutar AymurAI es mediante Docker.

```bash
docker run -d \
  --name aymurai-backend \
  --restart unless-stopped \
  -p 8899:8899 \
  ghcr.io/aymurai/api:full
```

Luego abrir:

```text
http://localhost:8899
```

Cuando se usa el frontend, ya sea la aplicación web o la aplicación de escritorio, elegir la opción **Servidor** e ingresar la URL base de la API:

```text
http://localhost:8899/api
```

Si AymurAI está desplegado en un servidor remoto, reemplazar `localhost` por la IP o el dominio del servidor.

Documentación de la API:

```text
http://localhost:8899/api/docs
```

Para despliegues donde sea importante persistir base de datos y caché, montar un directorio del host:

```bash
mkdir -p ./aymurai-cache

docker run -d \
  --name aymurai-backend \
  --restart unless-stopped \
  -p 8899:8899 \
  -v "$(pwd)/aymurai-cache:/resources/cache" \
  ghcr.io/aymurai/api:full
```

En servidores institucionales, recomendamos exponer AymurAI mediante un proxy inverso con HTTPS y un certificado TLS válido.

## Repositorios principales

- Backend, API, pipelines, imagen Docker y frontend integrado:
  [github.com/AymurAI/backend](https://github.com/AymurAI/backend)

- Releases de la aplicación de escritorio:
  [github.com/AymurAI/desktop-app/releases](https://github.com/AymurAI/desktop-app/releases)

- Modelos públicos en Hugging Face:
  [huggingface.co/aymurai](https://huggingface.co/aymurai)

## Documentación

- README del backend:
  [github.com/AymurAI/backend](https://github.com/AymurAI/backend)

- Documentación de la API luego de levantar el servicio:
  `http://localhost:8899/api/docs`

- Sitio web del proyecto:
  [aymurai.info](https://www.aymurai.info)

## Contacto

Para consultas, colaboraciones o despliegues institucionales:

- [info@datagenero.org](mailto:info@datagenero.org)
- [aymurai.info](https://www.aymurai.info)

## Citar AymurAI

Si usás AymurAI en investigación o publicaciones, por favor citá:

```bibtex
@techreport{feldfeber2022,
  author      = {Feldfeber, Ivana and Quiroga, Yasmín Belén and Guevara, Clarissa and Ciolfi Felice, Marianela},
  title       = {Feminisms in Artificial Intelligence: Automation Tools towards a Feminist Judiciary Reform in Argentina and Mexico},
  institution = {DataGenero},
  year        = {2022},
  url         = {https://drive.google.com/file/d/1P-hW0JKXWZ44Fn94fDVIxQRTExkK6m4Y/view}
}
```

## Licencia

AymurAI es software de código abierto bajo licencia MIT.
