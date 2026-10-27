# AI Job Application Automator

An AI automation project that removes the repetitive part of job hunting. For every job
posting it reads your resume and uses **Claude (Anthropic API)** to produce:

- a 0-100 resume/job **match score**
- matched and missing skills
- a tailored **cover letter**
- a ready-to-send **application email** (subject + body)

All results are saved to `output/` and ranked in `output/summary.csv`, so you can apply to
the best-fit jobs first.

## AI tool used

**Claude (Anthropic API, model `claude-sonnet-5-5`)** for analysis and text generation.
Claude Code was also used to build the project.

## How it works

```
resume.txt + jobs.json  ->  Claude prompt (JSON output)  ->  output/<company>.md + summary.csv
```

## Setup

```bash
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
export ANTHROPIC_API_KEY=your-key-here
```

## Run

```bash
python main.py              # real run with Claude
python main.py --dry-run    # offline keyword matching, no API key needed
```

Edit `data/resume.txt` and `data/jobs.json` with your own details.

## Structure

```
main.py          # the automation pipeline
data/resume.txt  # your resume (sample)
data/jobs.json   # job postings (sample)
output/          # generated applications (git-ignored)
```
