# OCR and RAG Experiments

## Description

This project benchmarks and demonstrates a wide range of Optical Character Recognition (OCR) and Retrieval-Augmented Generation (RAG) techniques for extracting, cleaning, and querying information from PDF documents. It covers both text-based and image-based PDFs, with a special focus on handling mathematical equations and complex layouts. The notebook provides code and commentary for using and comparing popular OCR tools, PDF parsers, and RAG pipelines, including integration with state-of-the-art LLMs and Vision-Language Models.

---

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Supported Tools & Models](#supported-tools--models)
- [Example Workflow](#example-workflow)
- [Results & Recommendations](#results--recommendations)
- [References](#references)
- [License](#license)

---

## Installation

1. **Clone the repository** and navigate to the project directory.

2. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

3. **Set up API keys**  
   Create an `.env` file in your project directory with your API keys:

   ```
   OPENAI_API_KEY_DRACO=your_openai_api_key
   MISTRAL_API_KEY=your_mistral_api_key
   GEMINI_API_KEY=your_gemini_api_key
   COHERE_API_KEY=your_cohere_api_key
   ```

---

## Usage

1. **Open the notebook**  
   Launch Jupyter and open `ocr_RAG_tests.ipynb`.

2. **Configure file paths**  
   Place your PDF files in the `pdfs` directory or update the `files_path` and `pdf_file` variables as needed.

3. **Run the cells**  
   The notebook is organized into sections for each tool and workflow. You can run all cells or focus on the tools/models you want to benchmark.

4. **Output**  
   - Cleaned and formatted Markdown files are saved to your Desktop.
   - JSON files with parsed document data are also generated.
   - Results and recommendations are printed in the notebook.

---

## Supported Tools & Models

The notebook includes code and benchmarks for:

- **PDF Text Extraction:**  
  - `OpenAI OCR`
  - `Marked-pdf`
  - `docling`
  - `Pytesseract`
  - `Mistral OCR`
  - `surya-ocr`
  - `alibaba-damo/mgp-str-base`
  - `LatexOCR`
  - `zerox`
  - `Ollama OCR`
  - `X-PLUG/mPLUG-DocOwl`
  - `OlmOCR`
  - `GOT OCR`
  - `Nougat OCR`
  - `MegaParse`
- **RAG & LLMs:**  
  - OpenAI GPT-4o, GPT-4o-mini
  - Gemini 2.5
  - Cohere Embed v4
  - ColPali (via Byaldi)
  - Qwen2-VL-2B/7B
  - Visual RAG pipelines

---

## Results & Recommendations

- **Best overall, especially for equations and complex layouts:**  
  - OpenAI GPT-4o Vision (via API) and marked-pdf.
- **Good for contracts and simple text:**  
  - `docling`, `mistral`, `pytesseract`.
- **Visual RAG:**  
  - ColPali + Qwen2-VL pipeline is promising for multimodal retrieval and QA.
- **Other tools:**  
  - Many open-source OCR tools struggle with equations and complex formatting.

See the notebook for detailed benchmarks and code for each tool.

---

## References

- [OpenAI Cookbook: Parse PDF Docs for RAG](https://cookbook.openai.com/examples/parse_pdf_docs_for_rag)
- [Marker](https://github.com/VikParuchuri/marker)
- [Docling](https://github.com/docling-project/docling)
- [MistralAI](https://docs.mistral.ai/capabilities/document/)
- [Byaldi (ColPali)](https://github.com/AnswerDotAI/byaldi)
- [Qwen2-VL](https://huggingface.co/Qwen/Qwen2-VL-7B-Instruct)
- [Cohere](https://cohere.com/)
- [Google Gemini](https://ai.google.dev/)

---

**Note:**  
Some tools require API keys and/or GPU support. See the notebook comments for installation and usage tips for each tool.