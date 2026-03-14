# Resume Builder

A Python script that analyzes your existing DOCX resume and optimizes it to better match a specific job description by adding relevant content and tweaking existing sections.

## Features

- **Automatic Analysis**: Extracts key skills, experience requirements, and responsibilities from job descriptions
- **Smart Modifications**: Adds missing skills, enhances experience descriptions, and includes job-specific achievements
- **30-40% Modification**: Targets optimal resume enhancement without complete overhaul
- **DOCX Support**: Works directly with Microsoft Word documents

## Installation

1. Install Python dependencies:
```bash
pip install -r requirements.txt
```

2. Download NLTK data (first run only):
```bash
python -c "import nltk; nltk.download('punkt'); nltk.download('stopwords')"
```

## Usage

### Job Description Input Folder Structure

Place the job description file in the `resume-builder/input` folder with the name format:

```
<CompanyName>_jd.txt
```

For example:

```
resume-builder/input/AcmeCorp_jd.txt
```

### Run the Tool

```bash
python resume-builder.py AcmeCorp
```

This will:
- Read your resume from `assets/resume/MohitMahendraSingh_latest.docx`
- Read the job description from `resume-builder/input/AcmeCorp_jd.txt`
- Output the optimized resume into:
  `resume-builder/output/MohitMahendraSingh_AcmeCorp_Resume.docx`

### Optional Arguments

- `--job-file <path>`: Override the default job description file path.
- `-o, --output <path>`: Override the default output file path.
- `--dry-run`: Analyze and show results without saving a modified file.

## How It Works

1. **Analysis Phase**:
   - Extracts skills, experience requirements, and keywords from the job description
   - Analyzes your current resume for existing content

2. **Enhancement Phase**:
   - Identifies missing skills and technologies
   - Adds relevant achievements based on job responsibilities
   - Enhances experience descriptions where appropriate

3. **Modification Phase**:
   - Updates skills section with missing technologies
   - Adds a "Key Achievements" section with job-specific accomplishments
   - Maintains 30-40% modification rate for optimal results

## Example

```bash
python resume-builder.py my_resume.docx "We are looking for a DevOps Engineer with experience in AWS, Docker, Kubernetes, and CI/CD pipelines. The candidate should have 5+ years of experience in cloud infrastructure and automation."
```

This will create `my_resume_optimized.docx` with enhanced content matching the DevOps Engineer requirements.

## Output

The script will:
- Display analysis results showing job requirements found
- Show similarity score between current resume and job description
- Save the optimized resume as a new DOCX file
- Preserve all original formatting and structure

## Notes

- Always review the modified resume before using it
- The script aims for 30-40% content modification to maintain authenticity
- Original resume file is never modified - a new file is always created
- Works best with standard resume formats and clear job descriptions