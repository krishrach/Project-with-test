# Test info

- Name: Перевірка змін сторінки за скриншотом
- Location: /home/kris/Documents/e2e-screenshot-tests/tests/screenshots/local.spec.js:3:1

# Error details

```
Error: expect(Buffer).toMatchSnapshot(expected)

  49 pixels (ratio 0.01 of all image pixels) are different.

Expected: /home/kris/Documents/e2e-screenshot-tests/tests/screenshots/local.spec.js-snapshots/screenshots-local-page-index-page-chromium-linux.png
Received: /home/kris/Documents/e2e-screenshot-tests/test-results/screenshots-local-Перевірка-змін-сторінки-за-скриншотом-chromium/screenshots-local-page-index-page-actual.png
    Diff: /home/kris/Documents/e2e-screenshot-tests/test-results/screenshots-local-Перевірка-змін-сторінки-за-скриншотом-chromium/screenshots-local-page-index-page-diff.png

    at /home/kris/Documents/e2e-screenshot-tests/tests/screenshots/local.spec.js:5:35
```

# Page snapshot

```yaml
- heading "Вітаємо на локальній сторінці" [level=1]
- textbox "Ім'я користувача"
- textbox "Пароль"
- button "Увійти"
```

# Test source

```ts
   1 | const { test, expect } = require('@playwright/test');
   2 |
   3 | test('Перевірка змін сторінки за скриншотом', async ({ page }) => {
   4 |   await page.goto('http://localhost:3000');
>  5 |   expect(await page.screenshot()).toMatchSnapshot('screenshots/local-page/index-page.png');
     |                                   ^ Error: expect(Buffer).toMatchSnapshot(expected)
   6 | });
   7 |
   8 | test('Порівняння скриншота елемента', async ({ page }) => {
   9 |   await page.goto('http://localhost:3000');
  10 |   const element = await page.locator('h1');
  11 |   expect(await element.screenshot()).toMatchSnapshot('screenshots/local-page/index-page-element-h1.png');
  12 | });
  13 |
  14 |
```