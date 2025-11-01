## Book Translation Tool (with Gemini API)
A Python tool  to translate PDF documents page-by-page using the Google Gemini, maintaining translation context.

### Features
* __Intelligent Translation:__ Leverages the power of **Google Gemini** for high-quality, nuanced translations.
* __Context Preservation:__ Feeds the translation from the previous page as context for the next one, improving consistency across long documents. 
* __Structured Output:__ Saves all translations in **JSON Lines** (`.jsonl`) format, perfect for data analysis or further processing.
* __Advanced Error Handling:__ Robustly manages API errors, including rate limits, with automatic retry logic.
* __Detailed Logging:__ Tracks every operation with clear, timestamped log messages for easy debugging.

### Installation and Configuration
Follow these steps to set up the project locally.

1. **Copy the repository:** 
   ```bash 
   git clone https://github.com/alipour66m/book-translation-tool.git
   cd book-translation-tool 
   ```
2. **Create and activate a virtual environment** *(recommended)*:
   * __macOS/Linux:__
      ```bash
      python3 -m venv .venv
      source .venv/bin/activate
      ```
   * __Windows:__
      ```bash
      python -m venv .venv
      .\.venv\Scripts\activate
      ```
3. **Install the dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
4. **Configure your API Key:**

   Copy the example environment file:
   ```bash
   cp .env.example .env
   ```
   Now, edit the `.env` file and add your Google Gemini API key:
   ``` py
   API_KEY = "your_gemini_api_goes_here"
   ```
   *You can get your API key from [Google AI Studio](https://aistudio.google.com/app/api-keys)*

### Usage
1. Place your PDF file (e.g., `book.pdf`) in the root folder of the project.
2. Create your prompt file (e.g., `prompt.txt`) or use one from the `prompts/` directory as a starting point.
3. Run the script from your terminal:
   ```bash
   python bookTranslation.py
   ```
4. Follow the on-screen prompts to provide the paths to your PDF, output file, and prompt file.

The script will begin processing the PDF page by page, showing real-time progress.

### Output Format
The output `.jsonl` file will contain one JSON object for each page of the PDF.

**Example of a successfully translated page:**
```json
{
   "page_number": 1,
   "status": "success",
   "original_text_preview": "In principio era il Verbo...",
   "translated_text": "In the beginning was the Word...",
   "error_message": null
}
```
**Example of a page that failed:**
```json
{
   "page_number": 2,
   "status": "error",
   "original_text_preview": "This page was empty or unreadable...",
   "translated_text": null,
   "error_message": "Page did not contain any extractable text."
}
```

## Contributing 
Contributions are welcome! This is a personal project, but I'm, open to collaboration.
Please feel free to open an issue to discuss a new feature or submit a pull request.

## License
This project is licensed under the MIT License - see the `LICENSE` file for details.

## Author
_**Luca D'Alessandro**_

*Mathematical Sciences for AI Student, Sapienza University of Rome*

Passionate about Artificial Intelligence and building tools to solve real-world problems.
* **[GitHub](https://github.com/luca-dalessandro)**
* **[LinkedIn](https://www.linkedin.com/in/luca-d-alessandro-904o13d4/)**
