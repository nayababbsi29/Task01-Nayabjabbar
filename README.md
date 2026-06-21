# Project 1: Zero-Shot & Few-Shot Data Extraction

## Goal
Extract structured data from messy, unstructured text and convert it into clean, valid JSON using prompt engineering.

## What I Did
- Used `"""` delimiters to separate instructions from raw data
- Set temperature to 0 so the output stays consistent every time
- Added 2 few-shot input/output examples so the AI learns the expected format
- Tested the prompt in both zero-shot and few-shot modes
- Tried a prompt injection attack, found a weakness, then fixed the prompt to defend against it

## Tests Performed
1. Normal input — correct JSON returned
2. Input with a missing field — returned `null` instead of guessing
3. Few-shot test with unseen data — followed the format correctly
4. Prompt injection attack (no defense) — failed, fake command leaked into output
5. Prompt injection attack (with defense) — passed, fake command ignored
6. Final test without any examples — still worked correctly

## What I Learned
Delimiters alone aren't enough to stop prompt injection. The prompt needed an explicit rule telling the AI to ignore any commands hidden inside the data.
