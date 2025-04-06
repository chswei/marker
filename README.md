# PDF to Markdown Converter using Marker

This project uses the [Marker](https://github.com/VikParuchuri/marker) library to convert PDF files into Markdown format, including extracting text and images.

## Requirements

This script requires Python and the following packages. It is recommended to use a virtual environment.

*   `marker-pdf`: The core library for PDF conversion.
*   `accelerate`: Required by Marker for efficient model loading and execution.

You can install these using `uv` (or `pip`) within your activated virtual environment:

```bash
uv pip install marker-pdf accelerate
# or
pip install marker-pdf accelerate
```

## Usage

1.  **Activate your virtual environment:**
    ```bash
    source .venv/bin/activate  # Adjust if your venv path is different
    ```
2.  **Run the conversion script:**
    Provide the path to the PDF file you want to convert as a command-line argument.
    ```bash
    python convert.py path/to/your/document.pdf
    ```
    Replace `path/to/your/document.pdf` with the actual path to your PDF.

3.  **Output:**
    The script will create an `output_markdown` subdirectory (if it doesn't exist) in the same directory where you run the script.
    Inside `output_markdown`, you will find:
    *   A `.md` file with the same base name as your input PDF, containing the converted Markdown text.
    *   Any images extracted from the PDF, saved as separate files (e.g., `.jpeg`, `.png`). The Markdown file will reference these image files.

## Notes

*   The first time you run the script, Marker will download necessary machine learning models, which may take some time depending on your internet connection.
*   Conversion time depends on the complexity and length of the PDF, as well as your system's hardware (especially if using GPU acceleration, which `accelerate` helps enable).
