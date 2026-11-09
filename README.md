# Playwright UI Testing Mini Project

I built this project to practise writing and debugging browser tests with Playwright and TypeScript.

## What I tested

- Verified that a browser tab’s title contained the expected text.
- Checked that the browser navigated to the expected URL.
- Located an image by its alt text and verified that it was visible.

## Troubleshooting a locator timeout

The nopCommerce demo opened at the expected URL, but the automated browser reported the page title `Just a moment...`. The test timed out because the verification screen had no store logo for `getByAltText()` to find.

To check the locator separately, I used `page.setContent()` to load a small HTML example with an image that had the same alt text. The visibility assertion passed on that controlled page.

## Run the tests

From the project folder in Windows PowerShell, run:

```powershell
npm.cmd ci
npx.cmd playwright install chromium
npx.cmd playwright test --project=chromium
```

Add `--headed` to the last command to watch the browser run the tests.