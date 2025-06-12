# WIWB Postman Collections

This directory contains Postman collections for testing WIWB APIs. These collections are automatically generated from the JSON test case files and provide an easy way to test API endpoints interactively using Postman.

## 📁 Collection Files

The Postman collections are generated from the corresponding test JSON files:

- **`wiwb1_baseline_collection.json`** - Generated from `../regression/general.json` for WIWB1 API
- **`wiwb1_fews_collection.json`** - Generated from `../regression/fews.json` for WIWB1 API  
- **`wiwb2_baseline_collection.json`** - Generated from `../regression/general.json` for WIWB2 API
- **`wiwb2_fews_collection.json`** - Generated from `../regression/fews.json` for WIWB2 API

## 🔄 Generation Process

These collections are automatically generated using the `generate_postman_collection.py` script from the test suite repository (https://github.com/jonathan-gerb/wiwb-testsuite). The script:

1. Reads test cases from JSON files in the `../regression/` directory
2. Converts each test case into a Postman request with proper formatting
3. Adds authentication handling (pre-request scripts or OAuth 2.0)
4. Generates test scripts for response validation
5. Handles special response types (CSV, GeoTIFF, ZIP, NetCDF4) appropriately

### Special Response Handling

For test cases that expect special response formats like `<csv>`, `<geotiff>`, `<zipfile>`, or `<netcdf4_file>`, the collections only include basic status code validation since Postman cannot effectively validate binary or specialized file formats.

## 🚀 Getting Started

### 1. Import into Postman

1. Open Postman
2. Click **Import** in the top left
3. Select **Upload Files** and choose one of the collection JSON files
4. The collection will be imported with all requests and test scripts

### 2. Configure Authentication

#### Built-in OAuth 2.0
The authorization for each collections can be configured to use Postman's built-in OAuth 2.0 feature.

**Setup Steps:**
1. Right-click the collection, the text where it might say for example `WIWB2 FEWS API TESTS`
2. Go to the **Variables** tab
4. Set `client_id` and `client_secret` in collection variables
2. Go to the **Authentication** tab
5. Click **Get New Access Token** to authenticate
6. Click **proceed** in the popup window
6. Click **Use This Token** in the popup window.

All requests in the collection can now be excecuted
