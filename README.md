
# EODAG Sentinel-2 Downloader

This project allows downloading Sentinel-2 products using EODAG and the Copernicus Dataspace.

## 🚀 Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/AlexEco1/Sentinel-2-download-with-eodag.git
cd Sentinel-2-download-with-eodag
```

### 2️⃣ Create and Activate the Conda Environment

```bash
mamba create -n eodag_env python=3.9 -y
mamba activate eodag_env
```

If you are using Conda instead of Mamba:

```bash
conda create -n eodag_env python=3.9 -y
conda activate eodag_env
```

### 3️⃣ Install the Python Dependencies

```bash
pip install -r requirements.txt
```

## 🔑 Authentication

Create a `.env` file in the project root with your Copernicus Dataspace credentials:

```ini
COP_USERNAME=<your Copernicus username>
COP_PASSWORD=<your Copernicus password>
```

⚠️ **Note:** The `.env` file is ignored by Git and should never be pushed.

## 🛰️ Usage

Run the main script:

```bash
python main.py
```

## 📁 Project Structure

```
eodag_download/
├── .gitignore
├── .env                # Your Copernicus credentials (not included in repo)
├── main.py             # Main download script
├── downutils.py        # Download utility functions
├── discoverutils.py    # Search filtering functions
├── utils.py            # Additional utility functions
├── satellite_list.yml  # Satellite type definitions
├── eodag_ref.yml       # EODAG provider configuration
├── requirements.txt    # Python dependencies
└── sentinel-2/         # Downloaded products will be saved here
```

## 📌 Notes

- Satellite types are defined in `satellite_list.yml`.
- The script requires your **Area of Interest (AOI)** in **GeoJSON format** (`{"type": "Polygon", "coordinates": [...]}`), as copied directly from the Copernicus Browser.  
  The script handles the transformation to WKT internally.
- Credentials are injected automatically from the `.env` file into the provider configuration.
