  

---

# **📘 PDF to Audiobook Converter**  

## **📖 Overview**  
The **PDF to Audiobook Converter** is a Python-based desktop application that allows users to convert PDF files into audiobooks. This versatile tool supports both text-based and image-based PDFs. It first tries to extract text directly from the PDF using **pdfplumber**. If the PDF contains scanned images or embedded text, it switches to **OCR (Optical Character Recognition)** using **easyocr**.  

Once the text is extracted, the application converts it into clear, human-like speech using **pyttsx3**, and saves the output as an **MP3 audiobook file**. The user can also play the audiobook directly from the app using an intuitive, user-friendly graphical user interface (GUI) built with **Tkinter**.  

This project aims to make audiobooks accessible to everyone and helps users convert their favorite PDF e-books, articles, and documents into portable audio files.  

---

## **✨ Key Features**  
- **Dual Text Extraction**: Extracts text directly from PDFs or via OCR for image-based PDFs.  
- **Text-to-Speech Conversion**: Converts extracted text into clear, human-like speech.  
- **Audiobook File Generation**: Saves the audiobook in MP3 format in a dedicated folder.  
- **In-App Audiobook Player**: Play the audiobook directly from the application.  
- **Interactive GUI**: User-friendly interface for PDF uploads, audiobook generation, and playback.  
- **Multi-threaded Processing**: Ensures a smooth, non-blocking user experience.  
- **Error Handling**: Alerts users when issues occur (like missing files or processing failures).  

---

## **🛠️ Technologies Used**  
- **Python**: The primary programming language for the project.  
- **pdfplumber**: Extracts text from text-based PDFs.  
- **pdf2image**: Converts PDF pages to images for OCR processing.  
- **easyocr**: Extracts text from images via Optical Character Recognition (OCR).  
- **pyttsx3**: Converts extracted text into an audiobook (MP3) file.  
- **playsound**: Plays the generated audiobook directly within the app.  
- **Tkinter**: Used to create the graphical user interface (GUI).  

---

## **📁 Folder Structure**  
```
📦 PDF-to-Audiobook-Converter  
├── 📂 audiobooks/         # Stores generated MP3 audiobooks  
├── 📄 main.py             # Main application code  
├── 📄 requirements.txt    # Required libraries for the project  
└── 📄 README.md           # Project documentation (this file)  
```

---

## **⚙️ Installation and Setup**  
Follow the steps below to set up the **PDF to Audiobook Converter** on your system.  

### **1️⃣ Clone the Repository**  
```bash
git clone https://github.com/your-username/PDF-to-Audiobook-Converter.git
cd PDF-to-Audiobook-Converter
```

### **2️⃣ Create a Virtual Environment (Optional but Recommended)**  
```bash
python -m venv venv
source venv/bin/activate  # For Linux/MacOS
venv\Scripts\activate     # For Windows
```

### **3️⃣ Install Required Libraries**  
Install all the dependencies listed in `requirements.txt` using:  
```bash
pip install -r requirements.txt
```

### **4️⃣ Run the Application**  
Run the following command to launch the application:  
```bash
python main.py
```

If all goes well, the application window will open, and you’ll be able to upload and convert PDFs into audiobooks.  

---

## **📚 How to Use the Application**  
1. **Launch the Application**: Run `main.py` to open the PDF to Audiobook Converter.  
2. **Upload a PDF File**: Click on the **Upload PDF** button to select a PDF from your system.  
3. **Wait for Text Extraction**: The application will extract text from the PDF (via **pdfplumber** or **OCR** if needed).  
4. **Generate Audiobook**: The extracted text is converted into an audiobook and saved in the **audiobooks** folder as an MP3 file.  
5. **Play Audiobook**: Click the **Play Audiobook** button to listen to the generated audiobook.  

---

## **📋 Algorithm**  

Here is a detailed step-by-step explanation of how the system works.  

### **1️⃣ Upload PDF**  
- The user selects a PDF file using the file dialog.  
- The file path is captured, and a background thread is started to process the file.  

### **2️⃣ Text Extraction**  
- **Step 1**: Attempt to extract text directly using **pdfplumber**.  
- **Step 2**: If no text is extracted, convert the PDF to images using **pdf2image**.  
- **Step 3**: Use **easyocr** to extract text from each image, page-by-page.  

### **3️⃣ Text-to-Speech Conversion**  
- **Step 4**: Process the extracted text to improve punctuation spacing for better speech clarity.  
- **Step 5**: Convert the processed text into speech using **pyttsx3**.  
- **Step 6**: Save the audiobook as an **MP3 file** in the **audiobooks** folder.  

### **4️⃣ Audiobook Player**  
- **Step 7**: User can play the generated audiobook directly from the app using **playsound**.  

---

## **💻 Code Explanation**  

Here is a quick explanation of the main files and functions in the repository.  

### **main.py**  
This file contains all the core logic, including text extraction, OCR, text-to-speech conversion, and GUI creation.  

### **Key Functions**  
| **Function**               | **Description**                                             |
|-------------------------- |---------------------------------------------------------- |
| `extract_text_from_pdf()`   | Extracts plain text from a PDF using **pdfplumber**.        |
| `extract_text_with_ocr()`   | Extracts text from images using **easyocr**.                |
| `pdf_to_image()`            | Converts PDF pages into images for OCR processing.         |
| `text_to_speech_with_expressions()` | Converts text into an audiobook (MP3) using **pyttsx3**. |
| `convert_to_audiobook()`    | Handles the entire text-to-speech process and updates progress. |
| `play_audiobook()`          | Plays the generated audiobook.                             |
| `upload_pdf()`              | Handles the file upload process, text extraction, and audiobook generation. |
| `get_unique_filename()`     | Generates a unique filename if an existing one already exists. |

---

## **📋 Requirements**  
To run the application, you’ll need the following libraries:  

```
tkinter
pdfplumber
pdf2image
pyttsx3
playsound
easyocr
pillow
numpy
```

To install all the dependencies, use:  
```bash
pip install -r requirements.txt
```

---

## **📋 Troubleshooting**  
**Issue**: Error while converting PDF to images.  
**Solution**: Ensure **poppler** is installed on your system. Follow this [Poppler Installation Guide](https://blog.alivate.com.au/poppler-windows/).  

**Issue**: Text not extracted from PDF.  
**Solution**: If OCR extraction fails, check if the PDF contains clear, readable images.  

---

## **🔮 Possible Enhancements**  
- **Add Pause/Resume Controls**: Enable pause and resume functionality for audiobook playback.  
- **Multi-Language Support**: Add support for more languages in OCR and TTS.  
- **Customizable Voice Options**: Allow users to change the voice, pitch, and speed of speech synthesis.  
- **Batch PDF Upload**: Allow users to upload multiple PDFs for batch processing.  

---

## **🤝 Contributing**  
Contributions are welcome! To contribute:  
1. Fork the repository.  
2. Create a new feature branch (`git checkout -b feature-name`).  
3. Make changes, then commit (`git commit -m "Added new feature"`).  
4. Push to your branch (`git push origin feature-name`).  
5. Open a pull request and describe your changes.  

---

## **📝 License**  
This project is licensed under the **MIT License**. See the `LICENSE` file for more details.  

---

## **👤 Author**  
- **GitHub**: [SamirYMeshram](https://github.com/SamirYMeshram)  
- **Email**: samirYmeshram@gmail.com 

---
