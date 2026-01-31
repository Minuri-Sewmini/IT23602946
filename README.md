# Singlish to Sinhala Automation Suite

## ## Project Overview
This is a robust automation framework developed with **Playwright** and **TypeScript**. Its primary goal is to perform high-accuracy validation of phonetic Singlish-to-Sinhala translations on the [Swift Translator](https://www.swifttranslator.com/) web platform.

## ## Why This Project is Unique
Automating real-time translation tools is challenging because results are generated dynamically. This project overcomes these challenges using advanced automation techniques:

1. **Mimic Human Behavior** 
   - Standard automation tools enter text instantly (`page.fill()`), which often fails to trigger translation engines. 
   - We use `.type()` with a **150ms delay** per character to simulate a real user, ensuring the website's JavaScript properly converts the text.

2. **Regex-Based Smart Waiting** 
   - To prevent capturing "English" text before it turns into "Sinhala," we implemented a custom **Unicode Regex assertion**.
   - The test specifically waits until it detects Sinhala characters (`/[\u0D80-\u0DFF]/`) in the output box.

3. **Data-Driven Scalability** 
   - The entire test suite is driven by a `testData.json` file.
   - Adding dozens of new test cases (Positive & Negative) requires **no code changes**.

## ## Technical Implementation 
- **Language**: TypeScript
- **Framework**: Playwright
- **Key Logic**:
  - **Sequential Input**: `await inputBox.type(data.input, { delay: 150 });`
  - **Unicode Assertion**: `await expect(outputContainer).toContainText(/[\u0D80-\u0DFF]/, { timeout: 20000 });`
- **Config Highlights**:
  - `screenshot: 'on'` → automatically capture screenshots on test failures.
  - Timeout extended to **20 seconds** to accommodate slow internet responses.

## ## Project Structure
- `tests/singlish_test.spec.ts` – Core test script with intelligent sync logic.
- `testData.json` – External database for phonetic test scenarios.
- `playwright.config.ts` – Configured for **Headed Mode**, automatic **Screenshots**, and **Tracing** to ensure full visibility during failures.

## ## Getting Started
1. **Install Dependencies**: `npm install`
2. **Execute Tests**: `npx playwright test --project=chromium`
3. **Generate Reports**: `npx playwright show-report`

## ## Test Cases & Coverage 
- **Positive Cases**: Correctly spelled Singlish sentences.
- **Negative Cases**: Random or incorrectly typed inputs.
- **Unicode Validation**: Ensures all Sinhala outputs are correctly rendered.
- **Scalability**: Easy addition of hundreds of test cases via `testData.json`.

