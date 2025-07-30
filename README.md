# Deezer Playlist Exporter

## Overview
The **Deezer Playlist Exporter** is a Python script that creates a user-friendly GUI application to extract track information from a Deezer playlist and save it as a formatted Excel file. Users input a Deezer ARL token (for authentication), a playlist ID, and a file path for the output Excel file. The script fetches track details (e.g., track name, artist, album, duration, and link) from the Deezer API, organizes them into a table, and saves them in an Excel file with auto-adjusted column widths, capped at 50 units, and a frozen top row for easy viewing. The application runs as a standalone executable on Windows, requiring no Python installation for end users, and operates without displaying a command window.

## Prerequisites
- A Windows computer (Windows 7 or later) to perform the compilation.
- Internet connection to download tools and dependencies.
- The provided Python script saved as `deezer_playlist_exporter.py` in a specific folder.
- No prior programming experience is required; follow each step carefully.

## Step-by-Step Instructions to Compile the Script

### 1. Create a Working Folder
- Create a new folder to store the script and related files.
  - Example: Create a folder named `DeezerExporter` on your Desktop.
  - To do this:
    - Right-click on your Desktop, select **New > Folder**, and name it `DeezerExporter`.
    - Path example: `C:\Users\YourUsername\Desktop\DeezerExporter`.

### 2. Save the Python Script
- Copy the provided Python script (starting with `import requests`).
- Open Notepad or any text editor:
  - Press `Win + R`, type `notepad`, and press Enter.
- Paste the script into Notepad.
- Save the file in your `DeezerExporter` folder:
  - Click **File > Save As**.
  - Navigate to `C:\Users\YourUsername\Desktop\DeezerExporter`.
  - Set **File name** to `deezer_playlist_exporter.py`.
  - Set **Save as type** to **All Files (*.*)**.
  - Click **Save**.

### 3. Install Python
You need Python to compile the script, even though the final executable won't require it.

- **Download Python**:
  - Open your web browser (e.g., Chrome, Edge).
  - Go to [python.org/downloads](https://www.python.org/downloads/).
  - Click the **Download Python 3.10.x** button (or the latest version, e.g., 3.11 or 3.12).
- **Install Python**:
  - Run the downloaded installer (e.g., `python-3.10.x.exe`).
  - **Important**: Check the box **Add Python 3.x to PATH** at the bottom of the installer window.
  - Select **Install Now** and follow the prompts.
  - Once installed, close the installer.
- **Verify Python Installation**:
  - Press `Win + S`, type `cmd`, and open **Command Prompt**.
  - Type the following and press Enter:
    ```
    python --version
    ```
  - You should see something like `Python 3.10.x`. If you see an error, repeat the installation and ensure **Add Python to PATH** is checked.

### 4. Install PyInstaller
PyInstaller converts the Python script into a standalone executable.

- **Open Command Prompt**:
  - Press `Win + S`, type `cmd`, and open **Command Prompt**.
- **Install PyInstaller**:
  - Type the following command and press Enter:
    ```
    pip install pyinstaller
    ```
  - Wait for the installation to complete (it may take a minute or two).
  - Verify the installation by typing:
    ```
    pyinstaller --version
    ```
  - You should see a version number (e.g., `5.13.0`). If you get an error, repeat the `pip install pyinstaller` command.

### 5. Install Required Python Libraries
The script uses libraries (`requests`, `pandas`, `openpyxl`) that must be installed before compiling.

- **Navigate to Your Working Folder**:
  - In the Command Prompt, change to your `DeezerExporter` folder by typing:
    ```
    cd C:\Users\YourUsername\Desktop\DeezerExporter
    ```
    - Replace `YourUsername` with your actual Windows username.
    - Press Enter. You should see the prompt change to include `DeezerExporter`.
- **Install Libraries**:
  - Run the following command to install all required libraries:
    ```
    pip install requests pandas openpyxl
    ```
  - Wait for the installation to complete. This may take a few minutes, as `pandas` and `openpyxl` are large libraries.
  - If you see any errors, ensure you have an internet connection and try again.

### 6. Compile the Script with PyInstaller
Compile the script into a single `.exe` file.

- **Ensure You're in the Correct Folder**:
  - In the Command Prompt, confirm you're in the `DeezerExporter` folder:
    ```
    cd C:\Users\YourUsername\Desktop\DeezerExporter
    ```
  - Verify the script is there by typing:
    ```
    dir
    ```
  - You should see `deezer_playlist_exporter.py` listed.
- **Run PyInstaller**:
  - Type the following command and press Enter:
    ```
    pyinstaller --onefile --noconsole --name DeezerPlaylistExporter deezer_playlist_exporter.py
    ```
  - Explanation of the command:
    - `--onefile`: Creates a single `.exe` file with everything bundled.
    - `--noconsole`: Ensures no command window appears when the executable runs (ideal for GUI apps).
    - `--name DeezerPlaylistExporter`: Names the output file `DeezerPlaylistExporter.exe`.
    - `deezer_playlist_exporter.py`: The script to compile.
  - PyInstaller will create several folders (`build`, `dist`) and files. Wait for it to finish (this may take 2-5 minutes).

### 7. Locate the Executable
- Once PyInstaller finishes, find the executable:
  - Open File Explorer and navigate to `C:\Users\YourUsername\Desktop\DeezerExporter\dist`.
  - Inside the `dist` folder, you’ll find `DeezerPlaylistExporter.exe`.
- This is the standalone application you can share with others.

### 8. Test the Executable
- Double-click `DeezerPlaylistExporter.exe` in the `dist` folder to run it.
- A GUI window will appear, prompting for:
  - **ARL Token**: Your Deezer authentication token.
  - **Playlist ID**: The ID of the Deezer playlist to export.
  - **Save as (Excel file)**: The location to save the output Excel file.
- Test the application:
  - Enter a valid Deezer ARL token and playlist ID (obtained from your Deezer account).
  - Click **Browse** to select a save location for the Excel file (e.g., `playlist.xlsx`).
  - Click **Export Playlist** to generate the Excel file with track details.
- The Excel file will include columns for track number, name, artist, album, duration, and link, with formatted columns and a frozen top row.
- If the GUI doesn’t appear or errors occur, see the **Troubleshooting** section.

### 9. Distribute the Executable
- Copy `DeezerPlaylistExporter.exe` from the `dist` folder to share with others.
- Users can run it on any Windows computer (Windows 7 or later) without installing Python or any libraries.
- The executable is portable and can be placed anywhere (e.g., Desktop, USB drive).

## Troubleshooting

- **Command Prompt says `python` or `pip` is not recognized**:
  - Reinstall Python and ensure **Add Python to PATH**
