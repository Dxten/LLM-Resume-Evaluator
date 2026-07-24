# AI Resume-JD Matcher

An AI-powered tool that evaluates how well a resume matches a given job description — parsing both into structured data and using an LLM to generate a match verdict, score, and reasoning.

## Features

- **Accepts any job description as text input** — paste in the JD you're targeting
- **Parses PDF and Word resumes automatically** — extracts and cleans text from `.pdf` and `.docx` files
- **Structured extraction with Pydantic** — both the JD and resume are parsed into well-defined schemas (skills, experience, requirements, etc.)
- **LLM-powered matching** — sends structured JD and resume data to an LLM (via Groq) for intelligent comparison
- **Match verdict + score + reasoning** — returns a clear final output: whether it's a match, a numeric score, and the reasoning behind it

## Tech Stack

- **Python** — core language
- **Pydantic** — schema definition and structured data validation
- **Groq** — LLM inference for matching and reasoning
- **pypdf / python-docx** — resume parsing (PDF and Word)

## How It Works

1. Provide a job description (as plain text).
2. Upload a resume (PDF or DOCX) — it's parsed and converted into clean text.
3. Both the JD and resume are passed through Pydantic schemas to extract structured fields (skills, experience, education, requirements, etc.).
4. The structured data is sent to an LLM, which compares the two.
5. The tool returns:
   - **Match Verdict** (e.g., Strong Match / Partial Match / No Match)
   - **Final Score** (numeric)
   - **Reasoning** (explanation for the verdict)

## Setup

```bash
# Clone the repo
git clone https://github.com/Dxten/LLM-Resume-Evaluator.git
cd LLM-Resume-Evaluator

# Install dependencies with uv
uv sync

# Add your Groq API key to a .env file
echo "GROQ_API_KEY=your_key_here" > .env

# Run the project
uv run main.py
```

## Usage

```bash
uv run main.py --resume path/to/resume.pdf --jd "paste job description here"
```

*(Adjust this section to match your actual CLI/script interface.)*

## Example Output

```
Match Verdict: Strong Match
Final Score: 87/100
Reasoning: The candidate's experience in Python and API development
aligns closely with the JD's core requirements. Minor gap in cloud
infrastructure experience noted.
```

## Project Structure

```
project1/
├── main.py            # Entry point
├── project.py          # Core matching logic
├── pyproject.toml       # Project dependencies
├── uv.lock             # Locked dependency versions
└── README.md
```

