# Deep Site Editor 🚀

A powerful web-based tool for streaming and processing HTML content using AI capabilities. This application allows you to analyze and modify web content efficiently using advanced language models through the OpenRouter API.

🌐 **Live Demo**: [https://rolsite.github.io/deepsiteeditor](https://rolsite.github.io/deepsiteeditor)

## ⭐ Credits

This project is based on [Deepsite by enzostvs](https://huggingface.co/spaces/enzostvs/deepsite), available on Hugging Face Spaces. We appreciate their original work and contribution to the open-source community.

## ⚠️ Security Disclaimer

**IMPORTANT**: During testing, antivirus software has flagged potential security concerns with the original Deepsite implementation. These alerts suggest that some scripts might reference files hosted on potentially compromised servers. While we've taken steps to enhance security in this implementation, users should:

- Run the application in a controlled environment
- Keep their antivirus software active
- Monitor for any suspicious activity
- Use at their own discretion and risk

## 🌟 Features

- Real-time HTML content streaming and processing
- Integration with OpenRouter API for AI capabilities
- User-friendly interface with configuration options
- System prompt customization
- Efficient content handling and display
- Natural language code editing - request changes to your generated code using simple English prompts
- Interactive code modifications within the model's context window

## 📋 Prerequisites

- Modern web browser (Chrome, Firefox, Safari, or Edge)
- OpenRouter API key
- Local development server (like Live Server VS Code extension or any HTTP server)

## 🔑 Getting an OpenRouter API Key

1. Visit [OpenRouter](https://openrouter.ai/)
2. Sign up for an account or log in if you already have one
3. Navigate to the API Keys section in your dashboard
4. Click on "Create New Key"
5. Copy your API key and keep it secure

## 🚀 Quick Start

1. Clone this repository to your local machine
2. Set up a local development server (see options above)
3. Open the application through the server URL
4. Click on the configuration icon (⚙️) to open the settings modal
5. Enter your OpenRouter API key in the configuration modal
6. Configure any additional settings as needed
7. Start using the application!

## 💻 Usage Instructions

### Basic Operation

1. **Initial Setup**:
   - Configure your API key through the settings modal
   - Customize the system prompt if needed

2. **Processing Content**:
   - Enter or paste your HTML content into the input area
   - The application will process and display the content in real-time

3. **Natural Language Code Editing**:
   - Once your initial code is generated, you can request changes using natural language
   - Simply describe what you want to modify in plain English
   - The AI will understand and implement your requested changes
   - Continue the conversation to refine the code further
   - Note: Changes are limited to the context window of the AI model being used

### Advanced Features

- **Content Streaming**: The application processes content in chunks for optimal performance
- **Error Handling**: Built-in error detection and reporting for API issues
- **Configuration Options**: Customize the behavior through the settings modal

## ⚙️ Configuration Options

The settings modal allows you to configure:
- OpenRouter API Key
- System prompts
- Other processing parameters

## 🔒 Security

- API keys are stored securely in your browser's local storage
- No sensitive data is transmitted to third parties
- All API communications are encrypted

## 🛠️ Troubleshooting

Common issues and solutions:

1. **Authentication Errors**:
   - Verify your API key is correct
   - Ensure the key is properly entered in the configuration
   - Check if your API key has sufficient credits

2. **Content Display Issues**:
   - Clear your browser cache
   - Refresh the page
   - Check for any console errors

## 📝 Notes

- The application processes HTML content in real-time
- Response times may vary based on content length and API response speed
- Keep your API key secure and never share it publicly

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

## 📄 License

This project is open source and available under the MIT License.

---

For additional support or questions, please open an issue in the repository.

## ⚠️ Important Note About Running the Application

The application **cannot** be run by simply opening the `index.html` file directly in a browser. This is due to:
- Browser security restrictions (CORS policy)
- ES6 module loading requirements
- Local file access limitations

Instead, you must use a local development server. Here are some options:

1. **Using VS Code (Recommended)**:
   - Install the "Live Server" extension
   - Right-click on `index.html`
   - Select "Open with Live Server"

2. **Using Python**:
   - Open terminal in project directory
   - Python 3: `python -m http.server 8080`
   - Visit `http://localhost:8080`

3. **Using Node.js**:
   - Install `http-server` globally: `npm install -g http-server`
   - Run: `http-server`
   - Visit the URL shown in terminal

## 🔄 Forking and Deploying Your Own Instance

You can create your own instance of Deep Site Editor by following these steps:

### 1. Fork the Repository

1. Visit the [Deep Site Editor repository](https://github.com/rolsite/deepsiteeditor)
2. Click the "Fork" button in the top-right corner
3. Select your account as the destination for the fork
4. Wait for GitHub to complete the forking process

### 2. Enable GitHub Pages

1. Go to your forked repository's settings
   - Click on "Settings" in the top menu
   - Select "Pages" from the left sidebar

2. Configure the Source
   - Under "Source", click the dropdown menu
   - Select "gh-pages" branch
   - Click "Save"

3. Wait for Deployment
   - GitHub will start deploying your site
   - This usually takes a few minutes
   - You'll see a message saying "Your site is published at..."

### 3. Access Your Instance

1. Your site will be available at:
   `https://YOUR_USERNAME.github.io/deepsiteeditor`

2. Configure Your Instance:
   - Open the site in your browser
   - Click the settings icon (⚙️)
   - Enter your OpenRouter API key
   - Customize other settings as needed

### 4. (Optional) Local Development

If you want to develop locally:

1. Clone your fork:
   ```bash
   git clone https://github.com/YOUR_USERNAME/deepsiteeditor.git
   cd deepsiteeditor
   ```

2. Set up development server (choose one):
   ```bash
   # Using Python
   python -m http.server 8080

   # Using Node.js
   npx http-server

   # Or use VS Code Live Server
   ```

3. Make your changes:
   - Edit files as needed
   - Test locally using your preferred server
   - Commit and push changes to GitHub
   - GitHub Pages will automatically update

### 5. Keeping Your Fork Updated

To sync with the original repository:

1. Add the upstream remote:
   ```bash
   git remote add upstream https://github.com/rolsite/deepsiteeditor.git
   ```

2. Fetch and merge updates:
   ```bash
   git fetch upstream
   git checkout main
   git merge upstream/main
   git push origin main
   ```

**Note**: Remember to never commit your API keys or sensitive information to the repository.

## 🔒 Known Issues and Solutions

### CORS Issues on GitHub Pages

When deploying to GitHub Pages, you might encounter CORS (Cross-Origin Resource Sharing) errors when trying to access the OpenRouter API. This happens because GitHub Pages enforces strict security policies. To fix this, you have several options:

1. **Use a CORS Proxy (Recommended for Testing)**
   - Update the API URL in the code to use a CORS proxy
   - Example using cors-anywhere:
     ```javascript
     const url = 'https://cors-anywhere.herokuapp.com/https://openrouter.ai/api/v1/chat/completions';
     ```
   - Note: For production, set up your own proxy server

2. **Set Up Your Own Backend (Recommended for Production)**
   - Create a simple backend service (Node.js, Python, etc.)
   - Route API requests through your backend
   - Deploy to platforms like:
     - Vercel
     - Netlify
     - Heroku
     - Azure Functions
     - AWS Lambda

3. **Configure OpenRouter Headers**
   - Make sure your request includes the correct headers:
     ```javascript
     headers: {
       'Content-Type': 'application/json',
       'Authorization': `Bearer ${apiKey}`,
       'HTTP-Referer': 'https://YOUR_USERNAME.github.io/deepsiteeditor',
       'X-Title': 'DeepSiteEditor'
     }
     ```

4. **Local Development**
   - When developing locally, use a development server (as described above)
   - Local development servers typically don't have CORS restrictions

### Security Considerations

- When using a CORS proxy, be cautious with sensitive data
- Never expose your API keys in client-side code
- Consider implementing token encryption
- Use environment variables for sensitive data when possible 