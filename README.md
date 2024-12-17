# Repo-To-Txt

Convert GitHub repositories or local directories into a single formatted text file. This tool is particularly useful for preparing code for AI models, documentation, or analysis.

## Features

- **GitHub Repository Support**: Convert any public or private GitHub repository into a formatted text file
- **Local Directory Support**: Convert local directories or zip files into a formatted text file
- **Smart File Selection**: 
  - Tree view of repository/directory structure
  - Filter by file extensions
  - Selective file inclusion
- **Multiple Output Formats**:
  - Formatted text file with directory structure
  - ZIP file download
- **Token Counter**: Built-in GPT token counter for the generated output
- **.gitignore Support**: Respects .gitignore rules when processing directories
- **Security**: Runs entirely in the browser - no server-side processing

## Live Demo

Visit [https://otey247.github.io/repo-to-txt](https://otey247.github.io/repo-to-txt)

## Deployment

### GitHub Pages Deployment

1. Fork or clone this repository
2. Update paths in HTML files:
   ```html
   # In index.html
   <a href="./local.html">
   
   # In local.html
   <a href="./">
   ```

3. Update script imports to use relative paths:
   ```html
   <script type="module" src="./js/index.js"></script>
   <script src="./js/lucide.min.js"></script>
   <script src="./js/jszip.min.js"></script>
   ```

4. Create a `.nojekyll` file in the root:
   ```bash
   touch .nojekyll
   ```

5. Update canonical URLs in both HTML files:
   ```html
   <!-- For index.html -->
   <link rel="canonical" href="https://[username].github.io/[repo-name]/">
   <meta property="og:url" content="https://[username].github.io/[repo-name]/">

   <!-- For local.html -->
   <link rel="canonical" href="https://[username].github.io/[repo-name]/local.html">
   <meta property="og:url" content="https://[username].github.io/[repo-name]/local.html">
   ```

6. Deploy to GitHub Pages:
   - Go to repository Settings → Pages
   - Set source to "Deploy from a branch"
   - Select "main" branch and "/ (root)" folder
   - Click Save

7. (Optional) Custom Domain Setup:
   - Add your domain name to the CNAME file
   - Add these DNS records at your domain registrar:
     ```
     Type  Name   Value
     A     @      185.199.108.153
     A     @      185.199.109.153
     A     @      185.199.110.153
     A     @      185.199.111.153
     CNAME www    your-username.github.io
     ```
   - Configure custom domain in GitHub Pages settings

Your site will be available at `https://[username].github.io/[repo-name]/` or your custom domain.

## Local Development

### Prerequisites

- A modern web browser
- Git (optional)
- Docker (optional)

### Running Locally

#### Method 1: Direct Browser

1. Clone the repository:
```bash
git clone https://github.com/otey247/repo-to-txt.git
cd repo-to-txt
```

2. Open `index.html` in your web browser

#### Method 2: Using Docker

1. Clone the repository:
```bash
git clone https://github.com/otey247/repo2txt.git
cd repo-to-txt
```

2. Build and run with Docker:
```bash
docker build -t repo-to-txt .
docker run -d -p 8080:80 repo-to-txt
```

3. Visit `http://localhost:8080` in your browser

#### Method 3: Using Docker Compose

1. Clone the repository
2. Run:
```bash
docker-compose up -d
```
3. Visit `http://localhost:8080` in your browser

##  Technology Stack

- Vanilla JavaScript (ES6+)
- TailwindCSS for styling
- Lucide Icons
- JSZip for ZIP file handling
- GPT Tokenizer for token counting

## Usage

### Converting a GitHub Repository

1. Visit the homepage
2. Enter a GitHub repository URL
   - Format: `https://github.com/owner/repo` or `https://github.com/owner/repo/tree/branch/path`
3. (Optional) Enter a GitHub Personal Access Token for private repositories
4. Click "Fetch Directory Structure"
5. Select desired files
6. Click "Generate Text File" or "Download ZIP"

### Converting a Local Directory

1. Click "Convert From Local Directory Instead" on the homepage
2. Either:
   - Select a directory using the directory picker
   - Upload a ZIP file
3. Select desired files
4. Click "Generate Text File"

## Security

- No server-side processing - everything runs in your browser
- Personal Access Tokens are stored locally in your browser
- No data is transmitted except to GitHub's API

## License

[MIT License](LICENSE)

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/YourFeature`
3. Commit changes: `git commit -am 'Add YourFeature'`
4. Push to the branch: `git push origin feature/YourFeature`
5. Submit a Pull Request

## Bug Reports

Please report bugs by opening an issue on GitHub or emailing abinthomasonline@gmail.com.

## Support

If you find this tool useful, please consider:
- Starring the repository
- Sharing it with others
- Contributing to the codebase

## Contact

For support or inquiries, please email [Jump Starts](mailto:jo.otey@sogeti.com).

---

Deployed by [Sogeti Jump Starts](https://github.com/CGSOG-JumpStarts)
