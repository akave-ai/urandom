# urandom

Example scripts and integration code for [Akave documentation](https://docs.akave.xyz).

This repository contains reference implementations demonstrating how to integrate various tools and frameworks with Akave's S3-compatible storage.

## Overview

The `urandom` repository provides production-ready example scripts that showcase Akave's capabilities across different use cases. Each directory contains standalone examples with detailed documentation.

## Directory Structure

### 📁 `huggingface/`

Integration examples for using Hugging Face datasets with Akave's S3-compatible storage.

📖 **[Full Documentation](https://docs.akave.xyz/akave-o3/solutions-and-integrations/huggingface/)**

**Files:**
- `huggingface_s3.py` - Core `HuggingFaceS3` class providing methods to:
  - Transfer Hugging Face datasets to Akave storage
  - Save and load datasets from S3-compatible endpoints
  - List buckets and manage dataset paths
  
- `huggingface_test.py` - Comprehensive test suite with 7 examples:
  1. Creating and saving custom datasets
  2. Dataset transformations with tokenization
  3. Transferring existing datasets (MNIST)
  4. Dataset streaming
  5. Dataset versioning
  6. Different dataset formats (Arrow, Parquet)
  7. Loading and saving pre-existing datasets

**Configuration:**

**An example `.env.example` file is included in the `huggingface/` directory:**
```env
AKAVE_ACCESS_KEY=your_access_key
AKAVE_SECRET_KEY=your_secret_key
AKAVE_ENDPOINT_URL=your_endpoint_url
AKAVE_BUCKET_NAME=your_bucket_name
```

To use the example, copy the `.env.example` file to a new `.env` file in the `huggingface/` directory and fill in your actual credentials.

### 📁 `s3fs/`

Direct S3FS integration examples for file operations with Akave O3 storage.

📖 **[Full Documentation](https://docs.akave.xyz/akave-o3/solutions-and-integrations/s3fs/)**

**Files:**
- `s3fs_test.py` - Complete test script demonstrating:
  - Bucket listing and content exploration
  - File upload/download operations
  - Directory creation and management
  - File copying and deletion
  - Pandas DataFrame integration (CSV/JSON)
  - Reading file contents directly from storage

**Configuration:**
Uses AWS CLI profile `akave-o3` with endpoint `https://o3-rc2.akave.xyz`

**Usage:**
```bash
# Run all tests
python s3fs_test.py your-bucket-name --operation all

# List buckets and contents
python s3fs_test.py your-bucket-name --operation list

# Upload a file
python s3fs_test.py your-bucket-name --operation upload --file path/to/file

# Download a file
python s3fs_test.py your-bucket-name --operation download --file remote/path
```

## Requirements

### Hugging Face Examples
```bash
pip install s3fs datasets transformers pandas numpy python-dotenv
```

### S3FS Examples
```bash
pip install s3fs pandas
```

## Getting Started

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd urandom
   ```

2. **Set up credentials**
   - For Hugging Face examples: Create a `.env` file in the `huggingface/` directory
   - For S3FS examples: Configure AWS CLI profile `akave-o3`

3. **Install dependencies**
   ```bash
   # Install packages individually as listed above
   ```

4. **Run examples**
   ```bash
   # Hugging Face
   cd huggingface
   python huggingface_test.py
   
   # S3FS
   cd s3fs
   python s3fs_test.py your-bucket-name
   ```

## Documentation

For complete documentation on Akave's S3-compatible storage and additional integration examples, visit [docs.akave.xyz](https://docs.akave.xyz).