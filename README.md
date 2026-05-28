# parcial2-rag-fintech
Sistema RAG para la consulta de regulación Fintech y Crowdfunding en Colombia - Universidad de los Andes
# Sistema RAG: Regulación Fintech y Crowdfunding en Colombia

**HE2: Inteligencia Artificial Aplicada a la Economía**  
Universidad de los Andes — 2026-1

## Descripción

Sistema de Retrieval-Augmented Generation (RAG) aplicado al dominio 
de regulación financiera, FinTech y crowdfunding en Colombia bajo la 
supervisión de la Superintendencia Financiera de Colombia (SFC).

El sistema permite consultar normativa colombiana vigente (decretos, 
circulares, manuales de la SFC) y obtener respuestas contextualizadas 
y trazables a los documentos originales, sin alucinaciones.

## Estructura del repositorio

- `datap2/` — Corpus documental: 12 PDFs de normativa colombiana
- `parcial_rag_final.ipynb` — Notebook con el pipeline RAG completo
- `reporte_parcial2.pdf` — Reporte formal del proyecto

## Pipeline

1. Extracción de texto con `pdfplumber`
2. Chunking con `RecursiveCharacterTextSplitter` (800 chars, overlap 150)
3. Embeddings con `intfloat/multilingual-e5-small` (384 dimensiones)
4. Base de datos vectorial con FAISS (1.540 vectores)
5. Generación con LLaMA 3.1 (8B) vía API de Groq

## Requisitos para ejecutar

- Cuenta en [Groq](https://console.groq.com) → API key gratuita
- Cuenta en [Hugging Face](https://huggingface.co) → token gratuito
- Configurar ambas en Secrets de Google Colab como 
  `GROQ_API_KEY` y `HF_TOKEN`
