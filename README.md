# 🚀 Universal AI Interface (100MB Upload Support)

A lightweight, single-file web application that connects to **OpenRouter** to provide a Gemini-like chat experience. This version is specifically optimized to handle large document uploads (up to 100MB) and multimodal inputs (images + text).

## ✨ Features

-   **📁 Massive File Support**: Upload documents, code, or logs up to 100MB.
-   **👁️ Multimodal Vision**: Support for image analysis (when using vision-capable models).
-   **💾 Smart History**: Automatically excludes large file data from LocalStorage to prevent browser crashes while keeping chat text intact.
-   **🌗 Dark Mode**: Full support for light and dark themes.
-   **📱 Fully Responsive**: Works seamlessly on mobile, tablet, and desktop.
-   **🛠️ Customization**: Change models, API keys, and system prompts on the fly.

## 🚀 Getting Started

### 1. Prerequisites
You will need an **OpenRouter API Key**. You can get one at [openrouter.ai](https://openrouter.ai/).

### 2. Installation
1.  Save the `index.html` file to your computer.
2.  Open `index.html` in any modern web browser (Chrome, Firefox, Edge, or Safari).

### 3. Setup
1.  Click the **Settings** (gear icon) in the sidebar.
2.  Paste your **OpenRouter API Key**.
3.  Choose a model (default is `deepseek/deepseek-r1:free`).
    * *Recommended for Images:* `google/gemini-2.0-flash-exp:free`
4.  Click **Save**.

---

## 📂 Handling Large Files (100MB)

This application uses a unique "Context Injection" method to allow large files:

* **Text/Code Files**: The app reads the file content and appends it to your prompt as a structured block (e.g., `--- FILE: data.csv ---`).
* **Images**: Images are converted to Base64 and sent via the multimodal API.
* **LocalStorage Protection**: Since browsers limit local storage to ~5MB, any file larger than 2MB is used for the current conversation but is **not** saved to the permanent chat history. This ensures your app never slows down or breaks due to storage limits.

## 🛠️ Technical Stack

-   **Tailwind CSS**: Styling and layout.
-   **Marked.js**: High-speed Markdown rendering.
-   **Highlight.js**: Syntax highlighting for code blocks.
-   **DOMPurify**: Security against XSS when rendering AI responses.
-   **OpenRouter API**: The backbone for AI communication.

## 📝 Important Notes

-   **Privacy**: Your API Key is stored locally in your browser's `localStorage`. It is never sent to any server other than OpenRouter.
-   **Model Compatibility**: Ensure the model you select supports the file type you are sending. For example, use a "Vision" model if you are uploading images.
-   **Error Handling**: If a file is too large for the specific AI model's context window (token limit), the API may return an error.

---

*Created with ❤️ for high-performance AI interaction.*
