# AymurAI

Language: **English** | [Español](README.es.md)

AymurAI is an open-source application that uses artificial intelligence to support the anonymization and structured analysis of judicial rulings related to gender-based violence in Latin America.

The project helps judicial teams process rulings, review model predictions, anonymize sensitive information, and curate structured datasets for public-interest research, transparency, and institutional decision-making.

AymurAI combines:

- A **web interface** served from the backend.
- A **Windows desktop application**.
- A **FastAPI backend**.
- Machine learning pipelines for:
  - document anonymization;
  - structured information extraction for public datasets.

Learn more at [aymurai.info](https://www.aymurai.info).

## What AymurAI Does

AymurAI currently supports two main workflows:

1. **Anonymizer**
   - Detects named entities and sensitive information in judicial documents.
   - Supports manual review and correction.
   - Generates anonymized output documents.

2. **Data-public**
   - Extracts structured information from judicial rulings.
   - Supports human validation.
   - Helps build datasets about gender-based violence cases.

The system is designed for Spanish-language judicial documents and has been developed in collaboration with feminist, technical, and judicial teams in Latin America.

## Main Features

AymurAI provides an integrated backend and frontend experience.

Main features include:

- Bundled web application available at `/`.
- Public API mounted under `/api`.
- Swagger documentation at `/api/docs`.
- PDF and DOCX document processing.
- PDF anonymization with layout preservation.
- DOCX anonymization with ODT export.
- Configurable anonymization and disambiguation policies.
- Production Docker image with models and frontend included.
- Windows desktop application (optional).

## Quick Start With Docker

The recommended way to run AymurAI is through Docker.

```bash
docker run -d \
  --name aymurai-backend \
  --restart unless-stopped \
  -p 8899:8899 \
  ghcr.io/aymurai/api:full
```

Then open:

```text
http://localhost:8899
```

When using the frontend, either the web application or the desktop application, choose the **Server** option and enter the API base URL:

```text
http://localhost:8899/api
```

If AymurAI is deployed on a remote server, replace `localhost` with the server IP address or domain.

API documentation:

```text
http://localhost:8899/api/docs
```

For deployments where database/cache persistence matters, mount a host directory:

```bash
mkdir -p ./aymurai-cache

docker run -d \
  --name aymurai-backend \
  --restart unless-stopped \
  -p 8899:8899 \
  -v "$(pwd)/aymurai-cache:/resources/cache" \
  ghcr.io/aymurai/api:full
```

On institutional servers, we recommend exposing AymurAI through a reverse proxy with HTTPS and a valid TLS certificate.

## Main Repositories

- Backend, API, pipelines, Docker image, and bundled frontend:
  [github.com/AymurAI/backend](https://github.com/AymurAI/backend)

- Desktop application releases:
  [github.com/AymurAI/desktop-app/releases](https://github.com/AymurAI/desktop-app/releases)

- Public models on Hugging Face:
  [huggingface.co/aymurai](https://huggingface.co/aymurai)

## Documentation

- Backend README:
  [github.com/AymurAI/backend](https://github.com/AymurAI/backend)

- API documentation after running the service:
  `http://localhost:8899/api/docs`

- Project website:
  [aymurai.info](https://www.aymurai.info)

## Contact

For questions, collaborations, or institutional deployments, contact:

- [info@datagenero.org](mailto:info@datagenero.org)
- [aymurai.info](https://www.aymurai.info)

## Citing AymurAI

If you use AymurAI in research or publications, please cite:

```bibtex
@techreport{feldfeber2022,
  author      = {Feldfeber, Ivana and Quiroga, Yasmín Belén and Guevara, Clarissa and Ciolfi Felice, Marianela},
  title       = {Feminisms in Artificial Intelligence: Automation Tools towards a Feminist Judiciary Reform in Argentina and Mexico},
  institution = {DataGenero},
  year        = {2022},
  url         = {https://drive.google.com/file/d/1P-hW0JKXWZ44Fn94fDVIxQRTExkK6m4Y/view}
}
```

## License

AymurAI is open-source software licensed under the MIT License.
