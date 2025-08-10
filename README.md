# ALXprodev-Devops

## Overview
This repository contains advanced shell scripting examples that demonstrate various automation techniques, API interactions, and data processing workflows.

## Advanced_shell Directory

The `Advanced_shell` directory contains a collection of Bash scripts that showcase different aspects of shell automation and data processing using the Pokémon API (PokeAPI) as a data source.

### Scripts Description

#### 1. `apiAutomation-0x00`
**Purpose**: Basic API interaction and error handling
- **Functionality**: 
  - Makes a simple HTTP request to the PokeAPI to fetch Pikachu's data
  - Saves the response to `data.json` and error messages to `errors.txt`
  - Includes basic validation to check if the data was successfully retrieved
- **Usage**: `./apiAutomation-0x00`
- **Output**: Creates `data.json` with Pikachu's information

#### 2. `data_extraction_automation-0x01`
**Purpose**: Data extraction and formatting from JSON files
- **Functionality**:
  - Uses `jq` to extract specific fields (name, type, weight, height) from `data.json`
  - Employs `awk` for data transformation and formatting
  - Converts units (hectograms to kg, decimeters to meters)
  - Capitalizes the first letters of name and type
- **Dependencies**: Requires `jq` and a valid `data.json` file
- **Usage**: `./data_extraction_automation-0x01`
- **Output**: Formatted string with Pokémon information

#### 3. `batchProcessing-0x02`
**Purpose**: Sequential batch processing of multiple API requests
- **Functionality**:
  - Processes a predefined list of Pokémon (Bulbasaur, Ivysaur, Venusaur, Charmander, Charmeleon)
  - Makes sequential API requests with proper error handling
  - Creates a `pokemon_data` directory to store individual JSON files
  - Validates downloaded data using `jq`
  - Includes a 1-second delay between requests to be API-friendly
- **Dependencies**: Requires `jq`
- **Usage**: `./batchProcessing-0x02`
- **Output**: Creates `pokemon_data/` directory with individual JSON files for each Pokémon

#### 4. `summaryData-0x03`
**Purpose**: Data aggregation and CSV report generation
- **Functionality**:
  - Processes all JSON files in the `pokemon_data` directory
  - Extracts relevant data (name, height, weight) from each file
  - Generates a CSV report with proper formatting and unit conversion
  - Calculates and displays average height and weight statistics
  - Uses `awk` for CSV processing and statistical calculations
- **Dependencies**: Requires the `pokemon_data` directory created by `batchProcessing-0x02`
- **Usage**: `./summaryData-0x03`
- **Output**: Creates `pokemon_report.csv` and displays statistics

#### 5. `batchProcessing-0x04`
**Purpose**: Parallel batch processing for improved performance
- **Functionality**:
  - Similar to `batchProcessing-0x02` but uses parallel processing
  - Runs multiple API requests simultaneously in background processes
  - Uses the `wait` command to synchronize all background jobs
  - Includes verification step to check successful downloads
  - Creates a separate directory `pokemon_data_parallel` for output
- **Usage**: `./batchProcessing-0x04`
- **Output**: Creates `pokemon_data_parallel/` directory with JSON files fetched in parallel

### Script Dependencies

- **curl**: For making HTTP requests to the API
- **jq**: For JSON parsing and manipulation
- **awk**: For text processing and calculations
- **bash**: All scripts are written for Bash shell

### Workflow Sequence

For the complete data processing workflow, run the scripts in this order:

1. `apiAutomation-0x00` - Get initial data
2. `data_extraction_automation-0x01` - Process the initial data
3. `batchProcessing-0x02` OR `batchProcessing-0x04` - Fetch multiple Pokémon data
4. `summaryData-0x03` - Generate summary report

### Key Features Demonstrated

- **API Integration**: HTTP requests using curl
- **Error Handling**: Proper validation and error reporting
- **JSON Processing**: Using jq for data extraction and validation
- **Parallel Processing**: Background jobs and synchronization
- **Data Transformation**: Unit conversion and formatting
- **File Operations**: Directory creation, file validation
- **CSV Generation**: Structured data output
- **Statistical Analysis**: Calculating averages and summaries

### Learning Outcomes

These scripts demonstrate:
- Best practices for shell scripting automation
- API interaction patterns
- Data validation and error handling
- Parallel vs sequential processing trade-offs
- Data transformation and reporting techniques
- Command-line tool integration (curl, jq, awk)

## Getting Started

1. Ensure all dependencies are installed (`curl`, `jq`)
2. Make all scripts executable: `chmod +x Advanced_shell/*`
3. Run scripts individually or follow the workflow sequence
4. Check generated files and reports in the working directory

---
*This project demonstrates advanced shell scripting techniques for automation, API integration, and data processing.*
