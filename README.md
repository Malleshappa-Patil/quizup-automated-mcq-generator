# QuizUp - AI Question Generator

QuizUp is a web-based application that leverages Google's Gemini 1.5 Pro AI model to automatically generate questions from uploaded documents. The application supports multiple question formats and difficulty levels, making it ideal for educators, students, and anyone looking to create quiz content from educational materials.

---

## Features

- **Multiple File Format Support**: Upload documents in PDF, TXT, or DOCX formats
- **AI-Powered Question Generation**: Utilizes Google Gemini 1.5 Pro for intelligent question creation
- **Customizable Options**:
  - Choose number of questions (1-50)
  - Select question types (Multiple Choice, True/False, Fill-in-the-Blanks)
  - Set difficulty levels (Easy, Medium, Hard)
- **Export Options**: Download generated questions in both TXT and PDF formats
- **Interactive UI**: Modern, responsive interface with drag-and-drop file upload
- **Real-time Processing**: Instant question generation and preview

---

## Workflow Diagram

![Screenshot 2024-12-31 152026](https://github.com/user-attachments/assets/86d0b43b-8905-43c7-b75c-86f21a0f57e1)


---

## Installation

1. Clone the repository:
```bash
git clone [your-repository-url]
cd quizup
```

2. Create and activate a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install required dependencies:
```bash
pip install flask pdfplumber python-docx google-generativeai fpdf Werkzeug
```

4. Set up your Google API key:
- Get your API key from Google AI Studio
- Create a `.env` file in the project root directory:
```bash
GOOGLE_API_KEY=your-api-key-here
```
- Alternatively, set it as an environment variable or directly in `app.py`

---

## Environment Configuration

The application uses a `.env` file to store sensitive configuration. Create a `.env` file in the root directory:

```env
GOOGLE_API_KEY=your-google-api-key-here
```

**Important**: Never commit your `.env` file to version control. Add it to `.gitignore`:

```gitignore
.env
```

---

## Project Structure

```
quizup/
├── app.py              # Main Flask application
├── .env               # Environment variables (not in version control)
├── templates/
│   ├── index.html     # Main upload page
│   └── results.html   # Question display page
├── uploads/           # Temporary storage for uploaded files
└── results/           # Generated question files (TXT/PDF)
```

---

## Usage

1. Start the application:
```bash
python app.py
```

2. Open your web browser and navigate to `http://127.0.0.1:5000/`

3. Upload a document and configure:
   - Select your document file (PDF/TXT/DOCX)
   - Choose the number of questions
   - Select question type
   - Set difficulty level

4. Click "Generate Questions" to create your quiz

5. View generated questions and:
   - Toggle answer visibility
   - Download as TXT or PDF
   - Return to generate more questions

---

## Technical Details

- **Backend**: Python Flask
- **Frontend**: HTML, CSS (Tailwind CSS), JavaScript
- **AI Model**: Google Gemini 1.5 Pro
- **File Processing**: 
  - PDFPlumber for PDF extraction
  - python-docx for DOCX processing
  - Built-in file handling for TXT files

---

## API Configuration

The application uses Google's Generative AI API. To configure:

1. Obtain an API key from Google AI Studio
2. Add the API key to your `.env` file:
```env
GOOGLE_API_KEY=your-api-key-here
```

---

## Notes

- The application creates `uploads/` and `results/` directories automatically
- Uploaded files are deleted after processing
- Generated files are stored in the `results/` directory
- API key quota limitations may require restarting the application if exceeded
- Keep your `.env` file secure and never share it publicly

---

## Contributing

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Submit a pull request

---

## License

---

## Acknowledgments

- Google Generative AI for the Gemini 1.5 Pro model
- Flask framework
- Tailwind CSS for styling

Happy learning with QuizUp! 🎓
