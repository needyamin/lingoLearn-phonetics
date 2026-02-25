# Building Linux AppImage on Windows

## ✅ Successful Build Method: Docker (Recommended)

The AppImage has been successfully built using Docker! This is the recommended method.

### Quick Start

**Automated Script:**
```bash
build-linux-docker.bat
```
This script will:
1. Check if Docker is running
2. Build the Docker image
3. Build the Linux AppImage
4. Save it to the `dist/` folder

**Manual Commands:**
```bash
# 1. Build the Docker image (only needed once, or after Dockerfile changes)
docker build -f Dockerfile.linux-build -t tts-pronunciation-linux-builder .

# 2. Run the container to build the AppImage (use your project path)
docker run --rm -v "y:/Projects/tts-pronunciation-practice/dist:/app/dist" tts-pronunciation-linux-builder
```

Or from project root:
```bash
npm run dist:linux:docker
```

### Output
The AppImage will be created at:
```
dist/TTS Pronunciation Practice-1.0.0.AppImage
```
Size: ~101 MB

### Prerequisites
- Docker Desktop must be installed and running
- At least 2GB of free disk space

---

## Alternative Methods (Not Recommended on Windows)

### Option 2: Enable Windows Developer Mode
1. **Start Docker Desktop** (you have it installed)
2. Run the build with Docker support:
   ```bash
   npm run dist:linux -- --linux --x64 -c.linux.target=AppImage
   ```
   Or set the environment variable to use Docker:
   ```bash
   set USE_HARD_LINKS=false
   npm run dist:linux
   ```

### Option 2: Enable Windows Developer Mode
1. Open **Settings** → **Update & Security** → **For Developers**
2. Turn on **Developer Mode**
3. Restart your terminal
4. Run: `npm run dist:linux`

### Option 3: Run PowerShell as Administrator
1. Right-click PowerShell and select "Run as Administrator"
2. Navigate to the project directory
3. Run: `npm run dist:linux`

### Option 4: Use GitHub Actions (Cloud Build)
Create a GitHub Actions workflow to build the AppImage in the cloud on Linux runners.

## Current Configuration
- Linux target: AppImage
- Icon: asset/icon.png
- Category: Education
- Output: dist/

## Test with Docker
If Docker Desktop is running, use:
```bash
npm run dist:linux
```

Electron-builder will automatically use Docker if it detects it's running on Windows building for Linux.
